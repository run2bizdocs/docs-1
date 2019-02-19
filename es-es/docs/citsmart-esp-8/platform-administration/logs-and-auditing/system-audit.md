title:  Auditoría del sistema
Description: Permite gestionar los eventuales riesgos al sistema
#Auditoría del sistema

Esta funcionalidad permite administrar los posibles riesgos al sistema, al auditar todas las ejecuciones hechas en forma de logs.

Antes de empezar 
-----------------

Es necesario la instalación previa de los siguientes productos:

-   ACTIVEMQ con la versión 5.15.8 o superior;

-   Mongodb.

También es necesario establecer los siguientes parámetros en CITSmart (Parametrización \>
Parámetros CITSmart):

-   En el parámetro 52, configrar el valor "true";

-   En el parámetro 53, informar el tipo de registro que desea. Los tipos son: ‘CIT_LOG’
    (archivo del log) y ‘DB_LOG’ (guarda en la base);

-   En el parámetro 425, informar la URL de acceso a la Auditoría CITSmart (Ej.:
    http://localhost:8088);

-   En el parámetro 424, informar la URL de acceso al ActiveMQ (Ej.:tcp://citACTIVEMQ:61616).

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

3.  En el campo "Frecuencia en días" se puede ajustar una rutina de backup de los
    registros de auditoría, al elegir la periodicidad del backup en días.

    !!! Abstract "NOTA"

        La elección de la frecuencia debe ser a partir de 1 (un) día para la ejecución del
        backup.  

4.  Se dispone de la posibilidad de determinar un período específico (fecha
     de inicio y fin) para la generación de los logs de auditoría del sistema.

    !!! note "IMPORTANTE"

        Se ofrecen tres tipos de auditoría del sistema: auditoría de los datos del
        sistema, del acceso al sistema y sus licencias.

***Auditoría de datos del sistema***

*Presenta el historial de todos los datos de cambio, inclusión y exclusión
hechas en el sistema.*

1.  Acceder al menú principal Sistema \>
    Camino de auditoría \> Auditoría de datos;

2.  Se presentarán los logs de auditoría de todo el movimiento hecho en el programa,
    mostrando la fecha y hora de las actualizaciones, dirección IP, nombre del
    ejecutor de la actualización, nombre de la tabla, tipo de operación efectuada
    en el sistema. Al hacer clic en el botón datos se mostrará lo que de hecho fue
    actualizado en el programa.

    !!! Abstract "ATENCIÓN"

        El campo “Operaciones” presenta el tipo de acción hecha en la actualización
        del sistema en prueba. Se define por símbolos, y sus significados son:

        -   La letra "C" significa "Cambio" en los datos del sistema;

        -   La letra "I" simboliza la "Inserción" de nuevos datos al sistema;

        -   La letra "E" significa la "Exclusión" de los datos del sistema.  

3.  Se libera también la búsqueda de determinado *log* a través de los filtros dispuestos
    en la pantalla.

***Auditoría de accesos al sistema***

*Presenta el historial de los accesos al sistema (entradas y salidas).*

1.  Acceder al menú principal Sistema \>
    Camino de auditoría \> Auditoría de acceso;

2.  Se presentarán los usuarios que han iniciado y cerrado sesión en el sistema,
    registrando también la fecha y la hora de cada una de estas actividades;

    !!! Abstract "NOTA"  
        Si el sistema expirar, no será posible capturar el cierre de sesión del
        sistema, quedando registrado, por lo tanto, sólo la información de entrada
        de la sesión de acceso.  

3.  Existen filtros para ayudar la búsqueda de un determinado acceso.

***Auditoría de licencias del sistema***

*Informa las licencias utilizadas para la validación del sistema.*

1.  Acceder al menú principal Sistema \>
    Camino de auditoría \> Auditoría de licencia;

2.  Presenta los datos de las licencias adquiridas y usadas para la ejecución
    del sistema;

3.  Es posible buscar una determinada licencia y su plazo de validez por los
    filtros liberados en la pantalla principal.
    
!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/15/2019 – Larissa Lourenço
