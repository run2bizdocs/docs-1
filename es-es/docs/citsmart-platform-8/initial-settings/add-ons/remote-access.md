Title: Implementar Acceso Remoto

# Implementar Acceso Remoto

La funcionalidad de acceso remoto permite que los equipos se tengan acceso de forma remota desde su instancia de CITSmart. En este sentido, utilizamos los recursos del protocolo VNC (Virtual Network Computing) a través del Apache Guacamole - Gateway de acceso remoto basado en la web - para hacer esta operación viable. Además de poder acceder remotamente a un elemento de configuración, todas las sesiones se guardan y se ponen a disposición de la información del EC. Esto garantiza un mejor control sobre las acciones realizadas, proporcionando un ambiente confiable y auditable.

Esta funcionalidad es un complemento (add-on) a la Gestión de Configuración y depende del proceso de inventarios para hacer el acceso remoto viable a un EC.


## Antes de empezar

Los siguientes requisitos antecede el uso efectivo de esta funcionalidad:
- Tener la Gestión de Configuración implementada;
- Tener un proceso de inventario definido y funcional;
- Tener los datos 

## Procedimiento

1. Descargar el contenedor GUACD;
2. Configurar las propriedades del GUACD en el servidor de aplicación;

    ```java
    CITSMART_PROTOCOL=http
    CITSMART_URL=your-instance.citsmartcloud.com
    CITSMARTGUACD_ID=guacd_id
    CITSMART_LOGIN=admin
    CITSMART_PASSWORD=********
    ```
	
3. Definir el directorio para la grabación de los vídeos (ej. /mp4);
    
    !!! success "Grabación de vídeo"
        Después del cierre de la sesión de acceso remoto, el vídeo generado entra en una cola de copilación para luego ser disponible en la plataforma. El tiempo de compilación dependerá del tiempo de sesión, además, el comienzo de la compilación está vinculado a la rutina cron, establecida en la conexión de acceso remoto.
    
## Lo que hacer después

Con el servicio del GuaCD activo y comunicable, el siguiente paso es crear una conexión de acceso remoto en su instancia y probar el recurso.

## Relacionados

[Crear conexión con el servidor de acceso remoto][1]

[1]:/es-es/citsmart-platform-8/processes/configuration/configuration/configure-remote-access.html
