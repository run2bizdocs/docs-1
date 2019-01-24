Title: Frequently Asked Questions - FAQ

# Frequently Asked Questions - FAQ

??? Question "Como são ranqueados os documentos no momento da pesquisa do Solr na base de conhecimento?"
    Assim, o documento que possuir a maior pontuação, é apresentado em primeiro lugar e os demais, com menor pontuação, em sequência.

    Para calcular a pontuação dos documentos o Solr utiliza um algoritmo padrão, onde é verificado a frequência do termo (term frequency) pesquisado. Mas, é possível alterar a pontuação com a utilização dos impulsionadores (boosts).
    
    Os impulsionadores do Solr podem ser utilizados em dois momentos, no momento da indexação ou consulta, sendo mais comum o seu uso na pesquisa.
    Alguns impulsionadores que podem alterar o cálculo da pontuação, no momento da pesquisa, são:
    
    -   term\^num: onde o “num” é a importância do termo pesquisado, exemplo:
    incident\^2;

    -   E também pode ser utilizado os impulsionadores de campo e as funções do
    dismax e edismax para impulsionar a pesquisa.
    
    No ITSM não é utilizado nenhum impulsionador, até o momento, somente é utilizado o cálculo padrão de pontuação do Solr, e no final da pesquisa é realizado a ordenação pela pontuação e pela quantidade de vezes que o conhecimento foi votado/curtido.
    
    Os impulsionadores estão em aberto para o uso, mas para utilizá-los é necessária uma análise melhor da importância dos campos e dos documentos adicionados ao Solr, pela base de conhecimento.
    
??? Question "Como o Gerenciamento de Eventos pode se transformar numa ferramenta de monitoramento de negócios??"
    ESQUEMA DE WEBSERVICE PARA SISTEMAS LEGADOS (MONITORAMENTO DE NEGÓCIOS)
    É possível conectar o componente EVM com qualquer software, mesmo um diferente daqueles que o módulo de Gerenciamento de Eventos normalmente se integra (Nagios, Zabbix e Inventory), desde que os dados enviados (via webservice) segam um padrão pré-estabelecido..
    
    Uma vez que os dados são enviados para o Citsmart Event Monitor, podem ser criadas regras (por exemplo, com o EPL do Esper) para que determinados eventos sejam disparados de acordo com alguma condição observada nos dados. 
    
    Exemplo "Folha de Pagamentos": 
    
    - Digamos que seja regra de uma empresa não contratar mais de 5 funcionários por setor.
    - O programa de folha de pagamento poderia enviar os dados mínimos de cada contratação por departamento (definido no plano orçamentário da empresa), de modo que sempre que o número de contração por departamento ultrapassar o limite pré-estabelecido, um evento de “excesso de contratação” poderia ser disparado.
    
??? Question "Como acessar a solicitação de serviço a partir da notificação de e-mail?"
    Para acessar a solicitação de serviço a partir da notificação de e-mail, proceda conforme orientações abaixo:
   
    1. Certifique-se de que esteja logado no sistema;
    2. Abra a notificação de e-mail referente a solicitação de serviço;
    3. A notificação terá o número da solicitação com um hyperlink, basta clicar no número, que logo em seguida será redirecionado para tela de Gerenciamento de Serviços apresentando as informações da solicitação.
    
??? Question "Como faço o desenho de ativos que compõem o meu serviço?"
    É feito o desenho de ativos que compõem o serviço utilizando a ferramenta de Desenho de Mapa de Serviço que proporciona desenhos eficientes e eficazes para gerenciamento do serviço durante seu ciclo de vida, demonstrando os itens de configuração relacionados.
    
    Para realizar esse desenho, proceda conforme as orientações abaixo (ver conhecimento Configuração dos atributos do serviço):
    
    1. Acesse a funcionalidade de Desenho de Mapa do Serviço referente ao Serviço de Negócio Gerência de Portfólio e Catálogo → Gerenciamento de Portfólio e Catálogo → Menu Apoio →  Avançar Portfólio → Catálogo de Serviços → Avançar Serviço → Mapa de Serviço;
    2. Será apresentada a tela para desenho dos ativos que compõem o serviço de negócio;
    3. Realize o desenho;
    4.  Acesse a funcionalidade de Desenho de Mapa do Serviço referente ao Serviço de Apoio/Técnico: Gerenciamento de Portfólio e Catálogo → Menu Apoio →  Avançar Portfólio → Catálogo de Serviços → Avançar Serviço → Mapa de Serviço;  
    5. A tela para projetar os ativos que compõem o Serviço de Apoio/Técnico será apresentada;
    6. Realize o desenho.
    
??? Question "Como definir um grupo padrão para o atendimento de primeiro nível da solicitação de serviço?"
    Para definir o grupo padrão para atendimento de 1º nível, proceda conforme as orientações abaixo:
   
    1. Acesse a funcionalidade de Cadastro de Grupo através da navegação no menu principal Acesso e Permissão → Grupo. Será apresentada a tela de cadastro de grupo, exibindo os contratos;
    2. Realize o cadastro do grupo de 1º nível, caso não esteja cadastrado, e proceda com o preenchimento dos campos;
    3. Caso o grupo de 1º nível já esteja cadastrado no sistema, realize a pesquisa do grupo e obtenha o seu número de identificação (ID);
    4. Após obter o ID do grupo de 1º nível, acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal. Parametrização → Parâmetros Citsmart;
    5. Será apresentada a tela Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    6. Realize a pesquisa do parâmetro "9 - ID Grupo Nível 1";
    7. Selecione o mesmo;
    8. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o número de identificação (ID) do grupo de 1º nível;
    9. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
    REGRA: após a configuração do parâmetro, ao realizar o registro de uma Solicitação de Serviço/Incidente, caso não tenha informado o grupo para atendimento do serviço, será escalado o grupo, o qual foi definido no parâmetro para atendimento de 1º nível.
    
