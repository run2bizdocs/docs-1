Title: Configurando Java para el WildFly

## Configurando Java para el WildFly

Algunos parámetros de Java deben establecerse para que el servidor de aplicaciones funcione. Entre en el directorio `/bin` home del wildfly `/opt/wildfly/bin`. Edite el archivo `standalone.conf` e incluir la nueva configuración después de la siguiente línea:

``` shell
#
# Specify the exact Java VM executable to use.
#
#JAVA=""

if [ "x$JBOSS_MODULES_SYSTEM_PKGS" = "x" ]; then
   JBOSS_MODULES_SYSTEM_PKGS="org.jboss.byteman"
fi

```

Agregue el siguiente fragmento después de la línea de arriba:

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

Las dos secciones más importantes de la línea de arriba son:

``` shell
JAVA_OPTS="$JAVA_OPTS -Xms12g"
JAVA_OPTS="$JAVA_OPTS -Xmx12g"
```
Ellos indican el límite de uso de memoria de la máquina virtual Java y deben variar de acuerdo con la cantidad de memoria del servidor que está instalando. Puede considerar 2 GB para el sistema operativo y el resto para Java si está ejecutando el servidor de aplicaciones de base de datos desmembrado. Si la base se ejecuta en el mismo servidor (que no recomendamos para la producción), debe considerar la necesidad de uso de memoria de la base, sistema operativo y, finalmente, configurar el uso de Java. Los valores de (xmx) y (xms) pueden ser los mismos para mejorar el rendimiento de CITSmart.

Y finalmente, descomenta la línea de abajo:

``` shell
#JAVA_HOME="/opt/java/jdk"
```

Y configúralo de la manera correcta:

``` shell
#JAVA_HOME="/opt/jdk"
```

## Próximo paso

[Incluyendo WildFly en el systemd][1]

[1]:/es-es/citsmart-platform-9/get-started/installation-and-upgrade/perform-installation/include-wildfly-systemd.html
