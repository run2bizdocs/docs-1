Title: Preguntas frecuentes - FAQ

# Preguntas frecuentes - FAQ

??? Question "¿Cómo son clasificados según el ranking los documentos en el momento de la consulta de SOLR en la base de conocimientos?"

    Para rankear (colocar) los documentos en el momento de la búsqueda, el Solr genera una puntuación (score) para cada documento.

    Así, el documento que posee la mayor puntuación, es presentado en primer lugar y los demás, con menor puntuación, en secuencia.

    Para calcular la puntuación de los documentos, Solr utiliza un algoritmo default, donde se comprueba la frecuencia del término (term frequency) investigado. Pero, es posible cambiar la puntuación con la utilización de los impulsores (boosts).

    Los impulsores del Solr pueden ser utilizados en dos momentos, en el momento de la indexación o consulta, siendo más común su uso en la búsqueda.

    Algunos impulsores que pueden cambiar el cálculo de la puntuación, en el momento de la búsqueda, son:
    
    -  term^num:donde el "num" es la importancia del término búscado, por ejemplo: incid ^ 2;

    -  y también puede ser utilizado los impulsores de campo y las funciones del dismax y edismax para impulsar la búsqueda.
    
    En el ITSM no se utiliza ningún impulsor, hasta el momento, sólo se utiliza el cálculo default de puntuación del Solr, y al final de la investigación se realiza la ordenación por la puntuación por la cantidad de veces que el conocimiento fue votado/gustado.

    Los impulsores están abiertos para el uso, pero para utilizarlos es necesario un análisis mejor de la importancia de los campos y de los documentos añadidos al Solr, por la base de conocimiento.

    
??? Question "¿Cómo puede la Gestión de Eventos convertirse en una herramienta de Monitorización de Negocios?"
    
    ESQUEMA DE WEBSERVICE PARA SISTEMAS LEGADOS (MONITOREO DE NEGOCIOS)
    Es posible conectar el componente EVM con cualquier software, incluso un diferente de los que el módulo de Gestión de eventos normalmente se integra (Nagios, Zabbix e Inventory), siempre y cuando los datos enviados (vía webservice) sigan un padrón preestablecido.

    Una vez que los datos se envían al CITSmart Event Monitor, se pueden crear reglas (por ejemplo, con el EPL de espera) para que determinados eventos se disparen de acuerdo con alguna condición observada en los datos.

    Ejemplo "Hoja/Nómina de pago":
    
    - Digamos que es una regla de una empresa no contratar a más de 5 empleados por sector.
    - El programa de nóminas podría enviar los datos mínimos de cada contratación por departamento (definido en el plan presupuestario de la empresa), de modo que cuando el número de contracción por departamento supera el límite preestablecido, un evento de "exceso de contratación " Podría ser disparado.
    
??? Question "¿Cómo acceder a la solicitud de servicio a partir de la notificación de e-mail?"
    
    Para acceder a la solicitud de servicio desde la notificación de correo electrónico, proceda de la siguiente manera:
   
    1. Asegúrese de que está conectado al sistema.
    2. Abra la notificación de correo electrónico referente a la solicitud de servicio;
    3. La notificación tendrá el número de solicitud con un hipervínculo, simplemente haga clic en el número, que luego será redirigido a la pantalla de Gestión de servicios presentando la información de la solicitud.
    
??? Question "¿Cómo hago el diseño de activos que componen mi servicio?"
   
    Se hace el diseño de activos que componen el servicio utilizando la herramienta de Diseño de Mapa de Servicio que proporciona diseños eficientes y eficaces para la gestión del servicio durante su ciclo de vida, demostrando los ítems de configuración relacionados.

    Para realizar este diseño, proceda de acuerdo con las siguientes instrucciones (ver conocimiento [Configurar atributos del servicio](/es-es/citsmart-esp-8/processes/portfolio-and-catalog/use/configure-services-attributes.html) ):
    
    1. Acceda a la funcionalidad de diseño de mapa del servicio referente al servicio de negocio Gerência de Portafolio y Catálogo → Gestión de Portafolio y Catálogo > Menu Apoyo > Avanzar Portafolio > Catálogo de Servicios > Avanzar Servicio > Mapa de Servicios;
    2. Se presentará la pantalla para el diseño de los activos que componen el servicio de negocio;
    3. Realice el diseño
   
    
??? Question "¿Cómo definir un grupo padrón para el atendimiento del primer nivel de la solicitud de servicio?"
   
    Para definir el grupo predeterminado para la atención de primer nivel, proceda de acuerdo con las siguientes instrucciones:
   
    1. Acceda a la funcionalidad de registro de grupo mediante la navegación en el menú principal Acceso y Permiso → Grupo. Se mostrará la pantalla de registro de grupo, mostrando los contratos;
    2. Realizar el registro del grupo de 1º nivel, si no está registrado, y proceder con el llenado de los campos;
    3. Si el grupo de primer nivel ya está registrado en el sistema, realice la búsqueda del grupo y obtenga su número de identificación (ID);
    4. Después de obtener el ID del grupo de primer nivel, acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal. Parametrización > Parámetros CITSmart.
    5. Se mostrará la pantalla Parámetros de CITSmart, haga clic en la pestaña Búsqueda de parámetros de CITSmart
    6. Realice la búsqueda del parámetro "9 - ID Grupo Nível 1"
    7. Seleccione el mismo.
    8. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, introduzca el número de identificación (ID) del grupo de primer nivel
    9. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
    
    REGLA: después de la configuración del parámetro, al realizar el registro de una Solicitud de Servicio/Incidente, si no ha informado al grupo para atención del servicio, será escalado el grupo, el cual fue definido en el parámetro para atención de 1º nivel.
    
??? Question "¿Cómo configurar la autenticación del Nagios vía LDAP?"
    
    La configuración de autenticación de Nagios a través de LDAP pasa por:
    
    1. Cambie el archivo thruk.conf de la siguiente manera:
    ```sh
    vim /etc/apache2/conf-available/thruk.conf
	```
    <Location /thruk/>
    Options ExecCGI FollowSymLinks
    AuthName "LDAP Authentication"
    AuthType Basic
    AuthBasicProvider ldap
    AuthLDAPURL ldap://auth01.citsmartcloud.com/dc=citsmart,dc=com?uid?sub?(objectClass=*)
    Require ldap-group ou=people,o=citsmartco,dc=citsmart,dc=com
    Require valid-user
    </Location>

    2. Ejecutar:
    ```sh
    /etc/init.d/apache2 restart
	```
    ```sh
    /etc/init.d/thruk restart
	```
	```sh
    /etc/init.d/nagios reload
	```
    