??? Question "Como configurar a autenticação do Nagios via LDAP?"
    A configuração de autenticação do Nagios via LDAP passa por:
    
    1. Alterar o arquivo thruk.conf da seguinte forma:
    ```sh
    vim /etc/apache2/conf-available/thruk.conf
	```
    <Location /thruk/>
    Options ExecCGI FollowSymLinks
    AuthName "LDAP Authentication"
    AuthType Basic
    AuthBasicProvider ldap
    AuthLDAPURL ldap://auth01.citsmartcloud.com/dc=citsmart,dc=com?uid?sub?(objectClass=*)
    Require ldap-group ou=people,o=citsmartco,dc=citsmart,dc=com
    Require valid-user
    </Location>

    2. Executar:
    ```sh
    /etc/init.d/apache2 restart
	```
    ```sh
    /etc/init.d/thruk restart
	```
	```sh
    /etc/init.d/nagios reload
	```
    
??? Question "Como configurar a resposta automática de pesquisas de satisfação?"
    O mecanismo de resposta automática, que responderá automaticamente as pesquisas de satisfação das solicitações de serviço, acontece quando a pesquisa de satisfação não for respondida pelo usuário, dentro de um prazo definido pelo administrador do sistema.
    
    Para realizar a configuração das respostas automáticas, proceda conforme orientações abaixo:

    1. Configure os seguintes parâmetros do sistema que definem o comportamento do mecanismo de resposta automática ( ver conhecimento Regras de parametrização - Provisionamento e logística):
    Parâmetro 139: Define o prazo máximo, em dias, que o usuário tem para responder a pesquisa de satisfação, antes que essa seja respondida automaticamente pelo sistema;
    Parâmetro 152: Nota padrão que será atribuída as pesquisas de satisfação que forem respondidas automaticamente. Opções: OTIMO, BOM, REGULAR E RUIM;
    Parâmetro 151: Ativa ou Desativa as respostas automáticas no sistema. S para ativar e N para desativar.
    2. Acesse a funcionalidade de Processamento Batch (Sistema → Processamento Batch).
    3. Será apresentada a tela de cadastro de processamento batch preencha os campos:
    Descrição: informe a descrição que identificará esse processamento. Por exemplo: “Resposta automática pesquisa satisfação”;
    Situação: a situação define se esse processamento estará ativo ou inativo. Quando ele se encontrar inativado as solicitações deixarão de ser respondidas;
    Tipo: selecionar o tipo “Classe Java”;
    Agendamento: define quando essa rotina será executada, cabe ao administrador do sistema definir qual o melhor horário e frequência para a execução;
    Conteúdo: informe o texto: br.com.centralit.citcorpore.quartz.job.AvaliarSolicitacoesNaoRespondidas;
    4. Clique no botão Gravar para efetuar o registro.
    
	REGRA: a partir do momento da gravação, no horário e dia agendado, as solicitações não respondidas (com prazo superior ao definido no parâmetro 139) serão automaticamente respondidas (com o valor definido no parâmetro 152), caso o parâmetro 151 esteja com valor ‘S’.

??? Question "Como configurar o nome das fases do ciclo de vida dos ICs (itens de configuração)?"
    A configuração dos nomes das fases do ciclo de vida do IC pode ser realizada a partir da tela de Configuração do GCAS e a partir da tela de Parâmetros do CITSmart. Para realizar essa configuração, proceda conforme orientações abaixo:
  
    CONFIGURAÇÃO A PARTIR DA TELA DE CONFIGURAÇÃO DO GCAS
    
    1. Acesse a funcionalidade de Configuração do GCAS através da navegação no menu principal Processos ITIL → Gerência de Configuração → Configuração do GCAS. Feito isso, será apresentada a tela de configuração dos parâmetros (atributos) de gerenciamento de configuração e ativos de serviço;
    2. Informe os valores dos parâmetros (atributos):
    Nome do Grupo de ICs que estão na Fase de Desenvolvimento (Ex: ICs em Desenvolvimento)
    Nome do Grupo de ICs que estão na Fase de Produção (Ex: ICs em Produção)
    Nome do Grupo de ICs que estão na Fase de Produção (Ex: ICs em Homologação).
    3. Clique no botão Gravar para efetuar a operação, onde a data, hora e usuário serão gravados automaticamente para uma futura auditoria.
    4. Após configuração dos parâmetros referente ao nome das fases do ciclo de vida do IC, será exibido na tela de Gerenciamento de Itens de Configuração a descrição das fases do ciclo de vida do IC, conforme especificado no valor do parâmetro.
    
	CONFIGURAÇÃO A PARTIR DA TELA DE PARÂMETROS DO CITSMART
    
    1. Acesse a funcionalidade de Parâmetros do CITSmart através da navegação no menu principal Parametrização → Parâmetros Citsmart.
    2. Após isso, será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart. Será apresenta a tela para pesquisa de parâmetros;
    3. Realize a pesquisa do parâmetro "92 - Nome do Grupo de ICs que estão na Fase de Desenvolvimento (Ex: ICs em Desenvolvimento)"
    4. Selecione o mesmo. Após isso, será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado;
    5. No campo valor, informe o nome do grupo de ICs da fase de desenvolvimento;
    6. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    7. Realize a pesquisa do parâmetro "93 - Nome do Grupo de ICs que estão na Fase de Produção (Ex: ICs em Produção)";
    8. Selecione o mesmo. Após isso, será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado;
    9. No campo valor, informe o nome do grupo de ICs da fase de produção
    10. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    11. Realize a pesquisa do parâmetro "94 - Nome do Grupo de ICs que estão na Fase de Produção (Ex: ICs em Homologação)"
    12. Selecione o mesmo. Após isso, será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado
    13. No campo valor, informe o nome do grupo de ICs da fase de homologação
    14. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.

