title:  Mantenimiento del flujo de trabajo 
Description: modelar sus objetivos de negocio, describiendo los pasos que necesitan ser ejecutados para alcanzar esos objetivos, a través de un diagrama de flujo.
#Mantenimiento del flujo de trabajo

Los flujos son representaciones visuales de algo que se mueve continuamente.
La funcionalidad de Mantenimiento de Flujos tiene el propósito de modelar sus 
objetivos de negocio, describiendo los pasos que necesitan ser ejecutados para 
alcanzar esos objetivos, a través de un diagrama de flujo.

Procedimiento
-------------

1.  Acceda a la funcionalidad por el menú principal Sistema \> Mantenimiento de
    Flujos;

2.  Aparecerá la pantalla de inicio de la funcionalidad. Las siguientes actividades están
    disponibles aquí:
    
    -  Podemos buscar los flujos previamente registrados al hacer clic en "Filtros
       avanzados" y completar los datos;
       
    -  En el botón "Editar", puede haber varias versiones del mismo flujo;
    
    !!! Abstract "NOTA"
    
        El modelo tiene por objetivo preservar el estado del flujo de trabajo que
        está vinculado a algún servicio, evitando cambios en flujo productivo.
        
    -  La opción "Exportar" permite la exportación del flujo en el formato JSON;
    
    -  En "Borrar" se pueden eliminar los flujos.
    
    !!! Abstract "NOTA"
    
        La exclusión sólo será posible si no hay ningún servicio vinculado al flujo
        a ser removido.

3.  Al hacer clic en "Editar" y seleccionar cualquier versión del flujo,
    se muestra la información del flujo en tres pestañas: "Datos del flujo",
    "Diagrama" y "Documentación". Cada uno tiene la siguiente función:
    
-   En la pestaña "Datos del flujo", se expondrán los datos con la información del flujo,
    tales como: su nombre, el proceso al que está vinculado (el flujo estará
    visible sólo para el proceso al que está vinculado), su versión, la
    descripción del flujo y la opción para permitir la reapertura de un servicio
    independientemente de la configuración de grupo.
    
    !!! tip "SUGERENCIA"
    
        La opción de reapertura en el flujo puede ser útil en escenarios en los que no hay
        muchos servicios donde se permite la reapertura, por lo que al marcar la opción "permitir 
        reaberutra" no es necesario utilizar la acción "reopen" en el permiso del flujo.

-   La pestaña "Diagrama" representa una herramienta de diseño de flujo. En el lado izquierdo
    de esta pantalla se encuentra la organización de los elementos que componen la
    funcionalidad de flujo. Al hacer clic en cada uno de estos elementos, quedarán
    accesible cada actividad realizada por estos elementos, que son:
    
    -   **Eventos:** son los elementos de los eventos que pueden utilizarse en el
        diseño del flujo. Son ellos:
        
        -   Evento Inicial
        
        -   Evento Intermedio de Envío de Enlace
        
        -   Evento Intermedio de Captura de Enlace
        
        -   Evento Intermedio de Temporizador
        
        -   Boundary - Evento Intermedio de Captura de Errores
        
        -   Evento Intermedio de Captura de Señal
        
        -   Evento de Finalización con Error
        
        -   Evento Final
        
    -   **Actividades:** son los elementos de actividades que pueden ser utilizados
        en el diseño del flujo. Son ellos:
        
        -   Tarea del Usuario
        
        -   Tarea Script
        
        -   Envió de Mensajes - Correo Electrónico
        
        -   Business Rule Task
        
        -   Tarea de Servicio - ESI
        
        -   Almacenamiento de Datos
        
        -   Subproceso
        
    -   **Extensiones:** son las extensiones que se pueden utilizar en el diseño del
        flujo. Son ellas:
        
        -   Comunicación REST
        
        -   Notificación
        
        -   Asignación de Variable
        
        -   Conversación Watson
        
    -   **Gateways:** son los elementos de gateway que se pueden utilizar en el
        diseño del flujo. Son ellos:
        
        -   Gateway Inclusivo
        
        -   Gateway Paralelo
        
        -   Gateway Exclusivo
        
        -   Gateway Complejo
        
        -   Gateway Basado en Evento
        
    -   **Swimianes:** son los elementos de swimianes que pueden ser utilizados en el
        diseño del flujo. Son ellos:
        
        -   Pool/Participante
        
        -   Lane
        
    -   **Artefacto:** es el elemento de artefacto que pueden utilizarse en el
        diseño del flujo. Son ellos:
        
        -   Anotación de Texto
        
    -   En esta pestaña, también se permite, al hacer clic en "Generar Documentación", la
        exportación en PDF de las informaciones generadas en la pestaña "Documentación".     
        Además, al hacer clic en "Guardar", podemos elegir la forma de este almacenamiento
        ("Como nueva versión" que significa versionar y generar una nueva visión del flujo o
        "En la versión original" que significa guardar el flujo en la versión actual, la que
        está siendo editada).
        
    -   En la pestaña "Documentación" se genera una visión de toda la información del flujo
        (diagrama, descripción de elementos utilizados en el diagrama).
        
-   En la pestaña "Documentación" se genera una visión de toda la información del flujo
    (diagrama, descripción de elementos utilizados en el diagrama).
    
!!! Abstract "NOTA"
    
    Es importante recordar que:
    
    - las normativas configuradas en el flujo tendrán prioridad en relación a las
    las marcas de la plantilla de solicitud de servicio, ya que este es un complemento del flujo;
    
    - para utilizar el componente "Conversación Watson" la organización debe poseer la
    arquitectura IBM BlueMIX, permitiendo así el acceso a la API de Conversación del Watson;
    
    - para borrar un elemento que se ha insertado en el dibujo del flujo, haga clic en
    el elemento y después en Ctrl+Delete.
    
Diagrama de un flujo de trabajo
-------------------------------------   

![Diagrama del Flujo](images/flow-diagram.png)
 
-   1 - Representa el inicio del flujo de trabajo;
 
-   2 - Representa una tarea del usuario a se hacer en el flujo (que en enste
    caso significa 'aprobación o rechazo de la tarea');

-   3 - Representa la segunda tarea del usuario que se ejecuta en el flujo (que
    en este caso significa "aprobación o rechazo de la tarea");
   
-   4 - Representa el "Gateway exclusivo" (que representa una condición de flujo exclusiva,
    en la que se seguirá una de las rutas creadas a partir del Gateway, de acuerdo con una 
    información a ser probada. Este gateway se puede representar visualmente como el rombo 
    vacío o con un marcador de "x") del flujo;
    
-   5 - Representa el evento final del flujo de trabajo (que en este caso significa
    la conclusión de la excisión de la tarea o el rechazo de la tarea;
    
-   6 - Representa la tercera tarea del usuario a desempeñar en el flujo (que
     en este caso significa 'ejecutar la tarea', si la misma ha sido aprobada).   
    

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 - Larissa Lourenço
