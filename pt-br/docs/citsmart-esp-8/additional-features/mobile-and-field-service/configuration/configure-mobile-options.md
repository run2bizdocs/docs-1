title: Configurar as opções de mobile
Description: Tem por objetivo configurar as opções de Menu para o uso via mobile. 
#Configurar as opções de mobile
Esta funcionalidade tem por objetivo configurar as opções de Menu para o uso via mobile. Ao configurar estas opções, as mesmas estarão disponíveis no aplicativo CITSmart SM e no site ITSM na versão mobile.

!!! Abstract "ATENÇÃO"

    O aplicativo SM permite utilizar as funcionalidades da versão *web* escolhidas na versão mobile, tendo as mesmas funções que a versão desktop.  

Antes de começar
----------------

É necessário instalar, previamente, o aplicativo CITSmart Enterprise ITSM no
dispositivo mobile.

Procedimento
------------

1.  Acessar a funcionalidade através da navegação no menu principal Acesso e
    permissão \> Configuração das opções de mobile;

2.  Clicar no botão "Novo";

3.  Preencher os campos necessários (título, a situação, a descrição nas três
    línguas do CITSmart [português, inglês e espanhol] e selecionar o menu que
    melhor se ajusta à funcionalidade desejada);

4.  Clicar em "Gravar" para efetuar a operação.


!!! Abstract "ATENÇÃO"

    Para que o técnico em campo, possa visualizar tickets apenas atribuídos a ele
    em sua listagem de solicitações, o atendente/administrador deverá setar o parâmetro 435 para
    a opção “Sim”.

### Obter assinatura em atendimento de campo


A opção para que um técnico possa colher assinatura de um validador em
campo, seguirá a configuração:

*No CITSmart*:

1.  Acessar o menu principal Processos \> Gerência de Portfólio e Catálogo \>
    Portfólio;

2.  Buscar pelo portfolio pretendido e clicar em “Avançar”;

3.  Selecionar o serviço e clicar em “Avançar”;

4.  Clicar na guia **Contratos**;

5.  Selecionar o contrato e clicar em “Avançar”;

6.  Clicar na guia **Requisições**;

7.  Selecionar a atividade e clicar em “Editar”;

8.  Configura para a opção “Sim” o campo **Exige assinatura para Mobile**;

9.  Clicar em “Gravar”.

*No mobile*:

1.  Ao capturar um ticket (usando o mobile), o técnico deve preencher os
    campos disponibilizados e ao colocar o ticket com status de “Resolvido”, o
    campo de **Assinaturas** ficará ativo para que se possa colocar o Número do
    registro, o Nome e a Assinatura do validador em campo. Esta assinatura será
    feita com o dedo na tela do mobile;

2.  Clicar no botão “Opções” e em seguida em “Gravar e avançar o fluxo”;

3.  O ticket não aparecerá mais na listagem do técnico.

4.  O atendente/administrador verá em sua listagem de solicitações (no CITSmart), o ticket atendido
    pelo técnico (via mobile) com o status “Resolvido” e ao abrir poderá visualizar
    assinatura colhida também.

Relacionado
-----------

[Manual do usuário do aplicativo mobile CITSmart Enterprise ITSM (Android)](/pt-br/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-android.html)

[Manual do Usuário do aplicativo mobile CITSmart ITSM Enterprise (iOS)](/pt-br/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-ios.html)

[Configurar parametrização - ticket](/pt-br/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ticket.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/17/2019 – Larissa Lourenço
