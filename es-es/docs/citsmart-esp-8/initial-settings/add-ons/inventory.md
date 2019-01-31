Title: Habilitar Inventory

Habilitar Inventory
-----------------

CITSmart Inventory - El inventario es un componente del CITSmart ESP que permite registrar y administrar rutinas de inventario. El le permite proporcionar información sobre los elementos de configuración de su organización y administrarlos a través del proceso de la Gestión de Configuración.  

El Inventory trabaja en conjunto con el [Monitor de Eventos CITSmart - EVM][1] y como un colector de datos (ej.: paquetes XML); el EVM sirve como repositorios para esta información. Por lo tanto, para activar el inventario, primero debe configurar el EVM.  


Procedimiento
-------------

1. Descargar el paquete war del componente EVM;  
2. Descomprimir los archivos;  
3. Copiar el paquete a la carpeta de implementación del servidor de aplicaciones Wildfly;  
4. Configurar las [Propriedades del Sistema][1] con los datos de la instancia CITSmart ESP;

Lo que hacer después 
-------

Para probar el Inventory, [configurar][2] las conexiones en la instancia CITSmart ESP.

Relacionado
----------

[Habilitar Event Monitor][3]

[1]:/es-es/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html
[2]:/es-es/citsmart-esp-8/processes/event/configuration/set-inventory-connection.html
[3]:/es-es/citsmart-esp-8/initial-settings/add-ons/event-monitor.html

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 - Anna Martins  
	
