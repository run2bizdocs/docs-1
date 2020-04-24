Title: CITSmart extra settings

# CITSmart extra settings

Create a file called citsmart.cfg in /opt/wildfly/standalone/configuration/ with the information bellow:

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

Give permission for the wildfly user to this file:

``` shell
[root@server /tmp]# chown wildfly.wildfly /opt/wildfly/standalone/configuration/citsmart.cfg
```

!!! note

	In the citsmart.cfg file, the default value is TRUE (even if not set), that is, if this 
	option doesn't exist in the file, the system will use the TRUE value for this property. 
	Defined as TRUE, it enables the Thread that updates the service request fact table at the 
	system initialization. Defined as FALSE, the update will occur only after adding or changing 
	the service request.


## Quartz Configuration

CITSmart Batch Processing uses Quartz for scheduling and processing system routines. Create a 
file named "quartz.properties" in the path
`/opt/wildfly/standalone/configuration/`. The settings are different for the common standalone, 
for standalone configured in cluster mode. In either case, configure wildfly as follows.

### Standalone configuration without cluster

If you are running wildfly in standalone mode but without cluster configuration, enter the following information in the quarts.properties file:

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

### Standalone configuration with configured cluster

If you have a standalone running in cluster mode, quartz settings differ depending on the database used. Below are the settings for each of the possible scenarios.
At any database, the settings apply to the same quartz.properties file in the same path you entered earlier.

Configuration for Postgres Database

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

Configuration for Microsoft SQL Server Database

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

Configuration for Oracle Database

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

## Creating directories for installation

Create all directories below necessary for the solution to run. Remember that the owner of the directories must be the Wildfly user.

``` shell

[root@server /tmp]# mkdir -p /opt/citsmart/{ged,kb,twinwords,attachkb,upload}
[root@server /tmp]# chown -R wildfly.wildfly /opt/citsmart/

```

## Next step

[Installing certificate SSL][1]

[1]:/en-us/citsmart-platform-9/get-started/installation-and-upgrade/perform-installation/install-certificate.html
