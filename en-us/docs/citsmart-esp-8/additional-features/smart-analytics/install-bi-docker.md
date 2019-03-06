title: Configure BI solution (Smart Analytics) via Docker
Description: This document is intended to configure the BI in the CITSmart instance.
#Configure BI solution (Smart Analytics) via Docker

CITSmart Analytics is a solution of Business Intelligence (BI) for analyzing the data
from CITSmart. The BI solution uses resources of the tools [Saiku
Analytics](https://www.meteorite.bi/products/saiku-reporting) and [Pentaho](https://www.hitachivantara.com/go/pentaho.html).

It's possible to have BI in your environment using the container structure of
Docker, following the installation configuration.

Before getting started
----------------

The user must have Docker previously installed. The system manager must have a 
Bitbucket account so that he/she can access the citbi repository.

Procedure
------------

*Installation*

1.  Clone the citbi repository:

    git clone https://diogojapiassu@bitbucket.org/diogojapiassu/citbi.git

1.  Enter the command and then unzip:

    
    cd /citbi/files/
    
    ```sh
    unzip storage.zip
    ```
    command to build image
    
    cd/citbi/
    
    ```
    docker build -t registry.citsmartcloud.com/templates/bi .
    ```
    
1.  In the folder /citbi/composes, configure the database:
    ```sh
    vi /citbi/composes/
    [docker-compose.yml](https://bitbucket.org/diogojapiassu/citbi/src/master/composes/docker-compose.yml)
    ```
    
    i (enter)

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
    
    Check:

    ```
    cat /citbi/composes/docker-compose.yml
    ```

1.  In the folder /citbi/composes:

Build and start container:

```
docker-compose up -d
```

Verify log of container:

```
docker logs -f citBI
```

*Configuration*

1.  Access the Saiku as a manager:

    <http://127.0.0.1:8282/>

1.  Add the Schema available on:

    <https://bitbucket.org/diogojapiassu/citbi/src/master/files/SchemaEnglish.xml>

1.  Add DataSource:

    jdbc:postgresql://127.0.0.1:5432/citsmart_equipeteste_equatorial

*Useful commands: box*

1.  Verify active containers:

    ```
    docker ps
    ```

1.  Verify inactive containers:
    
    ```
    docker ps -a
    ```

1.  Stop container:
    
    ```
    docker stop citBI
    ```

1.  Remove container:
    ```
    docker rm citBI
    ```

What to do next
------------------

1. To enjoy the benefits of BI in your CITSmart instance, it's necessary to
configure the parameters 401 and 412. To do so, access the main menu
Parametrization \> CITSmart Parameters;

2. Detais of the parameters:

    -   401: URL os Saiku server

    Example: http://127.0.0.1:8282

    -   412: Job to update the password Saiku

    Example:
    http://127.0.0.1:8282/kettle/executeJob/?job=/home/ec2-user/repo-cit/job_create_users_saiku.kjb&loginParam=loginCitSmart


Related
-----------

[Using Smart Analytcs (BI) to generate reports](/en-us/citsmart-esp-8/additional-features/smart-analytics/use-bi-solution.html)



!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/28/2019 – Anna Martins
