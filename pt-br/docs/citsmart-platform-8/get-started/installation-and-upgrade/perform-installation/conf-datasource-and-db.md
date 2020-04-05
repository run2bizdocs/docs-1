Title: Configurando o Datasource e Drives de banco

# Configurando o Datasource e Drives de banco

Antes de criar um datasource, é necessário adicionar um módulo de um banco de dados ao sistema. Cada banco tem seu próprio driver de conexão, mas as configurações de todos partem do mesmo princípio: fazer o download do driver do fabricante, copiá-lo para o wildfly, configurar no sistema. As configurações serão feitas via jboss-cli, mas todas elas podem ser feitas também via XML no arquivo standalone-full.xml caso deseje.

No exemplo abaixo usaremos o driver do PostgreSQL. Cada banco de dados possui seu próprio método de configuração, recomendamos procurar na documentação do fabricante do banco de dados de sua escolha caso seja diferente de nossa documentação.

O download do driver JDBC do PostgreSQL pode ser encontrado no endereço https://jdbc.postgresql.org no link downloads. A versão do driver utilizado pela CITSmart é a 4.1 build 9.3 Build 1104.

```sh
wget https://jdbc.postgresql.org/download/postgresql-9.3-1104.jdbc41.jar
```

Acesse novamente o jboss-cli para adicionar o driver com comando abaixo (considerando que você tenha feito o download para pasta `/tmp`):

```sh
module add --name=org.postgres --resources=/tmp/postgresql-9.3-1104.jdbc41.jar --dependencies=javax.api,javax.transaction.api
```

Com esse comando, o driver será adicionado automaticamente a pasta `/opt/wildfly-12.0.0.Final/modules/org/postgres/main/`

Continue no CLI e execute o comando abaixo para incluir um datasource:

```sh
/subsystem=datasources/jdbc-driver=postgres:add(driver-name="postgres",driver-module-name="org.postgres",driver-xa-datasource-class-name=org.postgresql.xa.PGXADataSource
```

## Criando o banco de dados do CITSmart

Independente da arquitetura do banco (se instalado no nesmo servidor ou separado) os passos abaixo servem para se criar um banco de dados e um usuário para o CITSmart. No procedimento partimos do pressuposto que você tenha acesso ao SGBD. Acesse o PostgreSQL com comando abaixo:

```sh
su - postgres
```
Logo depois,
```sh
psql
```
Abaixo o retorno dos comandos:
```sh
[root@server /tmp]#  su - postgres
bash-4.2$
bash-4.2$ psql
psql (9.6.15)
Type "help" for help.

postgres=#
```
Crie um usuário e senha para acesso ao banco do CITSmart (substitua a SUA_SENHA com uma senha de preferência):

```sh
create user citsmartdbuser with password 'SUA_SENHA';
```
Abaixo o retorno do comando:
```sh
postgres=# create user citsmartdbuser with password 'SUA_SENHA';
CREATE ROLE
postgres=#
```
Crie um banco de dados para o CITSmart:
```sh
create database citsmart_db with owner citsmartdbuser encoding 'UTF8' tablespace pg_default;
```
Abaixo o retorno do comando:
```sh
postgres=# create database citsmart_db with owner citsmartdbuser encoding 'UTF8' tablespace pg_default;
CREATE DATABASE
postgres=#
```
Dê permissão para o usuário do CITSmart:
```sh
alter role citsmartdbuser superuser;
```
Abaixo o retorno do comando:
```sh
postgres=# alter role citsmartdbuser superuser;
ALTER ROLE
postgres=#
```

Saia do PSQL e do shell do usuário postgres:
```sh
\q
```
Logo após,
```sh
exit
```
Conforme abaixo:
```sh
postgres=# \q
bash-4.2$ exit
exit
[root@server /tmp]#
```
Caso o banco esteja rodando no mesmo servidor, é necessário liberar a conexão para o usuário do CITSmart. Edite o arquivo  `/var/lib/pgsql/9.6/data/pg_hba.conf` e inclua a seguinte linha:

```sh
# Database administrative login by Unix domain socket
local   all             postgres                                ident
```
!!! Warning "ATENÇÃO"

    Não altere a linha `local  all postgres  peer` que vem por padrão, inclua a linha acima logo abaixo desta.


