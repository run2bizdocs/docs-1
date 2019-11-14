title: Cadastrar conexões LDAP
Description: Permite gerenciar diretórios, ou seja, acessar bancos de informações sobre os usuários de uma rede por meio de protocolos TCP/IP.

# Cadastrar conexões LDAP

O LDAP (*Lightweight Directory Access Protocol* - "Protocolo de acesso aos
diretórios leves") é um protocolo padrão que permite gerenciar diretórios, ou
seja, acessar bancos de informações sobre os usuários de uma rede por meio de
protocolos TCP/IP.

Você pode configurar o CITSmart para consultar bases de usuários disponíveis num serviço de diretório (Microsoft Active Directory ou open-LDAP) e, com isso, permitir que esses usuários se autentiquem no CITSmart usando suas credenciais, sem a necessidade de cadastrá-los manualmente (no CITSmart).

Atualmente, a leitura de dados em um servidor AD/LDAP se resume ao objeto "usuário". Dessa forma, você pode usar filtros para trazê-los para o CITSmart. Além disso, você pode utilizar a opção "Mapeamento de campos" para carregar informações de atributos (ex.: e-mail, telefone, localidade etc.).

Abaixo, é demonstrado um modelo de autenticação para clientes CITSmart Cloud que querem usar suas bases de diretórios locais (on-premises).

![Autenticação CITSmart LDAP](images/cloud-arch-authentication.png)

## Antes de começar

Caso você queira configurar a sincronização automática de usuários é preciso criar um CRON para esta finalidade (Ex. sincronizar usuários todo dia às 00:00). Para criar um agendamento vá no menu Processos > Gerência de Evento > Horário.

## Procedimento

### Configurar conexão

1.  Acessar o menu Parametrização > Configuração LDAP;
2.  Clicar no botão "Novo";
3.  Preencher os campos disponibilizados;

  | Campo | Descrição | Exemplo |
  |-----|---------|-------|
  | Implementação | Tipo do servidor de diretório | AD/OpenLDAP |
  | URL Conexão | Endereço de acesso à base de diretórios. Note que você poderá utilizar uma conexão não criptografada (porta 389) ou criptografada (porta 636) | ldaps://auth.domain.com:636 |
  | DN Base | DN Base usado para pesquisar entradas de usuários|dc=domain,dc=com |
  | DN Alias | Domínio/Nome da conexão, esse nome será visível na tela de login|domain.com |
  | Filtro | Filtro  para consulta de objetos nos diretórios | (&(objectCategory=person)(objectClass=user)) |
  | DN Manager | Usuário com permissão para buscar o diretório. Neste caso, informe o valor conforme o atritributo "distinguishedName" do AD | CN=Service User,OU=COMPANY,DC=domain,DC=com |
  | Pwd Manager|Senha do DN Manager | ***** |
  | Configuração padrão | Se a conexão está disponível na tela de login | Sim/Não |

    !!! info "IMPORTANTE"

        Caso não existam Grupos DN, preencher o campo “DN Grupo” apenas com um asterisco. Isto fará com que o sistema verifique todo o domínio.

4. Verificar conectividade com a base, para isso, clicar em "Testar Conexão", se todos os dados estiverem corretos você receberá a mensagem "Conexão realizada com sucesso";
5. Clicar no botão "Gravar".

    !!! warning "ATENÇÃO"

        Antes de pedir para testar **deve-se** clicar o botão "Gravar" para salvar a configuração, caso contrário o teste usará os dados anteriores às alterações feitas na tela.

### Configurar Grupo DN e Apontamentos

Após ter configurado uma conexão com sucesso, você deverá adicionar preferências para a sincronização de usuários, neste caso, você deve indicar Grupos LDAP e Mapeamento de campos. No caso dos "Grupos LDAP", você tem a possibilidade de criar personalizações onde determinados usuários herdarão automaticamente permissões no CITSmart via link com Perfil de Acesso ou Grupo. Para o item "Mapeamento de campos", você pode configurar a aplicação para ler as informações de atributos do AD/LDAP e trazê-las para o cadastro do colaborador (ex.: ler o atributo "mail" e alimentar o campo "e-mail" do colaborador).

1.  Para vincular novos grupos, clicar no botão "Adicionar" na área **Grupos LDAP** e informar os dados:

    | Campo | Descrição | Exemplo |
    |-------|-----------|---------|
    | DN Grupo | Caminho para o Grupo DN | OU=Users,OU=Company |
    | Filtro | Filtro para a pesquisa do objeto. Deixe em branco para usar o definido na conexão | (&(objectCategory=person)(objectClass=user)) |
    | Atributo para nome | Informar o atributo para leitura do nome (ex.: CN, SamAccountName etc.)  | CN |
    | Atualizar vínculos | Frequência com que os dados serão atualizados com base no servidor AD/LDAP (Opções: Sempre, Nunca ou Somente na criação) | Sempre |
    | Perfil de acesso | Perfil do sistema que os usuários herdarão | Administrador |
    | Grupo | Grupo do sistema que os usuários serão inseridos | Gerentes |
    | Agendamento | Período em que a sincronização automática será executada | [Todo dia]* |


2.  É possível vincular mapas de campos, para isso clicar no botão "Adicionar"
    na área **Mapeamento de campos**, digital o nome do campo LDAP e Selecionar o campo correspondente no CITSmart;

    | Campo no LDAP | Campo no sistema |
    |-------|-----------|
    | mail | E-mail |
    | telephoneNumber | Telefone |
    | localeID | Localidade |

3.  Clicar no botão "Gravar".

    !!! note "NOTA"

        Quando há um pedido de autenticação na tela de identificação do sistema
        (login e senha) é executado um ciclo de busca da conexão correta com base
        nesta configuração, ou seja, há uma tentativa de autenticação para cada
        domínio aqui cadastrado (isso se houver mais de um).


### Para usar o protocolo LDAPS

A utilização do protocolo LDAPS no CITSmart requer o certificado público do servidor AD/LDAP no repositório de certificados CA do JAVA (em seu servidor Wildfly). Assim, você deverá exportá-lo do servidor AD/LDAP e importá-lo em sua instância. Em caso de dúvidas acerca da importação de certificados no servidor de aplicação [documento de instalação][1].

## O que fazer depois

Para usar efetivamente a autenticação AD/LDAP é necessário, após o cadastro da conexão, alterar o parâmetro 22 e informar valor igual à "2", ou seja, indicar que o método padrão de autenticação no CITSmart é o AD/LDAP. De toda forma, a autenticação manual continuará funcionando normalmente.

## Relacionado

[Cadastrar horário][2]


[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation.html
[2]:/pt-br/citsmart-platform-8/processes/event/configuration/register-time.html
