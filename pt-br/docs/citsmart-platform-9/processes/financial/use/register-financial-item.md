title: Cadastrar Item Financeiro 
Description: Tem o objetivo de manter o item financeiro.

# Cadastrar Item Financeiro

Essa funcionalidade visa manter o item financeiro.

!!! faq "Você sabia?"

    Nos relatórios de BI, você pode acessar informações sintéticas e analíticas sobre:  
    Orçamento, Despesas, Valor Esperado, Valor Final, Valor de Custo, Valor Principal, ROI, Custo por Serviços, CAPEX, OPEX.  
    Também dados de BI sobre rateio por serviços, rateio por unidades de negócios, rateio por centros de resultados, rateio por contas contábeis, rateio por projetos e atividades contábeis.  
    
!!! note "Atenção para as entradas financeiras"

    Os lançamentos financeiros devem ser feitos respeitando o tipo, classificação, datas, categoria e eventuais repartições ou indicadores, pois esses dados serão processados para o cálculo de criação de custo, receita, preço final, variáveis, lucro e outros. Para saber mais, acesse o documento [Cálculo de Custos Financeiros](https://docs.citsmart.com/pt-br/citsmart-platform-9/processes/financial/use/financial-cost-calculation.html).
    
!!! note "Templates de custos baseados em SLA ou catálogo de serviço" 

    Os valores podem ser atribuídos diretamente a contratos de nível de serviço ou catálogo de nível de serviço de acordo com a regra de negócios que será usada. Para saber mais, acesse o documento [Criar tempo de atendimento](https://docs.citsmart.com/pt-br/citsmart-platform-9/processes/service-level/use/create-time-attendance.html). 

## Antes de começar

- [x] É necessário ter definido a permissão de acesso às funcionalidades do Gerenciamento Financeiro e criado o fluxo de trabalho de classificação, contrato, ciclo, subciclo e aprovação.


## Procedimento
    
1. Acessar o menu principal Processos > Gerência Financeira > Item Financeiro;
    
2. Clicar em "Novo" e preencher os campos disponíveis.
    
## Criar Item Financeiro.

Complete the fields available on the **Information** tab:

|Campo|Descrição|
|---|---|
|Tipo*|Orçamento, Custo/Despesa, Receita|
|Classificação* |(Capex, Direto, Fixo, Custo Unitário, Opex, Indireto, Variável, Rateio)|
|Data de vencimento*|A data que expirará|
|Data de referência*|A data de referência|
|Previsão|Está disponível apenas para a categoria Receita e Custos/Despesas (usada para simular previsões financeiras)|
|Categoria*|A categoria da que está sendo criada|
|Contrato|Selecionar um contrato para ser vinculado|
|Conta de orçamento|Uma conta específica para ser vinculada a esse item|
|Item financeiro de previsão|É possível procurar um título do item financeiro previsto| 
|Ciclo*|É o método financeiro, por exemplo, Anual, Mensal ou Trimestral|
|Subcicle*|Depende do ciclo|
|Código|Texto livre para criar ou inserir código financeiro|
|Título*|Título desse Item Financeiro|
|Status*|Sempre será criado como "Pendente"|

(\*) Indicar campos obrigatórios
    
### Valores e Rateios

Nesta guia, você registrará O valor de um item financeiro e também uma repartição por seus valores, detalhando o rateio por serviços, rateio por unidades de negócios, rateio por centros de resultados, rateio por contas contábeis, rateio por projetos e atividades contábeis.

|Campo|Descrição|
|---|---|
|Tipo de lançamento|Existem dois tipos: Valor - se você definir o valor, após o "Selecionar serviços", será apresentada uma lista com o serviço e seus valores; Contabilização de atividades prestadas - para esta opção, após Selecionar as atividades, será apresentada a lista da atividade que você selecionou, bem como suas informações e descrição|
|Valor previsto*|É possível estabelecer um número para o valor esperado|
|Valor principal*|Definir um valor para o valor principal|
|Adicionais*| Definir um número para os adicionais|
|Valor final*|Definir um número para o valor final|
|Rateios|Aqui, temos as opções para definir todos os tipos de rateio: rateio por serviços (ativos e ICs), rateio por unidade de negócios, rateio por centros de resultados, rateio por contas contábeis, rateio por projetos. Depois de selecionar o tipo, você adicionará o serviço, a unidade de negócios, o centro de resultados, a conta contábil e o projeto. Depois de adicioná-lo, aparecerá o valor e a porcentagem de cada um deles|

(\*) Indicar campos obrigatórios

### Conhecimento 

Selecione um documento financeiro já criado como um Conhecimento para vincular ao item financeiro, você pode.

| Objetos    | Descrição                         |
|------------|-----------------------------------|
| Adicionar conhecimento | Procurar/Vincular     |
| Grid               | Grid do conhecimento vicnulado
| Excluir     | Desvinular o conhecimento          |

### Aprovação

É possível criar aprovações e verificar as que foram criadas, aprovadas ou negadas. Na lista de aprovações, temos os seguintes campos:

|Campo    |Descrição                         |
|---------|----------------------------------|
|Ticket   |O número identifcando a aprovação |
|Data     |A data da aprovação               |
|Atividade|A atividade financeira            |
|Status   |O status da aprovação             |

### Histórico

Serão apresentadas todas as informações em uma grid sobre as mudanças/ações executadas e realizadas no item financeiro.
A grid informará Data e hora da ocorrência, o usuário, qual elemento está envolvido e os detalhes da ação.

## Ações

| Ação    | Descrição                                                   |
|---------|-------------------------------------------------------------|
| Salvar  | Criar/Mudar o item financeiro                               |
| Limpar  | Retornar os campos ao padrão                                |
|Pesquisar| Retornar para a lista anterior com os itens financeiros     |

## Relacionado

- [Cadastrar ciclo financeiro](/pt-br/citsmart-platform-9/processes/financial/use/register-financial-cycle.html)