??? Question "¿Cómo configurar la respuesta automática de encuestas de satisfacción?"
    
    El mecanismo de respuesta automática, que responderá automáticamente a las encuestas de satisfacción de las solicitudes de servicio, se produce cuando la encuesta de satisfacción no es respondida por el usuario, dentro de un plazo definido por el administrador del sistema.

    Para realizar la configuración de las respuestas automáticas, proceda de acuerdo a las siguientes instrucciones (ver conocimiento Reglas de parametrización - Aprovisionamiento y Logistica):

    1. Configure los siguientes parámetros del sistema que definen el comportamiento del motor de respuesta automática:
    
    - Parámetro 139: Define el plazo máximo, en días, que el usuario tiene para responder la encuesta de satisfacción, antes de que ésta sea respondida automáticamente por el sistema;
    
    - Parámetro 152: Nota default que se asigna a las encuestas de satisfacción que se responden automáticamente. Opciones: OPTIMO, BUENO, REGULAR Y MALO;
    
    - Parámetro 151: Activa o desactiva las respuestas automáticas en el sistema. S para activar y N para desactivar.
    
    2. Acceda a la funcionalidad de procesamiento por lotes (Sistema > Procesamiento Batch).
    3. Se mostrará la pantalla de registro de procesamiento por lotes, complete los siguientes campos con la respectiva información:
    
    - Descripción: informe la descripción que identificará este proceso. Por ejemplo: "Respuesta automática encuesta de satisfacción";
    
    - Situación: la situación define si este proceso estará activo o inactivo. Cuando se encuentre inhabilitado las solicitudes dejarán de ser respondidas;
    
    - Tipo: seleccionar el tipo "Clase Java";
    
    - Programación: define cuando esta rutina se ejecutará, corresponde al administrador del sistema definir cuál es la mejor hora y frecuencia para la ejecución;
    
    - Contenido: informe el texto: br.com.centralit.citcorpore.quartz.job.AvaliarSolicitacoesNoRespuestas;
    4. Haga clic en el botón Grabar para realizar el registro.
    
	REGLA: a partir del momento de la grabación, en el horario y día programado, las solicitudes no respondidas (con plazo superior al definido en el parámetro 139) serán automáticamente respondidas (con el valor definido en el parámetro 152), si el parámetro 151 está con valor ' S'.

??? Question "¿Cómo configurar el nombre de las fases del ciclo de vida de los ICs (Ítems de configuración)?"
    
    La configuración de los nombres de las fases del ciclo de vida del IC se puede realizar desde la pantalla de Configuración del GCAS y desde la pantalla de Parámetros del CITSmart. Para realizar esta configuración, proceda de la siguiente manera:
  
    CONFIGURACIÓN A PARTIR DE LA PANTALLA DE CONFIGURACIÓN DEL GCA
    
    1. Acceda a la funcionalidad de configuración del GCAS mediante la navegación en el menú principal Procesos ITIL > Gestión de Configuración > Configuración del GCAS. Hecho esto, aparecerá la pantalla de configuración de los parámetros (atributos) de gestión de configuración y activos de servicio;
    2. Introduzca los valores de los parámetros (atributos):
    - Nombre del Grupo de ICs en la fase Desarrollo (Ej.: ICs en desarrollo)
    - Nombre del Grupo de ICs en la fase Producción (Ej: ICs en Producción)
    - Nombre del Grupo de ICs en la fase Producción (Ej: ICs en Homologación).
    3. Haga clic en el botón Grabar para realizar la operación, donde la fecha, hora y usuario se guardarán automáticamente para una futura auditoría.
    4. Después de la configuración de los parámetros referentes al nombre de las fases del ciclo de vida del IC, en la pantalla de Gestión de ítems de configuración se muestra la descripción de las fases del ciclo de vida del IC, tal como se especifica en el valor del parámetro.
    
	CONFIGURACIÓN A PARTIR DE LA PANTALLA DE PARÁMETROS DEL CITSMART
    
    1. Acceda a la funcionalidad de Parámetros del CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart.
    2. Después de eso, aparecerá la pantalla de Parámetros de CITSmart, haga clic en la pestaña de búsqueda de parámetros de CITSmart. Se mostrará la pantalla para la búsqueda de parámetros;
    3. Realiza la búsqueda del parámetro "92 - Nombre del Grupo de ICs en la fase Desarrollo (Ej: ICs en Desarrollo)";
    4.Seleccione el mismo. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    5. En el campo valor, introduzca el nombre del grupo de IC de la fase de desarrollo;
    6. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    7. Realiza la búsqueda del parámetro "93 - Nombre del Grupo de ICs en la fase Producción (Ej: ICs en Producción)";
    8. Seleccione el mismo. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    9. En el campo valor, introduzca el nombre del grupo de IC de la fase de producción;
    10. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    11. Realiza la búsqueda del parámetro "94 - Nombre del Grupo IC en la fase Homologación (Ej: ICs en Homologación)";
    12. Seleccione el mismo. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    13. En el campo valor, introduzca el nombre del grupo de IC de la fase de homologación;
    14. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.