??? Question "Como configurar as notificações de e-mail de solicitação de serviços?"
    Ao registrar uma solicitação de serviço, realizar demais ações e encerrar a mesma, o solicitante será notificado..
    
	Para que essa notificação seja enviada é necessário realizar os seguintes procedimentos:
    
    1. Acesse os Serviços do Contrato referente ao serviço de negócio Gerenciamento de Portfólio → Portfólio de Serviços → Serviço de Negócio → Contrato → Serviços e serviço técnico Gerenciamento de Portfólio → Portfólio de Serviços → Serviço de Negócio → Serviço de Apoio/Técnico → Contrato → Serviços e informe o modelo de e-mail nos campos
        
        - "Modelo de E-mail Abertura Incidente/Requisição"
        - "Modelo de E-mail na finalização de Solicitações/Incidentes"
        - "Modelo de E-mail nas demais ações de Solicitações/Incidentes" 
        
	REGRA: caso não informe os modelos de e-mail, as notificações não serão enviadas.

    2. Acesse a funcionalidade de Cadastro de Grupo através da navegação no menu principal Cadastro Gerais → Gerência de Pessoal → Grupo.    
    3. Será apresentada a tela de Cadastro de Grupo. Caso o grupo já esteja registrado no sistema, realize a pesquisa do grupo;
    4. Selecione o mesmo;
    5. Será exibida a tela de registro do determinado grupo, defina se as notificações de e-mail (abertura, andamento e encerramento) referentes às solicitações, serão de envio obrigatório;
    
    REGRA: caso tenha determinado que as notificações serão obrigatórias, ao registrar uma solicitação de serviço, na tela de Registro de Incidente/Requisição de Serviço, essas opções já estarão selecionadas, não permitindo a sua alteração. Mas caso tenha determinado que as notificações não serão obrigatórias, ao registrar uma solicitação de serviço, essas opções poderão ser definidas pelo responsável do registro da solicitação.
    
    6. Na tela de Registro de Incidente/Requisição de Serviço, ao registrar uma solicitação de serviço será estabelecida a regra referente a notificação por e-mail, definida no cadastro de grupo.
    
    REGRA: quando registrar uma solicitação de serviço, será enviada a notificação somente para o grupo executor, o qual é responsável pelo atendimento da solicitação. Quando realizar a execução das demais ações e encerramento da solicitação de serviço, as notificações serão encaminhadas somente para o solicitante.
    
??? Question "Como definir a obrigatoriedade do vínculo da mudança com IC?"
    A obrigatoriedade do vínculo da mudança com o IC é definida na tela de Parâmetro do CITSmart. Para definir essa obrigatoriedade, proceda conforme orientações abaixo:

    1. Acesse a funcionalidade de Parâmetros do CITSmart através da navegação no menu principal Parametrização → Parâmetros CITSmart;
    2. Será apresentada a tela de Parâmetros do CITSmart, clique na aba Pesquisa de Parâmetros do CITSmart;
    3. Será apresenta a tela para pesquisa de parâmetros. Realize a pesquisa do parâmetro "85 - Verificação de vínculo de mudança relacionada ao Item de configuração (Default: S)";
    4. Selecione o mesmo;
    5. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o valor "S";
    6. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    7. Após configuração do parâmetro, quando for registrar um Item de Configuração, será obrigatório o vínculo da mudança.
    
??? Question "Como habilitar a rotina de leitura automática de e-mails?"
    Ao enviar um e-mail para o suporte do CITSmart será feita a leitura do e-mail automática, caso o e-mail seja referente a uma solicitação, será verificado o título do e-mail, se contém a palavra ‘Solicitação’ e o número da solicitação, caso contenha, será armazenado o e-mail como ocorrência na solicitação referente.
    
    Para que essa rotina de leitura de e-mails funcione perfeitamente, é necessário realizar os seguintes procedimentos:
    
    1. Instalar a versão do java 7, caso tenha versão inferior a rotina não funcionará;
    2. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização→ Parâmetros Citsmart;
    3. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    4. Será apresenta a tela para pesquisa de parâmetros, realize a pesquisa do parâmetro "23 - SMTP LEITURA - Servidor de entrada de e-mails do Service Desk" e selecione o mesmo;
    5. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o servidor de entrada de e-mail (ex.: orion.egrupo.com.br);
    6. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    7. Realize a pesquisa do parâmetro "24 - SMTP LEITURA - Caixa de entrada de e-mails do Service Desk" e selecione o mesmo;
    8. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o e-mail ou login da conta de e-mail (ex.: suporte.citsmart);
    9. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    10. Realize a pesquisa do parâmetro "25 - SMTP LEITURA - Senha da Caixa de entrada de e-mails do Service Desk" e selecione o mesmo;
    11. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, a senha da conta de e-mail;
    12. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    13. Realize a pesquisa do parâmetro "26 - SMTP LEITURA - Provider do servidor de e-mails do Service Desk (imaps, pops, imap, pop, etc)" e selecione o mesmo;
    14. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o protocolo que será utilizado para leitura de e-mails (ex.: imap ou pop) e clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    15. Realize a pesquisa do parâmetro "27 - SMTP LEITURA - Porta do servidor de e-mails do Service Desk" e selecione o mesmo;
    16. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe a porta que será utilizada para acessar o servidor de e-mails (587 para servidor pop ou 995 para servidor imap);
    17. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    18. Realize a pesquisa do parâmetro "28 - SMTP LEITURA - Pasta da caixa de entrada de e-mails do Service Desk" e selecione o mesmo;
    19. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe a pasta da caixa de entrada da conta de e-mail;
    20. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    21. Realize a pesquisa do parâmetro "200 - Habilitar rotina para leitura de e-mails novos automaticamente ?(ex: S ou N - Default 'N')" e selecione o mesmo;
    22. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o valor "S" para ativar a rotina de leitura de e-mail automaticamente;
    23. CClique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
