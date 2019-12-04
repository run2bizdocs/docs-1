Title: Componente Lookup
Description: O componente lookup do Neuro permite a criação de interfaces mater-datails em listagens de itens.

# Componente Lookup

O componente Lookup é um recurso do Neuro que permite a criação de listas rápidas de opções sendo possível uma interface mestre-detalhes (master-detail interface), ou seja, exibição de uma lista mestre e os detalhes do item selecionado, como por exemplo, criar campos para que o usuário selecione um país, logo após selecione um estado do país, e depois uma cidade do estado.

Para usar este recurso em formulários você deve:

* [x] Criar os Lookup's

* [x] Configurar elementos Lookup no formulário

## O que fazer antes

Antes de criar componentes lookup's você deve criar uma aplicação e, opcionalmente, uma conexão de banco de dados Neuro.

## Criar componentes Lookup's

1. Acessar a funcionalidade pelo menu Neuro > Gerenciamento > Componente Lookup;
2. Casdastrar o(s) componente(s) lookup;
3. Inserir as informações:

    |Campo|Descrição|Exemplo|
    |-----|---------|-------|
    |Nome|Identificador que não permite espaço|pais|
    |Descriição|Informações do lookup|País|
    |Aplicação|Aplicação Neuro|My App|
    |Conexão de Banco|Conexão de banco de dados (a mesma utilizada em objetos de negócio)|Neuro DB Connection|
    |Coluna ou expressão para campo chave|ID para retorno da chave|idpais|
    |Coluna ou expressão para descrição|Retorno do campo descrição|nomepais|
    |FROM e WHERE|Query para FROM e Query|`FROM pais`|

4. Clicar em "Testar o componente", para ver o resultado;
5. Clicar em "Salvar" para registrar os dados.


## Desenho da tela (Formulário)

1. Selecionar um formulário;
2. Clicar em "Desenho da tela";
3. Arrastar o elemento "Lookup" para a área de desenho;
4. Alterar a largura do campo conforme a necessidade;
5. Informar o nome da Label;
6. No item "Lookup" selecionar o registro desejado;
7. Informar a propriedade "Model" (atributo do formulário que vai receber o valor do campo chave do lookup);
8. No campo "Cláusula WHERE adicional", inserir a sintax SQL quando desejar filtrar o resultado da lista.

## Exemplo de utilização

Vamos exemplificar a criação de uma interface master-detail para permitir que o usuário selecione um país, estado do país e cidade do estado selecionado.

- **Lookup 1: País**

Nome: pais

Descrição: País

Aplicação: My App

Conexão de Banco: Neuro DB Connection 

Coluna ou expressão para campo chave: idpais

Coluna ou expressão para descrição: nomepais

FROM e WHERE:

```mysql
FROM pais
```

- **Lookup 2: Estado**

Nome: uf

Descrição: UF

Aplicação: My App

Conexão de Banco: Neuro DB Connection 

Coluna ou expressão para campo chave: iduf

Coluna ou expressão para descrição: `nomeuf||'('||siglauf||')'`

``` mysql
FROM ufs
```

- **Lookup 3: Cidade**

Nome: uf

Descrição: UF

Aplicação: My App

Conexão de Banco: Neuro DB Connection

Coluna ou expressão para campo chave: idcidade

Coluna ou expressão para descrição: nomecidade

``` mysql
FROM cidades
```

- **No formulário**

Para usar o recurso de master details, ou seja, mostrar dados com base num item selecionado anteriomente, você pode usar a mesma sintax dos SQL de objeto de negócio (conforme exemplo abaixo);

Inserir a sintax SQL no campo "Cláusula WHERE adicional" do elemento Lookup;

``` mysql
iduf = ${nameModel.iduf:INTEGER}
```


Ou inserir dentro do próprio componente Lookup (campo FROM e WHERE);

``` mysql
FROM cidades
WHERE iduf = ${nameModel.iduf:INTEGER}
```
