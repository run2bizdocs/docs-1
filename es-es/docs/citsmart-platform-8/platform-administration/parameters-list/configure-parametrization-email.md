title: Configurar parametrización - correo electrónico
Description: La parametrización de "correo electrónico" permite configurar el envío de lectura de correo electrónico
#Configurar parametrización - correo electrónico
Podemos definir el correo electrónico como un método que permite componer, enviar y recibir mensajes a través de sistemas electrónicos de comunicación. La parametrización de "correo electrónico" permite configurar el envío de lectura de correo electrónico, informar el dominio de correo electrónico predeterminado de la empresa, entre otras acciones, a fin de permitir la utilización del servicio de correo electrónico para agregar mejor experiencia en el uso de los diversos recursos disponibles en las soluciones CITSmart, permitiendo el envío de informaciones a los usuarios.

Procedimiento
-------------

1.  Acceder al menú principal Parametrización \> E-mail;

2.  Definir los valores de los parámetros (atributos);

3.  Hacer clic en "Guardar";

4.  La lista siguiente presenta los parámetros del "correo electrónico" y la
    finalidad de cada uno:

| **#** |                                                  **Nombre**                                                  |                    **Valores posibles**                   |                                                                                                                                                                     **Finalidad**                                                                                                                                                                    |                                                                      **Orientaciones complementarias**                                                                      |
|:-----:|:------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|   10  |           SMTP ENVÍO - Origen notificaciones por correo electrónico de las solicitudes de servicio           |               Ej.: citsmart@centralit.com.br              |                                                                                        Informar el correo electrónico que se utilizará como origen del envío de las notificaciones referentes a las Solicitudes de Incidente/Solicitudes abiertas o alteradas.                                                                                       |                                                                                 No se aplica                                                                                |
|   11  | SMTP ENVÍO - requiere autenticación para enviar correo electrónico (por ejemplo, S o N - por default: 'N ' ) |                     S o N (Default: N)                    | Establecer si el envío de correo electrónico utilizado para notificaciones requiere autenticación. Si el correo electrónico configurado en el parámetro 10 no requiere autenticación, se debe definir el valor "N". Si el correo requiere autenticación, se debe definir el valor "S" y configurar las autentificaciones en los próximos parámetros. |                                    Si no se establece el valor para el parámetro, el sistema automáticamente definirá el valor: "N" (No).                                   |
|   12  |                       SMTP ENVÍO - Autenticación de usuario para el correo electrónico                       |                       Ej.: citsmart                       |                                                                                                Informar al usuario de correo electrónico para la autenticación. Si el e-mail requiere autenticación, debemos informar al usuario que va autenticarse.                                                                                                |                                                  Si no informa correctamente el usuario, no se realizará la autenticación.                                                  |
|   13  |                      SMTP ENVÍO - contraseña para la autenticación de correo electrónico                     |                                                           |                                                                                             Indicar la contraseña del correo electrónico para la autenticación. Si el e-mail exige autenticación, debemos informar la contraseña del usuario del e-mail.                                                                                             |                                               Si no se notifica la contraseña correctamente, no se realizará la autenticación.                                              |
|   14  |                           SMTP ENVÍO - Servidor para el envío de correo electrónico                          |                     Ej.: 172.20.0.200                     |                                                                       Informar el servidor SMTP, utilizado para el envío de correo electrónico. El servidor SMTP se encarga de enviar a los destinatarios los mensajes de correo electrónico de las notificaciones del sistema.                                                                      |                            Si no se notifica el servidor SMTP, no podrá realizar el envío de correos electrónicos de notificaciones del sistema.                            |
|   23  |                         SMTP LECTURA - Servidor de entrada de e-mail del Service Desk                        |                     Ej.: 172.20.0.200                     |                                                                                                             Informar el servidor de correo electrónico del Service Desk al que se accede a la lectura de mensajes de correo electrónico.                                                                                                             |                                                                                 No se aplica                                                                                |
|   24  |                  SMTP LECTURA - Usuario de la Bandeja de entrada de e-mails del Service Desk                 |                       Ej.: citsmart                       |                                                                                                  Informar la cuenta de correo electrónico del Service Desk que se utilizará para recibir los mensajes de correo electrónico enviados por el usuario.                                                                                                 |                                                                                 No se aplica                                                                                |
|   25  |                 SMTP LECTURA - Contraseña de la Bandeja de entrada del e-mail de Service Desk                |                                                           |                                                                                       Informar la contraseña de la cuenta de correo electrónico, que se indica en el parámetro 24, para acceder a la bandeja de entrada de correo electrónico del Service Desk.                                                                                      |                                                                                 No se aplica                                                                                |
|   26  |        SMTP LECTURA - Proveedor del servidor de e-mails del Service Desk (imaps, pops, imap, pop, etc)       |                         Ej.: imap                         |                                                                                                          Informar el protocolo del servidor de correo electrónico del Service Desk que se utilizará para la lectura de correos electrónicos.                                                                                                         |                                                                                 No se aplica                                                                                |
|   27  |                         SMTP LECTURA - Puerto del servidor de e-mail de Service Desk                         |                          Ej.: 143                         |                                                                                                                               Informar el puerto del servidor que se utilizará para la lectura de correos electrónicos.                                                                                                                              |                                                                                 No se aplica                                                                                |
|   28  |                  SMTP LECTURA - Carpeta de la bandeja de entrada de e-mail del Service Desk                  |                         Ej.: Inbox                        |                                                                                                                      Indicar la carpeta de la bandeja de entrada del e-mail de la cuenta de correo electrónico del Service Desk.                                                                                                                     |                                                                                 No se aplica                                                                                |
|   72  |                        SMTP LECTURA - Límite de e-mail cargados en Solicitud Servicio                        |                          Ej.: 20                          |                     Establecer el límite de correo electrónico que se cargará en la pantalla de solicitud de Servicio/Incidente. Al hacer clic en el botón "cargar correo electrónico" en la pantalla de Solicitud de Servicios/Incidentes, se cargará la cantidad de correos electrónicos según lo establecido en el parámetro.                     |                                                                                 No se aplica                                                                                |
|  199  |        SMTP ENVÍO - Autenticación El correo electrónico utiliza TLS / SSL? (Ej.: S o N - Default 'N')        |                     S o N (Default: N)                    |                                                                                                                                  Establecer si el sistema de correo electrónico utilizará la autenticación starttls.                                                                                                                                 | Si no se indica el valor 'S' para el parámetro, sólo afectará a los servidores que utilizan TLS/SSL en la autenticación, y el sistema no podrá enviar correos electrónicos. |
|  269  |                                    SMTP ENVIO - Puerto de envío de e-mail                                    | Ej.: 465 (puerto seguro SSL/TLS), 25 e 26 (puertos común) |                                                                                                                       Informar el puerto del servidor que se utilizará para enviar mensajes de correo electrónico al servidor.                                                                                                                       |                                                                                 No se aplica                                                                                |
|  297  |                 Deshabilita el envío de e-mails del sistema (Valores: "S" o "N" Default: "N")                |                     S o N (Default: N)                    |                                                                                                                                            Deshabilita todos los envíos de correo electrónico del sistema.                                                                                                                                           |                                                                                 No se aplica                                                                                |


Tabla 1 - Lista de parâmetros

!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 – Larissa Lourenço
