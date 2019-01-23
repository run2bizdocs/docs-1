title: Habilitar a mensageria dentro do CITSmart
Description: Disponibiliza um canal de comunicação entre o solicitante (Smart Portal)) e o técnico (área de solicitação de serviço/ticket) via mensagem (email).
#Habilitar a mensageria dentro do CITSmart

O CITSmart disponibiliza um canal de comunicação entre o solicitante (Smart
Portal) e o técnico (área de solicitação de serviço/ticket) via mensagem
(email). Essa comunicação visa facilitar a resolução de um chamado. Este
conhecimento reúne informações pertinentes à configuração do serviço de
mensageria.

Procedimento
----------------

1.  Para que o serviço de mensageria esteja disponibilizado dentro do CITSmart é
    necessário setar o parâmetro 417 com o número do ID do modelo de e-mail que
    contenha algumas variáveis para poder ser enviado a mensageria;

2.  Abaixo estão listadas chaves para o envio de e-mail:

    -   \${IDSOLICITACAOSERVICO} - Número do ticket (chave pública);

    -   \${COMMENTTEXT} - Descrição do Comentário feito na mensageria;

    -   \${DATETIMECREATED} - Data em que o comentário foi cadastrado;

    -   \${USERNAME} - Nome do usuário que inseriu o comentário;

    -   \${REQUESTERNAME} - Nome do solicitante;

    -   \${REQUESTRESPONSIBLENAME} - Nome do técnico responsável pelo atendimento do
        ticket.


Relacionado
-------

[A área de trabalho da Central de Serviços](/pt-br/citsmart-esp-8/processes/tickets/use/desktop-of-service-desk.html)

[Configurar parametrização - ticket](/pt-br/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ticket.html)

[Configurar modelo de email](/pt-br/citsmart-esp-8/platform-administration/email-settings/email-templates-configure-email-template.html)

[Gerenciar minhas solicitações pelo Smart Portal](/pt-br/citsmart-esp-8/processes/portfolio-and-catalog/use/request-through-Smart-Portal.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/16/2019 - Anna Martins
