Title: Habilitar Event Monitor  

# Habilitar Event Monitor  

Event Monitor - EVM - é um módulo que visa ser um intermediário entre o CITSmart ESP e soluções de clientes (por exemplo, Nagios, CITSmart Inventoty), servindo como um repositório de informações de eventos, gerado por ferramentas de monitoramento ou processo de inventário.

Para ativá-lo em uma instância do CITSmart ESP, é necessário fazer o download do pacote WAR e executar a implementação no servidor de aplicativos Wildfly, que pode ser o mesmo que o CITSmart ESP. É importante observar que o EVM deve estar disponível em uma porta diferente do aplicativo ESP. Além disso, notamos que o EVM não possui sua própria interface, porque o gerenciamento é feito através do aplicativo ESP.

## Procedimento  

1. Baixar o pacote war do componente EVM;  
2. Descomprimir os arquivos;  
3. Copiar o pacote para a pasta de implementação do servidor de aplicação Wildfly;  
4. Configurar [Propriedades do Sistema][2] com dados de acesso do Mongo e a instância do CITSmart ESP;  

## O que fazer a seguir  

Para testar o EVM, [configurar][1] as conexões na instância do CITSmart ESP.  

[1]:/pt-br/citsmart-esp-8/processes/event/configuration/register-event-monitor-connection.html  
[2]:/pt-br/citsmart-esp-8/get-started/installation-and-upgrade/perform-installation.html



