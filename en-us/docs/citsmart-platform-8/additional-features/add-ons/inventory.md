Title: Implement CITSmart Inventory

# Implement CITSmart Inventory

CITSmart Inventory is a component of the CITSmart Platform that enables you to collect, register and manage information from IT assets. It enables you to manage the lifecycle of your organization's configuration items from the Configuration Management process.  


## Before getting started

CITSmart Inventory works in conjunction with [CITSmart Event Monitor - EVM][1] and as a data collector (eg XML packages) and EVM serves as a repositories for this information. Therefore, to enable Inventory, you must first configure EVM.  


## Procedure  

1. [Install][1] the Wildfly application server
2. Download the WAR package from the EVM component;  
3. Unpack the files;  
4. Copy the package to the deployment folder of the Wildfly application server;  
5. Configure [System Properties][2] with data of CITSmart Platform instance;

## What to do next  

To test the Inventory, [configure][3] the connections in the CITSmart Platform instance.

## Related

[Implement CITSmart Event Monitor][4]

[Asset and Configuration Management][5]

[1]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation.html
[2]:/en-us/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation.html#configuracao-do-system-properties
[3]:/en-us/citsmart-platform-8/processes/event/configuration/set-inventory-connection.html
[4]:/en-us/citsmart-platform-8/initial-settings/add-ons/event-monitor.html
[5]:/en-us/citsmart-platform-8/processes/configuration/overview.html

!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/22/2019 - João Pelles  
	
