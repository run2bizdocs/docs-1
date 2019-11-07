Title: conceitos basicos
Description: Workflow do CITSmart

# Conceitos Básicos
Os Fluxos do CITSmart podem ser desenhados utilizando uma vasta quantidade de elementos que estão disponíveis, abaixo está descrito os elementos bem como as suas características e propriedades.

## Elementos do Fluxo
Elementos é a nomenclatura utilizada para a agrupar os componentes que você pode utilizar na criação de um fluxo, eles são distribuídos de seguinte forma: **Eventos**, **Atividades**, **Extensões**, **Gateways**, **Swimlanes**, **Artefatos** e **Componentes Dinâmicos**.

Para entender melhor o que se encontra em cada grupo de Elementos e cada funcionalidade dos componentes verifique os itens abaixo.

### Eventos
Eventos são componentes utilizados para representar acontecimentos em um fluxo, podem representar a espera de que um fato aconteça para iniciar ou prosseguir a execução de uma atividade ou pode representar o início ou o término de um fluxo.

|Icone|Descrição|
------|-----|
|![ Start event CITSmart][1]|•	**Evento de Início** – elemento que dá início ao fluxo;|
|![ send event CITSmart][2]|•	**Evento Intermediário de Envio** – permite enviar o controle de uma atividade do usuário para outra atividade;|
|![ catch event CITSmart][3]|•	**Evento Intermediário de Captura** – permite receber o controle que foi enviado;|
|![ time event CITSmart][4]|•	**Evento Intermediário do Temporizador** - são eventos acionados por tempo definido e relacionados a uma Expressão Cron, pode ser utilizado como evento inicial ou intermediário. Um uso frequente para este evento está nos serviços Batch;|
|![ end event CITSmart][5]|•	**Evento de Fim** – elemento que identifica o fim do fluxo.|


### Atividades
Os componentes de atividades são representação do que será feito no fluxo.

|Icone|Descrição|
|------|-----|
|![ user task CITSmart][6]|•	**UTarefa de Usuário** - é usada para modelar o trabalho que precisa ser feito por uma ação humana;
|![ mensage CITSmart][7]|•	**Envio de Mensagem** – E-mail - é usada para "enviar" e-mails automaticamente para um ou mais usuários ou grupo (s) atribuídos a esta tarefa.|
|![ service task CITSmart][8]|•	**Tarefa de Serviço** – ESI - é uma solução "Bus Service" que permite criar fluxos de integração e interfaces entre soluções, bancos de dados, arquivos e / ou serviços existentes em um ambiente de computação|
|![ subprocess CITSmart][9]|•	**Subprocessos** - Permite a criação de solicitações ou incidentes ITSM, relacionados ou não à solicitação do workflow que está sendo executado.|

### Extensões
Os componentes de extensão integram o fluxo e com o usuário de forma prática e direta.

|Icone|Descrição|
|------|-----|
|![ REST CITSmart][10]|•	**Comunicação REST** - é uma conexão com serviços da Web acessando e passando parâmetros com o métodos GET ou POST.|
|![ notification CITSmart][11]|•	**Notificação** - usada para enviar notificação durante o processo de um ou mais usuários ou grupo atribuídos a ela.|

### Gateways
Os Gateways são componentes responsáveis por controlar iterações do fluxo, criando caminhos no mapeamento do processo em uma mesma sequência de atividades, um gateway é conectado ao fluxo através de fluxo de sequência.
São representados visualmente por um losango. O símbolo interno do losango identifica a interpretação da lógica do componente.

|Icone|Descrição|
|------|-----|
|![ Inclusivo CITSmart][12]|•	**Gateway Inclusivo** - divide o fluxo do processo em um ou mais fluxos. Ao dividir, um ou mais ramos são ativados. Todas as ramificações de entrada ativas devem ser concluídas antes da mesclagem|
|![ paralelo CITSmart][13]|•	**Gateway Paralelo** - Símbolo paralelo - Difere de outros gateways porque não depende de condições ou eventos. Em vez disso, os gateways paralelos são usados para representar duas tarefas simultâneas em um fluxo de negócios.|
|![ exclusivos CITSmart][14]|•	**Gateway Exclusivo** - baseado na condição, divide o fluxo em um ou mais caminhos mutuamente exclusivos. Ao dividir, ele roteia o fluxo de sequência para exatamente um dos ramos de saída. Ao mesclar, ele aguarda que uma ramificação de entrada seja concluída antes de acionar o fluxo de saída.|

### Swimlanes
|Icone|Descrição|
|------|-----|
|![Pool CITSmart][15]|•	**Pool/Participante** - Uma Pool é a representação gráfica de um contexto de workflow. Também age como uma “lane”. É um recipiente gráfico para particionar um conjunto de Atividades.|
|![ lane CITSmart][16]|• **Lane** - Uma Lane é uma subpartição dentro de um processo, às vezes dentro de um pool, e vai estender todo o comprimento do processo. As lanes são usadas para organizar e categorizar as Atividades.|

### Artefatos

|Icone|Descrição|
|------|-----|
|![ notes CITSmart][17]|•	**Notas de Texto** - Representar uma informação relevante ao modelo ou a elementos individuais dentro do processo.|

### Componentes dinâmicos


[1]:images/1.png
[2]:images/2.png
[3]:images/3.png
[4]:images/4.png
[5]:images/5.png
[6]:images/6.png
[7]:images/7.png
[8]:images/8.png
[9]:images/9.png
[10]:images/10.png
[11]:images/11.png
[12]:images/12.png
[13]:images/13.png
[14]:images/14.png
[15]:images/15.png
[16]:images/16.png
[17]:images/17.png
