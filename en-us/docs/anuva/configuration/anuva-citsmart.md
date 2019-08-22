Title: Making Anuva available on the CITSmart interface
# Making Anuva available on the CITSmart interface

Anuva is already natively integrated with CITSmart, so it is easy to add it to your environment.

## Procedure

1. With Administrator access, access the CITSmart parameter screen;
2. Change the parameter value “402 Anuva Assistant - External URL” to http://<name-of-your-workspace>.anuvaassistant.com    
3. Change the parameter value “441 Anuva Assistant - Conversation API” to http://<name-of-your-workspace><acronym-language>.anuvaassistant.com/webhooks/rest/webhook and click on “Save”   
4. Change the parameter value “442 Anuva Assistant - Parameters API” to http://<name-of-your-workspace><acronym-language>.anuvaassistant.com/conversations/
5. Configure parameter 453 "Default Anuva Assistant Fallback Message", with a message that Anuva will answer whenever it has no answer to that question.

!!! note "NOTE"
    
    For the acronym of the languages, use EN (English) and PT (Portuguese-Brazil).
    If these parameters are not available, upgrade your version of CITSmart.
   
 
!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
