Title: Download e software

# Software e Donwload

!!! info "ATENÇÃO"

    A instalação do CITSmart Enterprise requer sistema operacional GNU/Linux com kernel igual ou superior ao 3.10.

    Recomendamos Red Hat, CentOS, Debian ou Ubuntu.


Para execução do CITSmart Enterprise, baixaremos os pacotes necessários conforme
o procedimento relativo ao produto.

### Servidor de Aplicação Wildfly

!!! info "ATENÇÃO"
    No manual utilizaremos PostgreSQL.

    Você pode baixar o pacote para Oracle ou MSSQL e fazer as alterações
    igualmente descritas para PostgreSQL.

1. O download do Java JDK8u172 diretamente do repositório oficial
jdk-8u172-linux-x64.tar.gz  
2. Download do pacote diretamente do repositório oficial através do link
abaixo:<http://download.jboss.org/wildfly/12.0.0.Final/wildfly-12.0.0.Final.tar.gz>

    
   ![Java Download](images/java-download.png)
    
   Figura 1 - Tabela Java
    
3. Download do módulo jbdc para o postgresql: <http://files.citsmart.com/postgresql-jdbc-driver.tar.gz>

### Servidor de Banco de Dados MongoDB

!!! info "ATENÇÃO"
       
       No manual utilizaremos a distribuição GNU/Linux CentOS Linux release
      7.5.1804.
      Baixe e MongoDB conforme sua distribuição.
      A versão do MongoDB deve ser 3.4.

Para localizar o download conforme sua
distribuição: <https://www.mongodb.com/download-center#community>

Para o download do MongoDB para CentOS 7.5:
https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.4.15.tgz

### Servidor de Banco de Dados PostgreSQL/Oracle/MSSQL


!!! Abstract "ATENÇÃO"

    No manual utilizaremos PostgreSQL com download do repositório oficial.

   Recomenda-se que instalações de Oracle ou MSSQL sejam efetuados conforme
   informações e melhores práticas de cada fabricante:O CITSmart Enterprise é
   compatível com o PostgreSQL 9.2 ou superior e o download será feito no
   momento da configuração dos pacotes.

   *Oracle:* <https://docs.oracle.com/cd/E11882_01/server.112/e10897/toc.htm>

   *MSSQL:* <https://docs.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server>.

Servidor de Indexação Apache Solr
-------------------------------------


!!! info "ATENÇÃO"

    A versão homologada do Apache Solr é a 6.4.2.

    Solr 6.4.2: <http://files.citsmart.com/solr-6.4.2.zip>    

    Configurações para base de conhecimento: <http://files.citsmart.com/base_conhecimento_configs.zip>

Download dos arquivos assets para o CITSmart
------------------------------------------------

<http://files.citsmart.com/assets.tar.gz>


Configuração dos Pacotes
------------------------


!!! info "ATENÇÃO"

    Utilizaremos o diretório /opt para instalação de todos os pacotes para o
    CITSmart Enterprise.

    O GNU/Linux com instalação mínima deve estar configurado nas 4 máquinas.

    Nesse exemplo utilizaremos CentOS Linux release 7.5.1804. Caso deseje utilizar
    outra distribuição altere os comandos conforme o gerenciamento de pacotes.

Com os downloads finalizados podemos dar início a instalação da solução CITSmart Enterprise.


### Servidor de Banco de Dados MongoDB
 
1. Após baixar o MongoDB da versão 3.4.15 para sua correta distribuição, deve-se
  efetuar a descompressão para o diretório /opt

    ``` sh
    tar xvzf mongodb-linux-x86_64-rhel70-3.4.15.tgz -C /opt/*
    ```
	
    ``` sh	
    mkdir -p /data/db
    ```

    ``` sh	
	cd /opt/mongodb-linux-x86_64-rhel70-3.4.15/bin/
    ```

    ``` sh	
	./mongod 
    ```
	
	<message of unrestricted access \>  
	
2. Devemos criar um diretório para a base e iniciar o MongoDB. Repare que ele irá subir com permissões irrestritas de acesso.

3. Com o MongoDB iniciado, abra outro terminal, acesse o diretório bin do MongoDB e crie a base citsmart definindo seu usuário e senha.

    ``` sh
    cd /opt/mongodb-linux-x86_64-ubuntu1604-3.4.5/bin/
    ```

    ``` sh
    ./mongo
    ```

    <message of unrestricted access>

    ```sh
    use admin
    db.createUser({
    user: "admin",
    pwd: "yourpassword",
    roles:[
    { role: "root", db: "admin" },
    { role: "dbOwner", db: "citsmart" }
    ]
    })
    ```  
	
