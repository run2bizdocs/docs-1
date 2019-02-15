Title: Hacer la instalación

# Hacer la instalación

Instalación del Servidor de Aplicación Wildfly
-------------------------------------------

1.Descomprimir el paquete JAVA JDK en el directorio /opt y crear un link
simbólico conforme mostrado en el ejemplo abajo. *(Caso ya tenga hecho la
instalación del ítem Servidor de Indexación Apache Solr (sesión Configuración de los
paquetes) el mismo servidor que el Wildfly se va a quedar, no será necesario la ejecución
de los comandos de instalación del Java JDK abajo)*.

        ```sh
        tar xzvf jdk-8u172-linux-x64.tar.gz -C /opt/
        ```
    
        ```sh
        ln -s /opt/jdk1.8.0_172 /opt/jdk
        ```
    
2. Ejecutar los comandos siguientes para configuración de los paquetes para CITSmart;
    
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
    
3. crear un usuario para administrar el Wildfly;

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

4. Configurar **PATH** para el JAVA_HOME y el JBOSS_HOME. Para
eso,  haga conforme el ejemplo siguiente.

    ```sh
    vim /opt/wildfly/.bash_profile
    ```
    ```sh
    export JAVA_HOME="/opt/jdk"
    ```
    ```sh
    export JBOSS_HOME="/opt/wildfly"
    ```
    ```sh
    export PATH="$JAVA_HOME/bin:$JBOSS_HOME/bin:$PATH"
    ```
    
5. Haga una prueba para validar se el Wildfly está iniciando correctamente hasta ese
punto. Para eso, ejecute los comandos siguientes.

    ```sh
    su - citsmart -s /bin/bash
    ```

    ```sh
    java -version
    ```
    ```html
    java version "1.8.0_172"
    Java(TM) SE Runtime Environment (build 1.8.0_172-b11)
    Java HotSpot(TM) 64-Bit Server VM (build 25.172-b11, mixed mode)
    ```
    ```sh
    bin/standalone.sh
    ```

6. Parar el Wildfly (Iniciado anteriormente) y configurar el standalone.conf en el
directorio \$JBOSS_HOME/bin, conforme presentado abajo.


    ```sh
    mv standalone.conf standalone.dist
    ```

    ```sh
    vim standalone.conf
    ```
    ```java
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
    ```
    ```sh
    chown citsmart:citsmart /opt/wildfly/bin/standalone.conf
    ```


###Configuración del System Properties

En el bash del CLI ejecute los comandos siguientes para creación de las propiedades del
CITSmart.

