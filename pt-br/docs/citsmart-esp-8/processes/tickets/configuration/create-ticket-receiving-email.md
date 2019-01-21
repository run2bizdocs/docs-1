title: Criar um ticket automaticamente a partir do recebimento de um e-mail
Description: Permite a criação automática de um ticket quando uma mensagem de e-mail é enviada para um determinado endereço.
#Criar um ticket automaticamente a partir do recebimento de um e-mail

Esta funcionalidade permite a criação automática de um ticket quando uma
mensagem de e-mail é enviada para um determinado endereço. Neste contexto, a
solução monitora constantemente a presença de mensagens na caixa de e-mail, e
caso alguma mensagem tenha o status não lida, esta será utilizada para registro
de um novo ticket.

Por exemplo, um usuário poderia solicitar determinado serviço enviando uma
mensagem para servico\@empresa.com, após o recebimento do e-mail, a
funcionalidade, após checar que existe uma mensagem, registra um ticket
automaticamente. É importante destacar que após o registro do ticket, o e-mail é
marcado como lido.

O que fazer antes
---------

Para criar um ticket através de um recebimento de e-mail é necessário configurar
uma conta de e-mail para permitir o acesso via IMAP previamente.

Procedimento
----------

*Passo 1*

1.  Acessar a funcionalidade através da navegação do menu principal Sistema \>
    Ações automáticas \> Ações Incidentes/Requisições (ver conhecimento
    Cadastrar Ação automática de Incidentes/Requisições/Procedimentos).

*Passo 2*

1.  Criar ação automática de e-mail, acessando o menu principal Sistema \>
    Configurações \> Configuração de Ação automática via e-mail (ver
    conhecimento Criar ação automática de e-mail).

*Passo 3*

1.  Criar Rotina batch, acessando o menu principal Sistema \> Processamento
    Batch (ver conhecimento Processamento Batch):

    -   Baixar script em anexo.


Relacionado
-------

[Cadastrar ação automática de incidentes/requisições/procedimentos](/pt-br/citsmart-esp-8/additional-features/automation-of-operation/configuration/register-automatic-actions-incident-request-procedure.html)

[Criar ação automática via email](/pt-br/citsmart-esp-8/platform-administration/configuring-automatic-actions/email-create-automatic-action-via-email.html)

[Processamento Batch](/pt-br/citsmart-esp-8/platform-administration/configuring-automatic-actions/batch-batch-processing.html)


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RN9wA1DbVHEot2QD2gW8_jq)'

Anexo
------------
[Download - Verificar email][1]


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/16/2019 – Anna Martins
    
[1]:/pt-br/citsmart-esp-8/processes/tickets/images/rotina-verificar-email.docx
  
