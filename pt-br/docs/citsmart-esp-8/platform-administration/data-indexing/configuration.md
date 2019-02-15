Title: Configurar Serviço de Indexação

# Configurar Serviço de Indexação

O CITSmart ESP usa SOLR para indexar a informação na funcionalidade busca do Portal de Conhecimento.


## O que fazer antes

Instalar o componente SOLR, como apresentado no [manual de instalação][1].

## Procedimento

1. Acessar o menu principal Parametrização > Parâmetros CITSmart > 304;
2. Informar os dados do servidor SOLR;
    ```sh
    http://localhost:8983/solr/collection_name
    ```
3. Salvar.

## Relacionado

[Indexar Base de Conhecimento][2]

[1]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/download-software.html#servidor-de-indexacao-apache-solr_1
[2]:/pt-br/citsmart-esp-8/platform-administration/data-indexing/management.html


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/22/2019 - João Pelles  
