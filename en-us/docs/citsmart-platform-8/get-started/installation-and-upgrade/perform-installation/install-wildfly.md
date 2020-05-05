# Wildfly Installation

Wildfly can be downloaded directly from the community site in your download area at https://wildfly.org/downloads/. The version should be the same as suggested by the documentation in [Requisitos do sistema][1]. In this case, the tgz package should be downloaded `Java EE Full & Web Distribution`.

```sh
[root@server /tmp]# cd /tmp
[root@server /tmp]# wget https://download.jboss.org/wildfly/12.0.0.Final/wildfly-12.0.0.Final.tar.gz
```
Unzip the package to `/opt`:

```sh
[root@server /tmp]# tar -xvzf wildfly-12.0.0.Final.tar.gz -C /opt/
```
Create a symbolic link to wildfly version 12. This is intended to facilitate future administrations:

```sh
[root@server /tmp]# ln -s /opt/wildfly-12.0.0.Final /opt/wildfly
```

Send via scp and decompress the assets file provided by CITSmart inside the wildfly directory. This folder is required for the solution to function, and is made available to partners through our partner portal along with installation packages:

```sh
[root@server /tmp]# tar -xzvf assets.tar.gz -C /opt/wildfly/
```

Create a user and group to the wildfly:

```sh
[root@server /tmp]# groupadd -r wildfly
[root@server /tmp]# useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly
```

Create reports folder:

```sh
[root@server /tmp]# mkdir /opt/wildfly/reports
```

Change the wildfly folder permissions for the user created above:

```sh
[root@server /tmp]# chown -R wildfly.wildfly wildfly-12.0.0.Final/
```
## Testing Wildfly

From this step, we can perform a test to identify if Wildfly is working properly. Login with the wildfly user with the command below:

```sh
[root@server /tmp]# su - wildfly -s /bin/bash
```

And check if the java PATH is working correctly:

```sh
-bash-4.2$ java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
-bash-4.2$
```

Upload the service with the command below:

```sh
-bash-4.2$ ~/bin/standalone.sh
```

Follow the startup messages. If the server started correctly, a message similar to the one below appears:

```sh
INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0025: WildFly Full 12.0.0.Final (WildFly Core 4.0.0.Final) started in 3762ms - Started 292 of 513 services (308 services are lazy, passive or on-demand)
```

If the above message indicates that the service is functioning correctly, click on `[CTRL+C]` to stop the service. Next, type `exit` to logout from CITSmart user.

## Next step

[Configuring Java for the WildFly][2]

[1]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/system-requirements.html
[2]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-java-for-wildfly.html
