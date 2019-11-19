Title: Configurando o Java para o WildFly

## Configurando o Java para o WildFly

Alguns parâmetros do java precisam ser configurados para funcionamento do servidor de aplicação. Entre no diretório `/bin` home do wildfly `/opt/wildfly/bin`. Edite o arquivo `standalone.conf` e inclua a nova configuração após a seguinte linha:

``` shell
#
# Specify the exact Java VM executable to use.
#
#JAVA=""

if [ "x$JBOSS_MODULES_SYSTEM_PKGS" = "x" ]; then
   JBOSS_MODULES_SYSTEM_PKGS="org.jboss.byteman"
fi

```

Adicione o seguinte trecho após a linha acima:

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

Os dois trechos mais importantes da linha acima são:

``` shell
JAVA_OPTS="$JAVA_OPTS -Xms12g"
JAVA_OPTS="$JAVA_OPTS -Xmx12g"
```
Elas indicam o limite de utilização de memória da máquina virtual java e devem variar de acordo com a quantidade de memória do servidor que estiver instalando. Você pode considerar 2GB para o sistema operacional e o restante para o Java caso esteja rodando o servidor de aplicação desmembrado do de banco de dados. Caso o banco esteja rodando no mesmo servidor (o que não recomendamos para produção) você precisa considerar a necessidade de consumo de memória do banco, do sistema operacional, e por fim configurar a utilização por parte do java. Os valores de (xmx) e (xms) podem ser iguais para melhorar a performance do CITSmart.

E por fim, descomente a linha abaixo:

``` shell
#JAVA_HOME="/opt/java/jdk"
```

E configure da forma correta:

``` shell
#JAVA_HOME="/opt/jdk"
```

## Próximo passo

[Incluindo o WildFly no systemd][1]

[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/include-wildfly-systemd.html
