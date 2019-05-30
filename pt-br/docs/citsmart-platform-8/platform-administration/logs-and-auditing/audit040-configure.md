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
 
 - Adicionar as linhas que serão aqui apresentadas ao standalone do wildfly no subsystem do actuveqm;
 
 - Adicionar as linhas que serão aqui apresentadas ao standalone do wildfly no
 system-properties (igual é utilizado no CITSmart EVM e CITSmart Inventory);

 !!! Abstract "OBSERVAÇÃO"

     Configurar a conexão do banco mongo com host, port, user, pass e database (Provavelmente já existente, EVM e Inventory utilizam essas configurações).
     
    - O parâmetro 424 deve ficar em branco;
    
    - O parâmetro 425 deve ficar dessa forma (http://localhost:8080/itsm-audit);  

