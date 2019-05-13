title:  Auditoría del sistema
Description: Permite gestionar los eventuales riesgos al sistema
# Auditoría del sistema

Esta funcionalidad permite administrar los posibles riesgos al sistema, al auditar todas las ejecuciones hechas en forma de logs.

Antes de empezar 
-----------------

**Versión inferior a 0.4.0**

Es necesario la instalación previa de los siguientes productos:

-   ACTIVEMQ con la versión 5.15.8 o superior;

-   Mongodb.

**Versiones iguales o superiores a 0.4.0**

- No es necesario tener un ActiveMQ externo activo;

- No es necesario tener un servicio ejecutando el .jar de la auditoría;

- Audit ahora es un .war y se ejecuta dentro de Wildfly junto al ITSM en la carpeta "\deployments";

- Agregar las siguientes líneas al standalone del wildfly en el subsistema del activeqm:

<jms-queue name="ITSM.READ_DATA_AUDIT" entries="queue/ITSM.READ_DATA_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_DATA_AUDIT"/>
<jms-queue name="ITSM.READ_LICENSE_AUDIT" entries="queue/ITSM.READ_LICENSE_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_LICENSE_AUDIT"/>
<jms-queue name="ITSM.READ_ACCESS_AUDIT" entries="queue/ITSM.READ_ACCESS_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_ACCESS_AUDIT"/>
<jms-queue name="ITSM.READ_BACKUP_AUDIT" entries="queue/ITSM.READ_BACKUP_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_BACKUP_AUDIT"/>

- Agregar las siguientes líneas al standalone del wildfly en las system-properties (igual se utiliza en CITSmart EVM y CITSmart Inventory):

<property name="mongodb.host" value="localhost"/>
<property name="mongodb.port" value="27017"/>
<property name="mongodb.user" value="mongodb"/>
<property name="mongodb.password" value="mongodb"/>
<property name="mongodb.dabase.audit" value="itsm-audit"/>

!!! note "NOTA"

    Configurar la conexión con el banco mongo con host, port, user, pass y database (Probablemente ya existente, 
    EVM e Inventory utilizan estas configuraciones)

- El parámetro 424 debe quedar en blanco;

- El parámetro 425 debe quedar así (http://localhost:8080/itsm-audit);

!!! Abstract "ATENCIÓN"

    El puerto 8080 debe cambiarse si se cambia el CITSmart en otro puerto.

- Agregar el .war adjunto en la carpeta de deployments (O a través de la consola de Wildfly) y realizar start de Wildfly junto con CITSmart.

Procedimiento
------------

***Proceso para configurar la Auditoría:***

*Configuración para generar el backup de las auditorías.*

En primer lugar, es imprescindible configurar los parámetros específicos
de la funcionalidad.

1.  Acceder al menú principal
    Parametrización \> Parametrización de Auditoría;

2.  Informar en el campo “Directorio” la carpeta donde se mantendrá todos *Logs* de las
    auditorías hechas;

3.  En el campo "Frecuencia en días" se puede ajustar una rutina de backup de los registros de auditoría, al elegir la periodicidad del     backup en días.

    !!! Abstract "NOTA"

        La elección de la frecuencia debe ser a partir de 1 (un) día para la ejecución del backup.
 

4.  Se dispone de la posibilidad de determinar un período específico (fecha de inicio y fin) para la generación de los logs de auditoría del sistema.

    !!! note "IMPORTANTE"

        Se ofrecen tres tipos de auditoría del sistema: auditoría de los datos del
        sistema, del acceso al sistema y sus licencias.

***Auditoría de datos del sistema***

*Presenta el historial de todos los datos de cambio, inclusión y exclusión
hechas en el sistema.*

1.  Acceder al menú principal Sistema \> Camino de auditoría \> Auditoría de datos;

2.  Se presentarán los logs de auditoría de todo el movimiento hecho en el programa, mostrando la fecha y hora de las actualizaciones, dirección IP, nombre del ejecutor de la actualización, nombre de la tabla, tipo de operación efectuada en el sistema. Al hacer clic en el botón datos se mostrará lo que de hecho fue actualizado en el programa.

    !!! Abstract "ATENCIÓN"

        El campo “Operaciones” presenta el tipo de acción hecha en la actualización
        del sistema en prueba. Se define por símbolos, y sus significados son:

        -   La letra "C" significa "Cambio" en los datos del sistema;

        -   La letra "I" simboliza la "Inserción" de nuevos datos al sistema;

        -   La letra "E" significa la "Exclusión" de los datos del sistema.  

3.  Se libera también la búsqueda de determinado *log* a través de los filtros dispuestos en la pantalla.

***Auditoría de accesos al sistema***

*Presenta el historial de los accesos al sistema (entradas y salidas).*

1.  Acceder al menú principal Sistema \>
    Camino de auditoría \> Auditoría de acceso;

2.  Se presentarán los usuarios que han iniciado y cerrado sesión en el sistema,
    registrando también la fecha y la hora de cada una de estas actividades;

    !!! Abstract "NOTA"  
        
        Si el sistema expirar, no será posible capturar el cierre de sesión del sistema, quedando registrado, por lo tanto, sólo         la información de entrada de la sesión de acceso.  

3.  Existen filtros para ayudar la búsqueda de un determinado acceso.

***Auditoría de licencias del sistema***

*Informa las licencias utilizadas para la validación del sistema.*

1.  Acceder al menú principal Sistema \>
    Camino de auditoría \> Auditoría de licencia;

2.  Presenta los datos de las licencias adquiridas y usadas para la ejecución
    del sistema;

3.  Es posible buscar una determinada licencia y su plazo de validez por los filtros liberados en la pantalla principal.
    
!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/15/2019 – Larissa Lourenço