Se o banco de dados estiver rodando em outro servidor é necessário liberar a conexão a partir do Wildfly. Para isso inclua a seguinte linha no mesmo arquivo pg_hba.conf, substituindo o pelo endereço de IP do servidor wildfly:

```sh
host citsmart_db citsmartdbuser WILDFLY_IP_ADDRESS/32 md5
```

## Configurando o datasource para o citsmart

Existem oito entradas de datasource para o citsmart_db, sendo que quatro são para o CITSmart e quatro para o CITSmart Neuro. O usuário e senha é citsmartdbuser e SUA_SENHA criados no passo anterior. Caso tenha criado usuário, senha e banco de nomes diferentes, altere nos comandos abaixo.

Conecte no jboss-cli e execute os seguintes comandos:

### Datasource citsmart

```sh
/subsystem=datasources/data-source="/jdbc/citsmart":add(jndi-name="java:/jdbc/citsmart",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasource citsmartFlow

```sh
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":add(jndi-name="java:/jdbc/citsmartFluxo",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasourece citsmart_reports

```sh
/subsystem=datasources/data-source="/jdbc/citsmart_reports":add(jndi-name="java:/jdbc/citsmart_reports",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmart_reports":write-attribute(name=idle-timeout-minutes,value=5)
```

### Datasource citsmartBpmEventos

```sh
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":add(jndi-name="java:/jdbc/citsmartBpmEventos",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=min-pool-size,value=10)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=max-pool-size,value=300)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=pool-prefill,value=true)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=blocking-timeout-wait-millis,value=60000)
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":write-attribute(name=idle-timeout-minutes,value=5
```

### Datasource citsmart-neuro

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro":add(jndi-name="java:/env/jdbc/citsmart-neuro",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=min-pool-size,value=10)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=max-pool-size,value=300)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=pool-prefill,value=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

### Datasource citsmart-neuro-app1

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app1":add(jndi-name="java:/env/jdbc/citsmart-neuro-app1",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app1":write-attribute(name=min-pool-size,value=10)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app1":write-attribute(name=max-pool-size,value=300)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app1":write-attribute(name=pool-prefill,value=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app1":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app1":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

### Datasource citsmart-neuro-app2

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app2":add(jndi-name="java:/env/jdbc/citsmart-neuro-app2",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app2":write-attribute(name=min-pool-size,value=10)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app2":write-attribute(name=max-pool-size,value=300)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app2":write-attribute(name=pool-prefill,value=true)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app2":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
```
```sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app2":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

### Datasource citsmart-neuro-app3

```sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app3":add(jndi-name="java:/env/jdbc/citsmart-neuro-app3",driver-name="postgres",connection-url="jdbc:postgresql://pgdata.citsmart.com:5432/citsmart_db",user-name="citsmartdbuser",password="exemplo123",driver-class="org.postgresql.Driver", enabled=true, use-java-context=true)
```
``` sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app3":write-attribute(name=min-pool-size,value=10)
```
``` sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app3":write-attribute(name=max-pool-size,value=300)
```
``` sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app3":write-attribute(name=pool-prefill,value=true)
```
``` sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app3":write-attribute(name=flush-strategy,value=FailingConnectionOnly)
```
``` sh
/subsystem=datasources/data-source="/env\/jdbc\/citsmart-neuro-app3":write-attribute(name=blocking-timeout-wait-millis,value=60000)
```

Caso ocorra algum erro na criação de algum datasource, use o comando `remove` para removê-lo e inicie novamente a criação:

Exemplo, no caso abaixo iremos remover o datasource citsmart

```sh
/subsystem=datasources/data-source="/jdbc/citsmart":remove
```

Antes de sair do jboss-cli, execute o comando reload para aplicar as alterações e faça um teste de conexão com a base de dados:

```sh
reload
```
E faça um teste de conexão com o banco usando os comandos abaixo. Lembrando que o resultado precisa ser `"outcome" => "success"`:

``` sh
/subsystem=datasources/data-source="/jdbc/citsmart":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/jdbc/citsmartFluxo":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/jdbc/citsmart_reports":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/jdbc/citsmartBpmEventos":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app1":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app2":test-connection-in-pool
```
``` sh
/subsystem=datasources/data-source="/env/jdbc/citsmart-neuro-app3":test-connection-in-pool
```

## Próximo passo

[Configurando o Wildfly][1]

[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-wildfly.html
