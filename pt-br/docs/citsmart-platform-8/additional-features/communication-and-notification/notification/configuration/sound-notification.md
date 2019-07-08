Title: Configurar notificação sonora
Description: Configuração de um alarme sonoro para sinalizar ao atendente a chegada de um novo ticket

# Configurar notificação sonora

Este recurso permitir a configuração de um alarme sonoro para sinalizar ao atendente a chegada de um novo ticket em sua fila de trabalho.

## Antes de começar

* [x] Ter pelo menos um fluxo de trabalho definido em seu ambiente CITSmart;
* [x] É essencial possuir as condições mínimas para reprodução de áudio em seu computador;

## Procedimento

### 1. Criar um template de notificação

1. Acessar a funcionalidade através da navegação no menu principal Sistema > Notificações > Template de Notificação;
2. Clicar em "Novo" para criar um template;
3. Informar os dados da notificação, clicar em "Notificação Sonora" e importar o arquivo de audio;
4. Gravar as informações.

### 2. Inserir o elemento "Notificação" no fluxo

1. Acessar o menu principal Workflow > Desenho de Fluxo;
2. Selecionar e editar o fluxo desejado;
3. Na aba "Diagrama", clicar no item "Extensões", clicar e segurar o item "Notificação" e arrastar para a área de Desenho;
4. Clicar duas vezes sobre o ícone "Notificação", e logo após na aba "Configuração";
5. No campo "Template de notificação" selecionar o template para a notificação;
6. Gravar as alterações no fluxo;

### O que fazer depois

Pronto, a partir de agora quando você estiver na interface de ticket será possível identificar atendimentos pela notificação sonora.

!!! warning "ATENÇÃO"

    Mesmo se o usuário receber várias notificações ao mesmo tempo, o alarme sonoro só será acionado uma vez.

### Relacionado

[Cadastrar template de notificação][1]

[Criar um fluxo de trabalho][2]


[1]:/pt-br/citsmart-platform-8/additional-features/communication-and-notification/notification/configuration/template-create.html

[2]:/pt-br/citsmart-platform-8/workflow/use/create-flow.html
