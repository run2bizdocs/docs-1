title: Aprovar solicitação via e-mail
Description: Tem por objetivo aprovar ou rejeitar a solicitação de um ticket por meio do e-mail, sem a necessidade do administrador estar logado.
#Aprovar solicitação via e-mail

Esta funcionalidade tem por objetivo aprovar ou rejeitar a solicitação de um
ticket por meio do e-mail, sem a necessidade do administrador estar logado.

Antes de começar
--------------------

Para realizar a configuração do e-mail no ticket é necessário registrar
previamente o usuário, o grupo e configurar os parâmetros 33 e 370 conforme
orientações das regras de parametrização referente a sistema. Também é preciso
saber desenhar fluxo de aprovação de solicitação via e-mail cadastrado. Neste
fluxo deverá existir a tarefa "Aprovação" e o desenho para envio de e-mail,
cadastrar o modelo de e-mail com o modelo "Aguardando Aprovação" que se encontra
em anexo e o servidor de e-mail deverá ser configurado com todos os parâmetros
referentes a regras de parametrização de e-mail.

Procedimento
----------------

1.  Acessar a funcionalidade através da navegação no menu principal Sistema \>
    Manutenção de fluxos;

2.  Selecionar o fluxo de aprovação de solicitação e clicar em "Editar";

3.  Na aba **Diagrama**;

4.  No fluxo de aprovação de solicitação clicar no ícone "Envio de mensagem - email" e em seguida na pequena caixa cinza próxima ao conector configurado;

5.  Cadastrar, na aba **Identificação**, o nome e o modelo de e-mail a ser
    utilizado;

6.  Configurar, na aba **Destinatários**, os tipos destinatários (grupo/usuário)
    do e-mail a ser enviado (o sistema não busca destinatários via "Expressão").

*Configurar a notificação de aprovação do e-mail*

1.  Acessar a funcionalidade através do menu Sistema \> Configurações \>
    Modelo de e-mail;

2.  Colar o modelo de e-mail disponibilizado em HTML em anexo, no campo Texto e
    verificar as seguintes diretrizes:

    -   href="{TOKEN(serviceRequestIncident, \${IDSOLICITACAOSERVICO}, VIEW, 50)};

    -   serviceRequestIncident = Direcionamento da interface : esse campo não pode
        ser alterado pelo usuário;

    -   \${IDSOLICITACAOSERVICO} = Chave para incrementar o número da solicitação de
        serviço : esse campo não pode ser alterado pelo usuário;

    -   VIEW - chama o comando para abrir a solicitação : esse campo não pode ser
        alterado pelo usuário;

    -   MM (50) - Tempo de expiração do token em Minutos : esse campo pode ser
        alterado pelo usuário;

1.  Clicar em "Gravar".


Relacionado
-------

[Cadastrar um grupo](/pt-br/citsmart-esp-8/initial-settings/access-settings/user/register-groups.html)

[Cadastrar usuário](/pt-br/citsmart-esp-8/initial-settings/access-settings/user/users.html)

[Manutenção de fluxo de trabalho](/pt-br/citsmart-esp-8/platform-administration/flow-maintenance/workflow.maintenance.html)

[Configurar parametrização - email](/pt-br/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-email.html)

[Configurar parametrização -sistema](/pt-br/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-system.html)

Anexo
----------



<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RN9wA1DbVHEot2QD2gW8_jq)'

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/16/2019 – Anna Martins


