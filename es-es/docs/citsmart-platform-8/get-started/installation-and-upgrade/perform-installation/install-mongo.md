Title: Instalando MongoDB

# Instalando MongoDB

MongoDB se puede instalar a través del repositorio del yum disponible en la dirección https://repo.mongodb.org/. La versión aprobada por CITSmart es la 3.4. Suponiendo que el servidor es CentOS versión 7, cree un archivo en `/etc/yum.repos.d/` llamado mongo.repo e incluya el contenido a continuación. Recuerde de cambiar el `baseurl` por la URL de acuerdo con la versión de su sistema operativo. En el siguiente ejemplo, el repositorio elegido fue para un CentOS 7:

``` shell
[mongodb-org-3.4]
name=MongoDB 3.4 Repository
baseurl=https://repo.mongodb.org/yum/redhat/7/mongodb-org/3.4/x86_64/
gpgcheck=0
enabled=1
```

Después, instale el mongo:

``` shell
[root@server /tmp]# yum install mongodb-org
Loaded plugins: extras_suggestions, langpacks, priorities, update-motd
210 packages excluded due to repository priority protections
Resolving Dependencies
--> Running transaction check
---> Package mongodb-org.x86_64 0:3.4.23-1.el7 will be installed
--> Processing Dependency: mongodb-org-tools = 3.4.23 for package: mongodb-org-3.4.23-1.el7.x86_64
--> Processing Dependency: mongodb-org-shell = 3.4.23 for package: mongodb-org-3.4.23-1.el7.x86_64
--> Processing Dependency: mongodb-org-server = 3.4.23 for package: mongodb-org-3.4.23-1.el7.x86_64
--> Processing Dependency: mongodb-org-mongos = 3.4.23 for package: mongodb-org-3.4.23-1.el7.x86_64
--> Running transaction check
---> Package mongodb-org-mongos.x86_64 0:3.4.23-1.el7 will be installed
---> Package mongodb-org-server.x86_64 0:3.4.23-1.el7 will be installed
---> Package mongodb-org-shell.x86_64 0:3.4.23-1.el7 will be installed
---> Package mongodb-org-tools.x86_64 0:3.4.23-1.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

===========================================================================================================================
 Package                           Arch                  Version                      Repository                      Size
===========================================================================================================================
Installing:
 mongodb-org                       x86_64                3.4.23-1.el7                 mongodb-org-3.4                5.8 k
Installing for dependencies:
 mongodb-org-mongos                x86_64                3.4.23-1.el7                 mongodb-org-3.4                 12 M
 mongodb-org-server                x86_64                3.4.23-1.el7                 mongodb-org-3.4                 20 M
 mongodb-org-shell                 x86_64                3.4.23-1.el7                 mongodb-org-3.4                 11 M
 mongodb-org-tools                 x86_64                3.4.23-1.el7                 mongodb-org-3.4                 69 M

Transaction Summary
===========================================================================================================================
Install  1 Package (+4 Dependent packages)

Total download size: 112 M
Installed size: 286 M
Is this ok [y/d/N]:

```

Ponga el mongo en el servicio de inicio e inicie el servicio
``` shell
[root@server /tmp]# systemctl enable mongod
systemctl enable mongod
[root@server /tmp]# systemctl start mongod
```

## Cambio de límites del MongoDB

Edite el archivo `/etc/security/limits.conf` y agregue las líneas a continuación al final del archivo:

``` shell
# End of file

mongod soft nofile 64000
mongod hard nofile 64000
mongod soft nproc 64000
mongod hard nproc 64000

```

Edite el archivo /etc/mongod.conf y cambie las líneas siguientes:

``` shell
#security:

para

security:
  authorization: enabled

```

Reinicie el servicio del mongo:

``` shell
[root@server /tmp]# systemctl restart mongod
```
Conecte no mongodb para criar o banco de dados do CITSmart e configurar a senha de admin:
``` shell
[root@server /tmp]# mongo
MongoDB shell version v3.4.23
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.4.23
>
```

Ejecute el siguiente comando para crear el usuario y dar permiso:

```shell

> use admin
db.createUser({
user: "admin",
pwd: "yourpassword",
roles:[
{ role: "root", db: "admin" },
{ role: "dbOwner", db: "citsmart" }
]
})
Successfully added user: {
        "user" : "admin",
        "roles" : [
                {
                        "role" : "root",
                        "db" : "admin"
                },
                {
                        "role" : "dbOwner",
                        "db" : "citsmart"
                }
        ]
}

```

## Próximo paso

[Implementar CITSmart][1]

[1]:/es-es/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/deploy-citsmart.html
