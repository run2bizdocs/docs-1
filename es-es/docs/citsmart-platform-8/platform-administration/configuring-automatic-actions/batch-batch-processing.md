title: Procesamiento Batch
Description: Tiene el objetivo de registrar el procesamiento batch, que podrá ser utilizado en otras rutinas del sistema.
# Procesamiento Batch

Esta funcionalidad tiene el objetivo de registrar el procesamiento batch, que podrá 
ser utilizado en otras rutinas del sistema.

Rutinas como:

   - Verificación de correo electrónico
   
   - Verificación de la hora del servidor
   
   - Distribución automática de Tickets con balance de carga de trabajo 

Procedimiento
-------------

1.  Acceder al menú principal Sistema \> Procesamiento Batch;

2.  Hacer clic en "Nuevo";

3.  Completar los campos disponibles (descripción, tipo [clase Java,
    RhinoScript, SQL]; situación; expresión cron que define el tiempo de
    ejecución de la rutina y el contenido de la rutina, que se describirán en el
    contexto de la rutina para ser ejecutados en la herramienta);
    
    Ejemplo de contenido "Clase Java":
    ```html
    br.com.centralit.citcorpore.quartz.job.JobConfiguracaoAberturaAutomaticaViaEmail
    ``` 

4.  Hacer clic en "Guardar".

Rutinas Batch
-------------

-   Volver a la hora del servidor (descargar script adjunto);

    -   Tipo: RhinoScript

-   Hacer la lectura de correo electrónico (descargar script adjunto).

    -   Tipo: Clase Java

Adjunto
-----
[Descargar - Rutina de verificación de correo electrónico][1]

[Download - Rutina devuelve hora servidor][2]

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 – Larissa Lourenço


[1]:/es-es/citsmart-platform-8/platform-administration/configuring-automatic-actions/images/rotina-verificar-email.docx
[2]:/es-es/citsmart-platform-8/platform-administration/configuring-automatic-actions/images/rotina-retorna-hora-servidor.docx
