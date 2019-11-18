title: Configurar Tarefa de Usuário
Description: Este documento tem por objetivo configurar a atividade do usuário dentro do fluxo de trabalho

# Configurar Tarefa de Usuário

Após dar início a construção de um fluxo de trabalho é necessário entender como configurar uma tarefa de usuário para que sua experiência no momento de construir seja tão prática quando no momento que o usuário final utilizar o fluxo.

## Antes de Começar

No mínimo, você precisará ter um fluxo sendo registrado pois não é possível salvar o fluxo caso ele não tenha um evento de entrada e um de saída, para que isso aconteça é necessário que entre os dois eventos tenha uma tarefa para que seja possível o usuário interagir com o fluxo de alguma forma.

## Procedimentos para configurar a Tarefa de Usuário  

1. Abrir ou construir um Fluxo;

2. Clicar na aba “Diagrama”;

3. Para criar uma Tarefa de Usuário clique em Atividades para abrir as opções de atividades;

4. Selecione **Tarefa de Usuário** clicando e arrastando para a área de desenho;

Com um clique duplo em cima da atividade abrirá as seguintes propriedades:

* **Identificação**

  * **Nome** – da tarefa de usuário;

  * **Descrição** – para detalhar a tarefa do usuário;

  * **Identificador** – é uma sigla única para tarefa, serve para codificar Rhino e para formulário do neuro;

  * **Contabilizar SLA** – definir se “sim” ou “não” (o status “SLA Suspensa” aparecerá na interface de gestão de ticket);

  * **Percentual de execução** – campo informativo da quantidade que essa tarefa do fluxo tem em todo o fluxo;

  * **É uma tarefa de aprovação?** – definir se “sim” ou “não”;

* **Atribuição**

  * **Tipo Destinatário** – selecionar se será para grupo ou usuário específico;  

  * **Tipo Atribuição** – definir se a atribuição será de execução ou de acompanhamento;

  * **Grupo** – selecionar o grupo/usuário;

  * **Ou Expressão** – buscar por expressão já cadastrada previamente;

* **Ações do usuário**

  * **Selecione a ação do cadastro** – buscar por ação já cadastrada previamente;

  * **Botão de limpar** – permite apagar o que foi escrito;

  * **Botão de construção** – permite construir uma nova ação ou expressão;

* **Ações de entrada**

  * **Construir expressão** – definir uma expressão diretamente;

  * **Selecionar a ação do cadastro** – buscar por ação já cadastrada previamente;

* **Ações de saída**

  * **Construir expressão** – definir uma expressão diretamente;

  * **Selecionar a ação do cadastro** – buscar por ação já cadastrada previamente;

* **Interface**

  *  **Tipo de interação**:

    * **Definido no portfólio** - é possível que um template de ticket (questionário ou formulário) apareça pontualmente em um estado do fluxo, utilizando o que foi configurado no atributo de serviço “Atividade” (requisição/incidente) - campos: “Template CRIAÇÃO” e “Template acompanhamento”.

    * **Formulário padrão** – do sistema;

    * **Formulário Neuro** - possui um identificador para chamar o fluxo disparado por este formulário;

* **Base de conhecimento**

  * **Vincular base de conhecimento** – permite vincular uma base já existente;

6. Para realizar uma conexão com outro elemento do fluxo, clique uma vez no item que deseja conectar, aparecerá quatro pontos quadrados na cor laranja em volta do item, selecione a direção que deseja e araste o ponto laranja para o item que deseja que seja realizado a conexão;

7. Para utilizar a conexão da melhor forma é necessário configurá-la, para isso utilize o símbolo “+” que se encontra na cor laranja em cima da linha de conexão e com um duplo clique abra as seguintes propriedades:

* **Nome** – para identificação na linha de conexão;

* **Condição** – utiliza uma função que dá a devida condição para a linha;

* **Ação** – utiliza uma ação específica para a finalidade da linha;

* **Estado** – é uma expressão que gera um status para a atividade;


## E agora, o que devo fazer?

Agora é necessário definir se será necessário o uso dos Gateways para a construção do seu fluxo, para saber melhor como utiliza-los acesse o documento – [Controlar sequência com Gateway]()
