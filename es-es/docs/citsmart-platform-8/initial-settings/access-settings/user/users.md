title: Registrar usuario
Description: Ofrece acciones diversas, como, incluir, cambiar y borrar un usuario.
# Registrar usuario


Para que el colaborador pueda acceder al sistema, es necesario crear un usuario.
El sistema enviará un correo electrónico con el login y contraseña del nuevo
usuario que se ha creado por CITSmart.

Esta funcionalidad ofrece acciones diversas, como, incluir, cambiar y borrar un
usuario.

!!! warning "ATENCIÓN"

    El envío de login y contraseña al registrar un nuevo usuario no incluye los 
    usuarios importados a través de AD o LDAP.

Antes de empezar
--------------------

Para registrar un usuario, es necesario registrar previamente el perfil de
acceso y el colaborador.

Configurar los parámetros:

|#|Descripción|
|--------|---------|
|33|URL de acceso al sistema.|
|455|ID de la plantilla de correo electrónico que se enviará al usuario con la contraseña cuando se crea o cambia el usuario|

El administrador puede crear una nueva plantilla de correo electrónico editando la plantilla ya existente

    ID: 205
    ID de la Plantilla de Correo Electrónico: ACCESSCREDENCIAL
    
Solo incluir las claves:

    Usuário: ${LOGIN}
    Contraseña: ${NUEVACONTRASENA}

Procedimiento
-----------------

1.  Acceder al menú principal Registros Generales \> Gestión de Personal \>
    Usuario;

2.  Completar los campos disponibles;

3.  Hacer clic en "Guardar".

4. El sistema verifica si hay una plantilla de correo electrónico para el nuevo 
   empleado que tiene la clave de contraseña para enviar por correo electrónico;

5. El administrador del sistema registra o cambia el login y contraseña de un empleado en la pantalla de usuario;

6. El sistema verifica si:
    
    -    el sistema usa la política de contraseña;
    -    el usuario es LDAP o no;
    
7. El sistema permite el imput de una nueva contraseña;

8. Al guardar, el sistema envía los nuevos datos por correo electrónico al empleado.


Relacionado
-----------

[Registrar colaborador](/es-es/citsmart-platform-8/initial-settings/access-settings/user/register-employee.html)

[Crear perfil de acceso](/es-es/citsmart-platform-8/initial-settings/access-settings/profile/create-profile-access.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/28/2019 – Anna Martins

