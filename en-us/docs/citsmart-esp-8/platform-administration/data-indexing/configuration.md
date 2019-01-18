Title: Configure Indexing Service

# Configure Indexing Service

O CITSmart ESP utiliza o Apache SOLR para fazer indexação de informação na funcionalidade de pesquisa do Knowledge Portal.


## O que fazer antes

Instalar o componente SOLR, conforme consta no [manual de instalação][1].

## Procedure

1. Acessar o menu principal Parametrization > CITSmart Parameters > 304;
2. Informar os dados do servidor SOLR;
    ```sh
    http://localhost:8983/solr/collection_name
    ```
3. Salvar;

## Related

[Indexing Knowledge Base][2]

[1]:/en-us/citsmart-esp-8/get-started/installation-and-upgrade/1.overview.html
[2]:/en-us/citsmart-esp-8/platform-administration/data-indexing/management.html