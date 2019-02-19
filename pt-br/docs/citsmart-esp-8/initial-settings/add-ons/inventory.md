Title: Habilitar o CITSmart Inventory

# Habilitar o CITSmart Inventory

CITSmart Inventory - O Inventário é um componente do CITSmart ESP que permite registrar e gerenciar rotinas de inventário. Ele permite que se forneça informações sobre os itens de configuração de sua organização e gerencie-os por meio do processo do Gerenciamento de Configuração.  

Antes de começar
------------

O CITSmart Inventory trabalha em conjunto com [Monitor de Eventos CITSmart - EVM][1] e como um coletor de dados (ex.: pacotes XML) o EVM serve como repositórios para esta informação. Portanto, para ativar o Inventory, deve-se primeiro configurar o EVM.  


## Procedimento

1. Fazer download do pacote war do componente Inventory;  
2. Descompactar os arquivos;  
3. Copiar o pacote para a pasta de implantação do servidor de aplicativos Wildfly;  
4. Configurar as [Propriedades do Sistema][2] com os dados da instância CITSmart ESP;

## O que fazer depois  

Para testar o Inventory, [configurar][3] as conexões na instância CITSmart ESP.

## Relacionado

[Habilitar o Event Monitor no CITSmart][4]

[1]:/pt-br/citsmart-esp-8/initial-settings/add-ons/event-monitor.html
[2]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html#configuracao-do-system-properties
[3]:/pt-br/citsmart-esp-8/processes/event/configuration/set-inventory-connection.html
[4]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/22/2019 - João Pelles  
	
