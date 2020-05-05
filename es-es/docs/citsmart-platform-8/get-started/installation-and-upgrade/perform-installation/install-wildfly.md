# Instalación del Wildfly

Wildfly se puede descargar directamente desde el sitio de la comunidad en su área de descarga en https://wildfly.org/downloads/. La versión debe ser la sugerida por la documentación en [Requerimientos del sistema][1]. En este caso, se debe descargar el paquete tgz `Java EE Full & Web Distribution`.

```sh
[root@server /tmp]# cd /tmp
[root@server /tmp]# wget https://download.jboss.org/wildfly/12.0.0.Final/wildfly-12.0.0.Final.tar.gz
```
Descomprima el paquete en el `/opt`:

```sh
[root@server /tmp]# tar -xvzf wildfly-12.0.0.Final.tar.gz -C /opt/
```
Cree un enlace simbólico a wildfly versión 12. Esto tiene la intención de facilitar la administración futura:

```sh
[root@server /tmp]# ln -s /opt/wildfly-12.0.0.Final /opt/wildfly
```

Envíe por scp y descomprima el archivo de activos proporcionado por CITSmart dentro del directorio wildfly. Esta carpeta es necesaria para que la solución funcione, y está disponible para los socios a través de nuestro portal de socios junto con los paquetes de instalación:

```sh
[root@server /tmp]# tar -xzvf assets.tar.gz -C /opt/wildfly/
```

Cree un usuario y grupo para el wildfly:

```sh
[root@server /tmp]# groupadd -r wildfly
[root@server /tmp]# useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly
```

Cree la carpeta de informes:

```sh
[root@server /tmp]# mkdir /opt/wildfly/reports
```

Cambie los permisos de la carpeta wildfly para el usuario creado anteriormente:

```sh
[root@server /tmp]# chown -R wildfly.wildfly wildfly-12.0.0.Final/
```
## Probando el Wildfly

A partir de este paso, podemos realizar una prueba para identificar si el Wildfly funciona correctamente. Inicie sesión con el usuario del wildfly con el comando a continuación:

```sh
[root@server /tmp]# su - wildfly -s /bin/bash
```

Y asegúrese de que Java PATH esté funcionando correctamente:

```sh
-bash-4.2$ java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
-bash-4.2$
```

Cargue el servicio con el comando a continuación:

```sh
-bash-4.2$ ~/bin/standalone.sh
```

Siga los mensajes de inicio. Si el servidor se inició correctamente, aparece un mensaje similar al siguiente:

```sh
INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0025: WildFly Full 12.0.0.Final (WildFly Core 4.0.0.Final) started in 3762ms - Started 292 of 513 services (308 services are lazy, passive or on-demand)
```

Si el mensaje anterior indica que el servicio funciona correctamente. Haga clic en `[CTRL+C]` para detener el servicio. Después, escriba `exit` para salir del usuario CITSmart.

## Próximo paso

[Configurando Java para el WildFly][2]

[1]:/es-es/citsmart-platform-8/get-started/installation-and-upgrade/system-requirements.html
[2]:/es-es/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-java-for-wildfly.html
