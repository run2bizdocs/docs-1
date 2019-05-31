title: Configurar o Audit 0.4.0
Description: O objetivo deste documento é fornecer o norteamento técnico de instalação e configurações para o uso da funcionalidade de Auditoria (Audit), versão 0.4.0 (itsm-audit-0.4.0) do CITSmart Workflow 8.
# Configurar o Audit 0.4.0

O objetivo deste documento é fornecer o norteamento técnico de instalação e configurações para o uso da funcionalidade de Auditoria (Audit), versão 0.4.0 (itsm-audit-0.4.0) do CITSmart Workflow 8.

Antes de começar 
-----------------

Veja as principais novidades da versão 0.4.0

 - Não é preciso ter um AcitiveMQ externo ativo;
 
 - Não é preciso ter um serviço executando o .jar da auditoria;
 
 - Audit agora é um .war e é executado dentro do Wildfly junto ao ITSM na pasta "\deployments";
 
Procedimento
------------

1. Adicionar as seguintes linhas ao standalone do wildfly no subsystem do activemq:

    ```java
    <jms-queue name="ITSM.READ_DATA_AUDIT" entries="queue/ITSM.READ_DATA_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_DATA_AUDIT"/>
    <jms-queue name="ITSM.READ_LICENSE_AUDIT" entries="queue/ITSM.READ_LICENSE_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_LICENSE_AUDIT"/>
    <jms-queue name="ITSM.READ_ACCESS_AUDIT" entries="queue/ITSM.READ_ACCESS_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_ACCESS_AUDIT"/>
    <jms-queue name="ITSM.READ_BACKUP_AUDIT" entries="queue/ITSM.READ_BACKUP_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_BACKUP_AUDIT"/>
    ```
2. Adicionar as seguintes linhas ao standalone do wildfly no system-properties (igual é utilizado no EVM e Inventory):  

    ```java
    <property name="mongodb.host" value="localhost"/>
    <property name="mongodb.port" value="27017"/>
    <property name="mongodb.user" value="mongodb"/>
    <property name="mongodb.password" value="mongodb"/>
    <property name="mongodb.dabase.audit" value="itsm-audit"/>
    ```
3.Teste
