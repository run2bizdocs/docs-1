Title: Configuring Java to the WildFly

## Configuring Java to the WildFly

Some java parameters need to be set for the application server to work. Enter in the directory `/bin` home of wildfly `/opt/wildfly/bin`. Edit the file `standalone.conf` and include the new setting after the following line:

``` shell
#
# Specify the exact Java VM executable to use.
#
#JAVA=""

if [ "x$JBOSS_MODULES_SYSTEM_PKGS" = "x" ]; then
   JBOSS_MODULES_SYSTEM_PKGS="org.jboss.byteman"
fi

```

Add the following extract after the line above:

``` shell
if [ "x$JAVA_OPTS" = "x" ]; then
	JAVA_OPTS="$JAVA_OPTS -Xmx12g"
	JAVA_OPTS="$JAVA_OPTS -Xms12g"
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

The two most important sections of the line above are:

``` shell
JAVA_OPTS="$JAVA_OPTS -Xms12g"
JAVA_OPTS="$JAVA_OPTS -Xmx12g"
```
These indicate the memory usage limit of the java virtual machine and should vary based on the 
amount of memory of the server you are installing. You can consider 2GB for the operating system 
and the rest for Java if you are running the dismembered database application server. If the 
base is running on the same server (which we don't recommend for production) you need to 
consider the needs for memory usage of the base, operating system, and finally configure java 
usage. The (xmx) and (xms) values may be the same to improve CITSmart performance.

And finally, uncomment the line below:

``` shell
#JAVA_HOME="/opt/java/jdk"
```

And set it up the right way:

``` shell
#JAVA_HOME="/opt/jdk"
```

## Next step

[Including the WildFly in the system][1]

[1]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/include-wildfly-systemd.html
