Title: Notas de Release
Description: Notas de release, correcciones de errores y mejoras en la CITSmart Platform - V.8.0.

#Notas de Release... (2019/03/01)

##Correcciones

###Gestión de Ticket

Las funcionalidades de Sub-Solicitud y Solicitud Relacionada sufrieron una reestructuración que proporciona mayor conformidad a sus atribuciones, el enfoque de esta corrección fue aproximar la funcionalidad de lo que realmente es su propuesta.

Para más información, vea Relacionar Ticket y Registrar Sub-Solicitud
###Webservices
La sincronización para la creación de nuevas Actividades ha sufrido un cambio en su regla de negocio, porque no es posible crear una actividad que no tenga vínculo con el Servicio de Negocios y Portafolio. Por lo tanto, el webservice designado para crear, abrirá un ticket con los parámetros pasados en la configuración inicial del servicio.

La funcionalidad de crear un nuevo usuario, cuando está habilitada la sincronización de datos permanece coherente.

###Flujo

Se trata de barrar la edición de expresiones nativas y expresiones del mismo nombre.

##Nuevas Funcionalidades y Mejoras

###Acceso Rápido

El acceso rápido permite al usuario encontrar los principales procesos por medio de iconos que auxilian en la fijación y visualización de forma eficiente.

*El usuario visualiza solamente los iconos de los procesos que tiene acceso, con la excepción de los iconos del Simple, Portal del Conocimiento, Centro de Experiencia y Guía del Usuario.*

###Configuración de notificación por correo electrónico de ticket delegado
Creamos la posibilidad de configuración de notificación por correo electrónico en la funcionalidad de delegación del ticket
Para más información, vea Notificación vía correo electrónico de ticket delegado
###Configuración de notificación por correo electrónico de ticket reclasificado
Creamos la posibilidad de configuración de notificación por correo electrónico en la funcionalidad de reclasificación del ticket
Para más información, vea Notificación vía correo electrónico de ticket reclasificado

###Gestión de Cambio
La versión 8.0.0.0 de CITSmart ha sufrido mejoras en el proceso de gestión de cambios, trayendo el mundo ágil para gestionar las actividades que deberán ocurrir durante el alcance del cambio.

*Nota:* Esta funcionalidad reemplaza los parámetros de flujo estándar para el uso del proceso de cambio, por lo que es necesario cambiar para esta configuración.


Para más información, vea Gestión de Cambio

###Gestión de Problema
En la versión 8.0.0.0 de CITSmart, el proceso de gestión de problemas permite agregar actividades para auxiliar en la gestión de los equipos durante el diagnóstico de la causa raíz.

*Nota:* Esta funcionalidad reemplaza los parámetros de flujo estándar para utilizar el proceso de problema, por lo que es necesario cambiar para esta configuración.


Para más información, vea Gestión de Problema

###Configuración de uso para la Gestión de Liberación
El proceso de liberación gana más fuerza en la planificación, pruebas y homologación, permitiendo la designación de las actividades y gestión a la vista.

*Nota:* Esta funcionalidad reemplaza los parámetros de flujo estándar para utilizar el proceso de liberación, por lo que es necesario cambiar para esta configuración.


Para más información, vea Gestión de Liberación

###Revisión de Comentarios
En la versión 8.0.0.0, CITSmart permite la evaluación y publicación de los comentarios escritos sobre un conocimiento.

Para más información, vea Revisión de Comentario

###Acceso a la base de conocimiento de usuarios externos
Innovamos la forma de acceso a la base de conocimiento para usuarios que no tienen login de acceso a la herramienta CITSmart.

En la versión 8.0.0.0, conocimientos con permiso de visualización podrán ser accedidos por la comunidad en general, basta tener el enlace de acceso.


Para más información, vea Configurar acceso externo al Portal de Conocimiento

###Gestión de Elemento de Configuración
Se ha mejorado la experiencia del usuario, destacando un dashboard que presenta la cantidad de elementos de configuración, por grupo, tipo y aglutinados en los procesos de Incidente, Cambio y Liberación, dejando a la vista posibles EC que pasarán por alteración o involucrados en algún incidente.

