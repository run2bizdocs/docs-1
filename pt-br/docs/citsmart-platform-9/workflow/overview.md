Title: Introdução ao Workflow do CITSmart
Description: Visão geral de como criar e gerenciar um fluxo de trabalho no citsmart.

# Introdução ao Workflow do CITSmart

Fluxos são representações visuais de algo que se move continuamente. Assim, fluxos podem ser usados para representar graficamente um processo ou qualquer ação. Eles podem ser materializados em um papel (documento físico) ou em uma ferramenta eletrônica. No CITSmart, a funcionalidade de Workflow tem a finalidade de modelar seus objetivos de negócio, descrevendo os passos que precisam ser executados para atingir esses objetivos através de um fluxo digital inteligente. É possível criar fluxos de trabalho para auxiliar na gestão de serviços, problemas, mudanças, liberações, ações de continuidade, requisições de viagens e compras. Sendo assim, o fluxo de trabalho possui interação com os principais processos do CITSmart.

Os fluxos de trabalho automatizados dão vida às atividades do sistema, proporcionando que as atividades da sua organização sejam digitalizadas e automatizadas. Assim, você pode criar fluxos com controle de tarefas, adicionar notificações, subprocessos e estabelecer comunicação direta com outras aplicações, como é o caso do Neuro – que é um framework para a geração de aplicações.

Você vai perceber que tarefas do dia a dia, como realizar um pedido, registrar um ticket, aprovar uma solicitação podem ser feitas de forma rápida e inteligente, evitando o desperdício de tempo. Os fluxos do CITSmart te ajudam a materializar seus processos de negócio em uma visão sistêmica em que você tem total controle do que acontece.


## Conhecer a funcionalidade de fluxo

Antes de qualquer coisa você precisa se familiarizar com os conceitos básicos, regras de negócio e interface de utilização. A visualização da funcionalidade do menu do CITSmart depende de permissões atribuídas a um perfil de acesso, verifique se você tem essa permissão. Caso não tenha esse acesso liberado um administrador pode conceder esse acesso.

Para saber se seu perfil tem essa permissão, acesso o menu lateral superior à esquerda da tela, e verifique se a primeira opção de acesso é o Menu principal **Workflow**;


![workflow menu CITSmart][1]

**Padrão do sistema**

1: Criar um Fluxo de Trabalho;

2: Construir Expressões;

3: Modelagem de processos;

**Integração Neuro**

4: Fluxo de Integração;

5: Regras de negócio;

6: Processo de Negócio;

!!! note "NOTAS"
   Estes itens só estarão disponíveis quando a aplicação Neuro estiver habilitada em sua instância;

Caso já tenha esse acesso, basta clicar e seleciona a opção de **Desenho de fluxo** para que seja possível visualizar a tela de gerenciamento.

## Tela de Gerenciamento de Fluxo

Na tela de gerenciamento de fluxo você poderá: Criar um novo Fluxo, Editar, exportar e excluir

![workflow management CITSmart][2]

1: **Novo** - clicar para iniciar um novo projeto de fluxo;

2: **Campo de busca** - buscar um fluxo pelo nome ou parte dele;

3: **Editar** - clicar para editar um fluxo já existente, sendo possível escolher qual versão será editada;

4: **Exportar** - gera um documento exportável no formato JSON;

5: **Excluir** - clicar para remover um fluxo;

## Criar e Editar um Fluxo

Ao clicar no botão **”Novo”** ou **“Editar”** você é direcionado para a interface de criação/edição do Fluxo de trabalho que é composta por duas abas, a aba de **Dados de Fluxo** onde informará dados da identificação e a aba **Diagrama** onde é possível desenhar o fluxo.

Em um novo fluxo você encontra quatro botões com funções de **importar**, **gravar**, **limpar** e **voltar**, você poderá importar um fluxo (exportando anteriormente no formato JSON).

![fist button CITSmart][3]

Caso se trate da edição de um fluxo já existente os botões são modificados, acrescentando a opção de **Gerar Documentação** e trocando **Importar** por **Gravar**.

![second button CITSmart][4]

### Aba Dados do Fluxo  

Dados do Fluxo é uma aba para identificação do fluxo, onde é possível estruturar nomes para melhor experiência:

![flow data CITSmart][5]

1: **Nome** – Atribuir um nome para identificação do fluxo, para poder identificá-lo em caso de vinculação ou atribuição;

2: **Processo** – Atribuir ao fluxo um processo dentre todos que se encontram no CITSmart, para que seja melhor definido e identificado;

3: **Versão** – Visualizador da versão em que o fluxo aberto no momento se encontra;

4: **Descrição** – Atribuir uma descrição a respeito do fluxo para fácil entendimento;

5: **Permitir reabertura** – Opção para permitir que as atividades que estão vinculadas a esse fluxo tenham a possibilidade de serem reabertas independentemente das configurações de grupo;

6: **Criar/atualizar dados dos objetos de negócio na criação do ticket** – Opção que permite que seja criado ou atualizado os dados de objetos de negócio configurados na nossa linguagem Neuro no momento de criação de um ticket;

7: **Atualizar dados dos objetos de negócio após execução das tarefas de usuário** – Opção que permite atualizar os objetos de negócio criado durante a execução das tarefas de usuário.

### Aba Diagrama  

Na aba **diagrama** encontramos diversos Elementos para a construção do fluxo agrupados em **Eventos**, **Atividades**, **Extensões**, **Gateways**, **Swimlanes** e **Artefatos**, são diversos componentes para uma melhor construção e interação de fluxo de trabalho. Abaixo temos um exemplo de um fluxo sendo criado.

![diagram CITSmart][6]

1: **Elementos** – São conjuntos de itens/ferramentas para serem usadas no desenho do fluxo como explicado nos no item Conceitos Básicos;

2: **Área de Desenho** – local para desenho e construção do fluxo de trabalho;

### Aba Documentação

Na aba Documentação você poderá gerar um documento com todas as informações do fluxo desenhado - a descrição dos elementos utilizados no fluxo de trabalho e os documentos vinculados ao fluxo - sendo possível exportá-lo para PDF.  

## E agora, o que devo fazer?

Agora você pode criar um fluxo de trabalho, pense em uma necessidade de negócio e nos atores envolvidos. Vejo nossa documentação, ela vai te ajudar nessa jornada.

## Relacionado
[Conceitos básicos](https://docs.citsmart.com/pt-br/citsmart-platform-9/workflow/basic-concepts.html)

[1]:images/workflow-menu-citsmart.png
[2]:images/workflow-management-citsmart.png
[3]:images/fist-button-citsmart.jpg
[4]:images/second-button-citsmart.png
[5]:images/flow-data-citsmart.png
[6]:images/diagram-citsmart.png
