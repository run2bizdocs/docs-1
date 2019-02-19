Title: Habilitar o CITSmart Inventory

# Habilitar o CITSmart Inventory

O CITSmart Inventory é um componente da Plataforma CITSmart que permite coletar, registrar e gerenciar informações de ativos de T.I. Ele possibilita gerenciar as os itens de configuração de sua organização a partir do processo de Gerenciamento de Configuração.  

Antes de começar
------------

O CITSmart Inventory trabalha em conjunto com o [Monitor de Eventos CITSmart - EVM][1] e como um coletor de dados (ex.: pacotes XML) o EVM serve como repositórios para esta informação. Portanto, para ativar o Inventory, deve-se primeiro configurar o EVM.  


## Procedimento

1. [Instalar][1] o servidor de aplicação Wildfly;
2. Fazer download do pacote WAR do componente Inventory;  
3. Descompactar os arquivos;  
4. Copiar o pacote para a pasta de implantação do servidor de aplicativos Wildfly (ex. /deployments);  
5. Configurar as [Propriedades do Sistema][2] com os dados da instância CITSmart;

## O que fazer depois  

Para testar o Inventory, [configurar][3] as conexões na instância CITSmart ESP.

## Relacionado

[Habilitar o CITSmart Event Monitor][4]

[1]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html
[2]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html#configuracao-do-system-properties
[3]:/pt-br/citsmart-esp-8/processes/event/configuration/set-inventory-connection.html
[4]:/pt-br/citsmart-esp-8/initial-settings/add-ons/event-monitor.html



!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/22/2019 - João Pelles  
	