Para más información, vea Gestión de Elemento de Configuración

###Regla de Escalonamiento
Simplificamos el uso de las reglas de escalonamiento de los tickets, con pocos pasos será posible implementar la regla que antes contaba con innumerables configuraciones.

*Nota:* Esta funcionalidad reemplaza el uso de diversos parámetros de escalonamiento, por lo que es necesario cambiar para el uso efectivo de las reglas de escalonamiento.


Para obtener más información, vea Crear regla de escalonamiento

###Aprobación de Ticket
En la versión 8.0.0.0 de CITSmart, incluimos la aprobación de tickets a través de un nuevo icono directo en la lista de atención, no será necesario abrir el ticket para hacer la atención, presentamos la información disponible y las opciones configuradas para aceptar o rechazar el llamado.

Esta funcionalidad está disponible en Mobile SM y en el Portal de Servicios.

Para más información, vea Aprobar un ticket

###Actualización automática de la lista de tickets
Permitimos que la función de actualización automática de la lista de tickets esté habilitada para actualizar la lista automáticamente de vez en cuando.

Para más información, vea Actualización Automática de la Lista de Tickets

###Ocurrencia
El perfeccionamiento del registro de ocurrencia permite que el solicitante o técnico sea notificado vía correo electrónico. Además del permiso de incluir tiempo de ejecución de la actividad y mantener el secreto de la información catastrada, para que solamente los técnicos permitidos la vean.

Para más información, vea Registrar Ocurrencia en Ticket

###Simple - Gestión Ágil y a la vista
Simple fue creado con el propósito de traer el concepto de gestión ágil a la herramienta.
De forma independiente o aglutinada en una de las soluciones de Problema, Cambio y Liberación, Simple permite la reutilización de Sprints, compartir recursos, envío de actividades a otras Sprints y gestión a la vista.

Para más información, vea Simple

###Área del cliente
Proporcionamos un área específica para mejorar la experiencia de uso. En esta área se permitirá la presentación de servicios, informaciones, informes que más se aproximan al uso del día a día del cliente.

Para más información, vea Centro de Experiencia

###Business Intelligence
A partir de la versión 8.0.0.0 ofrecemos algunos informes cuantitativos de los principales procesos contenidos en CITSmart a través de nuestra nueva plataforma BI.

Para más información, vea Business Intelligence

###Auditoría
Reformulamos la auditoría del sistema para aumentar la agilidad y confiabilidad del recurso de búsqueda de auditoría.

Para más información, vea Auditoría del Sistema

###Política de Seguridad de Contraseñas
Mejoramos el requisito de seguridad de la información, implementado formas de seguridad de contraseñas para usuarios internos.

Para más información, vea Política de Seguridad de Contraseñas

###Movilidad
Entregamos una nueva aplicación que, de forma robusta, permitirá la atención a campo de técnicos que momentáneamente están sin conexión a internet.

La experiencia de movilidad va más allá de los recursos de suscripción y notas.

Para más información, vea Mobile Field Service

Aún en el contexto de movilidad, y no menos robusta, mejoramos la aplicación Mobile SM, que posee, entre otros usos, la capacidad de firma, aprobación y notas.

Para más información, vea Mobile Service Management

###Neuro
A partir de la versión 1.2.3.0 de Neuro, es posible crear automáticamente un cuestionario del CITSmart a partir del registro de objeto de negocio de Neuro. La idea de esta innovación es facilitar la extracción de respuestas de cuestionarios del CITSmart y formar informes de forma sencilla con la ayuda del Smart Report.

###Flujo
El paquete de flujos entregados a los procesos de Problema, Cambio y Liberación fueron simplificado, los productos fueron remodelados para estar adheridos a las posibilidades que el flujo ofrece.

Si el cliente no desea utilizar los nuevos flujos, la última versión 7.1.0 seguirá funcionando perfectamente.
