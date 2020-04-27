title: Configurar o Audit
Description: O objetivo deste documento é fornecer o norteamento técnico de instalação e configurações para o uso da funcionalidade de Auditoria (Audit), versão 0.5.0 (itsm-audit-0.5.0) do CITSmart 9.

# Instalar e configurar o Audit

O objetivo deste documento é fornecer o norteamento técnico de instalação e configurações para o uso da funcionalidade de Auditoria (Audit) no CITSmart.

O Audit é um componente do CITSmart que tem por objetivo possibilitar realizar auditorias no sistema. A auditoria abrange três diferentes perspectivas:

- Auditoria de alteração em tabelas do sistema;

- Auditoria de acesso ao sistema (logon e logout);

- Auditoria de licenças do sistema;

Veja as principais característica do Audit:

- O Audit é um .war e é executado dentro do Wildfly junto ao CITSmart no diretório "deployments";

- O Audit utiliza o banco de dados não relacional Mongo para o armazenamento de dados. Assim, é necessário criar uma base de dados e um usuário com acesso a esta base (o usuário e senha devem ser iguais aos utilizados para acesso à outras bases do mongo - ex. base do EVM/INV).

- Conforme a utilização do Audit na aplicação, são criadas automaticamente, quatro coleções (collections) de dados no mongo: accessAudit, backupAudit, dataAudit, licenseAudit.

## Antes de começar

Para utilizar os recursos do Audit é necessário, antes, realizar as seguintes configurações de parâmetros:

- [X] Parâmetro 53 com valor igual à "DB_LOG", isso indica que os logs do sistema serão armazenados no banco de dados;

- [X] Parâmetro 52 com valor igual à "true", isso habilita a auditoria do sistema;


## Procedimento

### Criar base dados e acesso ao Mongo

Acesse o Mongo e execute as ações abaixo:

O primeiro passo é criar uma base no Mongo, aqui iremos nomeá-la de "itsm-audit":

```sh
use itsm-audit
db.user.insert({name: "blank", age: 30})
```

Depois você precisa criar um usuário e definir permissões de acesso à base criada anteriormente (lembre-se que é necessário criar um usuário com o mesmo nome do utilizado para outros componentes do CITSmart, como é o caso do EVM/INV). Em nosso caso, iremos criar o usuário de nome "admin":

```sh
use itsm-audit
db.createUser({
user: "admin",
pwd: "admin",
roles:[
{ role: "dbOwner", db: "itsm-audit" }
]
})
```

### Configurar entradas no subsystem do Wildfly

Adicionar as seguintes linhas ao standalone do wildfly no subsystem do activemq. Você pode fazer as configurações de duas formas, via CLI do Wildfly ou alterando o arquivo de configuração stantalone-full.xml. Opte por uma das alternativas e realize as configurações:


- **CLI**

Entre no CLI do Wildfly:

```sh
/opt/wildfly/bin/jboss-cli.sh --connect
```

Adicione as seguintes entradas:

```sh
/subsystem=messaging-activemq/server=default/jms-queue=ITSM.READ_DATA_AUDIT:add(entries=["queue/ITSM.READ_DATA_AUDIT","java:jboss/exported/jms/queue/queue/ITSM.READ_DATA_AUDIT"])

/subsystem=messaging-activemq/server=default/jms-queue=ITSM.READ_LICENSE_AUDIT:add(entries=["queue/ITSM.READ_LICENSE_AUDIT","java:jboss/exported/jms/queue/queue/ITSM.READ_LICENSE_AUDIT"])

/subsystem=messaging-activemq/server=default/jms-queue=ITSM.READ_ACCESS_AUDIT:add(entries=["queue/ITSM.READ_ACCESS_AUDIT","java:jboss/exported/jms/queue/queue/ITSM.READ_ACCESS_AUDIT"])

/subsystem=messaging-activemq/server=default/jms-queue=ITSM.READ_BACKUP_AUDIT:add(entries=["queue/ITSM.READ_BACKUP_AUDIT","java:jboss/exported/jms/queue/queue/ITSM.READ_BACKUP_AUDIT"])

```

- **XML**

Edite o arquivo standalone-full.xml

```sh
vi /opt/wildfly/standalone/configuration/standalone-full.xml
```
Localize a seguinte linha,

```sh
<jms-queue name="neuroOutputQueue" entries="queue/neuroOutputQueue java:jboss/exported/jms/queue/queue/neuroOutputQueue"/>
```

Adicione as seguintes entradas abaixo da linha anterior:

```java
<jms-queue name="ITSM.READ_DATA_AUDIT" entries="queue/ITSM.READ_DATA_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_DATA_AUDIT"/>
<jms-queue name="ITSM.READ_LICENSE_AUDIT" entries="queue/ITSM.READ_LICENSE_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_LICENSE_AUDIT"/>
<jms-queue name="ITSM.READ_ACCESS_AUDIT" entries="queue/ITSM.READ_ACCESS_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_ACCESS_AUDIT"/>
<jms-queue name="ITSM.READ_BACKUP_AUDIT" entries="queue/ITSM.READ_BACKUP_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_BACKUP_AUDIT"/>
```

### Configurar propriedades no Wildfly


Adicione a seguinte linha ao standalone do wildfly no system-properties. Assim, como na configuração anterior, você pode adicionar as propriedades via CLI ou editando o arquivo standalone-full.xml.

É muito provável que você possua um Mongo configurado, assim, é muito provável que as seguintes propriedades já estejam presentes no stantalone-full.xml, elas são necessárias para o correto funcionamento do Audit:

```sh
/system-property=mongodb.host:add(value="citmongo")
/system-property=mongodb.port:add(value="27017")
/system-property=mongodb.user:add(value="admin")
/system-property=mongodb.password:add(value="admin")
```

- **CLI**

Acesse o CLI e adicione a seguinte entrada:

```sh
/system-property=mongodb.dabase.audit:add(value="itsm-audit")
```

- **XML**

Edite o arquivo standalone-full.xml e adicione a seguinte propriedade:

```sh
<property name="mongodb.dabase.audit" value="itsm-audit"/>
```

!!! Warning "ATENÇÃO"
    Assim como foi falado anteriormente, é necessário configurar a conexão do banco mongo com host, port, user, pass e database (Provavelmente já existente, EVM e Inventory utilizam essas configurações). É necessário que o usuário (Mongo) inserido tenha as devidas permissões para leitura e escrita no banco informado.

### Realizar o deploy do Audit

Baixe o pacote do Audit no servidor do CITSmart, descompacte-o e copie o arquivo .war para o diretório "deployments" do Wildfly:

```sh
cp itsm-audit-0.5.0.war /opt/wildfly/standalone/deployments/
```

### Parametrizar o Audit no CITSmart

Após o correto deploy do Audit, acesse o CITSmart, localize o menu Parametrização > Parâmetros CITSmart, localize o parâmetro de número 425 e insira a URL do Audit:

```html
https://127.0.0.1:8443/itsm-audit/
```

Após esses passos e configurações, a auditoria já deve estar em execução.

## Relacionado

[Realizar auditoria no sistema](/pt-br/citsmart-platform-9/platform-administration/logs-and-auditing/system-audit.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 9.0 &nbsp;&nbsp;
    <b>Updated:</b>04/25/2020 – Infra Team