??? Question "Como habilitar a regra de escalonamento do módulo de mudanças?"
    A regra de escalonamento de mudanças é habilitada na tela de Parâmetro do Citsmart.
    
    Para habilitar essa regra, proceda conforme orientações abaixo:

    1. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização → Parâmetros Citsmart;
    2. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    3. Será apresenta a tela para pesquisa de parâmetros, realize a pesquisa do parâmetro "193 - Habilita o escalonamento de mudanças definido nas regras de escalonamento? (Ex: S ou N - Padrão 'N')" e selecione o mesmo;
    4. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o valor "S" para ativar escalonamento de mudanças;
    5. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
??? Question "Como habilitar o Portal de Serviços (Smart Portal)?"
    Para que os usuários tenham acesso ao Portal ou ao Portal Smart, deve-se habilitar o mesmo da seguinte forma:
    
    1. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização → Parâmetros Citsmart. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart. Feito isso, será apresenta a tela para pesquisa de parâmetros;
    2. Realize a pesquisa do parâmetro "46 - Habilitar Portal como tela inicial do Citsmart?" e selecione o mesmo. Após isso, será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado;
    3. No campo valor, informe o valor "S" para habilitar o portal como tela inicial. Feito isso, clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    4. Após configurar o parâmetro, ao logar no sistema, será exibido como tela inicial o Portal.
    
??? Question "Como habilitar a pesquisa de satisfação?"
    A pesquisa de satisfação é a avaliação do atendimento da solicitação feita através da notificação por e-mail.
    
    Para habilitar essa pesquisa de satisfação, proceda conforme orientações abaixo:
    
    1. Crie o modelo de e-mail (o modelo de e-mail deve conter a seguinte palavra-chave: ${LINKPESQUISASATISFACAO})
    2. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização → Parâmetros Citsmart;
    3. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    4. Realize a pesquisa do parâmetro "31 - Envia e-mail na execução dos fluxos de solicitações/incidentes";
    5. Selecione o mesmo;
    6. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o valor "S" para que seja habilitado o envio de e-mail referente as solicitações de serviço;
    7. Clique no botão Gravar para efetuar a operação;
    8. Acesse os serviços de requisição, incidente e procedimento do contrato referente ao serviço de negócio Gerência de Portfólio e Catálogo → Gerenciamento de Portfólio e Catálogo → Menu Apoio → Avançar Portfólio → Catálogo de Serviços → Avançar Serviço e serviço técnico Gerência de Portfólio e Catálogo → Gerenciamento de Portfólio e Catálogo → Menu Apoio → Avançar Portfólio → Catálogo de Serviços → Avançar Serviço e verifique se o modelo de e-mail que foi criado está informado no campo "Modelo de E-mail na finalização de Solicitações/Incidentes";
    9. Ao receber uma notificação por e-mail da solicitação de serviço que foi atendida, será exibido um link para realizar a avaliação do atendimento. Ao clicar no link será aberta uma tela para avaliação do atendimento.
    
??? Question "Como habilitar a regra de escalonamento do módulo de problemas?"
    Para habilitar essa regra, proceda conforme orientações abaixo:
    
    1. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização → Parâmetros Citsmart;
    2. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    3. Será apresenta a tela para pesquisa de parâmetros, realize a pesquisa do parâmetro "194 - Habilita o escalonamento de problema definido nas regras de escalonamento? (Ex: S ou N - Default 'N')" e selecione o mesmo;
    4. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o valor "S" para ativar escalonamento de problemas;
    5. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
??? Question "Como habilitar a regra de escalonamento das solicitações de serviço?"
    A regra de escalonamento de solicitação de serviço é habilitada na tela de Parâmetro do Citsmart. Para habilitar essa regra, proceda conforme orientações abaixo:

    1. No arquivo citsmart.cfg colocar a rotina START_MONITORA_INCIDENTES=TRUE
    2. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Sistema → Parâmetros Citsmart;
    3. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    4. Pesquise e altere o parâmetro 190 - Liga o funcionamento das regras de escalonamento? (Ex: S ou N - Default:'N') informando o valor "S" para ativar escalonamento de solicitação de serviço;
    5. Pesquise e altere o parâmetro 31 - Envia e-mail na execução dos fluxos de solicitações/incidentes (Ex: S ou N) informando o valor "S";
    6. Pesquise e altere o parâmetro 297 - Desativa envio de e-mails do sistema (Valores: "S" ou "N" Default: "N") informando o valor "N";
    7. Também faça as devidas alterações nos seguintes parâmetros, conforme as necessidade e cenário da instalação: 
    
    - 195: Id do modelo de e-mail para envio de notificação de solicitação com prazo a vencer (Ex.: 1 );
    - 197: Login do usuário que receberá e-mail referente a regras de escalonamento de solicitação de serviço que estão vencendo (Ex.: Consultor);
    -113: ID do modelo de e-mail para escalação automática;
    - 10: SMTP ENVIO - E-mail origem das notificações de solicitações de serviço;
    - 33: URL de acesso ao sistema.
    
	8. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
   
