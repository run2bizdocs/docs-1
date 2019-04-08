Title: How to make Anuva available in CITSmart
# How to make Anuva available in CITSmart

Anuva is already natively integrated with CITSmart, so it's easy to add it to your environment.

Procedure
-----------
1. With Administrator access, access the CITSmart parameter screen 

2. Change the parameter value “402  	Anuva Assistant - External URL” 
   to http://<Your-Instance>.anuvaassistant.com
    
3. Change the parameter value “441 Anuva Assistant - Conversation API” to 
   http://< Your-Instance >< acronym-language>.anuvaassistant.com/webhooks/rest/webhook 
   and click on “Save”
   
4. Change the parameter value “442 Anuva Assistant - Parameters API” to 
   http://< Your-Instance >< acronym-language>.anuvaassistant.com/conversations/


!!! Abstract "NOTE"
    
    For the acronym of the languages, use EN (English), ES(Spanish) and 
    PT (Portuguese-Brazil).
   
!!! Abstract "NOTE"

    If these parameters are not available, upgrade your version of CITSmart.
   
 
!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
