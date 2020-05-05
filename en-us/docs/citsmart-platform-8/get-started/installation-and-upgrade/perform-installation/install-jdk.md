Title: JDK Download and Installation

# JDK Download and Installation

The Java SE Development Kit must be downloaded directly from the Oracle website. At the time of creation of this document, the path can be accessed by this address:

https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html

If the address is not working, look for the JDK in the download area of the Oracle website. Download the version according to your operating system architecture. In the example, we are using a `Linux CentOS 7.x 64bits`. All packages will be downloaded in the `/tmp`.

Download the jdk to local machine and upload to server via scp. For this, it's mandatory to have a user and password on the Oracle website (the registration is free). This is because Oracle's site requires acceptance of the terms of service before downloading. The latest version of JDK available at the time of documentation creation was the `jdk-8u231`. Always use the latest patch from the recommended version.

## Installing and configuring the JDK

Assuming the file is in `/tmp` execute the commands below to unzip:

``` shell
[root@server /tmp]# tar -xvzf jdk-8u231-linux-x64.tar.gz -C /opt/
```
Create a symbolic link to jdk folder in the downloaded version. This facilitates future updates and testing with other versions.

``` shell
[root@server /tmp]# ln -s /opt/jdk1.8.0_231 /opt/jdk
```

Create the java configuration file in /etc/profile.d/ called java.sh. Although the web server has its own java settings, this step prevents other java applications from causing problems.

``` shell
[root@server /tmp]# vi /etc/profile.d/java.sh
```

and add the following content (Wildfly will be installed later):

``` shell
export JAVA_HOME="/opt/jdk"
export JBOSS_HOME="/opt/wildfly"
export PATH="$JAVA_HOME/bin:$JBOSS_HOME/bin:$PATH"
```
Load the settings with the command below and test it:

``` shell
[root@server /tmp]# source /etc/profile.d/java.sh
[root@server /tmp]# java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
[root@server /tmp]#
```

## Next step

[Wildfly Installation][1]

[1]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/install-wildfly.html
