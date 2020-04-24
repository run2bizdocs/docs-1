Title: Configurando el servidor de aplicación

# Configurando el servidor de aplicación

Las configuraciones del servidor de aplicación se puede hacer de dos maneras: a través de jboss-cli o editando el archivo xml6. No hay diferencia técnica en ninguna de las opciones, y la elección depende de cada administrador. A continuación hay ambos ejemplos de configuración.

!!! Warning "ATENCIÓN"

    Esté atento a las variables para cambiarlas y adaptarlas según las configuraciones de entorno.

## Configurando servidor a través de jboss-cli

Conéctese a jboss-cli (suponiendo que el servidor se esté ejecutando) ejecutando el siguiente comando:

``` shell
[root@server /tmp]# /opt/wildfly/bin/jboss-cli.sh --connect
[standalone@localhost:9990 /]
```

Luego ejecute los siguientes comandos reemplazando los contenidos variables por la configuración de su entorno.

``` shell
[standalone@localhost:9990 /] /system-property=mongodb.host:add(value="citmongo")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=mongodb.port:add(value="27017")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=mongodb.user:add(value="admin")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=mongodb.password:add(value="admin")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.protocol:add(value="http")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.host:add(value="my.citsmart.com")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.port:add(value="8080")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.context:add(value="citsmart")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.login:add(value="citsmart.local\\\consultor")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.password:add(value="senhaConsultor")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.inventory.id:add(value="citsmartinventory")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.evm.id:add(value="citsmartevm")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.evm.enable:add(value=true)
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.inventory.enable:add(value=true)
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.port.updateparameters:add(value="9000")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=citsmart.inventory.pagelength:add(value="100")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=rhino.scripts.directory:add(value="")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=jboss.as.management.blocking.timeout:add(value="600")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=org.quartz.properties:add(value="$\{jboss.server.config.dir\}/quartz.properties")
{"outcome" => "success"}
[standalone@localhost:9990 /]/system-property=snmp.oid.repository.directory:add(value="/opt/templates")
{"outcome" => "success"}
```

Después de las configuraciones, para salir del CLI, escriba `quit`

``` shell
[standalone@localhost:9990 /] quit
[root@server /tmp]#
```
## Configurando el servidor a través de XML

Para editar el archivo XML utilizado por el wildfly a mano, ingrese en el directorio:

``` shell
[root@server /tmp]# /opt/wildfly/standalone/configuration
```
Y edite el archivo stantalone-full.xml e incluya la configuración XML CITSmart justo después de la cláusula siguiente:

``` xml
<server xmlns="urn:jboss:domain:6.0">
    <extensions>
        <extension module="org.jboss.as.clustering.infinispan"/>
        <extension module="org.jboss.as.connector"/>
		...
</extensions>
```

 Después de cerrar la configuración `</extensions>` incluya el siguiente fragmento:

 ``` xml
 <system-properties>
     <property name="mongodb.host" value="citmongo"/>
     <property name="mongodb.port" value="27017"/>
     <property name="mongodb.user" value="admin"/>
     <property name="mongodb.password" value="admin"/>
     <property name="citsmart.protocol" value="http"/>
     <property name="citsmart.host" value="my.citsmartcloud.com"/>
     <property name="citsmart.port" value="8080"/>
     <property name="citsmart.context" value="citsmart"/>
     <property name="citsmart.login" value="citsmart.local\\\consultor"/>
     <property name="citsmart.password" value="senhaConsultor"/>
     <property name="citsmart.inventory.id" value="citsmartinventory"/>
     <property name="citsmart.evm.id" value="citsmartevm"/>
     <property name="citsmart.evm.enable" value="false"/>
     <property name="citsmart.inventory.enable" value="false"/>
     <property name="rhino.scripts.directory" value=""/>
     <property name="jboss.as.management.blocking.timeout" value="600"/>
     <property name="citsmart.port.updateparameters" value="9000"/>
     <property name="citsmart.inventory.pagelength" value="100"/>
     <property name="org.quartz.properties" value="${jboss.server.config.dir}/quartz.properties"/>
     <property name="snmp.oid.repository.directory" value="/opt/templates"/>
 </system-properties>
 ```

 Después de configurar, reinicie el servicio para garantizar los cambios:

 ``` shell
 [root@server /tmp]# systemctl status wildfly
 ```

## Próximo paso

[Configurando el Datasource y Drives de base][1]

[1]:/es-es/citsmart-platform-9/get-started/installation-and-upgrade/perform-installation/conf-datasource-and-db.html