??? Question "¿Cómo configurar las notificaciones de e-mail de solicitud de servicios?"
    
    Al registrar una solicitud de servicio, realizar otras acciones y cerrar la misma, el solicitante será notificado.
    
	Para que esta notificación sea enviada es necesario realizar los siguientes procedimientos:
    
    1. Acceda a los Servicios del Contrato relativos al servicio de negocio Gestión de Portafolio > Portafolio de Servicios > Servicio de Negócio > Contrato > Servicios y servicio técnico Gestión de Portafolio > Portafolio de Servicios > Servicio de Negócio > Servicio de Apoyo/Técnico > Contrato > Servicios e informe o modelo de e-mail en los campos:
        
	- "Modelo de correo electrónico Apertura Solicitud/Incidente"
        - "Modelo de E-mail en la finalización de Incidentes/Solicitudes"
        - "Modelo de E-mail en las demás acciones de Solicitudes/Incidentes" 
        
	    REGLA: si notifica los modelos de correo electrónico, no se enviarán las notificaciones.

    2. Acceda a la funcionalidad de Registro de Grupo mediante la navegación en el menú principal Registros Gererales > Gestión de Personal > Grupo;    
    3. Se mostrará la pantalla de registro de grupo. Si el grupo ya está registrado en el sistema, realice la búsqueda del grupo;
    4. Seleccione el mismo;
    5. Se mostrará la pantalla de registro del grupo determinado, defina si las notificaciones de correo electrónico (apertura, progreso y cierre) referentes a las solicitudes, serán de envío obligatorio;
    
	    REGLA: si ha determinado que las notificaciones serán obligatorias, al registrar una solicitud de servicio, en la pantalla de Registro de Solicitud de Servicio/Incidente, estas opciones ya estarán seleccionadas, no permitiendo su alteración. Pero si ha determinado que las notificaciones no serán obligatorias, al registrar una solicitud de servicio, estas opciones pueden ser definidas por el responsable del registro de la solicitud.
    
    6. En la pantalla de Registro de Solicitud de Servicio/Incidente, al registrar una solicitud de servicio se establecerá la regla referente a la notificación por e-mail, definida en el registro de grupo.
    
	    REGLA: al registrar una solicitud de servicio, se enviará la notificación sólo al grupo ejecutor, el cual es responsable de la atención de la solicitud. Cuando se realiza la ejecución de las demás acciones y cierre de la solicitud de servicio, las notificaciones serán encaminadas solamente al solicitante.
    
??? Question "¿Cómo definir la obligatoriedad del vinculo del cambio IC?"
    
    La obligatoriedad del vínculo del cambio con el IC se define en la pantalla de Parámetro del CITSmart. Para definir esta obligatoriedad, proceda conforme a las siguientes directrices:

    1. Acceda a la funcionalidad de Parámetros del CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart;
    2. Se mostrará la pantalla de Parámetros del CITSmart, haga clic en la pestaña de búsqueda de parámetros del CITSmart;
    3. Se mostrará la pantalla para la búsqueda de parámetros. Realiza la búsqueda del parámetro "85 - ¿Verificar enlace del Cambio relacionado al IC?";
    4. Seleccione el mismo;
    5. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, informe el valor "S";
    6. Haga clic en el botón "Grabar" para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    7. Después de la configuración del parámetro, cuando se registre un ítem de configuración, será obligatorio el vínculo del cambio.
    
??? Question "¿Cómo habilitar la rutina de lectura automática de mensajes de e-mail?"

    Al enviar un e-mail al soporte del CITSmart se lee la lectura del correo electrónico automático, si el e-mail es referente a una solicitud, se verificará el título del e-mail, si contiene la palabra 'Solicitud' y el "el número de la solicitud, en caso de contener, se almacenará el correo electrónico como ocurrencia en la solicitud referente.

    Para que esta rutina de lectura de correos electrónicos funcione perfectamente, es necesario realizar los siguientes procedimientos:
    
     1.  Instalar la versión de java 7, si tiene versión inferior la rutina no
        funcionará;

     2.  Acceda a la funcionalidad de Parámetros de Citsmart a través de la
    navegación en el menú principal Parametrización > Parámetros
    Citsmart;

    3.  Se mostrará la pantalla de Parámetros de Citsmart, haga clic en la
    pestaña de Búsqueda de Parámetros de Citsmart;

     4.  Se mostrará la pantalla para la búsqueda de parámetros, realice la búsqueda
    del parámetro "23 - SMTP LECTURA - Servidor de entrada de e-mails del
    Service Desk" y seleccionelo;

    5.  Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, informe al servidor de entrada
    de correo electrónico (ej .: orion.egrupo.com.br)

    6.  Haga clic en el botón "Grabar" para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría.

    7.  Realice la búsqueda del parámetro "24 - SMTP LECTURA - Usuario de buzón de
    entrada de mensajes de Service Desk" y seleccionelo;

    8.  Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, informe el correo electrónico o
    login de la cuenta de correo electrónico (por ejemplo, soporte.citsmart)

    9.  Haga clic en el botón "Grabar" para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría.

    10. Realice la búsqueda del parámetro "25 - SMTP LECTURA - Contraseña de buzón
    de entrada de mensajes de Service Desk" y seleccionelo;

    11. Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, la contraseña de la cuenta de
    correo electrónico;

    12. Haga clic en el botón *Grabar* para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría;

    13. Realice la búsqueda del parámetro "26 - SMTP LECTURA - Proveedor del
    servidor de correo del Centro de Servicio (imaps, pops, imap, pop, etc)" y
    seleccionelo;

    14. Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, informe el protocolo que será
    utilizado para lectura de e-mails (ej. Imap o pop) y haga clic en el botón
    Grabar para efectuar la operación, En este caso la fecha, hora y usuario se
    almacenan automáticamente para una futura auditoría.

    15. Realice la búsqueda del parámetro "27 - SMTP LECTURA - Puerto del servidor
    de correo electrónico del Service Desk" y seleccionelo.

    16. Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, informe el puerto que se
    utilizará para acceder al servidor de correos electrónicos (587 para
    servidor pop o 995 para servidor imap);

    17. Haga clic en el botón *Grabar* para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría.

    18. Realice la búsqueda del parámetro "28 - SMTP LECTURA - Carpeta de la
    bandeja de entrada de correos electrónicos del Service Desk" y
    seleccionelo.

    19. Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, introduzca la carpeta de la
    bandeja de entrada de la cuenta de correo electrónico;

    20. Haga clic en el botón *Grabar* para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría.

    21. Realice la búsqueda del parámetro "200 - ¿Habilitar rutina para leer los
    nuevos mensajes de correo electrónico de forma automática (por ejemplo, S o
    N - Default 'N') y seleccione el mismo;

    22. Se mostrará la pantalla de registro del parámetro con el contenido referente
    al registro seleccionado, en el campo valor, introduzca el valor "S" para
    activar la rutina de lectura de e-mail automáticamente;

    23. Haga clic en el botón *Grabar* para realizar la operación, en este caso la
    fecha, hora y usuario serán almacenados automáticamente para una futura
    auditoría.

    
