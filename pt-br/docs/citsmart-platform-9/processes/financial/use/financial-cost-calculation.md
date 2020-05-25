Title: Cálculo de custos financeiros
Description:

# Cálculo de Custos Financeiros

## Antes de Começar

É necessário ter definido a permissão de acesso às funcionalidades do Gerenciamento Financeiro e ter permissão de uso da funcionalidade.

É necessário ter feito as entradas financeiras, criado os ciclos e classificações financeiras.  

Baseado nas entradas financeiras [Cadastrar item financeiro](https://docs.citsmart.com/pt-br/citsmart-platform-9/processes/financial/use/register-financial-item.html) e nas guias "distribuição de custos" e "definir preço" é possível monitorar todos os detalhes de custo (compra de hardware, manutenção de hardware, compra de software, licenças de software, instalação, incluindo serviços públicos, pessoal etc.) de acordo com a entrada financeira.  
Esse monitoramento dos detalhes de custo também pode ser feito através de relatórios.

## Procedimento

1 - Acessar o menu principal Processos > Gerência Financeira > Cálculo de Custos Financeiros

2 - Na tela principal do Cálculo de Custos Financeiros, temos as seguintes ações disponíveis:

|Ação|Descrição|
|------|-----------|
|Novo|Para criar um novo cálculo de custo financeiro|
|Gerar relatório CSV|Para gerar um relatório CSV|
|Filtros avançados|Para definir os filtros para encontrar um cálculo de custo já criado|
|Editar|Depois de selecionado um cálculo de custo já criado, essa opção aparecerá para editá-lo|
|Excluir|Depois de selecionado um cálculo de custo já criado, esta opção aparecerá para removê-lo|

## Cadastrar/Editar Cálculo de Custo

1 - Para criar um cálculo de custo, clique em "Novo";

2 - Para editar um cálculo de custo já criado, procure-o, clique nele e depois em "Editar";

3 - Selecione o período que você deseja, por exemplo, 12 meses (janeiro a dezembro);

4 - Selecione o serviço que você deseja fazer o cálculo financeiro;

5 - Informe a taxa mínima.

!!! abstract "Info"

    Em uma simulação, marque a caixa de seleção "Previsão".

|Campo|Descrição|
|-----|-----------|
|Data inicial(\*)|A data de iníco para o cálculo de custos|
|Data final(\*)|A data de finalização do cálculo de custos|
|Serviço(\*)|Selecionar o serviço que você deseja fazer o planejamento de custo|
|Taxa mínima(\*)|Configurar o valor da taxa mínima|
|Previsão(\*)|Selecionar a previsão de custo|

(\*) Indicar os campos obrigatórios

!!! abstract "NOTA"

    Selecione a data de início e de término para fazer o plano de 12 meses.
    
4 - Após preencher os campos, clique em "Gerar" para apresentar os valores. Gerará três guias para informações de valores:

### Cálculo de NPV e IRR

Com base nas informações adicionadas na funcionalidade "Item financeiro", a ferramenta apresentará os valores de acordo com as informações e cálculos apresentados nos campos:

|Campo|Descrição|
|-----|-----------|
|Mês|O mês de referência para apresentar os custos|
|Investmento|O valor de investimento|
|Receita|O valor da receita|
|Custo/Despesa|O valor de custo/despesa|
|Resultado|O valor do resultado|
|Valor presente|O valor presente|
|Valor atual líquido|O valor atual líquido|
|Taxa interna de retorno|O valor da taxa interna de retorno|

### Custo por Categoria

Essa guia apresenta a apropriação de custos por categorias. As categorias são: Investimentos e Distribuição de custos.

**Investmentos**

|Campo|Descrição|
|-----|-----------|
|Categoria|A categoria de investimento|
|Variaçao de cenário|A porcentagem de variação de cenário|
|Custo|O valor de custo fixo|
|%|A porcentagem atingida|
|Total|O valor final de investimento|

!!! tip

    Variação de cenário: esse campo permite realizar as variações financeiras

**Distribuição de custos**

Os custos calculados serão apropriados nos respectivos serviços e itens de configuração de acordo com o rateio ou valores fixos definidos nas entradas financeiras no [Cadastro de Item Financeiro](https://docs.citsmart.com/pt-br/citsmart-platform-9/processes/financial/use/register-financial-item.html) e será automaticamente associado ao serviço e ao IC.

!!! tip "Exemplo"

    Custo de rollup de um serviço voltado para o cliente (por exemplo, email) com a discriminação dos custos dos sistemas (por exemplo, MS Exchange, Lotus Notes) e a infraestrutura de TI de suporte associada (por exemplo, servidores, bancos de dados, rede, armazenamento) e aplicativos. 

|Campo|Descrição|
|-----|-----------|
|Categoria|A categoria do custo de distribuição|
|Variação de cenário|A porcentagem de variação de cenário|
|Custo|O valor de custo fixo|
|Rateio dos custos|O valor de rateio dos custos|

!!! tip

    Variação de cenário: esse campo permite realizar as variações financeiras

At the end of the page, we'll have the information about: **Number of months, Investment apportionment per month, Average cost per month and Total cost per month**

### Definir Preços

Preencha os campos disponíveis para definir os preços. No campo "Qual a forma precificar", selecione como fazer o preço, as opções disponíveis são: Valor fixo, Valor variável ou Ambos.

Se selecionar a opção **Valor Fixo**, preencha os campos:

Com base no serviço selecionado na guia anterior "Custo por categoria", os custos do serviço selecionado serão exibidos e o preço final do serviço (Preço final) utilizado será calculado nos campos "custo" e "lucro".

Os valores calculados podem ser atualizados e publicados no catálogo de serviços e no contrato de nível de serviço (ouro, prata e bronze).

|Campo|Descrição|
|-----|-----------|
|% de margem|Definir a margem de lucro|
|Custo|Definir o custo fixo|
|Preço final|O preço final do valor fixo|

Se selecionar a opção **Valor variável**, preencha os campos:

Com base no serviço selecionado na guia anterior "Custo por categoria", os custos do serviço selecionado serão exibidos e o preço do serviço será calculado usando os campos "quantidade prevista", "valor unitário mensal" e "margem de lucro".  
Os campos "quantidade prevista" e "valor unitário mensal" estão relacionados às métricas de demanda e serão calculados através do "fluxo de integração da captura de quantidade" para gerar o preço variado, respeitando as regras de negócios e a margem de lucro.

Os valores calculados podem ser atualizados e publicados no catálogo de serviços e no contrato de nível de serviço (ouro, prata e bronze).

|Campo|Descrição|
|-----|-----------|
|Qual é a unidade de medida|Definir a unidade de medida|
|Quantidade prevista|Definir a quantidade|
|Aceita quantidade abaixo do previsto?|Selecionar se aceita ou não|
|Valor unitário mensal|Uma vez preenchidos todos os valores nos campos anteriores, será exibido o valor unitário mensal, com as informações de:% Margem de lucro, Custo e Preço unitário final|
|Como calcular a quantidade mensalmente|Selecione como o cálculo será feito: informado manualmente ou calculado automaticamente|
|Fluxo de integração de captura de quantidade|Integração com sistemas internos e externos para capturar a quantidade de (acesso, serviços, horário de trabalho) realizada|

!!! tip

    No "Como calcular a quantidade mensalmente", se for selecionado "manualmente", os valores deverão ser informados manualmente; se selecionado "automaticamente", o fluxo de trabalho de integração deve ser selecionado para a contabilização dos serviços executados.  
    Para o campo "Qual a forma de precificar", na opção **Ambos** (custos fixos e variáveis), é possível definir um custo fixo para alguns casos e, se o número não for alcançado, é possível usar custos variáveis.