4. O retorno *“Successfully added user”* deve ser observado.

5. Digite **exit** para sair do console do MongoDB.

6. Retorne ao terminal anterior e finalize o processo do mongodb com um CTRL+C.


### PostgreSQL Database Server


!!! Abstract "ATENÇÃO"

    To this knowledge we'll use the version 9.5 of the PostgreSQL.
    We can install PostgreSQL with the steps in this official manual: https://www.postgresql.org/download/linux/redhat/

1. After install the PostgreSQL we can create the database, user and password;

    ``` sh
    systemctl start postgresql
    ```

    ``` sh
    su – postgres
    ```

    ``` sh
    psql
    ```

    ```sh
    create user citsmartdbuser with password 'exemple123';
    ```

<message CREATE ROLE>

    ``` sh
    create database citsmart_db with owner citsmartdbuser encoding 'UTF8' tablespace pg_default;
    ```

<mensagem CREATE DATABASE>

    ``` sh
    alter role citsmartdbuser superuser;
    ```

<mensagem ALTER ROLE>

    ``` sh
    \q
    ```

    ``` sh
    exit
    ```

2. Observar o retorno dos comandos analisando a correta execução.

3. Agora iremos configurar o **/var/lib/pgsql/9.5/data/pg_hba.conf** para permitir
a conexão do Wildfly para a database e usuário do citsmart. No final do arquivo
altere as linhas:

    Padrão: host all all 127.0.0.1/32 md5   
    Alterado: host citsmart_db citsmartdbuser IP_Wildfly/32 md5* |

4. Hora de abrir o listening no arquivo **/var/lib/pgsql/9.5/data/postgresql.conf**

    Padrão está comentado: 

    ``` sh
    listen_addresses = 'localhost' 
	``` 
	Alterado: 

    ``` sh
    listen_addresses = ‘0.0.0.0'
    ```	


5. Após as configurações, de um restart no postgresql.

``` sh
systemctl restart postgresql-9.5.service
```



### Servidor de Indexação Apache Solr

1. Instalar os pacotes unzip e lsof.

2. Descomprimir o JAVA e Solr para /opt/

    ``` sh
    yum install unzip lsof
    ```
	
	```sh
    tar xzvf jdk-8u172-linux-x64.tar.gz -C /opt/
	```
	
	```sh
    ln -s /opt/jdk1.8.0_172 /opt/jdk
	```
	
	```sh
    unzip solr-6.4.2.zip -d /opt/
	```
	
	```sh
    ln -s /opt/solr-6.4.2 /opt/solr
    ```

    ``` sh
    vim /etc/profile
    ```
    export JAVA_HOME="/opt/jdk"
    export PATH="$JAVA_HOME/bin:$PATH"

    ``` sh
    :wq
    ```

    ``` sh
    source /etc/profile
    ```

3. Criar um usuário para execução do Solr com shell falso e com permissão no
diretório do Solr para ele e inicie.
    
    ``` sh
    groupadd -r solr
	```
	
	```sh
    useradd -r -g solr -d /opt/solr -s /sbin/nologin solr
	```
	
	```sh
    chown -R solr:solr /opt/solr-6.4.2/
	```
	
	```sh
    su - solr -s /bin/bash
	```
	
	```sh
    bin/solr start
    ```    

4. Descomprimir o arquivo para configurações da base de conhecimento e execute a
criação da collection.

    ``` sh
    unzip -x base_conhecimento_configs.zip -d /opt/solr-6.4.2/
    ```
	
    ```sh
    su - solr -s /bin/bash
    ```

    ``` sh
    bin/solr create -c base_conhecimento -d base_conhecimento_configs -s 2 -rf 2
    ```
  

5. Observar que o retorno do comando deve ser algo como no exemplo abaixo.

Copying configuration to new core instance directory:

```sh
/opt/solr/server/solr/base_conhecimento
```
 	 
Creating new core 'base_conhecimento' using command:

```sh
http://localhost:8983/solr/admin/cores?action=CREATE&name=base_conhecimento&instanceDir=base_conhecimento
```
```java
{
"responseHeader":{
"status":0,
"QTime":3223},
"core":"base_conhecimento"}

```


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/17/2019 – Anna Martins
