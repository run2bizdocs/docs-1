Title: Histórico de Notas de Release
Description: Notas de release, correções de erros e melhorias na CITSmart.

# Histórico de Notas de Release

## Versão 8.0.0.9 (2019/05/31)

Bem-vindos ao Citsmart Versão 8.0.0.9.
A versão 8.0.0.9 do CITSmart apresenta algumas correções emergenciais.

|Problema|Descrição|
|--------|---------|
|3670|Validação do campo e-mail na tela de User Profile|
|3702|Correção em Scripts Neuro|
|3793|Otimização de SQL na lista de solicitações para reduzir o tempo de resposta|
|3879|Correção no Kanbam por atendente para visualizar a informação da tarefa|
|3895|Problemas na execução do cron do CMDB|
|3897|Sistema encaminhando reset de senha para usuário inativo|
|3915|Otimizando SQL lista de solicitações.|
|4038|Correção de upload de imagem na apresentação do portfólio.|

## Versão 8.0.0.7 (2019/05/17)
Com otimizações de desempenho, melhorias de usabilidade, ajustes e correções de falhas.

### Problemas Resolvidos

| **Código** | **Descrição Ticket**                                                                                                                                                                                                                                            | **tipo**  |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 3005       | Analise e melhoria na classe de menu do sistema                                                                                                                                                                                                                 | Melhoria  |
| 3004       | Analise e melhoria na classe de I18N                                                                                                                                                                                                                            | Melhoria  |
| 2869       | Analise e correção de Streams abertas                                                                                                                                                                                                                           | Corretiva |
| 3466       | Problemas de internacionalização                                                                                                                                                                                                                                | Corretiva |
| 3701       | [ITSM 9819] - Na Ger. Liberação sistema carregando outro usuário como responsável                                                                                                                                                                               | Corretiva |
| 3155       | Alterar nomes de Labels e ajustar Menus Neuro                                                                                                                                                                                                                   | Melhoria  |
| 2389       | Ajustes de arquitetura GRP                                                                                                                                                                                                                                      | Corretiva |
| 3884       | [ITSM 9845] - Falha ao carregar anexos em ambiente instável e lento                                                                                                                                                                                             | Corretiva |
| 3707       | Datepicker não funcional ao tentar selecionar a data no relatório de Problema. O mesmo permite preencher, porém, não permite selecionar data específica.                                                                                                        | Corretiva |
| 3264       | [ITSM-9480] - Verificar que o sistema não responde ao componente de e-mail desenhado no fluxo                                                                                                                                                                   | Corretiva |
| 3790       | [ITSM 9816] - Alteração do contexto dinâmico das telas que faltam do CITSmart \#3698                                                                                                                                                                            | Corretiva |
| 3870       | Verificar mensagem de erro ao clicar em "questionário"                                                                                                                                                                                                          | Corretiva |
| 3698       | [ITSM 9816] - Algumas URL's do citsmart não estão respeitando a configuração do jboss-web.xml. Ou seja , quando o contexto é alterado de "citsmart" para "anac", ou algo do tipo. Telas como formulário neuro e manutenção de fluxo deixam de funcionar. \#3790 | Corretiva |
| 3877       | Verificar comportamento do sistema ao tentar acessar a aplicação com consultor em uma base zerada                                                                                                                                                               | Corretiva |
| 3214       | [ITSM-9609] - Erro ao anexar um arquivo com caractere numeral                                                                                                                                                                                                   | Corretiva |
| 3471       | Somente exibir abas se houver conteúdo                                                                                                                                                                                                                          | Melhoria  |
| 3791       | [ITSM 9793] - Verificar que ao tentarmos alterar os dados do formulário de uma solicitação, ao se clicar em "Gravar" estas informações, não são persistidas.                                                                                                    | Corretiva |
| 3664       | [ITSM 9793] - Verificar que ao tentar reclassificar uma solicitação trocando a atividade, a aplicação não está carregando o formulário neuro dessa atividade.                                                                                                   | Corretiva |
| 2870       | [Neuro] Otimização da carga de internacionalização                                                                                                                                                                                                              | Corretiva |
| 3616       | Verificar problema de lentidão ao CADASTRAR UMA MUDANÇA com uma grande quantidade de anexos (anexos extensos).                                                                                                                                                  | Corretiva |
| 3649       | Alguns componentes do fluxo não são exibidos no browser Chrome                                                                                                                                                                                                  | Corretiva |
| 3610       | Ao acessar determinada tela pelo link não é carregado a lista de menu                                                                                                                                                                                           | Corretiva |
| 3661       | Melhoria nas consultas SQL cliente Estruturantes.                                                                                                                                                                                                               | Corretiva |
| 3678       | Criar forma de maior controle de requisições de webservices                                                                                                                                                                                                     | Melhoria  |
| 3499       | Itens do acesso rápido não estão seguindo Perfil de Acesso                                                                                                                                                                                                      | Corretiva |
| 3590       | [ITSM 9708] - Base de conhecimento com perfil por grupo não aparece para vinculo em Portfolio                                                                                                                                                                   | Corretiva |
| 3500       | Padronizar ícones e adicionar hints                                                                                                                                                                                                                             | Melhoria  |
| 1557       | Verificar que não está sendo possível selecionar um modelo de mudança na tela de template                                                                                                                                                                       | Corretiva |
| 3689       | Verificar que não está sendo possivel acessar o simple                                                                                                                                                                                                          | Corretiva |
| 3517       | Ajustes de internacionalização no CITSmart Workflow                                                                                                                                                                                                             | Corretiva |
| 3611       | Após instalação do sistema não esta sendo possível acessar o toolbarHeader                                                                                                                                                                                      | Corretiva |
| 3668       | Não estão sendo exibidos as aplicações do Acesso rápido nas telas antigas                                                                                                                                                                                       | Corretiva |
| 3624       | [ITSM 9623] - Ao reclassificar um ticket o mesmo esta apresentando a seguinte mensagem: Key must not be null or empty.                                                                                                                                          | Corretiva |
| 3623       | Removendo anexos ao avançar fluxo apos ser criado uma solicitação.                                                                                                                                                                                              | Corretiva |
| 3496       | Verificar padrão para cadastrar IC relacionado no CMDB                                                                                                                                                                                                          | Corretiva |
| 3494       | Verificar que quando o usuário clica na opção 'Visualizar mapa de relacionamento' a aplicação exibe mensagem de erro.                                                                                                                                           | Corretiva |
| 3187       | Mensagem de crítica (em pop-up) quanto obrigatoriedade de campo "Data Início" do Período na Avaliação do Contrato, apresentado com erro ortográfico.                                                                                                            | Corretiva |
| 3241       | Verificar que a informação do campo 'Caixa de Saída de E-mail' está multiplicando cada vez que grava um contrato.                                                                                                                                               | Corretiva |
| 3621       | Não está sendo possível remover os anexos da Liberação                                                                                                                                                                                                          | Corretiva |
| 3669       | Não está sendo possível criar um ticket pelo portal quando a atividade está configurada para não exibir o campo descrição                                                                                                                                       | Corretiva |
| 3607       | [ITSM-9097] - Tratar a gravação dos dados de formulário Neuro na Reclassificação                                                                                                                                                                                | Corretiva |
| 3512       | Lentidão ao carregar uma Mudança/Liberação/Problema com anexos                                                                                                                                                                                                  | Corretiva |
| 3506       | Neuro não instala automaticamente na migração do ITSM versão 7 para a 8                                                                                                                                                                                         | Corretiva |
| 3605       | [ITSM 9722] - Erro de tradução no Relatorio                                                                                                                                                                                                                     | Corretiva |
| 3602       | [ITSM 9773, 9824] Verificar que não está sendo possível publicar e nem versionar um conhecimento                                                                                                                                                                | Corretiva |
| 1602       | Acrescentar contandor no icone de anexo e mensagem e troca icones de lugares                                                                                                                                                                                    | Corretiva |
| 3501       | Exibição do botão flutuante                                                                                                                                                                                                                                     | Corretiva |
| 3609       | Não está sendo possível remover os anexos da aba de planejamento da Mudança                                                                                                                                                                                     | Corretiva |
| 3589       | Erro ao salvar os anexos. Sistema não salvava alguns anexos devido a problema de concorrência                                                                                                                                                                   | Corretiva |
| 3479       | Erro ao logar no sistema                                                                                                                                                                                                                                        | Corretiva |
| 3596       | Sistema não esta exibindo iframe. Spring boot : X-Frame-Options set to deny                                                                                                                                                                                     | Corretiva |
| 3463       | Alterar a label "Start" no breadcrumb para "Portal"                                                                                                                                                                                                             | Melhoria  |
| 3559       | Corretivas na última versão do Simple                                                                                                                                                                                                                           | Corretiva |
| 3378       | A função initialize não está retornando.                                                                                                                                                                                                                        | Corretiva |
| 3447       | Na tela de pesquisa avançada não exibe mensagem de sessão expirada                                                                                                                                                                                              | Corretiva |
| 3473       | Adicionar autocomplete no campo "email do contato"                                                                                                                                                                                                              | Corretiva |
| 3066       | Campo valor (numérico), no Registro de Formulário, permite digitar valores alfanuméricos, embora a aplicação não grave o registro , corrigir para que o campo preencha apenas o tipo definido                                                                   | Corretiva |
| 3281       | [ITSM-9629] - Modal para visualização de IC aberta por Ger de Eventos está muito pequena e precisa de ajustes                                                                                                                                                   | Corretiva |
| 3368       | A palavra "Solicitación" precisa ser substituída por "Solicitud".                                                                                                                                                                                               | Corretiva |
| 3186       | Mensagem de crítica (em pop-up) quanto obrigatoriedade de campo "Contrato" na Avaliação do Contrato apresentado com erro ortográfico                                                                                                                            |           |
| 3424       | Validar parâmetros do Neuro antes da gravação                                                                                                                                                                                                                   | Corretiva |
| 3166       | [ITSM-9562] - Verificar cadastro de ticket com espaço vazio                                                                                                                                                                                                     | Corretiva |
| 3201       | Correção de nomes em Impacto e Urgency na tela de tempo de atendimento                                                                                                                                                                                          | Corretiva |
| 3093       | Verificar comportamento do sistema quando o usuário clica na opção 'Sobre o CITSmart'                                                                                                                                                                           | Corretiva |
| 1910       | Mensagem não está internacionalizada (Depende do simple \#2878)                                                                                                                                                                                                 | Corretiva |
| 2919       | Não está fechando a modal ao aprovar a solicitação                                                                                                                                                                                                              | Corretiva |
| 3086       | Corrigir o termo: "I didnt'l like it" para "i didn't like it".                                                                                                                                                                                                  | Corretiva |
| 2780       | mudar status da operação na tela de auditoria I=INSERTE para C=CRIAÇÃO.                                                                                                                                                                                         | Corretiva |
| 3282       | [ITSM 9628] - Falha ao tentar Editar um Gerente Zabixx                                                                                                                                                                                                          | Corretiva |
| 3172       | Ao realizar uma aprovação via token e tiver sem uma sessão em operação.                                                                                                                                                                                         | Corretiva |
| 3179       | Verificar que ao atualizar a versão está dando erro nos scripts de atualização.(Relacionados às tarefas 3154 e 2838)                                                                                                                                            | Corretiva |
| 3278       | Não carrega labels depois da correção de scripts de banco de dados                                                                                                                                                                                              | Corretiva |
| 3286       | Possibilitar parse dos objetos no componente Rest                                                                                                                                                                                                               | Corretiva |
| 1665       | Geração de relatório de pesquisa em .PDF sem preenchimento de campos obrigatórios                                                                                                                                                                               | Corretiva |
| 3106       | No cadastro de Problema, ao vincular Ticket/Incidente, o componente de número está apresentando número negativos. Adendo: No mesmo campo (Number) está aceitando valores alfanuméricos (diferente do tipo na classe do mesmo)                                   | Corretiva |
| 3072       | Verificar que quando informamos na jordana de trabalho a hora final igual 00:00, a aplicação não calcula o SLA corretamente.                                                                                                                                    | Corretiva |
| 1596       | Verificar que o usuário alterou o último horário da JORNADA, porém ao criar solicitação essa alteração não foi refletida                                                                                                                                        | Corretiva |
| 3067       | Melhorias no processamento da fila de inventário (Therads)                                                                                                                                                                                                      | Melhoria  |

    
Caminho dos pacotes:  
>   1.       **Workflow**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Enterprise/8.0.0.7/CitsmartITSM-Enterprise-8.0.0.7.war.zip>

>   2.       **Neuro**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.10.war.zip>

>   3.       **Inventory**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip>

>   4.       **EVM**:
>    <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip>

>   5.       **Audit**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.4.0.war.zip>

>   6.       **Neuro**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.10.war.zip>

>   7.       **Inventory**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip>

>   8.       **EVM**:
>    <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip>

>   9.       **Audit**: <ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.4.0.war.zip>


## Versão 8.0.0.5 (2019/04/25)

### Problemas Resolvidos

| Problema | Descrição                                                                                                                                              |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3360     | Ger. de Problema - Erro ao recuperar Solução definitiva                                                                                                |
| 3361     | Ger. de Problema - Erro ao recuperar o campo de fechamento                                                                                             |
| 3362     | Ger. de Problema - Erro ao recuperar erro conhecido                                                                                                    |
| 3363     | Ger de Configuração – Erro ao recuperar Mudanças Concluídas relacionadas à Item de Configuração                                                        |
| 3364     | Ger. Liberação – Erro ao vincular Mudança encerrada em Liberação                                                                                       |
| 3365     | Ger. Problema – Adequação de interface para apresentar os campos “Mensagem de erro associada” e “Diagnóstico”                                          |
| 3366     | Ger. Mudança – Erro ao retornar Risco Simplificado                                                                                                     |
| 3393     | Ger. Liberação – Retorno da Regra de Negócio ao vincular uma mudança que tenha IC vinculado a uma Liberação, vincular automaticamente o IC à Liberação |
| 3282     | Ger. Eventos – Falha ao Editar um Ger. Genérico Zabbix                                                                                                 |
| 3115     | Ger. Eventos – Renderização maior da tela de Ger de Ticket                                                                                             |
| 3394     | Ger. Liberação – Sistema duplica anexos ao avançar fluxo                                                                                               |
| 3388     | Ger. Problema – Gravação de erro conhecido não seta campo de arquivamento e sistema não consegue recuperar o conhecimento                              |
| 3419     | Ger. Mudança – Sistema não recupera anexo colocado no campo de Revisão e fechamento                                                                    |

*Erro conhecido e solução*

Se atentem para o cenário descrito:

-   Pré Condições:

    1.  O cliente estará atualizando a versão 7 para a versão 8.0.0.5;

    2.  O consultor não parametrizou em Portfólio de Problema a pasta para
        gravar a base de conhecimento de Erro Conhecido;

-   O que ocorre:

    1.  O usuário acessa a tela de Gerenciamento de Problema;

    2.  O usuário informa o campo Causa Raiz e tenta acionar a gravação da base
        de conhecimento;

    3.  Ao abrir a tela de Base de Conhecimento para gravação o sistema exibe a
        mensagem de que o usuário não possui permissão;

-   Por que ocorre?

    1.  A mensagem ocorre porque o consultor não informou qual deveria ser a
        pasta de gravação do erro conhecido em Portfólio de Problema;

    2.  Uma vez tentado gravar o erro conhecido, o sistema não identifica a
        pasta e emite a mensagem;

    3.  Nesses casos, procure o Suporte Citsmart para realizar a adequação desse
        cadastro;

    4.  Faça a configuração da pasta para gravação de erro conhecido na tela de
        Portfólio de Problema;

    5.  No próximo cadastro a mensagem não se repetirá.
    
    
    
Caminho dos pacotes:  
**SM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Enterprise/8.0.0.5/CitsmartITSM-Enterprise-8.0.0.5.war.zip  
  
**Inventory**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip  
  
**EVM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip  
  
**Neuro**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.8.war.zip  
  
**Audit**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.2.0.zip


## Versão 8.0.0.4 (2019/04/12)

### Problema Resolvido

| Problema | Descrição                                                                                 |
|----------|-------------------------------------------------------------------------------------------|
| 3275     | Falha no momento de restaurar Grupo Executor, Impacto e Urgência em Gerência de Liberação |

## Versão 8.0.0.3 (2019/04/04)

### Problemas Resolvidos

| Problema | Descrição                                                                                                                                                                                                          |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 2573     | Erro conhecido na versão 8.0.0.0 ao responder a pesquisa de satisfação pelo Widget do Centro de Experiência. A versão 8.0.0.3 fornece uma solução definitiva para o erro ao gravar uma pesquisa de satisfação.     |
| 2122     | Falha no webservice de criação de solicitação de serviço. A versão 8.0.0.3 fornece solução definitiva para a falha apresentada ao tentar cadastrar uma solicitação de serviço via webservice.                      |
| 2917     | Falha ao realizar upload de anexos pela funcionalidade de solicitação de serviço. A versão 8.0.0.3 fornece solução para realizar upload dos anexos pela funcionalidade de solicitação de serviço.                  |
| 2777     | Falha intermitente no método que retorna o timezone para gravar registro de data e hora. No componente Neuro. A versão 8.0.0.3 fornece solução definitiva no componente Neuro para gravar registro de data e hora. |

## Versão 8.0.0.2 (2019/03/20)

## Problemas Resolvidos

| Problema | Descrição                      |
|----------|-----------------|
| 2309     | Falha intermitente e de maior incidência em ambientes clusterizado no método que retorna o timezone para gravar registro de data e hora. A versão 8.0.0.2 fornece solução definitiva para o erro ocasionado nas classes que utilizam timezone para gravação de registros. |
| 2124     | Falha de validação incorreta ao acessar uma base de conhecimento externa. A versão 8.0.0.2 fornece solução definitiva para a mensagem de expiração de sessão mostrada indevidamente quando o usuário tentava acessar uma base de conhecimento externa.                    |
| 2400     | Falha no componente de pesquisa avançada que não retornava palavras com “ç” e “ã”. A versão 8.0.0.2 fornece solução definitiva para a pesquisa avançada com palavras acentuadas.                                                                                          |


## Versão 8.0.0.1 (2019/03/08)

## Problemas Resolvidos

| Problema | Descrição                 |
|----------|---------------------------|
| 2576     | Erro conhecido em portfólio que não é exibido quando existe uma data final no serviço do contrato. A versão 8.0.0.1 fornece solução definitiva para o erro ocasionado pelo portfólio de serviços. |


## Versão 8.0.0.0 (2019/03/01)

### Correções

#### Gerenciamento de Ticket

As funcionalidades de Sub-Solicitação e Solicitação Relacionada sofreram uma reestruturação que proporciona maior conformidade à suas atribuições, o foco dessa correção foi aproximar a funcionalidade daquilo que realmente é a sua proposta.

Para mais informações, veja [Relacionar um Ticket][1] e [Cadastrar uma Sub-Solicitação][2]

#### Webservices

A sincronização para criação de novas Atividades sofreu uma alteração em sua regra de negócio, isso porque não é possível criar uma atividade que não tenha vínculo com Serviço de Negócio e Portfólio. Portanto, o webservice designado para criação irá abrir um ticket com os parâmetros passados na configuração inicial do serviço.

A funcionalidade de criar um novo usuário, quando estiver habilitado a sincronização de dados permanece consistente.

#### Fluxo

Tratativa para barrar edição de expressões nativas e expressões de mesmo nome.

### Novas Funcionalidades e Melhorias

#### Acesso Rápido

O acesso rápido permite que o usuário encontre os principais processos por meio de ícones que auxiliam na fixação e visualização de forma eficiente.

**O usuário visualiza somente os ícones dos processos que o mesmo possui acesso com exceção dos ícones Simple, Portal do Conhecimento, Centro de Experiência e Guia de Usuário.**

#### Configuração de notificação por e-mail de ticket delegado

Criamos a possibilidade de configuração de notificação por e-mail na funcionalidade de delegação do ticket
Para mais informações, veja [Notificação via e-mail de ticket delegado][3]

#### Configuração de Notificação por e-mail de ticket reclassificado

Criamos a possibilidade de configuração de notificação por e-mail na funcionalidade de reclassificação do ticket
Para mais informações, veja [Notificação via e-mail de ticket reclassificado][4]

#### Gerência de  Mudança

A versão 8.0.0.0 do CITSmart sofreu melhorias no processo de gerenciamento de mudanças, trazendo o mundo ágil para gerenciar as atividades que deverão ocorrer durante o escopo da mudança.

**Nota:** Essa funcionalidade substitui os parâmetros de fluxos padrões para utilização do processo de mudança, portanto, é necessária a alteração para essa configuração.


Para mais informações, veja [Gerência de Mudança][5]

#### Gerência de Problema

Na versão 8.0.0.0 do CITSmart o processo de gerenciamento de problema permite adicionar atividades para auxiliar no gerenciamento das equipes durante o diagnóstico da causa raiz.

**Nota:** Essa funcionalidade substitui os parâmetros de fluxos padrões para utilização do processo de problema, portanto, é necessária a alteração para essa configuração.


Para mais informações, veja [Gerência de Problema][6]

#### Configuração de uso para Gerência de  Liberação

O processo de liberação ganha mais força no planejamento, testes e homologação permitindo designação das atividades e gerenciamento à vista.

**Nota:** Essa funcionalidade substitui os parâmetros de fluxos padrões para utilização do processo de liberação, portanto, é necessária a alteração para essa configuração.


Para mais informações, veja [Gerência de Liberação][7]

#### Revisão de Comentários

Na versão 8.0.0.0 o CITSmart permite avaliação e publicação dos comentários escritos sobre um conhecimento.

Para mais informações, veja [Revisão de Comentário][8]

#### Acesso à base de conhecimento de usuários externo

Inovamos  a forma de acesso à base de conhecimento para usuários que não possuem login de acesso à ferramenta CITSmart.

Na versão 8.0.0.0 conhecimentos com permissão de visualização poderão ser acessados pela comunidade em geral, basta possuir o link de acesso.


Para mais informações, veja Configurar acesso externo ao [Portal de Conhecimento][9]

#### Gerência de Item de Configuração

Aprimoramos a experiência do usuário trazendo em destaque um dashboard que apresenta a quantidade de itens de configuração, por grupo, tipo e aglutinados nos processos de Incidente, Mudança e Liberação, deixando à vista possíveis IC’s que passarão por alteração ou envolvidos em algum incidente.

Para mais informações, veja [Gerenciamento de Item de Configuração][10]

#### Regra de Escalonamento

Simplificamos o uso das regras de escalonamento dos tickets, com poucos passos será possível implementar a regra que antes contava com inúmeras configurações.

**Nota**: Essa funcionalidade substitui o uso de diversos parâmetros de escalonamento, portanto, é necessária a alteração para o uso efetivo das regras de escalonamento.


Para mais informações, veja [Criar regra de escalonamento][11]

#### Aprovação de Ticket

Na versão 8.0.0.0 do CITSmart incluímos a aprovação de tickets através de novo ícone direto na lista de atendimento, não será necessário abrir o ticket para realizar o atendimento, apresentamos as informações disponíveis e as opções configuradas para aceite ou recusa do chamado.

Essa funcionalidade está disponível no Mobile SM e no Portal de Serviços.

Para mais informações, veja [Aprovar um ticket][12]

#### Atualização automática da lista de ticket

Permitimos que a função de atualização automática da lista de ticket seja habilitada para atualizar a lista automaticamente de tempos em tempos.

Para mais informações, veja [Atualização Automática da Lista de Ticket][13]

#### Ocorrência

O aprimoramento do cadastro de ocorrência permite que o solicitante ou técnico seja notificado via e-mail. Além da permissão de incluir tempo de execução da atividade e manter o sigilo da informação cadastrada, para que somente os técnicos permitidos a vejam.

Para mais informações, veja [Cadastrar ocorrência em Ticket][14]

#### Simple - Gestão Ágil e a vista

O Simple foi criado com o intuito de trazer o conceito de gestão ágil à ferramenta.
De forma independente ou aglutinada em uma das soluções de Problema, Mudança e Liberação, o Simple permite reutilização de Sprints, compartilhamento de recursos, envio de atividades à outras Sprints e gestão à vista.

Para mais informações, veja [Simple][15]

#### Área do cliente

Proporcionamos uma área específica para melhorar a experiência de uso. Nessa área será permitido a apresentação de serviços, informações, relatórios que mais se aproximam com o uso do dia a dia do cliente.

Para mais informações, veja [Centro de Experiência][16]

#### Business Intelligence

A partir da versão 8.0.0.0 disponibilizamos alguns relatórios quantitativos dos principais processos contidos no CITSmart através de nossa nova plataforma BI.

Para mais informações, veja [Business Intelligence][17]

#### Auditoria

Reformulamos a auditoria do sistema para aumentar a agilidade e confiabilidade do recurso de pesquisa de auditoria.

Para mais informações, veja [Auditoria do Sistema][18]

#### Política de Segurança de Senha

Aprimoramos o quesito de segurança da informação, implantado formas de segurança de senhas para usuários internos.

Para mais informações, veja [Política de Segurança de Senha][19]

#### Mobilidade

Entregamos um novo aplicativo que de forma robusta permitirá o atendimento a campo de técnicos que momentaneamente estão sem conexão à internet.

A experiência de mobilidade vai além com os recursos de assinatura e notas.

Para mais informações, veja [Manual de utilização do aplicativo CITSmart GO][20]

Ainda no contexto de mobilidade e não menos robusta, aprimoramos o aplicativo Mobile SM, que possui dentre outros usos a capacidade de assinatura, aprovação e notas.

Para mais informações, veja [Manual de utilização do aplicativo mobile CITSmart Experience][21]

#### Neuro

A partir da versão 1.2.3.0 do Neuro é possível criar automaticamente um questionário do CITSmart a partir do cadastro de objeto de negócio do Neuro. A ideia dessa inovação é facilitar a extração de respostas de questionários do CITSmart e formar relatórios de forma simples com o auxílio do Smart Report.


#### Fluxo

O pacote de fluxos entregues para os processos de Problema, Mudança e Liberação foram simplificados, os produtos foram remodelados para estarem aderentes às possibilidades que o fluxo oferece.

__Caso o cliente não queira utilizar os novos fluxos, a última versão 7.1.0 continuará funcionando perfeitamente.__


[1]:/pt-br/citsmart-platform-8/processes/tickets/use/register-ticket-related.html
[2]:/pt-br/citsmart-platform-8/processes/tickets/use/create-and-view-sub-request.html
[3]:/pt-br/citsmart-platform-8/processes/tickets/configuration/notification-delegated-email-ticket.html
[4]:/pt-br/citsmart-platform-8/processes/portfolio-and-catalog/configuration/send-email-reclassified-ticket.html
[5]:/pt-br/citsmart-platform-8/processes/change/overview.html
[6]:/pt-br/citsmart-platform-8/processes/problem/overview.html
[7]:/pt-br/citsmart-platform-8/processes/release/overview.html
[8]:/pt-br/citsmart-platform-8/processes/knowledge/use/review-reviews.html
[9]:/pt-br/citsmart-platform-8/processes/knowledge/configuration/configure-external-access-knowledge-portal.html
[10]:/pt-br/citsmart-platform-8/processes/configuration/overview.html
[11]:/pt-br/citsmart-platform-8/processes/tickets/use/create-escalation-rule.html
[12]:/pt-br/citsmart-platform-8/processes/tickets/use/approve-a-ticket.html
[13]:/pt-br/citsmart-platform-8/processes/tickets/use/desktop-of-service-desk.html
[14]:/pt-br/citsmart-platform-8/processes/tickets/use/register-ticket-occurrences.html
[15]:/pt-br/citsmart-platform-8/additional-features/project-management/simple-agile-management/simple-agile-management.html
[16]:/pt-br/citsmart-platform-8/processes/knowledge/use/create-experience-center.html
[17]:/pt-br/citsmart-platform-8/additional-features/smart-analytics/use-bi-solution.html
[18]:/pt-br/citsmart-platform-8/platform-administration/logs-and-auditing/system-audit.html
[19]:/pt-br/citsmart-platform-8/platform-administration/security/implement-password-security-rules.html
[20]:/pt-br/citsmart-platform-8/additional-features/mobile-and-field-service/apps/citsmart-field-service-manual.html
[21]:/pt-br/citsmart-platform-8/additional-features/mobile-and-field-service/apps/citsmart-app.html

