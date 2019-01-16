title: Habilitar a mensageria dentro do CITSmart
Description: Disponibiliza um canal de comunicação entre o solicitante (Smart Portal)) e o técnico (área de solicitação de serviço/ticket) via mensagem (email).
#Habilitar a mensageria dentro do CITSmart

O CITSmart disponibiliza um canal de comunicação entre o solicitante (Smart
Portal)) e o técnico (área de solicitação de serviço/ticket) via mensagem
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

Aárea de trabalho da Central de Serviços

Configurar parametrização - ticket

Configurar modelo de email

Gerenciar minhas solicitações pelo Smart Portal


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/16/2019 - Anna Martins
