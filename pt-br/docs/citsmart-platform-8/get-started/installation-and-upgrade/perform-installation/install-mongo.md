Title: Instalando o MongoDB

# Instalando o MongoDB

A instalação do MongoDB pode ser feita via repositório do yum disponível no endereço https://repo.mongodb.org/. A versão homologada pelo CITSmart é a 3.4. Considerando que o servidor seja CentOS versão 7, crie um arquivo no `/etc/yum.repos.d/` chamado mongo.repo, e inclua o conteúdo abaixo. Lembre-se de trocar o `baseurl` pelo URL de acordo com sua versão de sistema operacional. No exemplo abaixo o repositório escolhido foi para um CentOS 7:

``` shell
[mongodb-org-3.4]
name=MongoDB 3.4 Repository
baseurl=https://repo.mongodb.org/yum/redhat/7/mongodb-org/3.4/x86_64/
gpgcheck=0
enabled=1
```

Em seguida, instale o mongo:

``` shell
yum install mongodb-org
```
``` shell
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

Coloque o mongo no serviço de inicialização e inicie o serviço

``` shell
systemctl enable mongod
```
``` shell
systemctl start mongod
```

## Alterando os limites do MongoDB

Edite o arquivo `/etc/security/limits.conf` e adicione as linhas abaixo no fim do arquivo:

``` shell
# End of file

mongod soft nofile 64000
mongod hard nofile 64000
mongod soft nproc 64000
mongod hard nproc 64000

```

Edite o arquivo /etc/mongod.conf e altere as linhas abaixo:

``` shell
#security:

para

security:
  authorization: disabled

```

Reinicie o serviço do mongo:

``` shell
systemctl restart mongod
```
Conecte no mongodb para criar o banco de dados do CITSmart e configurar a senha de admin:
``` shell
mongo
```
``` shell
MongoDB shell version v3.4.23
connecting to: mongodb://127.0.0.1:27017
MongoDB server version: 3.4.23
>
```

Execute o comando abaixo para criar o usuário e dar permissão:

```shell
use admin
db.createUser({
user: "admin",
pwd: "admin",
roles:[
{ role: "root", db: "admin" },
{ role: "dbOwner", db: "citsmart" }
]
})
```

A seguinte saída deverá aparecer:
```shell
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

## Próximo passo

[Realizando o deploy do CITSmart][1]

[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/deploy-citsmart.html
