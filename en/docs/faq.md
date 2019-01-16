Title: Frequently Asked Questions

# Frequently Asked Questions

??? Question "How are documents ranked at the time of SOLR knowledge base search?"
    To rank the documents at the time of the search, Solr generates a score for each document.
    Thus, the document that has the highest score, is presented first and the others, with lower scores, in sequence.
    To calculate the document score Solr uses a standard algorithm, where the frequency of the searched term is checked. But, it is possible to change the punctuation with the use of the boosts.
    
	Solr's boosters can be used in two moments at the time of indexing or query, and their use in search is more common.
    Some boosters that may change the calculation of the score at the time of the survey are:
    
    *term^num: where "num" is the importance of the search term, example: incident^2;
    *And the field boosters and dismax and edismax functions can also be used to boost search.
    
	At ITSM, no booster is used, so far, only Solr's standard score calculation is used, and at the end of the search the ranking is done by the score and by the number of times the knowledge was voted / liked.
    
    Boosters are open for use, but to use them requires a better analysis of the importance of fields and documents added to Solr, by the knowledge base.
    
??? Question "How can Event Management become a business monitoring tool?"
    WEBSERVICE SCHEME FOR LEGACY SYSTEMS (BUSINESS MONITORING)
    You can connect the EVM component to any software, even one other than the one the Event Management module normally integrates (Nagios, Zabbix and Inventory) as long as the data sent via webservice follows a pre-set standard.
    
    Once the data is sent to the CITSmart Event Monitor, rules can be created (for example, with the Esper EPL) so that certain events are triggered according to some condition observed in the data.
    
    Example "Payroll":
    
    *Let's say it's the rule that one company does not hire more than 5 employees per industry.
    *The payroll program could send the minimum data of each hiring by department (defined in the company's budget plan), so that whenever the contraction number per department exceeds the pre-established limit, an event of "excess hiring "Could be fired.
    
??? Question "How do I access the service request from the e-mail notification?"
    To access the service request from the e-mail notification, proceed as follows:
    
    1. Make sure you are logged in to the system.
    2. Open the e-mail notification for the service request;
    3. The notification will have the request number with a hyperlink, just click on the number, which will then be redirected to the Service Management screen presenting the request information.
    
??? Question "How do I design the assets that make up my service?"
    The design of the assets that make up the service is done using the Service Map Design tool that provides efficient and effective drawings for managing the service during its life cycle, demonstrating the related configuration items.
    
    To carry out this design, proceed as follows (see knowledge Service attributes configuration):
    
    1. Access the Service Map Design feature for the Business Service Portfolio and Catalog Management → Portfolio and Catalog Management → Support Menu → Advanced Portfolio → Service Catalog → Next Service →Service Map;
    2. The screen for designing the assets that make up the business service will be presented;
    3. Perform the design
    4. Access the Service Asset Map Design functionality for the Support / Technical Service Portfolio and Catalog Management → Portfolio and Catalog Management → Support Menu → Advanced Portfolio → Service Catalog → Next Service → Service Map.
    5. The screen for designing the assets that make up the support / technical service will be presented;
    6. Perform the design
    
??? Question "How do I set a default group for the first level service request?"
    To set the default group for 1st level attendance, proceed as follows:
    
    1. Access the Group Registration feature by navigating in the main menu Access and Permission → Group. The group registration screen will be displayed, displaying the contracts;
    2. Make the registration of the group of 1st level, if not registered, and proceed with the completion of the fields;
    3. If the 1st level group is already registered in the system, carry out the group search and obtain their identification number (ID);
    4. After obtaining the 1st level group ID, access the CITSmart Parameters feature by navigating through the main menu. Parameterization → Parameters CITSmart.
    5. The CITSmart Parameters screen appears, click the CITSmart Parameters Search tab
    6. Perform the search for parameter "9 - Group ID Level 1"
    7. Select the same.
    8. The parameter registration screen with the contents of the selected record will be displayed, in the value field, enter the identification number (ID) of the 1st level group
    9. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    
    RULE: after setting the parameter, when registering a Service Request/Incident, if you have not informed the group to service the service, the group will be scaled, which was defined in the parameter For 1st level service.
    
??? Question "How to configure Nagios authentication via LDAP?"
    The Nagios authentication configuration via LDAP is:
    
    1. Change the thruk.conf file as follows:
    ```sh
    vim /etc/apache2/conf-available/thruk.conf
	```
    <Location /thruk/>
    Options ExecCGI FollowSymLinks
    AuthName "LDAP Authentication"
    AuthType Basic
    AuthBasicProvider ldap
    AuthLDAPURL ldap://auth01.citsmartcloud.com/dc=citsmart,dc=com?uid?sub?(objectClass=*)
    Require ldap-group ou=people,o=citsmartco,dc=citsmart,dc=com
    Require valid-user
    </Location>

    2. Run:
    ```sh
    /etc/init.d/apache2 restart
	```
    ```sh
    /etc/init.d/thruk restart
	```
	```sh
    /etc/init.d/nagios reload
	```
    
??? Question "How to configure the automatic satisfaction survey response?"
    The automatic response mechanism, which will answer automatically all service request satisfaction surveys, kicks in when the satisfaction survey is not filled out by the user within the deadline determined by the systems manager.
    
    To configure the automatic responses, proceed as instructed below:

    1. Configure the following system parameters which determine the behavior of the automatic response mechanism (see knowledge Parameterization rules - Provisioning and Logistics):
    Parameter 139: Determines a deadline, in days, the user has to fill out the satisfaction survey, before it is automatically filled out by the system;
    Parameter 152: Default rating which will be attributed to surveys that have been automatically filled out. Options: EXCELLENT, GOOD, REGULAR, POOR;
    Parameter 151: Activates or deactivates system automatic responses. Y to activate and N to deactivate.
    2. Access the Batch Processing feature (System → Batch Processing).
    3. The batch processing entry screen will be displayed, fill out the fields:
    Description: insert the description which will identify the processing. For example: "Automatic satisfaction survey response";
    Situation: the situation determines if this processing will be active or inactive. When it is inactive the requests will not be answered;
    Type: select the “Java Class” type;
    Schedule: determines when the activity will be executed, it is up to the administrator to determine the best time and recurrence ;
    Content: insert the text: br.com.centralit.citcorpore.quartz.job.AvaliarSolicitacoesNaoRespondidas;
    4. Click on the Save button to confirm the entry.
    
	RULE: from the moment of the entry, at the scheduled time and date, the unanswered requests (beyond the deadline defined on parameter 139) will automatically be answered (according to the value determined on parameter 152), in case parameter 151 has an "Y" value.

??? Question "How to configure the configuration Items lifecycle phases names?"
    The configuration of the CI lifecycle phases names can be performed through the GCAS Configuration Screen and through the CITSmart parameters screen. To perform this configuration, proceed as instructed below
    
    CONFIGURATION THROUGH THE GCAS CONFIGURATION SCREEN
    
	1. Access the GCAS Configuration feature navigating through the main menu ITIL Processes → Configuration Management → GCAS Configuration. Afterwards, the service assets and the management parameters (attributes) configuration screen will be displayed;
    2. Insert the parameters value (attributes):
    Name of the CIs Group which are in the Development Phase (i.e.: CIs in Development)
    Name of the CIs Group which are in the Production Phase (i.e.: CIs in Production)
    Name of the CIs group which are being confirmated (i.e.: CIs Being Confirmated).
    3. Click on the Save button to confirm the entry, at which time, date and user will be stored for a future audit.
    4. After configuring the parameters related to the CI lifecycle phases, the CI lifecycle phases' descriptions will be displayed on the Configuration Items Management screen, according to what was specified in the parameter value.
    
	CONFIGURATION THROUGH THE GCAS CONFIGURATION SCREEN
    
	1. Access the Citsmart Parameters feature (Parametrization → Citsmart Parameters).
    2. Then, the Citsmart Parameters screen will be displayed, click on the Search tab. The parameter search screen will be displayed;
    3. Perform a search for the parameter "92 - Name of The Ci Group is In Development Phase (e.g.: CIs in Development)"
    4. Select it. Then, the parameter registry screen featuring the selected entry data will be displayed.
    5. On the Value field, insert the name of the CI group in development.
    6. Click on the Save button to confirm the entry, at which time, date and user will be stored for a future audit.
    7. Search for the parameter "93 - Name of The CIs Group in Production Phase (e.g.: ICs em Produção)"
    8. Select it. Then, the parameter registry screen featuring the selected entry data will be displayed;
    9. On the Value field, insert the name of the CI group in production phase;
    10. Click on the Save button to confirm the entry, at which time, date and user will be stored for a future audit.
    11. Search for the parameter "93 - Name of The CIs Group in Confirmation Phase (e.g.: ICs em Produção)"
    12. Select it. Then, the parameter registry screen featuring the selected entry data will be displayed;
    13. On the Value field, insert the name of the CI group in confirmation phase;
    14. Click on the Save button to confirm the entry, at which time, date and user will be stored for a future audit.

??? Question "How to configure the service request notification e-mails?"
    When registering a service request, perform determined activities and its execution, the petitioner will be notified.
    
	In order for the notification be sent it is necessary to perform the following procedures :
    
    1. Access the Contract Services related to the business service Portfolio Management → Services Portfolio → Business Service → Contract → Services and technical service Portfolio Management → Service Portfolio → Business Service → Support/Technical Service → Contract → Services e and insert the e-mail template in the fields:
    "Incident/Request Opening E-mail Template"
    "Incident/Requistion Execution E-mail Template"
    "Incident/Request Ongoing Activities E-mail Template"
    
	RULE: if e-mail templates are not inserted, the notification will not be sent.

    2. Access the Group Register feature General Registration → Staff Management → Group.

    3. The Group Register screen will be displayed. If the group has already been registered in the system, search for it;
    4. Select it;
    5. The intended group entry screen will be displayed, determine if the e-mail notifications (opening, in progress and execution) related to the requests will be mandatory.
    
	RULE: if it is determined that notifications will be mandatory, when registering a service request, on the Incident/Request Service entry screen, these options will be selected already, not allowing any changes. But if it has been determined that notifications will not be mandatory, when registering a service request, these options will be available to be determined by the petitioner.
    
    6. On the Incident/Request Service Request screen, when registering a service request the rules related to the e-mail notifications will be established, determined in the group entry.
    
	RULE: when registering a service request, the notification will only be sent to the performer group, which is responsible for attending to the request. When the activities are in progress and then finished, the notifications will only be sent to the petitioner.
    
??? Question "How to define the obligatoriness of the linking change with IC?"
    The requirement of the change link to the CI is determined on the CITSmart Parameter screen. To determine this requirement, proceed as instructed below:

    1. Access the CITSmart Parameter feature navigating through the main menu.
    2. The CITSmart Parameter screen will be displayed, click on the Search tab.
    3. The parameter search screen will be displayed. Search for the parameter "85 - Verification of change link related to the configuration item (Default: Y)"
    4. Select it.
    5. Then, the parameter registry screen featuring the selected entry data will be displayed, on the value field, insert the "Y" value.
    6. Click on the Save button to confirm the entry, at which time, date and user will be stored for a future audit.
    7. After configuring the parameter, when registering a Configuration Item, the change link will be mandatory
    
??? Question "How to enable automatic e-mail reading routine?"
    When sending an e-mail to CITSmart support, the automatic e-mail will be read, if the e-mail refers to a request, the title of the e-mail will be verified, if it contains the word 'Request' and the Number of the request, if it contains, the e-mail will be stored as an occurrence in the relevant request.
    
    For this e-mail reading routine to work perfectly, the following procedures must be followed:
    
    1. Install the java 7 version, if it has lower version the routine will not work;
    2. Access the Citsmart Parameters feature by navigating in the main menu Parameterization → Citsmart Parameters.
    3. The Citsmart Parameters screen will appear, click the Citsmart Parameters Search tab.
    4. It will display the screen for parameter search, search the parameter "23-SMTP READ - Service Desk mail entry server" and select it;
    5. The parameter registration screen with the contents of the selected record will be displayed, in the value field, inform the e-mail entry server (eg orion.egrupo.com.br)
    6. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    7. Perform the search for the parameter "24 - SMTP READY - Service Desk mail inbox" and select the same;
    8. The parameter registration screen with the contents of the selected record will be displayed in the value field, inform the e-mail or login of the e-mail account (eg support.citsmart)
    9. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    10. Perform the parameter search "25 - SMTP READY - Service Desk E-Mailbox Password" and select the same;
    11. The parameter registration screen with the contents of the selected record will be displayed, in the value field, the password of the e-mail account;
    12. Click on the Save button to perform the operation, in this case the date, time and user will be stored automatically for a future audit;
    13. Perform the search of the parameter "26 - SMTP READY - Service Desk e-mail server provider (imaps, pops, imap, pop, etc)" and select it;
    14. The parameter registration screen with the contents of the selected record will be displayed in the value field, inform the protocol that will be used to read e-mails (eg imap or pop) and click the Save button to perform the operation, In this case the date, time and user will be stored automatically for a future audit.
    15. Perform the search for the parameter "27 - SMTP READY - Service Desk mail server port" and select the same.
    16. The parameter registration screen with the contents of the selected record will be displayed, in the value field, enter the port that will be used to access the mail server (587 for pop server or 995 for imap server);
    17. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    18. Perform the search for the parameter "28 - SMTP READY - Service Desk E-Mailbox Folder" and select it.
    19. The parameter registration screen with the contents of the selected record will be displayed, in the value field, inform the folder of the e-mail account's inbox;
    20. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    21. Perform the search for the parameter "200 - Enable routine for reading new e-mails automatically (ex: Y or N - Default 'N')" and select the same one;
    22. The parameter registration screen with the contents of the selected record will be displayed, in the value field, enter the "Y" value to activate the automatic reading routine;
    23. Click the Record button to perform the operation, in which case the date, time and user will be automatically stored for a future audit.
    
??? Question "How to enable the change module escalation rule?"
    The changes escalating rule is enacted on the CITSmart Parameter screen.
    
    To enable this rule, proceed as follows:

    1. Access the CITSmart Parameters feature navigating through the main menu Parametrization → CITSmart Parameters;
    2. The CITSmart Parameters screen will be displayed, click on the CITSmart Parameters Search tab;
    3. The CITSmart Parameters search screen will be displayed, search for the parameter "193 - Enable Change Escalation Rules (e.g. : Y or N - Default ´N´)"
    4. The parameter registry screen will be displayed according to the selected entry, on the Value field, insert the "Y" value to enact the change escalation.
    5. Click on the Save button to confirm the procedure, at which date, time and user will automatically be stored for a future audit.
    
??? Question "How to enable the portal?"
    In order for users to have access to the Portal or Smart Portal, you must enable it as follows:
    
    1. Access the Citsmart Parameters feature by navigating in the main menu Parameterization → Citsmart Parameters. The Citsmart Parameters screen will appear, click the Citsmart Parameters Search tab. Once this is done, it will display the screen for parameter search;
    2. Perform the parameter search "46 - Enable Portal as Citsmart home screen?" And select the same. After that, the parameter registration screen with the contents of the selected registry will be displayed, as shown in the figure below:
    3. In order for users to have access to the Portal or Smart Portal, you must enable it as follows:
    4. Access the Citsmart Parameters feature by navigating in the main menu Parameterization → Citsmart Parameters. The Citsmart Parameters screen will appear, click the Citsmart Parameters Search tab. Once this is done, it will display the screen for parameter search;
    
??? Question "How to enable the satisfaction survey?"


??? Question "How to enable the scheduling rule of the problems module?"


??? Question "How to enable the service requests escalation rule?"


??? Question "How to improve the performance of CITSmart Enterprise ITSM?"


??? Question "How to integrate the client company AD into CITSmart Enterprise ITSM that is in the cloud offered by CITSmart Corporation?"


??? Question "How to link staff members (users) to a group?"


??? Question "How to navegate the screens using the CITSmart Enterprise ITSM controls?"


??? Question "How to relate group to contract?"


??? Question "How to relate unit to contract?"


??? Question "How to replace each image of the CITSmart Enterprise ITSM logos?"


??? Question "How to setup the SOLR feature?"


??? Question "To which recipient will be sent notifications of ICs?"


??? Question "What does it take to configure an IC that is physically on the client's corporate network to be inventoried by the CITSmart Enterprise ITSM that is in the cloud offered by CITSmart Corporation?"


??? Question "What is the attachment upload features file size limit?"


??? Question "What is the Fato table of the service request module and how to insert data?"


??? Question "What is the impact of the "Solver Group" filter on the behavior of Inquiries and Incidents searches?"


??? Question "What is the meaning of each inventory status of CIs?"


??? Question "What is the meaning of each privacy a knowledge can have in the knowledge base?"


??? Question "What is the set of scripts indicated for the complete exclusion of a portfolio?"


??? Question "What is the set of scripts set to clear all inventory data and configuration items?"


??? Question "What is the type of permission for the Logdados table backup folder?"


??? Question "When does data synchronization occur with LDAP?"


??? Question "When is removed the data from the Logdata table?"


??? Question "When is the Logdata table Information deleted?"


??? Question "Why are the schedules created by the tool different from the current time?"


??? Question "Why in some reports does the same request appear more than once?"


??? Question "Why is the result "Empty Report" when generating the reportQuantitativeControlPercentual when selecting in the filter the situation "in progress" and the "solver group"?"


??? Question "Why will service request numbering not always follow a strict / perfect sequential order on the service request screen or in some reports?"


??? Question "Will the backup be overwritten or will there be a file for every day?"














