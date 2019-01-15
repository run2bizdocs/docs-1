Title: Enable Inventory

# Enable Inventory 

O CITSmart Inventory - Inventory - é um componente do CITSmart ESP que permite cadastrar e gerenciar rotinas de invetário. Com ele é possível trazer as informações dos iten de configuração de sua organização e gerenciá-las através do processo de Gerenciamento da Configuração.

O Inventory funciona em conjunto com o [CITSmart Event Monitor - EVM][1] - de modo que o Inventory funciona como coletor de dados (ex. pacotes XML) e o EVM funciona como reposítório para essas informações. Deste modo, para habilitar o Inventory é necessário, antes, configurar o EVM.

## Procedure  

1. Download the war package from the EVM component;  
2. Unpack the files;  
3. Copy the package to the deployment folder of the Wildfly application server;  
4. Configure [System Properties][2] with data of CITSmart ESP instance;

## What to do next  

To test the Inventory, [configure][3] the connections in the CITSmart ESP instance.

## Related

[Enable CITSmart Event Monitor][1]

[1]:/en-us/citsmart-esp-8/initial-settings/add-ons/event-monitor.html
[2]:/en-us/citsmart-esp-8/processes/event/configuration/set-inventory-connection.html
[3]:/en-us/citsmart-esp-8/get-started/installation-and-upgrade/4.perform-installation.html

