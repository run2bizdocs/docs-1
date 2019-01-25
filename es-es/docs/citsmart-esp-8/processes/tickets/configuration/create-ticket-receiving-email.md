title: Crear ticket automático desde el recebimiento del correo electrónico
Description: Permite la creación automática de un ticket cuando se envía un mensaje de correo electrónico a una dirección determinada.
#Crear ticket automático desde el recebimiento del correo electrónico


Esta funcionalidad permite la creación automática de un ticket cuando se envía
un mensaje de correo electrónico a una dirección determinada. En este contexto,
la solución monitorea constantemente la presencia de mensajes en el buzón de
correo, y si algún mensaje tiene el estado no leído, éste se utilizará para
registrar un nuevo ticket.

Por ejemplo, un usuario podría solicitar cierto servicio enviando un mensaje a
servico\@empresa.com, después de recibir el correo electrónico, la
funcionalidad, luego que comprobar que existe un mensaje, registra un ticket
automáticamente. Es importante destacar que después del registro del ticket, el
correo electrónico es marcado como leído.

Antes de empezar
--------------------

Para crear un ticket a través del recibimiento del correo electrónico, es
necesario configurar previamente una cuenta de correo electrónico para permitir
el acceso a través del IMAP.

Procedimiento
-----------------

*Paso 1*

1.  Acceder al menú principal Sistema \> Acciones Automaticas \> Acciones de
    Incidentes/Requerimientos/Procedimientos (ver conocimiento Registrar Acción
    Automatica de Incidentes/Requerimientos/Precedimientos).

*Paso 2*

1.  Crear acción automatica de correo electrónico al acceder al menú principal
    Sistema \> Configuración \> Configuración de la acción automatica a través
    de correo electrónico (ver conocimiento Crear acción automatica de correo
    electrónico).

*Paso 3*

1.  Crear Rutina Batch al acceder al menú principal Sistema \> Procesamiento
    Batch (ver conocimiento Procesamiento Batch):

    -   Descargar el guión.


Relacionado
-------

[Registrar acciones automaticas de incidentes/solicitudes/procedimientos](/es-es/citsmart-esp-8/additional-features/automation-of-operation/configuration/register-automatic-actions-incident-request-procedure.html)

[Crear acción automatica via correo eletronico](/es-es/citsmart-esp-8/platform-administration/configuring-automatic-actions/email-create-automatic-action-via-email.html)

[Procesamiento Batch](/es-es/citsmart-esp-8/platform-administration/configuring-automatic-actions/batch-batch-processing.html)


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2ROl8PJLi-kszYhGzr17uvz-)'

Adjunto
------------
[Download - Comprobar email][1]


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/25/2019 – Anna Martins
    
[1]:/pt-br/citsmart-esp-8/processes/tickets/images/rotina-verificar-email.docx
  