??? Question "Como melhorar o desempenho do CITSmart Enterprise ITSM?"
    O desempenho do sistema é definido como o tempo que o software demora para realizar uma determinada tarefa, visto que esse desempenho é um forte atributo de qualidade percebido pelos usuários do software.
    
    Existe a capacidade de o sistema funcionar com mais de uma instância, para isso, será necessário utilizar o arquivo de configuração (citsmart.cfg), onde é possível ativar ou inativar rotinas.
    
    Para utilizar essa capacidade, deverá existir o arquivo citsmart.cfg no diretório:
    ```sh
    \jboss\standalone\configuration\ (quando o Jboss sobe como uma única instância)
    \jboss\domain\configuration\ (quando é utilizado cluster, tem domains e hosts)
    ```
   
    RULE: where $ {value} is replaced by the corresponding values.
	
    1. START_MODE_RULES=${valor} (Este parâmetro define se processa as regras de escalonamento. Informe o valor TRUE para ativar ou FALSE para desativar).
    2. START_MODE_ITSM=${valor} (Este parâmetro define se apresenta a interface do ITSM. Informe o valor TRUE ou FALSE. Se estiver definido com o valor FALSE, não irá permitir abrir as funcionalidades de incidentes, etc. (do ITSM)).
    3. START_MONITORING_ASSETS=${valor} (Este parâmetro define se o monitoramento de ativos será ativado. Informe o valor TRUE para ativar ou FALSE para desativar).
    4. QUANTIDADE_BACKUPLOGDADOS=${valor} (Este parâmetro define a quantidade de itens da tabela logdados que serão feitos backup. Informe a quantidade de itens, ex.: 1000).
    5. Os parâmetros abaixo quando não ativados faz com que o sistema suba com as threads desativadas para melhorar o desempenho do sistema. É necessário configurar esses parâmetros antes da inicialização do Jboss para o funcionamento dos mesmos.
    6. START_MONITORA_INCIDENTES=${valor} (Este parâmetro define se desativa o monitoramento de incidentes. Informe o valor TRUE ativar ou FALSE desativar).
    7. START_VERIFICA_EVENTOS=${valor} (Este parâmetro define se desativa a verificação de eventos. Informe o valor TRUE ativar ou FALSE desativar).
    8. O uso dos parâmetros abaixo é opcional. Os mesmos fazem a separação do pool de conexão principal com o pool de execução do fluxo, inventário e relatório.
    - JDBC_ALIAS_BPM = java: / jdbc / $ {value} (Este parâmetro define o nome do datasource do fluxo. Informe o nome do datasource, ex. java:/jdbc/citsmartFluxo).
    - JDBC_ALIAS_INVENTORY = java: / jdbc / $ {value} (Este parâmetro define o nome do datasource do inventário. Informe o nome do datasource, ex.: java:/jdbc/citsmart_inventory).
    - JDBC_ALIAS_REPORTS = java: / jdbc / $ {value} (Este parâmetro define o nome do datasource dos relatórios. Informe o nome do datasource, ex.: java:/jdbc/citsmart_reports).
    9. O parâmetro abaixo separa o processamento da rotina de eventos BPM em um pool de thread separado do pool de thread principal do sistema, para aliviar no uso de recursos do banco de dados e do servidor.
    - JDBC_ALIAS_BPM_EVENTOS = java: / jdbc / $ {value} (Este parâmetro define o nome do datasource de eventos BPM. Informe o nome do datasource, ex. java: / jdbc / citsmartBpmEvents).
    
??? Question "Como integrar o AD da empresa do cliente no CITSmart Enterprise ITSM que está na cloud ofertada pela CITSmart Corporation?"
    Em relação ao LDAP compliance do CITSmart Enterprise ITSM, existem dois cenários:
    
    1. Em ambientes on-demand: há necessidade de conexão ao servidor de diretórios do cliente.
    2. Em ambiente cloud (ofertado pela CITSmart Corporation): há necessidade de habilitar a conexão ao servidor de diretórios do cliente.

??? Question "Como vincular colaboradores (usuários) a um grupo?"
    Há duas formas de vincular os colaboradores (usuários) aos grupos, sendo:

    A PARTIR DO CADASTRO DE GRUPO
	
    1. Acesse a funcionalidade de Cadastro de Grupo através da navegação no menu principal. Posicione o mouse na opção  Acesso e Permissão e clique na opção Grupo (ver conhecimento Cadastro de grupo);
    2. Será apresentada a tela de Cadastro de Grupo. Caso o grupo já esteja registrado no sistema, realize a pesquisa do grupo e selecione o mesmo. Feito isso, será exibida a tela de registro do determinado grupo;
    3. Clique no ícone de adicionar do campo Colaboradores, será exibida a tela para pesquisa de colaboradores;
    4. Realize a pesquisa do colaborador que deseja vincular ao grupo e selecione o mesmo. Após isso, o colaborador será vinculado ao grupo;
    5. Após o vínculo, clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
    A PARTIR DO CADASTRO DE USUÁRIO
    
    1. Acesse a funcionalidade de Cadastro de Usuário através da navegação no menu principal. Posicione o mouse na opção Cadastro Gerais, Gerência de Pessoal e clique na opção Usuário (ver conhecimento Cadastro de usuário);
    2. Será apresentada a tela de Cadastro de Usuário. Caso o usuário já esteja registrado no sistema, realize a pesquisa do usuário e selecione o mesmo. Feito isso, será exibida a tela de registro do determinado usuário;
    3. Clique no ícone de adicionar do campo Grupo. Será exibida a tela para pesquisa de grupos;
    4. Realize a pesquisa do grupo desejado e selecione o mesmo. Após isso, o usuário será vinculado ao grupo;
    5. Após o vínculo, clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.

??? Question "Como relacionar grupo ao contrato?"
    Para relacionar grupo ao contrato, proceda conforme as orientações abaixo:
    
    1. Acesse a funcionalidade de Parâmetros do CITSmart através da navegação no menu principal. Posicione o mouse na opção Parametrização e clique na opção Parâmetros CITSmart. Será apresentada a tela de Parâmetros do CITSmart, clique na aba Pesquisa de Parâmetros do CITSmart. Feito isso, será apresenta a tela para pesquisa de parâmetros;
    2. Realize a pesquisa do parâmetro "41 - Faz o controle de vínculo de colaboradores aos contratos (S/N)?" e selecione o mesmo;
    3. No campo valor, informe o valor "S" para que seja exibido os contratos na tela de cadastro de grupo. Feito isso, clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    4. Após configurar o parâmetro, acesse a funcionalidade de Cadastro de Grupo através da navegação no menu principal Acesso e Permissão → Grupo. Será apresentada a tela de cadastro de grupo, exibindo os contratos (ver conhecimento Cadastrar um grupo).
    5. Caso o grupo que deseja vincular ao contrato já esteja registrado no sistema, realize a pesquisa do grupo e selecione o mesmo;
    6. Feito isso, será exibida a tela de registro do determinado grupo;
    7. Selecione os contratos, os quais o grupo será vinculado. Após isso, clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
