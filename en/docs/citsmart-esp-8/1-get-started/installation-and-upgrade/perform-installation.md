Title: Perform installation

# Presentation


# Package Configuration

!!! warning
    We'll use the directory /opt to install all packages to CITSmart Enterprise.GNU/Linux with minimum installation should be configured in the 4 machines.
    In this example, we'll use CentOS Linux release 7.5.1804. If you want to use other distribution, change the commands as in the package management.

After all the necessary download, we can start the installation of the solution CITSmart Enterprise.

## MongoDB Database Server

1. After download the MongoDB version 3.4.15, for its correct distribution, it's necessary the decompression to the directory /opt;

``` sh
tar xvzf mongodb-linux-x86_64-rhel70-3.4.15.tgz -C /opt/
```

``` sh
mkdir -p /data /db
```

``` sh
cd /opt/mongodb-linux-x86_64-rhel70-3.4.15/bin/
```

``` sh
./mongod
```

<message of unrestricted access >

2. We should create a directory to the base and start the MongoDB. Note that it will upload with access unrestricted permission;
3. With MongoDB started, open another terminal, access the bin directory of MongoDB and create the CITSmart base, settingg its user ande password;
4. It will appear the message "Sucessfully added user";
5. Type exit to leave the MongoDB console;

``` sh
cd /opt/mongodb-linux-x86_64-ubuntu1604-3.4.5/bin/
```

``` sh
./mongo
```


< message of unrestricted access >
use admin
db.createUser({
user: "admin",
pwd: "yourpassword",
roles:[
{ role: "root", db: "admin" },
{ role: "dbOwner", db: "citsmart" }
]
})

6. Return to the previous terminal and finish the mongodb process with CTRL+C.

## PostgreSQL Database Server

!!! warning
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

2. Note the command return analyzing the correct execution;
3. Now we'll configure the /var/lib/pgsql/9.5/data/pg_hba.conf to allow the Wildfly connection to the database and user of citsmart. At the end of the file change the lines:

Default: host all all 127.0.0.1/32 md5
Changed: host citsmart_db citsmartdbuser IP_Wildfly/32 md5

4. Time to open the listening in the file /var/lib/pgsql/9.5/data/postgresql.conf;

Default is commented: #listen_addresses = 'localhost'
Changed: listen_addresses = ‘0.0.0.0'

5. After the configuration, restart in the postgresql;

``` sh
systemctl restart postgresql-9.5.service
```

## Apache Solr Indexing Server

1. Install the pacjages unzip and Isof;
2. Decompress the JAVA and Solr to the /opt;

