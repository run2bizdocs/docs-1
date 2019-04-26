Description: Release Notes from CITSmart Version 8.0.0.5 of 04/22/2019

# Version 8.0.0.5
_04/22/2019_


## Problems Fixed

| Problem  | Description                                                                                                                                              |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3360     | Problem Mgmt. - Error retrieving the definitive Solution                                                                                                |
| 3361     | Problem Mgmt. - Error retrieving the closure field                                                                                             |
| 3362     | Problem Mgmt. - Errer retrieving known error                                                                                                    |
| 3363     | Configuration Mgmt. – Error retrieving Completed Changes related to the Configuration Item                                                        |
| 3364     | Release Mgmt. – Error linking Change closed in Release                                                                                       |
| 3365     | Problem Mgmt. – Interface suitability to display the fields "Associated error message" and "Diagnostics"                                          |
| 3366     | Change Mgmt. – Error retrieving Simplified Risk                                                                                                     |
| 3393     | Relese Mgmt. – Return of Business Rule when linking a change that has CI linked to a Release, automatically linking the CI to the Release |
| 3282     | Event Mgmt. – Failure when Edit a Zabbix Generic Manager                                                                                                 |
| 3115     | Event Mgmt. – Better rendering of the Ticket Mgmt. screen                                                                                             |
| 3394     | Release Mgmt. – System doubles attachments when forward flow                                                                                               |
| 3388     | Problem Mgmt. – Saving the known error does not set the archiving field and the system cannot recover the knowledge                              |
| 3419     | Change Mgmt. – System does not retrieve attachment placed in Revision and closure field                                                                    |

*Known error and solution*

Note the following scenario:

-   Preconditions:

    1.  The client will be upgrading from version 7 to version 8.0.0.5;

    2.  The consultant did not parametrize in the Problem Portfolio the folder 
        to save the Known Error knowledge base;

-   What happens:

    1.  The user accesses the Problem Management screen;

    2.  The user informs the Root Cause field and attempts to save the knowledge base;

    3.  When open the Knowledge Base screen for saving, the system presents the message 
        that the user does not have the permission;

-   Why does it happen?

    1.  The message appears because the consultant did not informed the folder to save 
        the known error in the Problem Portfolio;

    2.  Once you try to save the known error, the system does not identify the folder 
        and sends the message;

    3.  In these cases, contact the Citsmart Support to make the correctness of this 
        register;

    4.  Make the configuration of the known error saving folder on the Problem Portfolio 
        screen;

    5.  In the next registration the message will not be repeated.
    
    
    
Get the packages:

**SM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Enterprise/8.0.0.5/CitsmartITSM-Enterprise-8.0.0.5.war.zip  
  
**Inventory**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip  
  
**EVM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip  
  
**Neuro**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.8.war.zip  
  
**Audit**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.2.0.zip

