Description: Release Notes de CITSmart Versión 8.0.0.5 de 22/04/2019

# Versión 8.0.0.5
_25/04/2019_


## Problemas Resueltos

| Problema | Descripción                                                                                                                                              |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3360     | Ges. de Problema - Error al recuperar la Solución definitiva                                                                                                |
| 3361     | Ges. de Problema - Error al recuperar campo de cierre                                                                                             |
| 3362     | Ges. de Problema - Error al recuperar error conocido                                                                                                    |
| 3363     | Ges. de Configuración - Error al recuperar Cambios Terminados relacionadas al Elemento de Configuración                                                        |
| 3364     | Ges. Liberación – Error al vincular Cambio cerrada en la Liberación                                                                                       |
| 3365     | Ges. Problema – Adecuación de interfaz para mostrar los campos "Mensaje de error asociado" y "Diagnóstico"                                          |
| 3366     | Ges. Cambio – Error al retornar Riesgo Simplificado                                                                                                     |
| 3393     | Ges. Liberación – Retorno de la Regla de Negocio al vincular un cambio que tenga IC vinculado a una Liberación, vincular automáticamente el IC a la Liberación |
| 3282     | Ges. Eventos – Error al Editar un administrador genérico Zabbix                                                                                                 |
| 3115     | Ges. Eventos – Renderización mayor de la pantalla de Ges de Ticket                                                                                             |
| 3394     | Ges. Liberación – Sistema duplica los datos adjuntos al avanzar el flujo                                                                                               |
| 3388     | Ges. Problema – Grabación de error conocido no configura el campo de archivado y sistema no puede recuperar el conocimiento                              |
| 3419     | Ges. Cambio – Sistema no recupera el adjunto colocado en el campo de Revisión y cierre                                                                    |

*Error conocido y solución*

Se atentem para o cenário descrito:

-   Condiciones previas:

    1.  El cliente estará actualizando la versión 7 para la versión 8.0.0.5;

    2.  El consultor no parametrizó en el Portafolio de Problemas la carpeta 
        para grabar la base de conocimiento de Error Conocido;

-   Lo que ocurre:

    1.  El usuario accede a la pantalla de Gestión de Problemas;

    2.  El usuario informa del campo Causa Raíz e intenta accionar la grabación 
        de la base de conocimiento;

    3.  Al abrir la pantalla de Base de Conocimientos para grabar ,el sistema muestra 
        el mensaje de que el usuario no tiene permiso;

-   ¿Por qué ocurre esto?

    1.  El mensaje se produce porque el consultor no ha indicado cuál debería ser la 
        carpeta de grabación del error conocido en el Portafolio de Problema;

    2.  Una vez intentado grabar el error conocido, el sistema no identifica la 
        carpeta y emite el mensaje;

    3.  En estos casos, busque el soporte Citsmart para hacer la adecuación de este 
        registro;

    4.  Haga la configuración de la carpeta para la grabación de un error conocido en 
        la pantalla de Portafolio de Problema;

    5.  En el siguiente registro el mensaje no se repetirá.
    
    
        
Camino para los paquetes:

**SM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Enterprise/8.0.0.5/CitsmartITSM-Enterprise-8.0.0.5.war.zip  
  
**Inventory**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip  
  
**EVM**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip  
  
**Neuro**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.8.war.zip  
  
**Audit**:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.2.0.zip
