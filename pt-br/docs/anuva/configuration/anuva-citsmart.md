Title: Disponibilizar ANUVA Assistant na interface CITSmart
#Disponibilizar ANUVA Assistant na interface CITSmart

A ANUVA já se integra nativamente ao CITSmart, tornando o processo mais fácil.

Procedimento
-----------
1. Com acesso de Administrador, acessar a tela de parâmetros do CITSmart;

2. Alterar o valor do parâmetro “402 Anuva Assistant - External URL” 
para http://<nome-do-seu-workspace>.anuvaassistant.com ;

3. Alterar o valor do parâmetro “441 Anuva Assistant - Conversation API” 
para http://<nome-do-seu-workspace><sigla-idioma>.anuvaassistant.com/webhooks/rest/webhook 
e clicar em “Salvar;

4. Altere o valor do parâmetro “442 Anuva Assistant - Parameters API” 
para http://<nome-do-seu-workspace><sigla-idioma>.anuvaassistant.com/conversations/ ;

!!! Abstract "NOTA"
    
    Para os idiomas: inglês (usar EN) e espanhol (usar ES).
   
!!! Abstract "NOTA"

    Se estes parâmetros não estiverem disponíveis, atualizar a versão do CITSmart.
   
 
!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