??? Question "Como relacionar unidade ao contrato?"
    Para relacionar unidade ao contrato, proceda conforme as orientações abaixo:
    
    1. Acesse a funcionalidade de Parâmetros do CITSmart através da navegação no menu principal. Posicione o mouse na opção Parametrização e clique na opção Parâmetros CITSmart. Após isso, será apresentada a tela de Parâmetros do CITSmart, clique na aba Pesquisa de Parâmetros do CITSmart. Feito isso, será apresenta a tela para pesquisa de parâmetros;
    2. Realize a pesquisa do parâmetro "61 - Vincula contratos a unidade" e selecione o mesmo. Após isso, será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado; 
    3. No campo valor, informe o valor "S" para que seja exibido os contratos na tela de cadastro de unidade. Feito isso, clique no botão Gravar para efetuar a operação;
    4. Após configurar o parâmetro, acesse a funcionalidade de Cadastro de Unidade através da navegação no menu principal Cadastros Gerais → Gerência de Pessoal → Unidade. Será apresentada a tela de cadastro de unidade, exibindo os contratos; 
    5. Caso a unidade que deseja vincular ao contrato já esteja registrada no sistema, realize a pesquisa da unidade e selecione a mesma. Feito isso, será exibida a tela de registro da determinada unidade;
    6. Selecione os contratos, os quais a unidade será vinculada.
    7. Clique no botão "Gravar" para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria.
    
??? Question "Como substituir cada imagem das logomarcas do CITSmart ITSM Enterprise?"
    Sempre que houver necessidade de personalizar de forma adequada as logomarcas do CITSmart Enterprise ITSM, o procedimento abaixo deve ser executado:
    
    1. Acessar o caminho: Sistema → Configurações → Configurações de ambiente; aparecerá três espaços para upload de imagem:
      - Logo início: Imagem/Logomarca apresentada na tela inicial de login do sistema;
      - Logo portal: Imagem/Logomarca apresentada no Portal de Serviços do sistema;
      - Logo sistema: Imagem/Logomarca apresentada ao acessar o sistema;
      - Logo relatório: Imagem/Logomarca apresentada nos relatórios do tipo jasper.
	
    2. Realizar upload (podem ser imagens diferentes).
    
	REGRA: caso o usuário não escolha uma nova logo, a logo default será a do CITSmart. Por questão de direitos autorais, esta mudança de logo é permitida somente na versão Enterprise do produto CITSmart ITSM.

    CONFIGURAÇÃO MAIS PRECISA DA IMAGEM PARA RELATÓRIOS JASPER
	
    O usuário tem acesso às propriedades da imagem que aparecerá nos relatórios.

	REGRA: caso a imagem personalizada pelo usuário não esteja configurada corretamente nos relatórios, ela deve ser redesenhada com proporções mais adequadas.
    
