title: Configurar solução BI (Smart Analytics) via Docker
Description: Este documento tem por objetivo configurar o BI na instância CITSmart.
#Configurar solução BI (Smart Analytics) via Docker

O CITSmart Analytics é a solução de Business Inteligence (BI) para a análise de
dados do CITSmart. A solução de BI utiliza recursos das ferramentas Saiku
Analytics[1] e Pentaho[2].

É possível ter o BI em seu ambiente utilizando a estrutura de containers do
Docker, devendo seguir a seguinte configuração de instalação.

Antes de começar
----------------

O usuário deverá ter o Docker previamente instalado. O administrador do sistema
deverá ter uma conta no Bitbucket para que ele possa ter acesso ao repositório
do citbi.

Procedimento
------------

*Instalação*

1.  Clonar repositório do citbi:

git clone https://bitbucket.org/diogojapiassu/citbi/src/master/

1.  Digitar o comando e em seguida descompactar:

    ```sh
    cd /citbi/files/
    ```
    ```sh
    unzip storage.zip
    ```
    
1.  Na pasta /citbi/composes, configurar o banco de dados:

vi /citbi/composes/
[docker-compose.yml](https://bitbucket.org/diogojapiassu/citbi/src/master/composes/docker-compose.yml)

\- \> i (inserir)

>   version: '2'

>   services:

>   citBI:

>   container_name: citBI

>   image: registry.citsmartcloud.com/templates/bi:latest

>   environment:

>   \- BI_HOST=127.0.0.1

>   \- BI_DATABASE= citsmart_equipeteste_equatorial

>   \- BI_PORT=5432

>   \- BI_USER=root

>   \- BI_PASSWORD=1

>   \- BI_LANGUAGE=pt-br

>   \- URL_SAIKU=http://localhost:8282

>   volumes:

>   \- /citbi/files/home:/home

>   ports:

>   \- 8282:8282

\-\>Ctrl+C

\-\>:wq!

Conferir:

cat /citbi/composes/docker-compose.yml

1.  Na pasta /citbi/composes:

Construir e iniciar o container:

docker-compose up -d

Verificar log do container:

docker logs -f citBI

*Configuração*

1.  Acessar o Saiku como administrador:

<http://127.0.0.1:8282/>

1.  Adicionar Schema disponível em:

<https://bitbucket.org/diogojapiassu/citbi/src/master/files/SchemaEnglish.xml>

1.  Adicionar DataSource:

*jdbc:postgresql://127.0.0.1:5432/citsmart_equipeteste_equatorial*

*Comandos úteis: caixa*

1.  Verificar containers ativos:

docker ps

1.  Verificar containers inativos:

docker ps -a

1.  Parar container:

docker stop citBI

1.  Remover container:

docker rm citBI

O que fazer depois
------------------

Para usufruir dos benefícios do BI em sua instância CITSmart é necessário
configurar os parâmetros 401 e 412. Para isso, acessar o menu principal
Parametrização \> Parâmetros CITSmart.

Detalhes dos parâmetros:

-   401: URL do servidor Saiku

Exemplo: http://127.0.0.1:8282

-   412: Job para atualização da senha Saiku

Exemplo:
http://127.0.0.1:8282/kettle/executeJob/?job=/home/ec2-user/repo-cit/job_create_users_saiku.kjb&loginParam=loginCitSmart

[1]:https://www.meteorite.bi/products/saiku-reporting

[2]:https://www.hitachivantara.com/go/pentaho.html

