Title: Prepare environment

# Presentation


# Software and Download

!!! warning
    From this point, it will be necessary a subscription.
    The CITSmart Enterprise installation requires an operating system GNU/Linux with kernel equal or higher than 3.10.
    We recommend Red Hat, CentOS, Debian or Ubuntu.

To execute the CITSmart Enterprise, we'll download the necessary package, as the procedure about the product.

## Wildfly Application Server

!!! warning
    In this knowledge we'll use PostgreSQL.
    You can download the package of Oracle or MSSQL and make the changes as described for the PostgreSQL.

1. Download the package directly of the official repository through the link: http://download.jboss.org/wildfly/12.0.0.Final/wildfly-12.0.0.Final.tar.gz
2. Download directly the Java JDK8u172 of the official repository jdk-8u172-linux-x64.tar.gz:

![Screenshot](images/java-download.png)

Figure 1 - Java table

3. Download the jdbc module for the postgresql:http://files.citsmart.com/postgresql-jdbc-driver.tar.gz

## MongoDB Database Server

!!! warning
    In this knowledge we'll use the distribution GNU/Linux CentOS Linux release 7.5.1804.
    Download the MongoDB as its distribution.
    The version of MongoDB should be 3.4.

To find the download as its distribution: https://www.mongodb.com/download-center#community
To download the MongoDB for CentOS 7.5: https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-rhel70-3.4.15.tgz

## PostgreSQL/Oracle/MSSQL Database Server

!!! warning
    In the knowledge, we'll use the PostgreSQL with download of official repository.

The CITSmart Enterprise is consistent with PostgreSQL 9.2 or higher and the download will be done when configure the packages.

It's recommended that the Oracle or MSSQL Installation to be done as the information and best practices of each manufacturer:

    Oracle: https://docs.oracle.com/cd/E11882_01/server.112/e10897/toc.htm
    MSSQL: https://docs.microsoft.com/en-us/sql/database-engine/install-windows/install-sql-server

## Apache Solr Indexing Server

!!! warning
    The version homologate of the Apache Solr is 6.4.2.

    Solr 6.4.2: http://files.citsmart.com/solr-6.4.2.zip
    Configurations to the knowledge base: http://files.citsmart.com/base_conhecimento_configs.zip

Download of assets files to CItsmart

    http://files.citsmart.com/assets.tar.gz

