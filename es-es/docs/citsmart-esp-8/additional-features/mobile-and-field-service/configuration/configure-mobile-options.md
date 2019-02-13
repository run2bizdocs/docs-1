title: Configurar las opciones del móvil
Description: Configurar las opciones de Menú para el uso vía móvil.
#Configurar las opciones del mobile
Esta funcionalidad tiene por objetivo configurar las opciones de Menú para el uso vía mobile.

Antes de empezar
--------------------

Es necesario instalar previamente la aplicación CITSmart Enterprise ITSM en el
dispositivo móvil.

Procedimiento
-----------------

1.  Acceder al menú principal Acceso y Permisos \> Configuración de las opciones
    de móvil;

2.  Hacer clic en "Nuevo";

3.  Completar los campos necesarios (título, situación, descripción en los tres
    idiomas de CITSmart [Portugués, Inglés y Español] y seleccionar el menú que
    mejor se ajuste a la funcionalidad);

4.  Hacer clic en "Guardar";

!!! Abstract "ATENCIÓN"

    Para que el técnico en campo, pueda ver tickets sólo asignados a él/ella en su 
    lista de solicitudes, el asistente/administrador deberá establecer el parámetro 
    435 para la opción "Sí".
    
### Obtener signatura en atención de campo

La opción para que un técnico pueda colectar signatura de un validador en campo,
se va a seguir la configuración:

*En CITSmart*

1.  Acceder al menú principal Procesos \> Gestión de Portafolio y Catálogo \>
    Portafolio;
    
2.  Buscar un portafolio y hacer clic en "Avanzar";

3.  Seleccionar el servicio y hacer clic en "Avanzar";

4.  Hacer clic en la pestaña **Contratos**;

5.  Seleccionar un contrato y hacer clic en "Avanzar";

6.  Hacer clic en la pestaña **Solicitudes**

7.  Seleccionar la actividad y hacer clic en "Editar";

8.  Configurar para la opción "Sí" en el campo **Exige la firma para Móvil**;

9.  Hacer clic en "Guardar".

*En mobile*

1.  Al capturar un ticket (usando el mobile), el técnico debe completar los
    campos disponibles y, al poner el ticket con status de "Resuelto", el
    campo de **Signaturas** quedará activo para que se pueda poner el Número del
    registro, nombre y la signatura del validador en campo. Esta signatura será
    hecha con el dedo en la pantalla del mobile;
    
2.  Hacer clic en "Opciones" y después en "Guardar y avanzar flujo";

3.  El ticket no aparecerá más en la lista del técnico;

4.  El asistente/administrador verá en su lista de solicitaciones (en CITSmart), el ticket atendido
    por el técnico (por mobile) con status "Resuelto" y, al abrirla, podrá ver la signatura
    también colectada.




Relacionado
-----------

[Guía del usuario de la aplicación móvil CITSmart Enterprise ITSM (Android)](/es-es/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-android.html)

[Guía del usuario de la aplicación móvil CITSmart ITSM Enterprise (iOS)](/es-es/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-ios.html)

[Configurar parametrización - ticket](/es-es/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ticket.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/25/2019 – Anna Martins
