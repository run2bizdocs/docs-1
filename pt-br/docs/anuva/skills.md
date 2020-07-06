Title: Habilidades

# Habilidades

As habilidades dentro da assistente virtual têm a funcionalidade de possíveis
respostas do chatbot às interações do usuário, podendo ser um erro utilizando o
fallback ou até mesmo uma habilidade pré-definida para responder ao usuário.

## Fallback

Fallback é uma habilidade cadastrada para o caso de a assistente virtual não
conseguir compreender a mensagem ou o objetivo do usuário, isso acontece quando
o usuário solicita algo diferente dos contextos cadastrados.

Dessa forma a assistente virtual utiliza algumas frases pré-definidas pelo
administrador da Anuva, que serão enviadas ao usuário como por exemplo “Não
entendi”, “Ainda não fui programada para responder isso”, “Pode reformular, não
entendi o que quis dizer” etc. Assim a sua assistente virtual pode avisar o
usuário final que esse pedido não pôde ser realizado ou compreendido, mostrando
para o usuário realizar outro pedido ou definir outro objetivo.

## Habilidade Estendida

Quando um usuário quer que a assistente virtual faça uma habilidade além das
pré-configuradas (texto, botão, imagem ou personalizado), através dessa
habilidade ele solicita essa nova habilidade para a equipe administradora da
Anuva que vai fazer o que o cliente solicitou com o nome que ele escolher.

## Nova Habilidade

1.  Após acessar a plataforma, acesse o menu “Habilidades”. É possível gerenciar
    as habilidades podendo editar, excluir e criar uma habilidade;

2.  Clique em novo para criar uma habilidade;

3.  Preencha os campos conforme necessidade:

|Campo| Descrição|
|-|-|
|Nome| Preencha com o nome de identificação da habilidade.|
|Tema| Selecione o tema entre a lista de temas criados no menu “Temas”.|
|Esta é uma habilidade de fallback?| Selecione se a habilidade é fallback ou não|
|Esta é uma habilidade estendida?| Selecione se esta habilidade é uma habilidade estendida |
|Deseja predefinir o comportamento do bot com base na última interação com o usuário? | Selecione se essa habilidade deve predefinir um comportamento do bot com base na última interação com o usuário final, selecione o “**Contexto**” e o “**Diálogo**” |

4.  Preencha os campos da tela, atentando-se ao tipo da habilidade: 

-   **Padrão**: será utilizada para representar habilidades que são respondidas
    através de uma resposta de texto pré-definida. Podem ser atribuídas várias
    frases pré-definidas de respostas sempre visando responder a mesma
    pergunta;     

-   **Personalizada**: será utilizada quando, para responder a um interesse do
    usuário, a Anuva precisar buscar informações em um outro sistema.

Acesse o conhecimento **“Como Anuva pode interagir com outros sistemas”** para entender como utilizar este tipo de habilidade;

-   **Botão**: Será utilizada sempre que for necessário limitar as respostas do
    usuário a uma determinada interação da Anuva. Ao utilizar essa opção, a
    Anuva responderá a interação do usuário exibindo botões. Um botão é definido
    por seu Nome e Valor.

No campo nome, é definido o botão que aparecerá para o usuário. No campo valor, é definido para a assistente como ela deve interpretar o interesse do usuário ao clicar o botão; 

-   **Imagem**: Pode ser utilizada quando desejar responder o usuário utilizando
    texto e imagem. A imagem associada a resposta será exibida na janela do
    chat.

5.  Clique em “Salvar” para finalizar o cadastro.
