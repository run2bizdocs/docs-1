title: Configurar solução BI (Smart Analytics) via Docker
Description: Este documento tem por objetivo configurar o BI na instância CITSmart.
# Configurar solução BI (Smart Analytics) via Docker

O CITSmart Analytics é a solução de Business Inteligence (BI) para a análise de
dados do CITSmart. A solução de BI utiliza recursos das ferramentas [Saiku
Analytics](https://www.meteorite.bi/products/saiku-reporting) e [Pentaho](https://www.hitachivantara.com/go/pentaho.html).

É possível ter o BI em seu ambiente utilizando a estrutura de containers do
Docker, devendo seguir a seguinte configuração de instalação.

Antes de começar
----------------

O usuário deverá ter o Docker previamente instalado.

Procedimento
------------

***Instalação***

1.  Fazer download do citBI em:
 
    ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/citBI/citbi-1.0.0/citbi-1.0.0.zip  e descompactá-lo

1.  Digitar o comando e em seguida descompactar:

    
    cd /citbi/files/
    
    ```sh
    unzip storage.zip
    ```
    comando para construir imagem
    
    cd/citbi/
    
    ```
    docker build -t registry.citsmartcloud.com/templates/bi .
    ```
    
1.  Na pasta /citbi/composes, configurar o banco de dados:
    ```sh
    vi /citbi/composes/
    [docker-compose.yml](/citbi/src/master/composes/docker-compose.yml)
    ```
    
    i (inserir)

    ```java
    version: '2'
    services:
      citBI:
        container_name: citBI
        image: registry.citsmartcloud.com/templates/bi:latest
        environment:
    - BI_HOST=127.0.0.1
    - BI_DATABASE= citsmart_equipeteste_equatorial
    - BI_PORT=5432
    - BI_USER=root
    - BI_PASSWORD=1
    - BI_LANGUAGE=pt-br
    - URL_SAIKU=http://localhost:8282
    volumes:
    - /citbi/files/home:/home
    ports:
    - 8282:8282
    - 8085:8085
    ```

    Ctrl+C

    :wq!
    
    Conferir:

    ```
    cat /citbi/composes/docker-compose.yml
    ```

1.  Na pasta /citbi/composes:

Construir e iniciar o container:

```
docker-compose up -d
```

Verificar log do container:

```
docker logs -f citBI
```

***Configuração***

1.  Acessar o Saiku como administrador:

    <http://127.0.0.1:8282/>

1.  Adicionar Schema disponível em:

    </citbi/src/master/files/SchemaEnglish.xml>

1.  Adicionar DataSource:

    jdbc:postgresql://127.0.0.1:5432/citsmart_equipeteste_equatorial

***Comandos úteis: caixa***

1.  Verificar containers ativos:

    ```
    docker ps
    ```

1.  Verificar containers inativos:
    
    ```
    docker ps -a
    ```

1.  Parar container:
    
    ```
    docker stop citBI
    ```

1.  Remover container:
    ```
    docker rm citBI
    ```

O que fazer depois
------------------

1. Para usufruir dos benefícios do BI em sua instância CITSmart é necessário 
configurar os parâmetros 401 e 412. Para isso, acessar o menu principal
Parametrização \> Parâmetros CITSmart;

2. Detalhes dos parâmetros:

    -   401: URL do servidor Saiku

    Exemplo: http://127.0.0.1:8282

    -   412: Job para atualização da senha Saiku

    Exemplo:
    http://127.0.0.1:8282/kettle/executeJob/?job=/home/ec2-user/repo-cit/job_create_users_saiku.kjb&loginParam=loginCitSmart


Relacionado
-----------

[Usar o Smart Analytics (BI) para gerar relatórios](/pt-br/citsmart-platform-8/additional-features/smart-analytics/use-bi-solution.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/28/2019 – Anna Martins