??? Question "¿Cómo habilitar la regla de escalabilidad del módulo de cambios?"
    
    La regla de escalado de cambios está habilitada en la pantalla de Parámetro de CITSmart.

    Para habilitar esta regla, proceda de la siguiente manera:

    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart;
    2. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de Búsqueda de Parámetros de CITSmart;
    3. Se mostrará la pantalla para la búsqueda de parámetros, realice la búsqueda del parámetro"193 - ¿Permite programar los cambios en las reglas de escalamiento definidos? (Ej: S o N - Default 'N')" y seleccione el mismo;
    4. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, informe el valor "S" para activar escalonamiento de cambios;
    5. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
    
??? Question "¿Cómo habilitar el Portal del Servicios (Smart Portal)?"
    
    Para que los usuarios tengan acceso al Portal o al Portal Smart, se debe habilitar el mismo de la siguiente forma:
    
    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart; Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de Búsqueda de Parámetros de CITSmart; Hecho esto, se mostrará la pantalla para la búsqueda de parámetros
    2. Realiza la búsqueda del parámetro "46 - ¿Habilitar Portal como Pantalla de inicio de CITSmart?" y seleccione el mismo. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    3. En el campo valor, introduzca el valor "S" para habilitar el portal como pantalla de inicio. Hecho esto, haga clic en el botón "Grabar" para efectuar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    4. Después de configurar el parámetro, al iniciar sesión en el sistema, se mostrará como pantalla inicial el Portal.
    
??? Question "¿Cómo habilitar la encuesta de satisfacción?"
    
    La encuesta de satisfacción es la evaluación de la atención de la solicitud hecha a través de la notificación por e-mail.

    Para habilitar esta encuesta de satisfacción, proceda conforme a las siguientes directrices:
    
    1. Cree la plantilla de correo electrónico (la plantilla de correo debe contener la siguiente palabra clave: $ {LINKPESQUISASATISFACAO});
    2. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart.
    3. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de Búsqueda de Parámetros de CITSmart;
    4. Realiza la búsqueda del parámetro "31 - Enviar e-mail flujos de ejecución de solicitudes/incidentes";
    5. Seleccione el mismo;
    6. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, informe el valor "S" para que sea habilitado el envío de e-mail referente a las solicitudes de servicio;
    7. Haga clic en el botón Grabar para realizar la operación;
    8. Acceda a los servicios de solicitud, incidente y procedimiento del contrato referente al servicio de negocio Gestión de Portafolio y Catálogo > Gestión de Portafolio > Menú Apoyo > Avanzar Portafolio > Catálogo de Servicios > Avanzar Servicio e servicio tecnico Gestión de Portafolio y Catálogo > Gestión de Portafolio > Menú Apoyo > Avanzar Portafolio > Catálogo de Servicios > Avanzar Servicio y asegúrese de que el modelo de correo electrónico que se creó está informado en el campo "Modelo de correo electrónico en la finalización de solicitudes / incidentes";
    9. Al recibir una notificación por correo electrónico de la solicitud de servicio que ha sido atendida, se mostrará un enlace para realizar la evaluación de la atención. Al hacer clic en el enlace se abrirá una pantalla para la evaluación de la atención.
    
??? Question "¿Cómo habilitar la regla de escalonamiento del módulo de problemas?"
    
    Para habilitar esta regla, proceda de la siguiente manera:
    
    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart;
    2. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de Búsqueda de Parámetros de CITSmart;
    3. Se mostrará la pantalla para la búsqueda de parámetros, realice la búsqueda del parámetro"194 - ¿Habilitar el escalonamiento de problema definido en las reglas de escalonamiento?". (Ej.: S o N - Default 'N')" y seleccione el mismo;
    4. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, informe el valor "S" para activar escalonamiento de cambios;
    5. Haga clic en el botón "Grabar" para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
    
??? Question "¿Cómo habilitar la regla de escalabilidad de las solicitudes de servicio?"
    
    La regla de escalado de solicitud de servicio está habilitada en la pantalla de Parámetro de CITSmart. Para habilitar esta regla, proceda de la siguiente manera:

    1. En el archivo citsmart.cfg colocar la rutina START_MONITORA_INCIDENTES = TRUE ;
    2. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Sistema > Parámetros CITSmart;
    3. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de Búsqueda de Parámetros de CITSmart;
    4. Busque y cambie el parámetro 190 - ¿ Activa el funcionamiento de las reglas de programación? (Ej.: S o N - Default: 'N') que indica el valor "S" para habilitar escalado de solicitud de servicio;
    5. Busque y cambie el parámetro 31 - Enviar e-mail flujos de ejecución de solicitudes/incidentes (Ej: S o N) informando el valor "S";
    6. Busque y cambie el parámetro 297 - Desactiva el envío de correos electrónicos del sistema (Valores: "S" o "N" Default: "N") informando el valor "N";
    7. También haga los debidos cambios en los siguientes parámetros, según las necesidades y escenario de la instalación: 
    
    - 195: Id plantilla de correo electrónico para envío de solicitud de notificación con un plazo de batir (Ej .: 1);
    - 197: Login usuario recibirá reglas de correo electrónico respecto a la solicitud de servicios de programación que expira (Ej.: Consultor);
    -113: Modelo ID de correo electrónico de escalada automática;
    - 10: SMTP ENVÍO - Ogiren notificaciones por correo electrónico de las solicitudes de servicio;
    - 33: URL para acceder al sistema.
    
	8. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
   