```java
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

###Configuración de los Datasources

Antes de crear los datasources, debemos adicionar al Wildfly el modulo JDBC del
PostgreSQL. Para eso, salga del modo jboss-cli y ejecute los comandos abajo.

1. Añadir el modulo del banco de datos como en el ejemplo abajo:

    ```sh
    mkdir -p /opt/wildfly/modules/system/layers/base/org/postgres/main
    ```

    ```sh
    tar xzvf postgresql-jdbc-driver.tar.gz -C /opt/wildfly/modules/system/layers/base/org/postgres/main
    ```

    ```sh
    chown citsmart:citsmart /opt/wildfly/modules/system/layers/base/org/postgres/ -R
    ```

2. Conectar en el jboss-cli nuevamente y ejecute el comando siguiente para adicionar el
módulo al standalone-full-ha.xml

   
    ```sh
    module add --name=org.postgres --resources=/opt/wildfly/modules/system/layers/base/org/postgres/main/postgresql-9.3-1103.jdbc41.jar --dependencies=javax.api,javax.transaction.api
    ```
    ```sh
    /subsystem=datasources/jdbc-driver=postgres:add(driver-name="postgres",driver-module-name="org.postgres",driver-xa-datasource-class-name=org.postgresql.xa.PGXADataSource
    ```

3. Hay **ocho entradas** de datasource para **citsmart_db**, siendo que
cuatro para Citsmart y cuatro para Citsmart Neuro. El usuario y contraseña
e **citsmartdbuser y exemplo123** creados respectivamente en el ítem *Servidor de Base de Datos
PostgreSQL*.

4. Para crear los datasources, ejecute los comandos CLI abajo:

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



    Antes de sair do jboss-cli execute o comando reload para aplicar as alterações e faça um teste de conexão com a base de dados.
    
    ```sh
    [standalone\@localhost:9990 /] :reload
    ```
    ```sh
    [standalone\@localhost:9990 /] /subsystem=datasources/data-source="/jdbc/citsmart":test-connection-in-pool { "outcome" =\> "success", "result" =\> [true] }
    ```

### Configurando los Subsytems


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
/subsystem=undertow/server=default-server/host=default-host/filter-ref=citsmart:add(predicate="regex('\^/?\$') and equals(/citsmart)")
/subsystem=undertow/server=default-server/host=default-host/setting=access-log:add
/subsystem=undertow/server=default-server/host=default-host/setting=access-log:write-attribute(name=pattern, value="%h %l %u [%t] \\"%r\\" %s %b \\"%{i,Referer}\\" \\"%{i,User-Agent}\\"")
/subsystem=messaging-activemq/server=default/jms-queue=filaDocumentoQueue:add(entries=["queue/filaDocumento","java:jboss/exported/jms/queue/filaDocumento"])
/subsystem=messaging-activemq/server=default/jms-topic=filaDocumentoTopic:add(entries=["topic/filaDocumento","java:jboss/exported/jms/topic/filaDocumento"])
/subsystem=messaging-activemq/server=default/jms-queue=neuroInputQueue:add(entries=["queue/neuroInputQueue","java:jboss/exported/jms/queue/queue/neuroInputQueue"])
/subsystem=messaging-activemq/server=default/jms-queue=neuroOutputQueue:add(entries=["queue/neuroOutputQueue","java:jboss/exported/jms/queue/queue/neuroOutputQueue"])
/subsystem=deployment-scanner/scanner=default:write-attribute(name=deployment-timeout,value=6000000)
```

Antes de salir del jboss-cli, ejecute el comando reload para aplicar los cambios.

```sh
[standalone\@localhost:9990 /] :reload
```

## Crear archivo citsmart.cfg

1. En el archivo citsmart.cfg, el valor predeterminado es TRUE, es decir, si esta opción no existe en el archivo, el sistema utilizará el valor TRUE para esa propiedad. Definido como TRUE, activa el Thread que actualiza la tabla fatos de solicitudes de servicio en el inicio del sistema. Definido como FALSE, la actualización sólo se producirá después de la inclusión o modificación de la solicitud de servicio;

2. Debemos crear un archivo citsmart.cfg en /opt/wildfly/standalone/configuration/ con las informaciones siguientes:


    ```java
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
    No olvides de cambiar el dueño de los archivos y directorios para el usuario
    CITSmart.


## Creación de directorios para instalación

No olvides de cambiar el dueño del directorio /opt/citsmart

1. Crear los directorios abajo para ser configurados en los 3 pasos de instalación web.

    Para GED: 

    ```sh
    mkdir -p /opt/citsmart/ged
    ```
    Para Base de Conocimiento:
	
    ```sh
    mkdir /opt/citsmart/kb
    ```
    Para Palavras homónimas:
	
	```sh
    mkdir /opt/citsmart/twinwords
    ```
    Para Anexos de Base de Conhecimento:
	
    ```sh
    mkdir /opt/citsmart/attachkb
    ```
    Para Upload: 
	
    ```
	mkdir /opt/citsmart/upload
    ```


## Generación del certificado auto-firmado SSL

Para el Wildfly se va a generar un certificado auto-firmado.
Caso usted tenga un certificado, es importante utilizarlo.

1. Conectar en el servidor del Wildfly.
    
    Creando nuevo alias con DNS (ejemplo itsm.citsmart.com): 
    
    
    ```sh
    /opt/jdk/bin/keytool -genkey -alias GRPv1 -keyalg RSA -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -ext san=dns:itsm.citsmart.com -validity 3650 -storepass 123456 Criando alias com IP do servidor do Jboss (exemplo 192.168.0.40): \# /opt/jdk/bin/keytool -genkey -alias GRPv1 -keyalg RSA -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -ext san=ip:192.168.0.40 -validity 3650 -storepass 123456 Exportando certificado para extensão .cer: \# /opt/jdk/bin/keytool -export -alias GRPv1 -keystore /opt/wildfly/standalone/configuration/GRPv1.keystore -validity 3650 -file /opt/wildfly/standalone/configuration/GRPv1.cer Adicionando certificado no cacerts do Java: \# /opt/jdk/bin/keytool -keystore /opt/jdk/jre/lib/security/cacerts -importcert -alias GRPv1 -file /opt/wildfly/standalone/configuration/GRPv1.cer
    ```
    
    **Recuerde de aplicar los permisos para el dueño del wildfly y java jdk**
    
    ```sh
    chown citsmart:citsmart /opt/jdk1.8.0_172/ -R chown citsmart:citsmart /opt/wildfly-12.0.0.Final/ -R
    ```

2. Después de generar el certificado, conecte nuevamente en el jboss-cli y ejecute los comandos siguientes:
    
    ```sh
    /subsystem=undertow/server=default-server/https-listener=https:read-attribute(name=security-realm)
    /subsystem=elytron/key-store=citsmartKeyStore:add(path="GRPv1.keystore",relative-to=jboss.server.config.dir,credential-reference={clear-text="123456"},type=JKS)
    /subsystem=elytron/key-manager=citsmartKeyManager:add(key-store=citsmartKeyStore,credential-reference={clear-text="123456"})
    /subsystem=elytron/server-ssl-context=citsmartSSLContext:add(key-manager=citsmartKeyManager,protocols=["TLSv1.2"])
    /core-service=management/security-realm=ApplicationRealm/server-identity=ssl:remove
    /core-service=management/security-realm=ApplicationRealm/server-identity=ssl:add(keystore-path="GRPv1.keystore", keystore-password-credential-reference={clear-text="123456"}, keystore-relative-to="jboss.server.config.dir",alias="GRPv1")
    ```
	
3. Antes de salir del jboss-cli, ejecute el comando reload para aplicar los cambios.

    ```sh
    [standalone\@localhost:9990 /] :reload
    ```

## Iniciando las soluciones siguiendo dependencias

1. Antes de salir del jboss-cli ejecute el comando reload para aplicar los cambios.

    **Servidor de Base de Datos PostgreSQL**:

    ```sh
    systemctl postgresql start
    ```

    **Servidor de Base de Datos MongoDB**

    ```sh
    /opt/mongodb-linux-x86_64-rhel70-3.4.15/bin/mongod --auth --port 27017
    ```

    **Servidor de Indexación Apache Solr**

    ```sh
    su solr /opt/solr/bin/solr start -s /bin/bash
    ```

    **Servidor de Aplicación Wildfly**

    ```sh
    su citsmart /opt/wildfly/bin/standalone.sh -s /bin/bash
    ```
    

## Implementación del CITSmart Enterprise


1. Enviar los archivos de implementación fornecidos para el servidor y los mueva para el directorio “deployments”.

    ```sh
    cp CitsmartITSM-Enterprise.war /opt/wildfly/standalone/deployments/
    ```

2. Hacer la implementación del Citsmart Neuro después de finalizar los pasos de la próxima sesión (Acceso al CITSmart Enterprise).


### Acesso al CITSmart Enterprise


1. Para acceder al CITSmart Enterprise, debemos acceder el IP o DNS y después el puerto y contexto.

    ```sh
    https://itsm.citsmart.com:8443/citsmart
    ```
	
!!! info
    El contexto CITSmart es estándar del CITSmart Enterprise.


## Implementación del CITSmart Neuro

1. Enviar los archivos de implementación fornecidos para el servidor y los mueva para el directorio “deployments”.

    ```sh
    cp citsmart-neuro-web.war /opt/wildfly/standalone/deployments/
    ```


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/17/2019 – Anna Martins
