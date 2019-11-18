Title: Organizar Fluxo com Pool e Swimlanes
Description: Organizar Fluxo com Pool e Swimlanes

# Organizar Fluxo com Pool e Swimlanes

Ao construir um Fluxo no CITSmart é uma boa prática prezar pela organização. Neste sentido, o uso de Pools e Swimlanes ajudam muito no entendimento de um diagrama

**Pool** - Representa o contexto do fluxo de trabalho, pode atribuir um diagrama (como um todo) para um grupo ou pessoa.

**Swimlanes** - Agrupam tarefas por executante. São utilizadas para aplicar uma atribuição global – para usuários/grupos interessados. A atribuição é aplicável à Tarefas de Usuário e Notificações (e-mail/sistema).

## Antes de Começar

Defina os atores do fluxo e tarefas, também é recomendado que os dados solicitados na aba “**Dados do Fluxo**” estejam preenchidos.

## Procedimento

1. Editar um Fluxo;

2. Clicar na aba “Diagrama”;

3. Definir a Pool

  a. Para utilizar uma Pool basta clicar no ícone de “Pool” ou “Lane” (situado na barra de ferramentas), clicar, segurar e arrastá-la para a área de desenho (espaço quadriculado à direita) e clique duas vezes para configurá-la. Clique em “Adicionar” para atribuir o grupo ou o usuário;

4. Definir Swimlanes para executantes do Fluxo

  - Para utilizar uma Swimlane basta segurar e arrastar para dentro da Pool já adicionada na área de desenho, não contendo limites de Swimlanes dentro de uma Pool;

As propriedades tanto de uma Pool quanto de uma Swimlane são compostas por:

* **Identificação**

  * **Nome** – para identificação da Pool;

  * **Descrição** – para descrição;

* **Atribuição**

  * **Tipo Destinatário** – selecionar se será para grupo ou usuário específico;

  * **Tipo Atribuição** – definir se a atribuição será de execução ou de acompanhamento;

  * **Grupo** – Inserir o grupo/usuário;

  * **Ou Expressão** – buscar por expressão já cadastrada previamente;

!!! Regra
Ao realizar uma atribuição em um Pool de recursos, automaticamente os elementos herdarão as configurações. A hierarquia de atribuições é definida da seguinte forma:

1. Pool;

2. Swimlanes;

3. Tarefa de usuário e Notificações (E-mail/Sistema);

Qualquer atribuição realizada localmente, fará com que a atribuição hierárquica seja “Ignorada”.

## O que fazer a seguir

Configure as atividades de usuário que deseja utilizar e adicione outros elementos em seu fluxo.

## Relacionado

[Configurar Tarefa de Usuário](https://docs.citsmart.com/pt-br/citsmart-platform-8/workflow/use/user-task-configure.html)
