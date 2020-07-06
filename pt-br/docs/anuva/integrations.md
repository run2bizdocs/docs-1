Title: Integração

# Integrações

As integrações com a assistente virtual Anuva dizem respeito aos canais em que o
administrador irá disponibilizar a assistente. Essa funcionalidade permitirá a
inserção dos links das plataformas desejadas para haver a integração da
assistente virtual com o sistema selecionado.

Veremos adiante que o chat pode ser integrado nativamente ao CITSmart, além do
Facebook ou sistema próprio do usuário através de API Rest.

## Procedimento

1.  Após acessar a plataforma, acesse o menu “Integrações”;

2.  Serão apresentadas as seguintes opções de integração: Facebook Messenger,
    CITSmart e API Rest;

3.  Selecione qual opção você deseja integrar.

### CITSmart

A Anuva já se integra nativamente ao CITSmart, então é muito fácil adicioná-la
ao seu ambiente.

Para realizar a integração, é necessário que você configure os parâmetros
necessários no seu próprio ambiente de produção. Para isso, acesse o sistema e
no menu de processos, selecione Parametrização \> Parâmetros CITSmart.

Localize e preencha os seguintes parâmetros:

|**Parâmetro**|**Valor**|
|-|-|
|402 Helper Assistant - External URL|http://[nome-servidor].helperassistant.com|
|441 Helper Assistant - Conversation API|http://[nome-servidor][sigla-idioma].helperassistant.com/webhooks/rest/webhook|
|442 Helper Assistant - Parameters API|http://[nome-servidor][sigla-idioma].helperassistant.com/conversations/|

*CONFIRMAR NOMES DOS PARÂMETROS PARA ANUVA*

**Importante:** Os valores a serem preenchidos nos parâmetros acima dependerão
do valor apresentado na ferramenta Anuva. Para isso, acesse a sua assistente
virtual e selecione “Integrações”. Para integrar com a plataforma, selecione
“CITSmart” e serão apresentados os valores para copiar e colar no valor na
própria plataforma CITSmart. Esses parâmetros não podem ser alterados pelo
cliente.

*Facebook Messenger*

Também é possível de integrar a assistente virtual Anuva ao chat do Facebook
Messenger. Nesse caso as instruções são fornecidas pelo próprio Facebook e
fornecemos as informações necessárias para realizar a integração:

-   Callback URL

-   Verify Token

-   Secret

-   Page Access Token

*API Rest*

Nessa funcionalidade o cliente pode customizar a assistente virtual para outro
canal. Por exemplo, se o cliente já possuir um site institucional e deseja
incluir a assistente virtual para o seu chat. Para isso, basta selecionar a
opção de comunicação API Rest.

O API Rest é o protocolo de comunicação da assistente virtual. Nela são
apresentadas as seguintes informações para realizar a integração com sucesso:

-   Endpoint

-   Método

-   Media Type

E os formatos necessários para integração:

-   Formato de envio de mensagem ao bot:

{
"sender": "joao",
"message": "conte-me algumas coisas sobre você"
}

-   Formato de retorno da mensagem do bot em texto:

{
"recipient_id": "joao",
"text": "Eu posso ajudá-lo a trabalhar de maneira mais inteligente, em vez de
mais"
}

-   Formato de retorno da mensagem do bot em botão:

{
"recipient_id": "joao",
"text": "Você poderia avaliar o meu atendimento?",
"buttons": [
{
"title": "Sim",
"payload": "sim"
},
{
"title": "Não",
"payload": "não"
}
]
}

-   Formato de retorno da mensagem do bot em imagem:

{
"image":
"https://anuvaassistantimages.s3.amazonaws.com/dev/fe711b50-d974-11e9-9622-94de80f33bee.png",
"recipient_id": "joao"
}

Ou

{
"attachment":
"https://anuvaassistantimages.s3.amazonaws.com/dev/fe711b50-d974-11e9-9622-94de80f33bee.png",
"recipient_id": "joao"
}
