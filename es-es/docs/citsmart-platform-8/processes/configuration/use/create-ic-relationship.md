Title: Relacionar IC a un servicio

# Relacionar Ítem de Configuración a un servicio

El registro de la relación entre los ítems de configuración y los servicios tiene como objetivo mostrar en la CMDB las dependencias existentes entre cada uno de estos elementos. El registro se hace para ayudar a los operadores de IC a identificar servicios o elementos que se verán afectados durante el manejo de un cambio, ya sea en el area del IC, en el manejo de un incidente, de un cambio o  de un portafolio de servicio.
La relación existe de la siguiente manera:

- Entre Ítens de Configuración con otros Ítens de Configuración;
- Entre Ítens de Configuración con Servicios de Negocio/Apoyo;

## Lo qué hacer antes

El registro de la relación requiere:

- [X] Tener acceso a la interfaz de administración CMDB (consulte [Crear Perfil de Acceso][1]);

- [X] Registrar el tipo de relación de IC (consulte [Registrar el tipo de relación de IC][2]);

- [X] Tener Ítens de configuración inventariados;

- [X] Tener servicios configurados en el portafolio (negocio/apoyo);

## Procedimiento

1. Acceder a la funcionalidad por el menú Procesos > Gestión de Configuración > CMDB;

2. Buscar y seleccionar un Ítem de Configuración;

3. Hacer clic en la opción a la izquierda "Relación", después en "Editar";

4. Completar los campos disponibles;

    | Campo | Descripción |
    |-------|-----------|
    |Ítem (no editable) | Informa el Ítem de Configuración seleccionado para el diseño de las relaciones|
    |Icono | Le permite seleccionar un diseño que represente ese ítem de configuración |
    |Tipo de Relación| Identifica el tipo de relación (registrar tipo de relación de IC) |
    |Nombre|Autocompletar que devuelve las descripciones de Tipo de Relación registradas en la pantalla Tipo de Relación|
    |Nivel|Devuelve los niveles inferior y superior registrados en la pantalla Tipo de Relación|
    |Para|Identifica el otro punto del enlace de la relación;|
    |Tipo| Opciones para seleccionar: "Ítem de Configuración", "Servicio de Negocio" o "Servicio de Apoyo"|
    |Ítem|Autocompletar que le permite buscar el tipo seleccionado|
    |Icono|Le permite seleccionar un diseño que representa ese tipo seleccionado|

5. Hacer clic en "Guardar" para guardar los cambios hecho.

## Relacionado

[Ver mapa de relación de un IC][4]

[Crear Ítem de Configuración][3]

[1]:/es-es/citsmart-platform-8/initial-settings/access-settings/profile/create-profile-access.html
[2]:/es-es/citsmart-platform-8/processes/configuration/configuration/create-type-relationship-ci.html
[3]:/es-es/citsmart-platform-8/processes/configuration/use/register-CI.html
[4]:/es-es/citsmart-platform-8/processes/configuration/use/view-ci-relationship-map.html