??? Question "Como configurar o recurso SOLR?"
    CONFIGURAÇÃO DO PARÂMETRO
    
    1. Para configurar o parâmetro vá na tela Parametrização → Gerência de Conhecimento;
    2. Procure pelo parâmetro “URL do servidor do SOLR (Ex:http://localhost:8983/solr/collection_name)”
    3. Após informe a URL do servidor Solr, um exemplo de URL seria a seguinte: http://localhost:8983/solr/base_conhecimento

    INDEXAÇÃO DOS CONHECIMENTOS EXISTENTES
	
    1. Para indexar os conhecimentos vá em Sistema → Configurações → Gerência de Conhecimento (Indexação);
    2. Caso tenha conhecimentos indexados clique em “Remover indexação base de conhecimento”;
    3. Logo após clique em “Indexar base de conhecimento”;
    4. Caso ocorra algum erro clique em “Atualizar o servidor de indexação”;
    5. Logo após clique novamente em “Indexar base de conhecimento”;
    6. Caso ocorra algum erro entre em contato com o Suporte do ITSM.
    
??? Question "Para qual destinatário será feito envio de notificações de ICs?"
    As notificações de ICs serão enviadas para o destinatário definido na tela de Parâmetro do Citsmart.
    
	Para definir o destinatário, proceda conforme orientações abaixo:
    
    1. Acesse a funcionalidade de Parâmetros do Citsmart através da navegação no menu principal Parametrização → Parâmetros Citsmart;
    2. Será apresentada a tela de Parâmetros do Citsmart, clique na aba Pesquisa de Parâmetros do Citsmart;
    3. Será apresenta a tela para pesquisa de parâmetros;
    4. Realize a pesquisa do parâmetro "90 - Envio de e-mails de Notificação de ICs (1-Grupo, 2-Proprietário, 3-Todos)";
    5. Selecione o mesmo;
    6. Será apresentada a tela de registro do parâmetro com o conteúdo referente ao registro selecionado, no campo valor, informe o número de identificação do destinatário (1 - Grupo, 2 - Proprietário ou 3 - Todos);
    7. Clique no botão Gravar para efetuar a operação, neste caso a data, hora e usuário serão armazenados automaticamente para uma futura auditoria;
    8. Após configuração do parâmetro, será realizado o envio de e-mails de notificações de ICs para o destinatário (grupo, proprietário ou todos), conforme especificado no valor do parâmetro.
    
??? Question "O que é preciso para configurar um IC que está fisicamente na rede da empresa do cliente para ser inventariado pelo CITSmart Enterprise ITSM que está na cloud ofertada pela CITSmart Corporation?"
    [Original] Na cloud, o mongodb e evm/inv ficam na estrutura do cliente, devido não ser possível se conectar em um range interno com origem da cloud.
    
    [Para validação] Neste cenário específico, os componentes MongoDB, CITSmart EVM e CITSmart Inventory devem ser instalados e configurados dentro da estrutura de rede do cliente, pois não é possível ao CITSmart Enterprise ITSM (Cloud) se conectar a um range interno de um cliente.
    
??? Question "Qual o limite de tamanho de arquivo para upload nas funcionalidades com este recurso?"
    O upload dos anexos especifica o tamanho limite de 15 Mbytes para cada arquivo carregado no sistema. Porém, na tela do Portal continua com o limite de 5 Mbytes para o tamanho do arquivo.
   
??? Question "O que é a tabela Fato do módulo solicitação de serviço e como alimentá-la?"
    A tabela fato solicitação de serviço tem o propósito de receber informações consolidadas, referentes à solicitação de serviço.
    
    Tais como: 
    
    IDSOLICITACAOSERVICO
	
    DATAHORASOLICITACAO
	
    DIAABERTURA
	
    MESABERTURA
	
    ANOABERTURA
	
    DATAHORAFIM
	
    DIAFECHAMENTO
	
    MESFECHAMENTO
	
    ANOFECHAMENTO
	
    IDGRUPOATUAL
	
    GRUPOATUAL
	
    IDPRIORIDADE
	
    NOMEPRIORIDADE
	
    IDSERVICOCONTRATO
	
    IDCONTRATO
	
    NUMEROCONTRATO
	
    IDTIPOSERVICO
	
    NOMETIPOSERVICO
	
    IDPORTFOLIOSERVICO
	
    DESCPORTFOLIOSERVICO
	
    IDSOLICITANTE
	
    SOLICITANTE
	
    IDUSUARIORESPONSAVELATUAL
	
    TECNICORESPONSAVEL
	
    IDTIPODEMANDASERVICO
	
    TIPOSOLICITACAO
	
    IDCAUSAINCIDENTE
	
    CAUSA
	
    IDCATEGORIASOLUCAO
	
    CATEGORIASOLUCAO
	
    IDSTATUS
	
    STATUS
	
    IDACORDONIVELSERVICO
	
    PRAZOSLA_HH
	
    PRAZOSLA_MM
	
    IDCALENDARIO
	
    CALENDARIO
	
    DATAHORALIMITE
	
    DIALIMITESLA
	
    MESLIMITESLA
	
    ANOLIMITESLA
	
    TAREFAATUAL
	
    IDCLIENTE
	
    CLIENTE
	
    IDFORNECEDOR
	
    FORNECEDOR
	
    IDCATEGORIASERVICO
	
    CATEGORIASERVICO
	
    IDCONDICAOOPERACAO
	
    NOMECONDICAOOPERACAO
	
    IDORIGEM
	
    ORIGEMDASOLICITACAO
	
    IDMOEDA
	
    MOEDA
	
    IDTIPOFLUXO
	
    FLUXO
	
    IDIMPORTANCIANEGOCIO
	
    IMPORTANCIASERVICOAONEGOCIO
	
    IDLOCALIDADE
	
    LOCALIDADE
	
    IDUNIDADE
	
    UNIDADE
	
    URGENCIA
	
    IMPACTO
	
    RUPTURASLA
	
    QTDEREABERTURAS
	
    HOUVERECLASSIFICACAO
	
    TEMPOATENDIMENTOHH
	
    TEMPOATENDIMENTOMM
	
    TEMPOATRASOHH
	
    TEMPOATRASOMM
	
    MAJOR
	
    NOTAPESQUISASATISFACAO
	
    QTDESOLICITACOESFILHAS
	
    QTDESUBSOLICITACOES
	
    QTDEBASECONHECIMENTO
	
    QTDEPROBLEMAS
	
    QTDELIBERACAO
	
    QTDEMUDANCAS
	
    QTDEICS
	
    QTDEAPLICACOES
	
    QTDEPROJETOS
	
    QTDEANEXOS
	
    QTDEAGENDAMENTOATIVIDADES
	
    QTDEAGENDAMENTATIVFINALIZADAS
	
    CONTRATOAPOIO
	
    SERVICOAPOIO
	
    CUSTOSERVICO
	
    SERVICOINDISPONIVEL
	
    QTDEELOGIOS
	
    QTDEQUEIXAS
	
    PROCEDIMENTOCONTINUIDADE
	
    CUSTOINDISPONIBILIDADE
	
    IDSERVICO
	
    NOMESERVICO
	
    IDATIVIDADE
	
    NOMEATIVIDADE
	
    DATAHORACARGA
    
	Estas informações são alimentadas através da rotina de processamento batch do citsmart, rodando os scripts Rhino, nos anexos.
    
??? Question "Qual o impacto do filtro "Grupo Solucionador" no comportamento das pesquisas de requisições e incidentes?"
    Quando o filtro "grupo solucionador" estiver ativo, serão apresentadas apenas as solicitações fechadas, uma vez que ao selecionar este filtro, entende-se que há a necessidade de apresentar o grupo que de fato solucionou uma solicitação, não apresentando grupos responsáveis por tarefas (conforme o fluxo vinculado ao serviço da solicitação) executadas após a solicitação ser solucionada.
    
	Vejamos um exemplo genérico:
    - O serviço A possui um fluxo de qualidade vinculado. Após solucionada uma solicitação referente ao serviço A e avançar o fluxo, o grupo responsável será o de qualidade e este encerrará o ciclo de vida da solicitação em questão, porém este grupo não é o grupo que solucionou esta solicitação, ele apenas aprovou a solução e encerrou a solicitação, portanto não será apresentado no relatório gerado pela tela de pesquisa de Requisições e Incidentes quando o filtro "Grupo solucionador" estiver marcado com um grupo específico.
    - Entretanto, quando o filtro "Grupo Solucionador" não estiver ativo, o grupo apresentado no relatório ou na pesquisa será o grupo referente à tarefa atual da solicitação, ou seja, caso a solicitação esteja fechada e possua um fluxo de qualidade, será apresentado o grupo de qualidade como o grupo atual responsável pelo encerramento do ciclo de vida desta solicitação. E caso a solicitação esteja em andamento, será apresentado o grupo atual responsável pela execução desta solicitação.
    
??? Question "Quais o significado de cada status do inventário de ICs?"
    - Inventariado: o inventário conseguiu ler as informações do IC e se encerrou com sucesso;
    - Ignorado: na tela de citsmart/pages/evmInventoryConfiguracao/evmInventoryConfiguracao.load temos uma opção para ignorar as máquinas já inventariadas, essa marcação aparece quando isso ocorre;
    - Inacessível: quando o servidor encontra o IC, mas não consegue trazer as informações;
    - Não inventariado: quando nem encontra o IC na rede, mas tem conhecimento de que ele já existiu;
    - Em execução: durante a leitura do inventário, o IC fica nesse status.
    
??? Question "Qual o significado de cada privacidade que um conhecimento pode ter na base de conhecimento?"
    - Público: todos os usuários com acesso no Portal do Conhecimento possuem acesso, independente se têm acesso à pasta do conhecimento;
    - Confidencial: somente o autor e o aprovador podem visualizar o conhecimento;
    - Interno: somente pessoas com permissão na pasta do conhecimento podem visualizar.
    
??? Question "Quais as permissões necessárias na pasta de destino do backup da tabela Logdados?"
    A permissões na pasta devem ser de leitura e gravação para o usuário que o JBoss utiliza.
    
??? Question "Quando ocorre a sincronização dos dados com o LDAP?"
    O sistema sincroniza os dados das credenciais de seus usuários com o LDAP em três situações distintas:
    
    1. Na ativação da aplicação, geralmente em sequência ao procedimento de atualização de versão do produto;
    2. Quando o usuário faz o logon (o acesso ao sistema com seu login e senha), nesse momento o sistema automaticamente verifica a autenticação e permissão do usuário;
    3. Na funcionalidade Configuração de LDAP, quando o usuário clica na opção 'Sincronizar'.
    
??? Question "Quando ocorre a limpeza dos dados da tabela Logdados?"
    A rotina de backup da tabela LogDados retira os dados da tabela e salva em arquivo, ou seja, a tabela fica limpa após o processamento.
    
??? Question "Quando ocorre a limpeza dos dados da tabela Logdados?"
    A rotina de backup da tabela LogDados retira os dados da tabela e salva em arquivo, ou seja, a tabela fica limpa após o processamento.
    
??? Question "Por que os horários criados pela ferramenta estão diferentes da hora atual?"
    CENÁRIO
    1.Ao criar um chamado, a hora fica diferente da hora real, alternando entre 1 (uma) à 3 (três) horas de atraso ou adiantamento.

    O QUE CHECAR
    1. Arquivo de configuração do Banco Postgresql:
     - Postgresql.conf
     - timezone = 'BRAZIL/EAST'
    2. No container cloud:
     - Setting timezone on the operating system.
    3.Configuração do TimeZone no JRE: 
     - https://docs.oracle.com/javase/9/troubleshoot/time-zone-settings-jre.htm#JSTGD362
    
??? Question "Por que em alguns relatórios a mesma solicitação aparece mais de uma vez?"
    Em alguns relatórios como por exemplo o "Relatório Incidentes / Solicitações de Serviços - Detalhado", tanto no formato pdf como no xls, pode existir sim a mesma solicitação mais de uma vez, contudo são detalhamentos distintos porque trata de cada etapa da solicitação, então cada vez que ela "repete" é porque muda-se a tarefa, ou o responsável, ou a fase, ou a situação, ou o grupo solucionador ou a data hora final de atendimento.
    
    Já em outros relatórios, tais como o "Relatório Incidentes / Solicitações de Serviços" não há detalhamento da solicitação de acordo com as atividades e por isso não é mostrada a solicitação mais de uma vez. 
    
??? Question "Por que o resultado é "Relatório Vazio" ao gerar o relatorioControlePercentualQuantitativoSla selecionando no filtro a situação "em Andamento" e o "grupo solucionador"?"
    Não se trata de um erro, o campo de grupo solucionador é preenchido somente quando a solicitação é encerrada, isso faz com que só traga resultados para as situações do tipo "Fechada", incompatível com o que se está pedindo/informando nos filtros.
    
??? Question "Por que a numeração de solicitação de serviço nem sempre seguirá uma ordem sequencial rigorosa/perfeita na tela de solicitação de serviços ou em alguns relatórios?"
    Tanto a tela de Solicitação de Serviços quanto em alguns relatórios (tais como "Qualidade de Atendimento - SLA"), a ordenação do número das solicitações segue uma ordem sequencial crescente, exceto quando:
    
    1. Os relatórios agrupam os dados por algum critério especial (ex.: pelo prazo de SLA, que é o que acontece no caso do relatório "Qualidade de Atendimento - SLA")
    2. Quando o recurso denominado Sequence Block é impactado por um fator externo, isso ocorre se:
    - Há uma parada da aplicação para atualização de versão, ou manutenção de ambiente e posterior retorno.
    - O ambiente é clusterizado.
    
??? Question "O arquivo de backup será sobrescrito ou terá um arquivo para cada dia?"
    Se a sua rotina for um backup por dia, vai ser criado um arquivo por dia, contendo no nome a data do respectivo arquivo.
    
??? Question "Por que o sistema exibe mensagem de data inválida ao auditar o ticket?"
    Na interface do Gerenciamento do Ticket, especificamente no item "Auditoria”, ao tentar configurar a auditoria de um ticket aberto (definir as datas de início e fim no filtro), o seguinte erro pode ocorrer: o sistema apresentará a mensagem de "Data Inválida". Isto ocorre porque a funcionalidade necessita que o idioma definido no sistema e no navegador utilizado sejam idênticos.  
    Se este requisito não for observado e ocorrer esta diferença nos idiomas, ao auditar os tickets o sistema apresentará uma mensagem e impossibilitando auferir o relatório pretendido. Sendo necessário, portanto, igualar os idiomas do sistema e do navegador.  

	