``` sh
yum install unzip lsof
tar xzvf jdk-8u172-linux-x64.tar.gz -C /opt/
ln -s /opt/jdk1.8.0_172 /opt/jdk
unzip solr-6.4.2.zip -d /opt/
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

3. Create a user to execute the Solr with fake shell and permission in the directory Solr, then, start it;

``` sh
groupadd -r solr
useradd -r -g solr -d /opt/solr -s /sbin/nologin solr
chown -R solr:solr /opt/solr-6.4.2/
su - solr -s /bin/bash
bin/solr start
```

4. Decompress the file to the knowledge base configuration and execute the collection creation;

``` sh
unzip -x base_conhecimento_configs.zip -d /opt/solr-6.4.2/
su - solr -s /bin/bash
```

``` sh
bin/solr create -c base_conhecimento -d base_conhecimento_configs -s 2 -rf 2
```

5. Note that the command return should be something like the example bellow:

Copying configuration to new core instance directory: /opt/solr/server/solr/base_conhecimento
Creating new core 'base_conhecimento' using command: http://localhost:8983/solr/admin/cores?action=CREATE&name=base_conhecimento&instanceDir=base_conhecimento
{
"responseHeader":{
"status":0,
"QTime":3223},
"core":"base_conhecimento"}

# Wildfly Application Installation Server

1. We should decompress the JAVA JDK package in the directory /opt and create a symbolic link as presented in the example below. (If you have already done the installation described in the "Create the citsmart.cfg file" in the same server that the Wildfly will be, it'll 'not be necessary the command execution of the JAVA JDK installation below).

``` sh
tar xzvf jdk-8u172-linux-x64.tar.gz -C /opt/
```

``` sh
ln -s /opt/jdk1.8.0_172 /opt/jdk
```

2. Execute the commands below to configure the CITSmart package.

```sh
tar xzvf wildfly-12.0.0.Final.tar.gz -C /opt/
```

```sh
ln -s /opt/wildfly-12.0.0.Final /opt/wildfly
```

```sh
cp /etc/skel/.bash_profile /opt/wildfly/
```

```sh
tar xzvf assets.tar.gz -C /opt/wildfly/
```

```sh
mkdir /opt/wildfly/reports
```


3. Now we have to create a user to manage the Wildfly. For that, create the user citsmart and apply the necessary permission as in the example bellow:

```sh
groupadd -r citsmart
```

```sh
useradd -r -g citsmart -d /opt/wildfly -s /sbin/nologin citsmart
```

```sh
chown citsmart:citsmart /opt/wildfly-12.0.0.Final/ -R
```

```sh
chown citsmart:citsmart /opt/jdk1.8.0_172/ -R
```

4. Now we have to configure the PATH for the JAVA_HOME and JBOSS_HOME. For that, do as in the example below:

```sh
vim /opt/wildfly/.bash_profile
```

export JAVA_HOME="/opt/jdk"
export JBOSS_HOME="/opt/wildfly"
export PATH="$JAVA_HOME/bin:$JBOSS_HOME/bin:$PATH"

5. Make a test to validate if the Wildfly is starting correctly till this point. For that, execute the commands below:

```sh
su - citsmart -s /bin/bash
```

```sh
java -version
```

java version "1.8.0_172"
Java(TM) SE Runtime Environment (build 1.8.0_172-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.172-b11, mixed mode)

```sh
bin/standalone.sh
```

6. Stop the Wildfly (previously started) and configure the standalone.conf in the directory $JBOSS_HOME/bin, as presented below:

```sh
mv standalone.conf standalone.dist
```

```sh
vim standalone.conf
```

if [ "x$JBOSS_MODULES_SYSTEM_PKGS" = "x" ]; then
JBOSS_MODULES_SYSTEM_PKGS="org.jboss.byteman"
fi
if [ "x$JAVA_OPTS" = "x" ]; then
JAVA_OPTS="$JAVA_OPTS -Xms5200m"
JAVA_OPTS="$JAVA_OPTS -Xmx5200m"
JAVA_OPTS="$JAVA_OPTS -XX:MinHeapFreeRatio=40"
JAVA_OPTS="$JAVA_OPTS -XX:MaxHeapFreeRatio=80"
JAVA_OPTS="$JAVA_OPTS -XX:NewRatio=8"
JAVA_OPTS="$JAVA_OPTS -XX:SurvivorRatio=32"
JAVA_OPTS="$JAVA_OPTS -XX:+UseG1GC"
JAVA_OPTS="$JAVA_OPTS -XX:G1HeapRegionSize=4"
JAVA_OPTS="$JAVA_OPTS -XX:InitiatingHeapOccupancyPercent=50"
JAVA_OPTS="$JAVA_OPTS -Djava.net.preferIPv4Stack=true"
JAVA_OPTS="$JAVA_OPTS -Dorg.jboss.resolver.warning=true"
JAVA_OPTS="$JAVA_OPTS -Duser.timezone="America/Sao_Paulo""
JAVA_OPTS="$JAVA_OPTS -Djboss.modules.system.pkgs=$JBOSS_MODULES_SYSTEM_PKGS"
JAVA_OPTS="$JAVA_OPTS -Djava.awt.headless=true"
JAVA_OPTS="$JAVA_OPTS -Djboss.server.default.config=standalone-full-ha.xml"
JAVA_OPTS="$JAVA_OPTS -Djboss.bind.address=0.0.0.0"
JAVA_OPTS="$JAVA_OPTS -Djboss.bind.address.management=0.0.0.0"
else
echo "JAVA_OPTS already set in environment; overriding default settings with values: $JAVA_OPTS"
fi

```sh
chown citsmart:citsmart /opt/wildfly/bin/standalone.conf
```

## Wildfly Application Configuration Server

All configurations done in this document will be done through jboss-cli. For that, start the Wildfly in standalone, connect with jboss-cli and execute the following commands.

```sh
su citsmart /opt/wildfly/bin/standalone.sh -s /bin/bash
```

```sh
/opt/wildfly/bin/jboss-cli.sh --connect
```
[standalone@localhost:9990 /]

## Configure system properties

In the CLI bash, execute the commands below to create the CITSmart properties.

```sh
/system-property=mongodb.host:add(value="mongodb.citsmart.com")
/system-property=mongodb.port:add(value="27017")
/system-property=mongodb.user:add(value="admin")
/system-property=mongodb.password:add(value="admin")
/system-property=citsmart.protocol:add(value="http")
/system-property=citsmart.host:add(value="itsm.citsmart.com")
/system-property=citsmart.port:add(value="8080")
/system-property=citsmart.context:add(value="citsmart")
/system-property=citsmart.login:add(value="citsmart.local\\\consultor")
/system-property=citsmart.password:add(value="senhaConsultor")
/system-property=citsmart.inventory.id:add(value="citsmartinventory")
/system-property=citsmart.evm.id:add(value="citsmartevm")
/system-property=citsmart.evm.enable:add(value=true)
/system-property=citsmart.inventory.enable:add(value=true)
/system-property=rhino.scripts.directory:add(value="")
```

## Datasources configuration

Before creating the datasources, we have to add to the Wildfly the module JDBC of PostgreSQL. For that, exit the mode jboss-cli and execute the commands below.

1. Add the database module as in the example below:

```sh
mkdir -p /opt/wildfly/modules/system/layers/base/org/postgres/main
```

```sh
tar xzvf postgresql-jdbc-driver.tar.gz -C /opt/wildfly/modules/system/layers/base/org/postgres/main
```

```sh
chown citsmart:citsmart /opt/wildfly/modules/system/layers/base/org/postgres/ -R
```

2. Connect the jboss-cli once again and execute the command below to add the module to the standalone-full-ha.xml

```sh
[standalone@localhost:9990 /] module add --name=org.postgres --resources=/opt/wildfly/modules/system/layers/base/org/postgres/main/postgresql-9.3-1103.jdbc41.jar --dependencies=javax.api,javax.transaction.api
/subsystem=datasources/jdbc-driver=postgres:add(driver-name="postgres",driver-module-name="org.postgres",driver-xa-datasource-class-name=org.postgresql.xa.PGXADataSource
```

There are eight inputs of datasource for the citsmart_db, being four for CITSmart and three for CITSmart Neuro. The user and password is citsmartdbuser and exemplo123 created in the section "PostgreSQL Database Server".

3. To create datasources, execute the CLI commands below:

Datasource citsmart:

```sh
/subsystem=datasources/data-source="/jdbc/citsmart":add(jndi-name="java:/jdbc/citsmart",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=idle-timeout-minutes,value=5)
```

Datasource citsmartFlow:

```sh
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":add(jndi-name="java:/jdbc/citsmartFluxo",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=idle-timeout-minutes,value=5)
```

Datasourece citsmart_reports

```sh
/subsystem=datasources/data-source="/jdbc/citsmart_reports":add(jndi-name="java:/jdbc/citsmart_reports",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=idle-timeout-minutes,value=5)
```

Datasource citsmartBpmEventos

```sh
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":add(jndi-name="java:/jdbc/citsmartBpmEventos",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=idle-timeout-minutes,value=5
```

Datasource citsmart-neuro

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro":add(jndi-name="java:/env/jdbc/citsmart-neuro",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

Datasource citsmart-neuro-app1

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app1":add(jndi-name="java:/env/jdbc/citsmart-neuro-app1",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

Datasource citsmart-neuro-app2

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app2":add(jndi-name="java:/env/jdbc/citsmart-neuro-app2",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

Datasource citsmart-neuro-app3

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app3":add(jndi-name="java:/env/jdbc/citsmart-neuro-app3",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

4. Before exit the jboss-cli, execute the command reload to apply the changes. Then, make a connection text with database;

```sh
[standalone@localhost:9990 /] :reload
```

```sh
[standalone@localhost:9990 /] /subsystem=datasources/data-source="/jdbc/citsmart":test-connection-in-pool
{
"outcome" => "success",
"result" => [true]
}
```

## Configure subsytems

```sh
/subsystem=logging/root-logger=ROOT:write-attribute(name=level,value=INFO)
/subsystem=logging/console-handler=CONSOLE:write-attribute(name=level,value=INFO)
/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-post-size,value="5000485760")
/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-parameters,value="3000")
/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-header-size,value="65535")
/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-post-size,value="5000485760")
/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-header-size,value="65535")
/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-parameters,value="3000")
/subsystem=undertow/configuration=filter/rewrite=citsmart:add(target="/citsmart")
/subsystem=undertow/server=default-server/host=default-host/filter-ref=citsmart:add(predicate="regex('^/?$') and equals(/citsmart)")
/subsystem=undertow/server=default-server/host=default-host/setting=access-log:add
/subsystem=undertow/server=default-server/host=default-host/setting=access-log:write-attribute(name=pattern, value="%h %l %u [%t] \"%r\" %s %b \"%{i,Referer}\" \"%{i,User-Agent}\"")
/subsystem=messaging-activemq/server=default/jms-queue=filaDocumentoQueue:add(entries=["queue/filaDocumento","java:jboss/exported/jms/queue/filaDocumento"])
/subsystem=messaging-activemq/server=default/jms-topic=filaDocumentoTopic:add(entries=["topic/filaDocumento","java:jboss/exported/jms/topic/filaDocumento"])
/subsystem=messaging-activemq/server=default/jms-queue=neuroInputQueue:add(entries=["queue/neuroInputQueue","java:jboss/exported/jms/queue/queue/neuroInputQueue"])
/subsystem=messaging-activemq/server=default/jms-queue=neuroOutputQueue:add(entries=["queue/neuroOutputQueue","java:jboss/exported/jms/queue/queue/neuroOutputQueue"])
/subsystem=deployment-scanner/scanner=default:write-attribute(name=deployment-timeout,value=6000000)
```

1. Before exit the jboss-cli, execute the command reload to apply the changes;

```sh
[standalone@localhost:9990 /] :reload
```

## Create citsmart.cfg file

1. In the citsmart.cfg file, the default value is TRUE, that is, if this option does not exist in the file the system will take the value TRUE for this property. Set to TRUE it activates the Thread that updates the fact table of service requests at system startup. Set to FALSE the update will happen only after the inclusion or change of the service request;
2. We should create a file citsmart.cfg in /opt/wildfly/standalone/configuration/ with the information below:

```sh
START_MONITORA_INCIDENTES=FALSE
JDBC_ALIAS_REPORTS=
JDBC_ALIAS_BPM=
JDBC_ALIAS_BPM_EVENTOS=
START_VERIFICA_EVENTOS=FALSE
QUANTIDADE_BACKUPLOGDADOS=1000
START_MODE_RULES=FALSE
START_MODE_RULES=FALSE
LOAD_FACTSERVICEREQUESTRULES = TRUE
```

!!! warning
    Don't forget to change the owner of files and directories to the citsmart user

## Create directories to installation

!!! warning
    Don't forget to change the owner of directory /opt/citsmart

1. Create the directories below to be configured in the 3 (three) steps of web installation.

```sh
For GED: mkdir -p /opt/citsmart/ged
For Knowledge Base: mkdir /opt/citsmart/kb
For Twin Words: mkdir /opt/citsmart/twinwords
For Attachments of Knowledge Base: mkdir /opt/citsmart/attachkb
For Upload: mkdir /opt/citsmart/upload
```

## Generate certification SSL Self-Signed

!!! warning
    To the Wildfly, it'll be generated a self-signed certificate.
    If you have a certificate, it's possible to use it.

1. Connect in the Wildfly server;

Creating new alias with DNS (example itsm.citsmart.com): 

```sh
/opt/jdk/bin/keytool -genkey -alias GRPv1 -keyalg RSA -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -ext san=dns:itsm.citsmart.com -validity 3650 -storepass 123456
```

Creating alias with IP of Jboss server (example 192.168.0.40): 

```sh
/opt/jdk/bin/keytool -genkey -alias GRPv1 -keyalg RSA -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -ext san=ip:192.168.0.40 -validity 3650 -storepass 123456
```

Exporting certificate to extension .cer: 

```sh
/opt/jdk/bin/keytool -export -alias GRPv1 -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -validity 3650 -file /opt/wildfly/standalone/configuration/GRPv1.cer
```

Adding certificate in the cacerts of Java: 

```sh
/opt/jdk/bin/keytool -keystore /opt/jdk/jre/lib/security/cacerts -importcert -alias GRPv1 -file /opt/wildfly/standalone/configuration/GRPv1.cer
```

!!! warning
    Remember to apply the permissions to the wildfly and java jdk owner
    chown citsmart:citsmart /opt/jdk1.8.0_172/ -R
    chown citsmart:citsmart /opt/wildfly-12.0.0.Final/ -R

2. After generate the certificate, connect once again in the jboss-cli and execute the commands below:


```sh
/subsystem=undertow/server=default-server/https-listener=https:read-attribute(name=security-realm)
/subsystem=elytron/key-store=citsmartKeyStore:add(path="GRPv1.keystore",relative-to=jboss.server.config.dir,credential-reference={clear-text="123456"},type=JKS)
/subsystem=elytron/key-manager=citsmartKeyManager:add(key-store=citsmartKeyStore,credential-reference={clear-text="123456"})
/subsystem=elytron/server-ssl-context=citsmartSSLContext:add(key-manager=citsmartKeyManager,protocols=["TLSv1.2"])
/core-service=management/security-realm=ApplicationRealm/server-identity=ssl:remove
/core-service=management/security-realm=ApplicationRealm/server-identity=ssl:add(keystore-path="GRPv1.keystore", keystore-password-credential-reference={clear-text="123456"}, keystore-relative-to="jboss.server.config.dir",alias="GRPv1")
```

3. Before exit the jboss-cli, execute the command reload to apply the changes.

```sh
[standalone@localhost:9990 /] :reload
```

## Starting solutions following dependecies

You can create daemons as standard of your company or create solutions in the terminal.

### PostgreSQL Database Server

```sh
systemctl postgresql start
```

### MongoDB Database Server

```sh
/opt/mongodb-linux-x86_64-rhel70-3.4.15/bin/mongod--auth--port27017
```

### Apache Solr Indexing Server

```sh
su solr /opt/solr/bin/solr start -s /bin/bash
```

### Wildfly Application Server

```sh
su citsmart /opt/wildfly/bin/standalone.sh -s /bin/bash
```

### CITSmart Enterprise Deployment

1. Send the files of deployment provided to the server and move them to the directory "deployments";

```sh
cp CitsmartITSM-Enterprise.war /opt/wildfly/standalone/deployments/
```

2. Do the CITSmart Neuro deployment after finish the steps in section "CITSmart Neuro Deployment".

### Access CITSmart Enterprise

1. To access the CITSmart Enterprise, we should access the IP or DNS with the port and context:

Example of URL: https://itsm.citsmart.com:8443/citsmart

 2. The CITSmart context is standard to the CITSmart Enterprise.

First Access: Enter the URL > https://itsm.citsmart.com:8443/citsmart.

 3. Now, follow the steps in the manual of 3 steps and start to use the solution CITSmart Enterprise.

## CITSmart Neuro Deployment

1. Send the files of deployment provided to the server and move them to the directory "deployments".

```sh
cp citsmart-neuro-web.war /opt/wildfly/standalone/deployments/
```

<continue conforme os deploys disponíveis para sua subscrição>