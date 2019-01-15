Title: Enable Inventory

# Enable Inventory 

CITSmart Inventory - Inventory is a component of CITSmart ESP that allows you to register and manage inventory routines. It lets you bring information about your organization's configuration items and manage them through the Configuration Management process.  

Inventory works in conjunction with [CITSmart Event Monitor - EVM] [1]. Inventory works as a data collector (eg XML packages) and EVM serves as a repositories for this information. Therefore, to enable Inventory, you must first configure EVM.  


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

