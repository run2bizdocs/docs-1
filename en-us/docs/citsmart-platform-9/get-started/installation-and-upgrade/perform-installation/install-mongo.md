Title: Installing MongoDB

# Installing MongoDB

MongoDB can be installed via the yum repository available at https://repo.mongodb.org/. The CITSmart approved version is 3.4. Assuming the server is CentOS version 7, create a file in `/ etc / yum.repos.d /` called mongo.repo, and include the content below. Remember to exchange `baseurl` for the URL according to your operating system version. In the example below the repository chosen was for a CentOS 7:

``` shell
[mongodb-org-3.4]
name=MongoDB 3.4 Repository
baseurl=https://repo.mongodb.org/yum/redhat/7/mongodb-org/3.4/x86_64/
gpgcheck=0
enabled=1
```

Next, install the mongo:

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

Put the mongo in the startup service and start the service.
``` shell
[root@server /tmp]# systemctl enable mongod
systemctl enable mongod
[root@server /tmp]# systemctl start mongod
```

## Change MongoDB limits

Edit the file `/etc/security/limits.conf` and add the lines below at the end of the file:

``` shell
# End of file

mongod soft nofile 64000
mongod hard nofile 64000
mongod soft nproc 64000
mongod hard nproc 64000

```

Edit the file /etc/mongod.conf and change the lines below:

``` shell
#security:

to

security:
  authorization: disabled

```

Restart the mongo services:

``` shell
[root@server /tmp]# systemctl restart mongod
```
Connect the to mongodb to create CITSmart database and set admin password:
``` shell
[root@server /tmp]# mongo
MongoDB shell version v3.4.23
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.4.23
>
```

Run the command below to create the user and give permission:

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

## Next step

[Deploying CITSmart][1]

[1]:/en-us/citsmart-platform-9/get-started/installation-and-upgrade/perform-installation/deploy-citsmart.html
