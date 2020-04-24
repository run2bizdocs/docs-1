Title: Descarga e Instalación del JDK

# Descarga e Instalación del JDK

El kit de desarrollo Java SE debe descargarse directamente del sitio web de Oracle. En el momento de la creación de este documento, esta dirección puede acceder a la ruta:

https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html

Si la dirección no funciona, busque el JDK en el área de descarga del sitio web de Oracle. Descargue la versión de acuerdo con la arquitectura de su sistema operativo. En el ejemplo estamos usando un `Linux CentOS 7.x 64bits`. Todos los paquetes se descargarán en el `/tmp`.

Descargue el jdk a la máquina local y cárguelo al servidor a través de scp. Para hacer esto, debe tener un nombre de usuario y contraseña en el sitio web de Oracle (el registro es gratuito). Esto se debe a que el sitio de Oracle requiere la aceptación de los términos del servicio antes de la descarga. La última versión del JDK disponible en el momento de la creación de la documentación fue la `jdk-8u231`. Utilice siempre el último patch de la versión recomendada.

## Instalando e configurando el JDK

Asumiendo que el archivo está en el `/tmp`, ejecute los siguientes comandos para descomprimir:

``` shell
[root@server /tmp]# tar -xvzf jdk-8u231-linux-x64.tar.gz -C /opt/
```
Cree un enlace simbólico a la carpeta del jdk en su versión descargada. Esto facilita futuras actualizaciones y pruebas con otras versiones.

``` shell
[root@server /tmp]# ln -s /opt/jdk1.8.0_231 /opt/jdk
```

Cree el archivo de configuración de Java en /etc/profile.d/ llamado java.sh. Aunque el servidor web tiene su propia configuración de Java, este paso evita que otras aplicaciones de Java causen problemas.

``` shell
[root@server /tmp]# vi /etc/profile.d/java.sh
```

y agregue el siguiente contenido (el Wildfly se instalará más adelante):

``` shell
export JAVA_HOME="/opt/jdk"
export JBOSS_HOME="/opt/wildfly"
export PATH="$JAVA_HOME/bin:$JBOSS_HOME/bin:$PATH"
```
Cargue la configuración con el comando a continuación y pruebe:

``` shell
[root@server /tmp]# source /etc/profile.d/java.sh
[root@server /tmp]# java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
[root@server /tmp]#
```

## Próximo paso

[Instalación del Wildfly][1]

[1]:/es-es/citsmart-platform-9/get-started/installation-and-upgrade/perform-installation/install-wildfly.html
