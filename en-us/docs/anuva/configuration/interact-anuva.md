Title: How to interact with other systems
# How to interact with other systems

In order for Anuva to interact with other systems, it is necessary to add a custom ability in the dialog. 

The query is made through a Rest API, which must be made available by the system that holds information of interest to the user. Eg.: search for information on the status of a ticket, creation of tickets, generation of bills in the system.

Procedure
-----------

1. Access the menu “Dialogs” and click on “New”;

2. Complete the information of the **Interest** section;

3. In the **Ability** section, select the type Customized;

4. Complete API Section information, including body example and response;

5. If necessary, enter the heading;

6. In the Answers section, we have two action options:


    a) Answers in memory: In this case, the value returned by the API is associated with the selected attribute;
 
    b) Answers in text: Returns a text message to the user.
  
  
!!! Abstract "NOTA"

    A integração precisa ser homologada pela CITSmart, sendo assim que após configurar
    esta habilidade é preciso abrir um ticket para que se faça a homologação da integração.
    
    
!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
   
