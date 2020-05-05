Title: Introducción al Workflow de CITSmart
Description: Visión general de la creación y gestión de un flujo de trabajo en CITSmart.

# Introducción al Workflow de CITSmart

Flujos son representaciones visuales de algo que se mueve continuamente.Por lo tanto, se puede usar los flujos para representar gráficamente un proceso o cualquier acción. Ellos pueden materializarse en papel (documento físico) o una herramienta electrónica.En CITSmart, la funcionalidad de Workflow está diseñada para modelar sus objetivos de negocio al describir los pasos que debe seguir para alcanzar esos objetivos a través de un flujo digital inteligente. Es posible crear flujos de trabajo para ayudar en la gestión de servicio, problema, cambio, liberación, acciones de continuidad, solicitudes de viaje y compras. Como tal, el workflow tiene interacción con procesos clave de CITSmart.

Los flujos de trabajo automatizados dan vida a las actividades del sistema, permitiendo que las actividades de su organización sean digitalizadas y automatizadas. Por lo tanto, se puede crear flujos controlados por tareas, agregar notificaciones, subprocesos y establecer comunicación directa con otras aplicaciones, como Neuro - que es un framework para la generación de aplicaciones.

Descubrirá que las tareas cotidianas, como hacere un pedido, registrar un ticket, aprobar una solicitud, se pueden realizar de forma rápida e inteligente, evitando la pérdida de tiempo. Los flujos de CITSmart lo ayudan a materializar sus procesos comerciales en una vista sistémica en la que tiene un control completo de lo que sucede.

## Conocer la funcionalidad del flujo

En primer lugar, debe familiarizarse con los conceptos básicos, las reglas comerciales y la interfaz de usuario. La visualización la funcionalidad del menú CITSmart depende de los permisos asignados a un perfil de acceso, asegúrese de tener este permiso. Si no tiene este acceso, un gestor puede otorgarle este acceso.

Para saber si su perfil tiene este permiso, acceda al menú superior izquierdo de la pantalla y asegúrese de que la primera opción de acceso sea el Menú principal **Workflow**;


![workflow menu CITSmart][1]

**Estándar del sistema**

1: Crear un Workflow;

2: Construir Expresiones;

3: Modelado de procesos;

**Integración Neuro**

4: Flujo de Integración;

5: Reglas de negocio;

6: Proceso de Negocio;

!!! note "NOTAS"
   Estos elementos solo estarán disponibles cuando la aplicación Neuro esté habilitada en su instancia;

Si ya tiene este acceso, simplemente haga clic y seleccione la opción **Diseño de flujo** para ver la pantalla de administración.

## Pantalla de Gestión del Flujo

En la pantalla de gestión de flujo se puede: Crear un nuevo Flujo, Editar, exportar y borrar.

![workflow management CITSmart][2]

1: **Nuevo** - hacer clic para comenzar un nuevo proyecto de flujo;

2: **Campo de búsqueda** - buscar un flujo por su nombre o parte;

3: **Editar** - hacer clic para editar un flujo existente, siendo posible seleccionar qué versión editar;

4: **Exportar** - generar un documento exportable en formato JSON;

5: **Eliminar** - hacer clic para quitar un flujo;

## Crear y Editar un Flujo

Al hacer clic en el botón **Nuevo** o **Editar** se accede a la interfaz de creación/edición del flujo de trabajo que consta de dos pestañas, la pestaña **Datos del flujo**, donde ingresará los datos de identificación, y la pestaña **Diagrama** donde puede diseñar el flujo.

En un nuevo flujo, encontrará cuatro botones con las funciones **importar**, **grabar**, **limpiar** y **volver**, además, se puede importar un flujo (exportando previamente en formato JSON).

![fist button CITSmart][3]

Si edita un flujo ya existente, los botones se cambian agregando la opción de **Generar Documentación** y cambiando **Importar** por **Grabar**.

![second button CITSmart][4]

### Pestaña Datas del Flujo  

Datos del Flujo es una pestaña para la identificación del flujo, donde puede estructurar nombres para una mejor experiencia:

![flow data CITSmart][5]

1: **Nombre** – Asignar un nombre a la ID del flujo para que pueda identificarlo en caso de vinculación o asignación;

2: **Proceso** – Asignar al flojo un proceso entre todos aquellos en CITSmart para que esté mejor definido e identificado;

3: **Versión** – Visor de la versión actual del flujo abierto;

4: **Descripción** – Asignar una descripción del flujo para una fácil comprensión;

5: **Permitir la reapertura** – Opción para permitir que las actividades vinculadas a este flujo se vuelvan a abrir independientemente de la configuración del grupo;

6: **Grabar datos de objetos de negocio en la creación del ticket** – Opción que le permite crear o actualizar datos de objetos de negocio configurados en nuestro idioma Neuro al crear un ticket;

7: **Actualizar datos de objetos de negocio después de realizar las tareas de usuario** – Opción que permite actualizar los objetos de negocio creados durante la ejecución de las tareas del usuario.

### Pestaña Diagrama  

En la pestaña **diagrama** encontramos varios Elementos para la construcción del flujo agrupados en **Eventos**, **Actividades**, **Extensiones**, **Gateways**, **Swimlanes** y **Artefactos**, son varios componentes para una mejor construcción e interacción del flujo de trabajo. A continuación se muestra un ejemplo de un flujo que en la creación.

![diagram CITSmart][6]

1: **Elementos** – Estos son conjuntos de elementos/herramientas para usar en el diseño del flujo, como se explica en el elemento de Conceptos Básico;

2: **Área de Diseño** – sitio para diseño y construcción del flujo de trabajo;

### Pestaña Documentación

En la pestaña Documentación se puede generar un documento con toda la información del flujo diseñado - la descripción de los elementos utilizados en el flujo de trabajo y los documentos vinculados al flujo - siendo posible exportarlo a PDF.  

## Y ahora, ¿qué debo hacer?

Ahora puede crear un flujo de trabajo, piense en una necesidad de negocio y los actores involucrados. Vea nuestra documentación, ella te ayudará en esta jornada.

## Relacionado
[Conceptos básicos](https://docs.citsmart.com/pt-br/citsmart-platform-8/workflow/basic-concepts.html)

[1]:images/workflow-menu-citsmart.png
[2]:images/workflow-management-citsmart.png
[3]:images/fist-button-citsmart.jpg
[4]:images/second-button-citsmart.png
[5]:images/flow-data-citsmart.png
[6]:images/diagram-citsmart.png