??? Question "¿Cómo mejorar el rendimiento de CITSmart Enterprise ITSM?"
    
    El rendimiento del sistema se define como el tiempo que el software tarda en realizar una tarea determinada, ya que este rendimiento es un fuerte atributo de calidad percibido por los usuarios del software.

    Existe la capacidad del sistema para funcionar con más de una instancia, para ello, será necesario utilizar el archivo de configuración (citsmart.cfg), donde es posible activar o inactivar rutinas.

    Para utilizar esta capacidad, debe existir el archivo citsmart.cfg en el directorio:
    ```sh
    \jboss\standalone\configuration\ (quando o Jboss sobe como uma única instância)
    \jboss\domain\configuration\ (quando é utilizado cluster, tem domains e hosts)
    ```
   
    REGLA: donde está $ {valor} reemplaza por los valores correspondientes.
	
    1. START_MODE_RULES=${valor} (Este parámetro define si procesa las reglas de escalado. Introduzca el valor TRUE para activar o FALSE para desactivar);
    2. START_MODE_ITSM=${valor} (Este parámetro define si se muestra la interfaz de ITSM. Introduzca el valor TRUE o FALSE. Si se establece con el valor FALSE, no permitirá abrir las características de incidentes, etc. (del ITSM);
    3. START_MONITORING_ASSETS=${valor}(Este parámetro define si el monitoreo de activos se activará. Introduzca el valor TRUE para activar o FALSE para desactivar);
    4. QUANTIDADE_BACKUPLOGDADOS=${valor} (Este parámetro define la cantidad de elementos de la tabla eliminados que se harán copia de seguridad. Introduzca la cantidad de elementos, por ejemplo: 1000);
    5. Los parámetros siguientes cuando no se activan hacen que el sistema suba con los subprocesos deshabilitados para mejorar el rendimiento del sistema. Es necesario configurar estos parámetros antes del inicio de Jboss para el funcionamiento de los mismos;
    6. START_MONITORA_INCIDENTES=${valor} (Este parámetro define si desactiva el seguimiento de incidentes. Indique el valor TRUE activar o FALSE desactivar);
    7. START_VERIFICA_EVENTOS=${valor} (Este parâmetro define se desativa a verificação de eventos. Informe o valor TRUE ativar o FALSE desativar);
    8. El uso de los parámetros a continuación es opcional. Los mismos hacen la separación del pool de conexión principal con el pool de ejecución del flujo, inventario e informe.
    - JDBC_ALIAS_BPM = java: / jdbc / $ {value} (Este parámetro define el nombre del datasource del flujo. Introduzca el nombre del datasource, ej.: java:/jdbc/citsmartFluxo).
    - JDBC_ALIAS_INVENTORY = java: / jdbc / $ {value} (Este parámetro define el nombre del datasource del inventario. Introduzca el nombre del datasource, ej.: java:/jdbc/citsmart_inventory).
    - JDBC_ALIAS_REPORTS = java: / jdbc / $ {value} (Este parámetro define el nombre del datasource de los informes. Introduzca el nombre del datasource, ej.: java:/jdbc/citsmart_reports).
    9. El parámetro siguiente separa el procesamiento de la rutina de eventos BPM en un grupo de subprocesos independientes del grupo de subprocesos principal del sistema para aliviar el uso de recursos de base de datos y servidor.
    - JDBC_ALIAS_BPM_EVENTOS=java:/jdbc/${valor} (Este parámetro define el nombre del datasource de eventos BPM. Introduzca el nombre del datasource, ej.: java:/jdbc/citsmartBpmEventos).
    
??? Question "¿Cómo integrar el AD de la empresa del cliente en el CITSmart Enteprise ITSM que está en cloud ofrecida por CITSmart Corporation?"
    
    Con respecto de LDAP compliance de CITSmart Enterprise ITSM, hay dos escenarios:
    
    1. Entornos on-demand: el administrador debe conectarse al servidor de directorio del cliente;
    2. Entorno en la cloud (ofrecido por CITSmart Corporation): el administrador debe habilitar la conexión con el servidor del directorio del cliente.

??? Question "¿Cómo vincular colaboradores (usuarios) a un grupo?"
    
   Hay dos formas de vincular a los colaboradores (usuarios) a los grupos.

    A PARTIR DEL REGISTRO DE GRUPO
	
    1. Acceda a la funcionalidad de Registro de Grupo a través de la navegación en el menú principal. Posicione el puntero en la opción Acceso y Permiso y haga clic en la opción Grupo (ver [Registrar grupo](/es-es/citsmart-esp-8/initial-settings/access-settings/user/register-groups.html) );
    2. Se mostrará la pantalla de Registro de Grupo. Si el grupo ya está registrado en el sistema, realice la búsqueda del grupo y seleccione el mismo. Hecho esto, se mostrará la pantalla de registro del determinado grupo;
    3. Haga clic en el icono de agregar del campo Colaboradores, se mostrará la pantalla para búsqueda de colaboradores;
    4. Realice la búsqueda del colaborador que desea vincular al grupo y seleccione el mismo. Después de eso, el colaborador será vinculado al grupo;
    5. Después del vínculo, haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario se almacenar automáticamente para una futura auditoría.
    
    A PARTIR DO CADASTRO DE USUARIO
    
    1. Acceda a la funcionalidad de Registro de Usuario a través de la navegación en el menú principal. Sitúe el puntero en la opción Registros Generales, Administración de Personal y haga clic en la opción Usuario (ver [Registrar usuario](/es-es/citsmart-esp-8/initial-settings/access-settings/user/users.html));
    2. Se mostrará la pantalla de Registro de Usuario. Si el usuario ya está registrado en el sistema, realice la búsqueda del usuario y seleccione el mismo. Hecho esto, se mostrará la pantalla de registro del usuario determinado;
    3. Haga clic en el icono Agregar del campo Grupo. Se mostrará la pantalla para la búsqueda de grupos;
    4. Realice la búsqueda del grupo deseado y seleccione la misma. Después de eso, el usuario será vinculado al grupo;
    5. Después del vínculo, haga clic en el botón "Grabar" para realizar la operación, en este caso la fecha, hora y usuario se almacenar automáticamente para una futura auditoría.

??? Question "¿Cómo relacionar el grupo al contrato?"
    
    Para relacionar grupo al contrato, proceda conforme a las orientaciones abajo:
    
    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal. Coloque el puntero en la opción Parametrización y haga clic en la opción Parámetros CITSmart. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de consulta de parámetros de CITSmart. Hecho esto, se mostrará la pantalla para la búsqueda de parámetros;
    2. Realiza la búsqueda del parámetro "41 - ¿Hace que el control de vínculo de colaboradores a los contratos (S/N)?" y seleccione. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    3. En el campo valor, introduzca el valor "S" para que se muestren los contratos en la pantalla de registro de grupo. Hecho esto, haga clic en el botón Grabar para efectuar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    4. Después de configurar el parámetro, acceda a la funcionalidad de registro de grupo a través de la navegación en el menú principal Registros generales > Gestión de Personal > Grupo. Se mostrará la pantalla de registro de grupo, mostrando los contratos (ver [Registrar grupo](/es-es/citsmart-esp-8/initial-settings/access-settings/user/register-groups.html));
    5. Si el grupo que desea vincular al contrato ya está registrado en el sistema, realice la búsqueda del grupo y seleccione el mismo;
    6. Hecho esto, se mostrará la pantalla de registro del determinado grupo;
    7. Seleccione los contratos a los que se vinculará el grupo;
    8. Haga clic en el botón "Grabar" para efectuar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
    
??? Question "¿Cómo relacionar la unidad al contrato?"
    
    Para relacionar unidad al contrato, proceda de acuerdo con las siguientes directrices:
    
    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal opción Parametrización > Parámetros CITSmart. Después de eso, aparecerá la pantalla de Parámetros de CITSmart, haga clic en la pestaña de búsqueda de parámetros de CITSmart. Hecho esto, se mostrará la pantalla para la búsqueda de parámetros;
    2. Realice la búsqueda del parámetro "61 - Vincula contratos a unidad" y seleccione el mismo. Después de eso, aparecerá la pantalla de registro del parámetro con el contenido referente al registro seleccionado;
    3. En el campo valor, introduzca el valor "S" para que se muestren los contratos en la pantalla de registro de unidad. Hecho esto, haga clic en el botón Grabar para efectuar la operación;
    4. Después de configurar el parámetro, acceda a la funcionalidad de registro de unidad a través de la navegación en el menú principal Registros Generales > Gestión de personal > Unidad. Se mostrará la pantalla de registro de unidad, mostrando los contratos;
    5. Si la unidad que desea vincular al contrato ya está registrada en el sistema, realice la búsqueda de la unidad y seleccione la misma. Hecho esto, se mostrará la pantalla de registro de la determinada unidad;
    6. Seleccione los contratos, a los que se vinculará la unidad;
    7. Haga clic en el botón Grabar para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría.
    
??? Question "¿Cómo reemplazar cada imagen de los logotipos de CITSmart Enterprise ITSM?"
   
    Siempre que sea necesario personalizar correctamente los logotipos de CITSmart Enterprise ITSM, se debe realizar el siguiente procedimiento:
    
    1. Acceder al camino: Sistema > Configuración > Configuración de ambiente; aparecerá tres espacios para subir imágenes:
      - Logo inicio: Imagen/Logomarca que aparece en la pantalla inicial de inicio de sesión del sistema;
      - Logo portal: Imagen/Logomarca que aparece en el Portal de Servicios del sistema;
      - Logo sistema: Imagen/Logomarca que se presenta al acceder al sistema;
      - Logo Informe: Imagen/Logomarca que se presenta en los informes del tipo jasper.
	
    2. Realizar upload (pueden ser imágenes diferentes).
    
	REGLA: si el usuario no elige una nueva insignia, el logo predeterminado será el del CITSmart. Por motivos de derechos de autor, este cambio de logo sólo se permite en la versión Enterprise del producto CITSmart ITSM.

    CONFIGURACIÓN MÁS PRECISA DE LA IMAGEN PARA INFORMES JASPER
	
    El usuario tiene acceso a las propiedades de la imagen que aparecerá en los informes.

	REGLA: si la imagen personalizada por el usuario no está configurada correctamente en los informes, debe rediseñarse con las proporciones más adecuadas.
    
??? Question "¿Cómo configurar el recurso SOLR?"
    
    CONFIGURACIÓN DEL PARÁMETRO
    
    1. Para configurar el parámetro vaya a la pantalla Parametrización → Gestión de Conocimiento;
    2. Busque el parámetro “URL del servidor de SOLR (Ej: http://localhost:8983/solr/collection_name)” ;
    3. Después de indicar la dirección URL del servidor Solr, un ejemplo de URL sería el siguiente: http://localhost:8983/solr/base_conocimiento .

    INDEXACIÓN DE LOS CONOCIMIENTOS EXISTENTES
	
    1. Para indexar los conocimientos vaya en Sistema > Configuraciones > Gestión de conocimiento (Indexación);
    2. Si tiene conocimientos indexados, haga clic en "Eliminar la indexación de base de conocimientos";
    3. Luego haga clic en "Indexar base de conocimiento";
    4. Si se produce algún error, haga clic en "Actualizar el servidor de índices";
    5. Después de hacer clic de nuevo en "Indexar base de conocimiento";
    6. Si se produce algún error, póngase en contacto con el soporte de ITSM.
    
??? Question "¿Para cuál destinatario se hará el envío de notificaciones de ICs?"
    
    Las notificaciones de IC se enviarán al destinatario definido en la pantalla de Parámetro de CITSmart.

    Para definir el destinatario, proceda de la siguiente manera:
    
    1. Acceda a la funcionalidad de Parámetros de CITSmart a través de la navegación en el menú principal Parametrización > Parámetros CITSmart.
    2. Se mostrará la pantalla de Parámetros de CITSmart, haga clic en la pestaña de búsqueda de parámetros de CITSmart;
    3. Se mostrará la pantalla para la búsqueda de parámetros;
    4. Realiza la búsqueda del parámetro "90 - Envío de correos electrónicos de notificación IC (1-Grupo, 2-Propietario, 3-Todos)";
    5. Seleccione el mismo;
    6. Se mostrará la pantalla de registro del parámetro con el contenido referente al registro seleccionado, en el campo valor, introduzca el número de identificación del destinatario (1 - Grupo, 2 - Propietario o 3 - Todos);
    7. Haga clic en el botón "Grabar" para realizar la operación, en este caso la fecha, hora y usuario serán almacenados automáticamente para una futura auditoría;
    8. Después de la configuración del parámetro, se realizará el envío de e-mails de notificaciones de IC para el destinatario (grupo, propietario o todos), según se especifica en el valor del parámetro.
    
??? Question "¿Qué es necesario para configurar un IC que está físicamente en la red de la empresa del cliente para ser inventariado por el CITSmart Enterprise ITSM que está en la cloud ofrecida por CITSmart Corporation?"
    
    [Original] En la nube, el mongodb y evm / inv quedan en la estructura del cliente, debido a que no es posible conectarse a un rango interno con origen de la nube.
    
    [Para validación] En este escenario específico, los componentes MongoDB, CITSmart EVM y CITSmart Inventory deben instalarse y configurarse dentro de la estructura de red del cliente, ya que no es posible que el CITSmart (Cloud) se conecte a un rango interno de un cliente.
    
??? Question "¿Cuál es el límite de tamaño de archivo para Upload en las funcionalidades con estas característica?"
    
    La carga de los archivos adjuntos especifica el tamaño límite de 15 Mbytes para cada archivo cargado en el sistema. Sin embargo, en la pantalla del Portal continúa con el límite de 5 Mbytes para el tamaño del archivo.
   
??? Question "¿Qué es la tabla Fato del módulo solicitud de servicio y cómo alimentarla?"
    
    La tabla de FATO solicitud de servicio tiene el propósito de recibir informaciones consolidadas, referentes a la solicitud de servicio.

    Tales como: 
    
    IDSOLICITACAOSERVICO
	
    DATAHORASOLICITACAO
	
    DIAABERTURA
	
    MESABERTURA
	
    ANOABERTURA
	
    DATAHORAFIM
	
    DIAFECHAMENTO
	
    MESFECHAMENTO
	
    ANOFECHAMENTO
	
    IDGRUPOATUAL
	
    GRUPOATUAL
	
    IDPRIORIDADE
	
    NOMEPRIORIDADE
	
    IDSERVICOCONTRATO
	
    IDCONTRATO
	
    NUMEROCONTRATO
	
    IDTIPOSERVICO
	
    NOMETIPOSERVICO
	
    IDPORTFOLIOSERVICO
	
    DESCPORTFOLIOSERVICO
	
    IDSOLICITANTE
	
    SOLICITANTE
	
    IDUSUARIORESPONSAVELATUAL
	
    TECNICORESPONSAVEL
	
    IDTIPODEMANDASERVICO
	
    TIPOSOLICITACAO
	
    IDCAUSAINCIDENTE
	
    CAUSA
	
    IDCATEGORIASOLUCAO
	
    CATEGORIASOLUCAO
	
    IDSTATUS
	
    STATUS
	
    IDACORDONIVELSERVICO
	
    PRAZOSLA_HH
	
    PRAZOSLA_MM
	
    IDCALENDARIO
	
    CALENDARIO
	
    DATAHORALIMITE
	
    DIALIMITESLA
	
    MESLIMITESLA
	
    ANOLIMITESLA
	
    TAREFAATUAL
	
    IDCLIENTE
	
    CLIENTE
	
    IDFORNECEDOR
	
    FORNECEDOR
	
    IDCATEGORIASERVICO
	
    CATEGORIASERVICO
	
    IDCONDICAOOPERACAO
	
    NOMECONDICAOOPERACAO
	
    IDORIGEM
	
    ORIGEMDASOLICITACAO
	
    IDMOEDA
	
    MOEDA
	
    IDTIPOFLUXO
	
    FLUXO
	
    IDIMPORTANCIANEGOCIO
	
    IMPORTANCIASERVICOAONEGOCIO
	
    IDLOCALIDADE
	
    LOCALIDADE
	
    IDUNIDADE
	
    UNIDADE
	
    URGENCIA
	
    IMPACTO
	
    RUPTURASLA
	
    QTDEREABERTURAS
	
    HOUVERECLASSIFICACAO
	
    TEMPOATENDIMENTOHH
	
    TEMPOATENDIMENTOMM
	
    TEMPOATRASOHH
	
    TEMPOATRASOMM
	
    MAJOR
	
    NOTAPESQUISASATISFACAO
	
    QTDESOLICITACOESFILHAS
	
    QTDESUBSOLICITACOES
	
    QTDEBASECONHECIMENTO
	
    QTDEPROBLEMAS
	
    QTDELIBERACAO
	
    QTDEMUDANCAS
	
    QTDEICS
	
    QTDEAPLICACOES
	
    QTDEPROJETOS
	
    QTDEANEXOS
	
    QTDEAGENDAMENTOATIVIDADES
	
    QTDEAGENDAMENTATIVFINALIZADAS
	
    CONTRATOAPOIO
	
    SERVICOAPOIO
	
    CUSTOSERVICO
	
    SERVICOINDISPONIVEL
	
    QTDEELOGIOS
	
    QTDEQUEIXAS
	
    PROCEDIMENTOCONTINUIDADE
	
    CUSTOINDISPONIBILIDADE
	
    IDSERVICO
	
    NOMESERVICO
	
    IDATIVIDADE
	
    NOMEATIVIDADE
	
    DATAHORACARGA
    
	Esta información se alimenta a través de la rutina de procesamiento por lotes de CITSmart, ejecutando los scripts Rhino, en los archivos adjuntos.
	[Download - ScriptRhino Tabla fato SQLserver][1]
	[Download - ScriptRhino Tabla fato PostgreSQL][2]
	[Download - ScriptRhino Tabla fato Oracle V71][3]
	[Download - ScriptRhino Tabla fato Oracle V70][4]
	[Download - ScriptRhino Tabla fato SQLserver V71][5]
	[Download - ScriptRhino Tabla fato PostgreSQL V70][6]
	[Download - ScriptRhino Tabla fato PostgreSQL V71][7]
	
    
??? Question "Qual o impacto do filtro "Grupo Solucionador" no comportamento das pesquisas de requisições e incidentes?"
    Quando o filtro "grupo solucionador" estiver ativo, serão apresentadas apenas as solicitações fechadas, uma vez que ao selecionar este filtro, entende-se que há a necessidade de apresentar o grupo que de fato solucionou uma solicitação, não apresentando grupos responsáveis por tarefas (conforme o fluxo vinculado ao serviço da solicitação) executadas após a solicitação ser solucionada.
    
	Vejamos um exemplo genérico:
    - O serviço A possui um fluxo de qualidade vinculado. Após solucionada uma solicitação referente ao serviço A e avançar o fluxo, o grupo responsável será o de qualidade e este encerrará o ciclo de vida da solicitação em questão, porém este grupo não é o grupo que solucionou esta solicitação, ele apenas aprovou a solução e encerrou a solicitação, portanto não será apresentado no relatório gerado pela tela de pesquisa de Requisições e Incidentes quando o filtro "Grupo solucionador" estiver marcado com um grupo específico.
    - Entretanto, quando o filtro "Grupo Solucionador" não estiver ativo, o grupo apresentado no relatório ou na pesquisa será o grupo referente à tarefa atual da solicitação, ou seja, caso a solicitação esteja fechada e possua um fluxo de qualidade, será apresentado o grupo de qualidade como o grupo atual responsável pelo encerramento do ciclo de vida desta solicitação. E caso a solicitação esteja em andamento, será apresentado o grupo atual responsável pela execução desta solicitação.
    
??? Question "Quais o significado de cada status do inventário de ICs?"
    - Inventariado: o inventário conseguiu ler as informações do IC e se encerrou com sucesso;
    - Ignorado: na tela de citsmart/pages/evmInventoryConfiguracao/evmInventoryConfiguracao.load temos uma opção para ignorar as máquinas já inventariadas, essa marcação aparece quando isso ocorre;
    - Inacessível: quando o servidor encontra o IC, mas não consegue trazer as informações;
    - Não inventariado: quando nem encontra o IC na rede, mas tem conhecimento de que ele já existiu;
    - Em execução: durante a leitura do inventário, o IC fica nesse status.
    
??? Question "Qual o significado de cada privacidade que um conhecimento pode ter na base de conhecimento?"
    - Público: todos os usuários com acesso no Portal do Conhecimento possuem acesso, independente se têm acesso à pasta do conhecimento;
    - Confidencial: somente o autor e o aprovador podem visualizar o conhecimento;
    - Interno: somente pessoas com permissão na pasta do conhecimento podem visualizar.
    
??? Question "Quais as permissões necessárias na pasta de destino do backup da tabela Logdados?"
    A permissões na pasta devem ser de leitura e gravação para o usuário que o JBoss utiliza.
    
??? Question "Quando ocorre a sincronização dos dados com o LDAP?"
    O sistema sincroniza os dados das credenciais de seus usuários com o LDAP em três situações distintas:
    
    1. Na ativação da aplicação, geralmente em sequência ao procedimento de atualização de versão do produto;
    2. Quando o usuário faz o logon (o acesso ao sistema com seu login e senha), nesse momento o sistema automaticamente verifica a autenticação e permissão do usuário;
    3. Na funcionalidade Configuração de LDAP, quando o usuário clica na opção 'Sincronizar'.
    
??? Question "Quando ocorre a limpeza dos dados da tabela Logdados?"
    A rotina de backup da tabela LogDados retira os dados da tabela e salva em arquivo, ou seja, a tabela fica limpa após o processamento.
    
??? Question "Quando ocorre a limpeza dos dados da tabela Logdados?"
    A rotina de backup da tabela LogDados retira os dados da tabela e salva em arquivo, ou seja, a tabela fica limpa após o processamento.
    
??? Question "Por que os horários criados pela ferramenta estão diferentes da hora atual?"
    CENÁRIO
    1.Ao criar um chamado, a hora fica diferente da hora real, alternando entre 1 (uma) à 3 (três) horas de atraso ou adiantamento.

    O QUE CHECAR
    1. Arquivo de configuração do Banco Postgresql:
     - Postgresql.conf
     - timezone = 'BRAZIL/EAST'
    2. No container cloud:
     - Setting timezone on the operating system.
    3.Configuração do TimeZone no JRE: 
     - https://docs.oracle.com/javase/9/troubleshoot/time-zone-settings-jre.htm#JSTGD362
    
??? Question "Por que em alguns relatórios a mesma solicitação aparece mais de uma vez?"
    Em alguns relatórios como por exemplo o "Relatório Incidentes / Solicitações de Serviços - Detalhado", tanto no formato pdf como no xls, pode existir sim a mesma solicitação mais de uma vez, contudo são detalhamentos distintos porque trata de cada etapa da solicitação, então cada vez que ela "repete" é porque muda-se a tarefa, ou o responsável, ou a fase, ou a situação, ou o grupo solucionador ou a data hora final de atendimento.
    
    Já em outros relatórios, tais como o "Relatório Incidentes / Solicitações de Serviços" não há detalhamento da solicitação de acordo com as atividades e por isso não é mostrada a solicitação mais de uma vez. 
    
??? Question "Por que o resultado é "Relatório Vazio" ao gerar o relatorioControlePercentualQuantitativoSla selecionando no filtro a situação "em Andamento" e o "grupo solucionador"?"
    Não se trata de um erro, o campo de grupo solucionador é preenchido somente quando a solicitação é encerrada, isso faz com que só traga resultados para as situações do tipo "Fechada", incompatível com o que se está pedindo/informando nos filtros.
    
??? Question "Por que a numeração de solicitação de serviço nem sempre seguirá uma ordem sequencial rigorosa/perfeita na tela de solicitação de serviços ou em alguns relatórios?"
    Tanto a tela de Solicitação de Serviços quanto em alguns relatórios (tais como "Qualidade de Atendimento - SLA"), a ordenação do número das solicitações segue uma ordem sequencial crescente, exceto quando:
    
    1. Os relatórios agrupam os dados por algum critério especial (ex.: pelo prazo de SLA, que é o que acontece no caso do relatório "Qualidade de Atendimento - SLA")
    2. Quando o recurso denominado Sequence Block é impactado por um fator externo, isso ocorre se:
    - Há uma parada da aplicação para atualização de versão, ou manutenção de ambiente e posterior retorno.
    - O ambiente é clusterizado.
    
??? Question "O arquivo de backup será sobrescrito ou terá um arquivo para cada dia?"
    Se a sua rotina for um backup por dia, vai ser criado um arquivo por dia, contendo no nome a data do respectivo arquivo.
    
??? Question "Por que o sistema exibe mensagem de data inválida ao auditar o ticket?"
    Na interface do Gerenciamento do Ticket, especificamente no item "Auditoria”, ao tentar configurar a auditoria de um ticket aberto (definir as datas de início e fim no filtro), o seguinte erro pode ocorrer: o sistema apresentará a mensagem de "Data Inválida". Isto ocorre porque a funcionalidade necessita que o idioma definido no sistema e no navegador utilizado sejam idênticos.  
    Se este requisito não for observado e ocorrer esta diferença nos idiomas, ao auditar os tickets o sistema apresentará uma mensagem e impossibilitando auferir o relatório pretendido. Sendo necessário, portanto, igualar os idiomas do sistema e do navegador.  

	
