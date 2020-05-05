Title: Configuraciones extras de CITSmart

# Configuraciones extras de CITSmart

Cree un archivo llamado citsmart.cfg en /opt/wildfly/standalone/configuration/ con la información a continuación:

``` shell
START_MONITORA_INCIDENTES=FALSE
JDBC_ALIAS_REPORTS=
JDBC_ALIAS_BPM=
JDBC_ALIAS_BPM_EVENTOS=
START_VERIFICA_EVENTOS=FALSE
QUANTIDADE_BACKUPLOGDADOS=1000
START_MODE_RULES=FALSE
START_MODE_RULES=FALSE
LOAD_FACTSERVICEREQUESTRULES=TRUE
INICIAR_PROCESSAMENTOS_BATCH=TRUE
```

Dar permiso de usuario wildfly para este archivo:

``` shell
[root@server /tmp]# chown wildfly.wildfly /opt/wildfly/standalone/configuration/citsmart.cfg
```

!!! note

	En el archivo citsmart.cfg, el valor predeterminado es TRUE (incluso si no está configurado),es decir, si esta opción no existe en el archivo, el sistema usará el valor TRUE para esta propiedad. Establecido en TRUE, habilita el Thread que actualiza la tabla de hechos de solicitud de servicio al inicio del sistema. Establecido en FALSE, la actualización ocurrirá solo después de agregar o cambiar la solicitud de servicio.


## Configuración de Quartz

El procesamiento Batch de CITSmart utiliza Quartz para programar y procesar rutinas del sistema. Cree un archivo llamado "quartz.properties" en la ruta `/opt/wildfly/standalone/configuration/`. Las configuraciones difieren para la standalone común, para la standalone configurada en modo de clúster. En cualquier caso, configure wildfly de las siguientes maneras.

### Configuración standalone sin cluster

Si está ejecutando el wildfly en modo standalone, pero sin configuración de clúster, ingrese la siguiente información en el archivo quarts.properties:

``` shell
#===============================================================
#Configure Main Scheduler Properties
#===============================================================
org.quartz.scheduler.instanceName = CitSmartMonitor
org.quartz.scheduler.instanceId = AUTO
#===============================================================
#Configure ThreadPool
#===============================================================
org.quartz.threadPool.threadCount =  5
org.quartz.threadPool.threadPriority = 5
org.quartz.threadPool.class = org.quartz.simpl.SimpleThreadPool
#===============================================================
#Configure JobStore
#===============================================================
org.quartz.jobStore.class = org.quartz.simpl.RAMJobStore
```

### Configuración standalone con cluster configurado

Si tiene una standalone funcionando en modo de clúster, la configuración de quartz varía según la base de datos utilizada. A continuación se encuentran las configuraciones para cada uno de los escenarios posibles. Cualquiera que sea la base de datos, la configuración se aplica al mismo archivo quartz.properties en la misma ruta que ingresó anteriormente.

Configuración de la base de datos Postgres

``` shell
#============================================================================
# Configure Main Scheduler Properties
#============================================================================
org.quartz.scheduler.instanceName = CitSmartMonitor
org.quartz.scheduler.instanceId = AUTO
#============================================================================
# Configure ThreadPool
#============================================================================
org.quartz.threadPool.class = org.quartz.simpl.SimpleThreadPool
org.quartz.threadPool.threadCount = 25
org.quartz.threadPool.threadPriority = 5
#============================================================================
# Configure JobStore
#============================================================================
org.quartz.jobStore.misfireThreshold = 60000
org.quartz.jobStore.class = org.quartz.impl.jdbcjobstore.JobStoreTX
org.quartz.jobStore.driverDelegateClass = org.quartz.impl.jdbcjobstore.PostgreSQLDelegate
org.quartz.jobStore.useProperties = true
org.quartz.jobStore.dataSource = citsmart
org.quartz.jobStore.tablePrefix = QRTZ_
org.quartz.jobStore.isClustered = true
org.quartz.jobStore.clusterCheckinInterval = 20000
org.quartz.dataSource.citsmart.jndiURL= java:/jdbc/citsmart
```

Configuración para la base de datos de Microsoft SQL Server

``` shell
#============================================================================
# Configure Main Scheduler Properties
#============================================================================
org.quartz.scheduler.instanceName = CitSmartMonitor
org.quartz.scheduler.instanceId = AUTO
#============================================================================
# Configure ThreadPool
#============================================================================
org.quartz.threadPool.class = org.quartz.simpl.SimpleThreadPool
org.quartz.threadPool.threadCount = 25
org.quartz.threadPool.threadPriority = 5
#============================================================================
# Configure JobStore
#============================================================================
org.quartz.jobStore.misfireThreshold = 60000
org.quartz.jobStore.class = org.quartz.impl.jdbcjobstore.JobStoreTX
org.quartz.jobStore.driverDelegateClass = org.quartz.impl.jdbcjobstore.MSSQLDelegate
org.quartz.jobStore.useProperties = true
org.quartz.jobStore.dataSource = citsmart
org.quartz.jobStore.tablePrefix = QRTZ_
org.quartz.jobStore.isClustered = true
org.quartz.jobStore.clusterCheckinInterval = 20000
org.quartz.dataSource.citsmart.jndiURL= java:/jdbc/citsmart
```

Configuración para la base de datos Oracle

``` shell
#============================================================================
# Configure Main Scheduler Properties
#============================================================================
org.quartz.scheduler.instanceName = CitSmartMonitor
org.quartz.scheduler.instanceId = AUTO
#============================================================================
# Configure ThreadPool
#============================================================================
org.quartz.threadPool.class = org.quartz.simpl.SimpleThreadPool
org.quartz.threadPool.threadCount = 25
org.quartz.threadPool.threadPriority = 5
#============================================================================
# Configure JobStore
#============================================================================
org.quartz.jobStore.misfireThreshold = 60000
org.quartz.jobStore.class = org.quartz.impl.jdbcjobstore.JobStoreTX
org.quartz.jobStore.driverDelegateClass = org.quartz.impl.jdbcjobstore.oracle.OracleDelegate
org.quartz.jobStore.useProperties = true
org.quartz.jobStore.dataSource = citsmart
org.quartz.jobStore.tablePrefix = QRTZ_
org.quartz.jobStore.isClustered = true
org.quartz.jobStore.clusterCheckinInterval = 20000
```

## Creando directorios para la instalación

Cree todos los directorios a continuación necesarios para el funcionamiento de la solución. Recuerde que el propietario de los directorios debe ser el usuario wildfly.

``` shell

[root@server /tmp]# mkdir -p /opt/citsmart/{ged,kb,twinwords,attachkb,upload}
[root@server /tmp]# chown -R wildfly.wildfly /opt/citsmart/

```

## Próximo paso

[Instalando certificado SSL][1]

[1]:/es-es/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/install-certificate.html
