Title: Configurando el Datasource y Drives de base

# Configurando el Datasource y Drives de base

Antes de crear un datasource, se debe agregar un módulo de base de datos al sistema. Cada base tiene su propio driver de conexión, pero todas las configuraciones asumen el mismo principio: descargar el driver del fabricante, cópielo en wildfly, configúrelo en el sistema. La configuración se realizará a través de jboss-cli, pero todos se pueden realizar a través de XML en el archivo standalone-full.xml si lo desea.

En el siguiente ejemplo usaremos el driver PostgreSQL. Cada base de datos tiene su propio método de configuración, recomendamos buscar en la documentación del fabricante de la base de datos de su elección si difiere de nuestra documentación.

La descarga del driver JDBC de PostgreSQL se puede encontrar en https://jdbc.postgresql.org en el enlace de descargas. La versión del driver utilizada por CITSmart es 4.1 build 9.3 Build 1104.

```sh
[root@server /tmp]# wget https://jdbc.postgresql.org/download/postgresql-9.3-1104.jdbc41.jar
```

Acceda nuevamente a jboss-cli para agregar el driver con el siguiente comando (suponiendo que lo haya descargado en la carpeta `/tmp`):

```sh
[standalone@localhost:9990 /] module add --name=org.postgres --resources=/tmp/postgresql-9.3-1104.jdbc41.jar --dependencies=javax.api,javax.transaction.api
```

Con este comando, el driver se agregará automáticamente a la carpeta `/opt/wildfly-12.0.0.Final/modules/org/postgres/main/`

Continúe con la CLI y ejecute el siguiente comando para agregar un datasource:

```sh
[standalone@localhost:9990 /] /subsystem=datasources/jdbc-driver=postgres:add(driver-name="postgres",driver-module-name="org.postgres",driver-xa-datasource-class-name=org.postgresql.xa.PGXADataSource
```

## Creando la base de datos de CITSmart

Independientemente de la arquitectura de la base (ya sea instalada en el mismo servidor o separado), los pasos a continuación son para crear una base de datos y un usuario para CITSmart. En el procedimiento asumimos que tiene acceso al SGBD. Acceda al PostgreSQL con el comando a continuación:

```sh
[root@server /tmp]#  su - postgres
bash-4.2$
bash-4.2$ psql
psql (9.6.15)
Type "help" for help.

postgres=#
```
Cree un nombre de usuario y contraseña de acceso a la base de CITSmart (reemplace la SU_CONTRASEÑA con una contraseña preferida):

```sh
postgres=# create user citsmartdbuser with password 'SUA_SENHA';
CREATE ROLE
postgres=#
```
Crear una base de datos para CITSmart:

```sh
postgres=# create database citsmart_db with owner citsmartdbuser encoding 'UTF8' tablespace pg_default;
CREATE DATABASE
postgres=#
```
Dar permiso al usuario de CITSmart:

```sh
postgres=# alter role citsmartdbuser superuser;
ALTER ROLE
postgres=#
```

Salga del PSQL y del shell del usuario de postgres:

```sh
postgres=# \q
bash-4.2$ exit
exit
[root@server /tmp]#
```
Si la base se está ejecutando en el mismo servidor, es necesario liberar la conexión al usuario de CITSmart. Edite el archivo  `/var/lib/pgsql/9.6/data/pg_hba.conf` e incluye la siguiente línea:

```sh
# Database administrative login by Unix domain socket
local   all             postgres                                ident
```
!!! Warning "ATENCIÓN"

    No cambie la línea `local all postgres peer` que viene por defecto, incluya la línea de arriba justo debajo de esta.


Si la base de datos se ejecuta en otro servidor, es necesario liberar la conexión desde Wildfly. Para hacer esto, incluya la siguiente línea en el mismo archivo pg_hba.conf, reemplazándolo con la dirección IP del servidor Wildfly:

```sh
host citsmart_db citsmartdbuser WILDFLY_IP_ADDRESS/32 md5

```

## Configurando el datasource para citsmart

Hay ocho entradas de datasource para citsmart_db, cuatro para CITSmart y cuatro para CITSmart Neuro. El nombre de usuario y la contraseña son citsmartdbuser y SU_CONTRASEÑA, creados en el paso anterior. Si creó un nombre de usuario, contraseña y base de nombres diferentes, cámbielo en los comandos abajo.

Conéctese a jboss-cli y ejecute los siguientes comandos:

### Datasource citsmart

```sh
/subsystem=datasources/data-source="/jdbc/citsmart":add(jndi-name="java:/jdbc/citsmart",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasource citsmartFlow

```sh
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":add(jndi-name="java:/jdbc/citsmartFluxo",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasourece citsmart_reports

```sh
/subsystem=datasources/data-source="/jdbc/citsmart_reports":add(jndi-name="java:/jdbc/citsmart_reports",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasource citsmartBpmEventos

```sh
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":add(jndi-name="java:/jdbc/citsmartBpmEventos",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=idle-timeout-minutes,value=5
```

### Datasource citsmart-neuro

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro":add(jndi-name="java:/env/jdbc/citsmart-neuro",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)#
```

### Datasource citsmart-neuro-app1

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app1":add(jndi-name="java:/env/jdbc/citsmart-neuro-app1",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

### Datasource citsmart-neuro-app2

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app2":add(jndi-name="java:/env/jdbc/citsmart-neuro-app2",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```
### Datasource citsmart-neuro-app3

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app3":add(jndi-name="java:/env/jdbc/citsmart-neuro-app3",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

Antes de salir de jboss-cli, ejecute el comando reload para aplicar los cambios y realizar una prueba de conexión de la base de datos:

```sh
[standalone@localhost:9990 /]: reload
```
Y haga una prueba de conexión con todos las bases con los siguientes comandos. Recordando que el resultado debe ser `"outcome" => "success"`:

``` sh
/subsystem=datasources/data-source="/jdbc/citsmart":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmart_reports":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmart-neuro":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmart-neuro-app1":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmart-neuro-app2":test-connection-in-pool
/subsystem=datasources/data-source="/jdbc/citsmart-neuro-app3":test-connection-in-pool
```

## Próximo paso

[Configurando el Wildfly][1]

[1]:/es-es/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-wildfly.html
