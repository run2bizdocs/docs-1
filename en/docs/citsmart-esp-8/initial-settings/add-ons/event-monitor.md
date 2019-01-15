Title: Enable Event Monitor

# Enable Event Monitor

O Event Monitor - EVM - é um módulo que tem como objetivo ser o um intermediador entre o CITSmart ESP e soluções clientes (Ex.Nagios, CITSmart Inventoty), além de servir como repositório para guardar informações de eventos, geradas por ferramentas de monitoração ou de processo de inventário. 

Para habilitá-lo em um instância CITSmart ESP é necessário baixar o pacote WAR e realizar deploy no servidor de aplicação Wildfly, que pode ser o mesmo do CITSmart ESP. É importante atentar-se que o EVM deverá estar disponível em uma porta diferente da aplicação ESP. Além disso, resssaltamos que o EVM não possui interface própria pois usa gerência é feita via aplicação ESP.

O EVM utiliza o banco de dados não relacional Mongo para salvar as informações, sendo assim, na configuração é necessário ter um ambiente Mongo online.

## Procedure

1. Baixar o pacote war do componente EVM;
2. Descompactar os arquivos;
3. Copiar o pacote para a pasta deployment do servidor de aplicação Wildfly;
4. Configurar [System Properties][2] com os dados de acesso ao Mongo e à instância CITSmart ESP;

## What to do next

Para testar o EVM, [configurar][1] as conexões na instância CITSmart ESP.

[1]:/en-us/citsmart-esp-8/processes/event/configuration/register-event-monitor-connection.html
[2]:/en-us/citsmart-esp-8/get-started/installation-and-upgrade/4.perform-installation.html#configure-system-properties