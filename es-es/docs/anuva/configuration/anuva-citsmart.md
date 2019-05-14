Title: Disponer Anuva en la interfaz CITSmart
# Disponer Anuva en la interfaz CITSmart

Anuva ya se integra nativamente al CITSmart, entonces es muy fácil añadirla a su entorno.

Procedimiento
-----------
1. Con acceso de administrador, acceda a la pantalla de parámetros del CITSmart;

2. Cambiar el valor del parámetro “402 Anuva Assistant - External URL” 
para http://<Su-Instancia>.anuvaassistant.com

3. Cambiar el valor del parámetro “441 Anuva Assistant - Conversation API” 
para http://< Su-Instancia ><sigla-idioma>.anuvaassistant.com/webhooks/rest/webhook 
y hacer clic en "Guardar"

4. Cambiar el valor del parámetro “442 Anuva Assistant - Parameters API” 
para http://< Su-Instancia ><sigla-idioma>.anuvaassistant.com/conversations/

!!! Abstract "NOTA"
    
    Para la abreviatura de los idiomas, utilice EN (Inglés) ES (Español) y PT (Portugués-Brasil).
   
!!! Abstract "NOTA"

    Si estos parámetros no están disponibles, actualice su versión de CITSmart.
   
 
!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
