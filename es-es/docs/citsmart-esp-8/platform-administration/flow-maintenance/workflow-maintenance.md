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




!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 - Larissa Lourenço
