Title: Disponibilizar Anuva na interface CITSmart
# Disponibilizar Anuva na interface CITSmart

A Anuva já se integra nativamente ao CITSmart, então é muito fácil adicioná-la ao seu ambiente.

## Procedimento

1. Com acesso de Administrador, acesse a tela de parâmetros do CITSmart
2. Altere o valor do parâmetro “402 Anuva Assistant - External URL” para http://<nome-do-seu-workspace>.anuvaassistant.com
3. Altere o valor do parâmetro “441 Anuva Assistant - Conversation API” para http://<nome-do-seu-workspace><sigla-idioma>.anuvaassistant.com/webhooks/rest/webhook e clique em “Salvar”
4. Altere o valor do parâmetro “442 Anuva Assistant - Parameters API” para http://<nome-do-seu-workspace><sigla-idioma>.anuvaassistant.com/conversations/


!!! note "NOTA"

    Para a sigla dos idiomas, use EN (Inglês) e PT (Português-Brasil).
    Se os parâmetros mencionados não estiverem disponíveis, atualizar a versão do CITSmart.


!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/07/2019 - Anna Martins
