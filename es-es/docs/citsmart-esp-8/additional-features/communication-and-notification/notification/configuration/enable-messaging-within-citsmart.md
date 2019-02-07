title: Habilitar la mensajería dentro del CITSmart
Description: Ofrece un canal de comunicación entre el solicitante (Smart Portal) y el técnico (área de solicitud de servicio/ticket) vía mensaje (correo electrónico).
#Habilitar la mensajería dentro del CITSmart


CITSmart ofrece un canal de comunicación entre el solicitante (Smart Portal) y
el técnico (área de solicitud de servicio/ticket) vía mensaje (correo
electrónico). Esta comunicación tiene por objeto facilitar la resolución de un
llamado. Este conocimiento reúne información pertinente a la configuración del
servicio de mensajería.

Procedimiento
-----------------

1.  Para que el servicio de mensajería esté disponible dentro del CITSmart, es
    necesario establecer el parámetro 417 con el número del ID del modelo de
    correo electrónico que contenga algunas variables para poder ser enviado a
    mensajería;

2.  A continuación se enumeran las claves para el envío de correo electrónico:

    -  \${IDSOLICITUDSERVICIO} - Número del ticket (clave pública);

    -  \${COMMENTTEXT} - Descripción del Comentario hecho en la mensajería;

    -  \${DATETIMECREATED} - Fecha en que se registró el comentario;

    -  \${USERNAME} - Nombre de usuario que ha introducido el comentario;

    -  \${REQUESTERNAME} - Nombre del solicitante;

    -  \${REQUESTRESPONSIBLENAME} - Nombre del técnico responsable por el servicio
         del ticket.



Relacionado
-------

[La área de trabajo del service desk](/es-es/citsmart-esp-8/processes/tickets/use/desktop-of-service-desk.html)

[Configurar parametrización - ticket](/es-es/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ticket.html)

[Configurar modelo de email](/es-es/citsmart-esp-8/platform-administration/email-settings/email-templates-configure-email-template.html)

[Gestionar mis solicitudes por el Smart Portal](/es-es/citsmart-esp-8/processes/portfolio-and-catalog/use/request-through-Smart-Portal.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/25/2019 - Anna Martins
