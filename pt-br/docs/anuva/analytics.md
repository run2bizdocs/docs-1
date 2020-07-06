Title: Analytics

# Anuva Analytics

Após treinar as interações e diálogos da Anuva, é preciso monitorar as
interações da sua assistente com os usuários para garantir que ela está sendo
efetiva no atendimento às solicitações e assim garantir a sua qualidade e
assertividade. 

Essas interações podem ser visualizadas na opção Analytics. É a sessão da
plataforma responsável por visualizar relatórios e indicadores. Os módulos estão
divididos da seguinte forma: Lista de Conversação, Rankings de Intents, Ranking
de Respostas e Ranking de Fallback.

### Antes de começar

- É necessário ter realizado pelo menos um treinamento;

- E ter realizado ao menos uma interação com a assistente virtual.

### Procedimento

1.  Após acessar a plataforma, acesse o menu “Analytics”;

2.  Selecione um dos módulos disponíveis: Listar Conversas, Rankings de Intents,
    Ranking de Respostas e Ranking de Fallback.

## Listar conversa

Neste módulo é possível visualizar todas as conversas realizadas pelo chatbot
durante um intervalo de tempo selecionado. O sistema apresentará informações
relativas as conversas realizadas nesse período.

Após clicar em “Listar conversa”, primeiramente, é obrigatório a definição de um
período de tempo no campo “Intervalo”.

Depois de definir um tempo, clique em “Filtrar”.

A ferramenta apresentará as informações de conversação dependendo do tempo de
sua escolha.

Teremos as seguintes informações para análise:

|Função|Descrição|
|-|-|
|Data e hora|A data e hora que foi realizada a conversa entre um usuário e a assistente.|
|Versão|A versão vai variar de acordo com a maturidade do chatbot. Isso significa que a versão da assistente muda de acordo com a quantidade de informação que recebe e os treinamentos a qual é submetida.|
|Canal|O canal que o usuário utilizou para a conversa. Podendo ser de canais diferentes, conforme os configurados na plataforma Anuva. Por exemplo: Facebook, Twitter, Smart Chat, entre outros.|
|Identificação do usuário|A identificação do usuário que conversou com a assistente.|

Além dessas informações, também apresenta duas opções:

|Função|Descrição|
|-|-|
|Ver|Nessa opção é possível ver o detalhamento da conversa entre o usuário e a assistente. O balão de cor azul é a mensagem do usuário. Podemos ver que abaixo dele existe uma porcentagem, que significa a acurácia da assistente e, ao lado, a intent que foi entendida pela Anuva. Caso queira incluir essa frase do usuário à intent entendida, basta clicar nela que você será redirecionado para a página de diálogos. Já o balão de cor branca é a mensagem enviada pela assistente. Abaixo dele a habilidade que foi cadastrada para esse tipo de intent. Caso queira incluir algo novo dessa conversa para a habilidade, basta clicar nela e você também será redirecionado para a página de diálogos. Além disso, também são apresentadas as opções “Atualizar”, caso a conversa ainda esteja acontecendo e você queira receber as novas mensagens; “Exportar” para realizar o download dessa conversa; e “Voltar” para voltar a página anterior.|
|Download|É possível baixar a conversa em formato xls, onde você poderá ver as interações entre usuário e chatbot.         


## Ranking de intents

Nesta modalidade é permitido verificar em formato de gráfico quais intents estão
sendo mais utilizadas pelos usuários do sistema, ou seja, o que os usuários
estão mais perguntando e/ou demandando da assistente.

Após clicar em “Ranking de intents”, primeiramente, é obrigatório a definição de
um período de tempo no campo “Intervalo”. Depois de definir um tempo, clique em
“Filtrar”.

Será apresentado um gráfico com as principais intents de acordo com o período
selecionado. No lado esquerdo está o gráfico em si, em dias, e no lado direito a
legenda do que representam as cores e suas determinadas intents.

Ao final de cada intent existe uma lupa. Ao clicar nessa lupa, você será
direcionado para a página de lista de conversa dessa intent, que mostrará a
lista dependendo do período informado para o gráfico.

Além disso, ao clicar em alguma intent da legenda, você será direcionado para a
página de diálogo relacionada, onde é possível analisar se as frases estão
corretas ou fazer alguma alteração.

## Ranking de respostas

Funciona de forma parecida ao ranking de intents. Nesta modalidade é permitido
verificar quais habilidades estão sendo mais utilizadas pelos usuários do
sistema, ou seja, o que a assistente mais responde durante a interação com o
usuário.

Após clicar em “Ranking de respostas”, primeiramente, é obrigatório a definição
de um período de tempo no campo “Intervalo\*”. Depois de definir um tempo,
clique em “Filtrar”.

Será apresentado um gráfico com as principais habilidades de acordo com o
período selecionado. No lado esquerdo está o gráfico em si, em dias, e no lado
direito a legenda do que representa as cores e suas determinadas habilidades.

No final de cada habilidade existe uma lupa. Ao clicar nessa lupa, você será
direcionado para a página de lista de conversa dessa habilidade, que mostrará a
lista dependendo do período informado para o gráfico.

Além disso, ao clicar em alguma habilidade da legenda, você será direcionado
para a página de diálogo relacionada, onde é possível analisar se as frases
estão corretas ou fazer alguma alteração.

## Ranking fallback

Nesta modalidade podemos verificar quais são as intents que o sistema não
conseguiu entender, ou seja, quais interações com usuário que foram
insatisfatórias pois a assistente não conseguiu entender o objetivo da mensagem.
O fallback, para o sistema, é uma habilidade previamente cadastrada que
apresenta uma mensagem como resposta ao usuário, criada por um administrador da
plataforma a fim de informar ao usuário que a assistente não tem conhecimentos,
cadastrados e treinados, suficientes para atender à solicitação.

Após clicar em “Ranking fallback”, primeiramente, é obrigatório a definição de
um período de tempo no campo “Intervalo\*”. Depois de definir um tempo, clique
em “Filtrar”.

Será apresentado um gráfico com a habilidades de fallback que não foi entendida
pela assistente, de acordo com o período selecionado. No lado esquerdo está o
gráfico em si, em dias, e no lado direito a legenda com a habilidade de
fallback.

Ao clicar na legenda do fallback, você será direcionado para a página de lista
de conversa dessa habilidade dependendo dos dias selecionados no filtro de
intervalo. Ao ver essas conversas, o analista pode verificar se a falta de
compreensão da assistente é correto, ou seja, se o usuário está demandando algo
fora do escopo de criação dela ou se é uma carência, e nesse caso o
administrador pode melhorar sua interação e acurácia, construindo novos fluxos
de conversação ou refinando os existentes.
