Title: Componente Lookup
Description: El componente lookup de Neuro permite la creación de interfaces master-datails en las listas de elementos.

# Componente Lookup

El componente lookup es un recurso de Neuro que le permite crear listas rápidas de opciones y puede tener una interfaz de master-details, es decir, mostrar una lista maestra y los detalles del elemento seleccionado, como crear campos para que el usuario seleccione un país, luego seleccione un estado del país y luego una ciudad del estado.

Para usar este recurso en formularios, se debe:

* [x] Crear los Lookup

* [x] Configurar elementos Lookup en el formulario

## Lo qué hacer antes

Antes de poder crear los componentes lookup, se debe crear una aplicación y, opcionalmente, una conexión de base de datos Neuro.

## Crear componentes Lookup

1. Acceder a la funcionalidad por el menú Neuro > Gestión > Componente Lookup;
2. Registrar el(los) componente(s) lookup;
3. Ingresar las informaciones:

    |Campo|Descripción|Ejemplo|
    |-----|---------|-------|
    |Nombre|Identificador que no deja espacio|pais|
    |Descripción|Informaciones de lookup|País|
    |Aplicación|Aplicación Neuro|My App|
    |Conexión de Base|Conexión de base de datos (igual que la utilizada en los objetos de negocio)|Neuro DB Connection|
    |Columna o expresión para campo clave|ID para retorno de la clave|idpais|
    |Columna u expresión para descripción|Retorno del campo descripción|nombrepais|
    |FROM y WHERE|Query para FROM y Query|`FROM pais`|

4. Hacer clic en "Testar componente", para ver el resultado;
5. Hacer clic en "Guardar" para registrar los datos.


## Diseño de la pantalla (Formulario)

1. Seleccionar un formulario;
2. Hacer clic en "Diseño de la pantalla";
3. Arrastre el elemento "Lookup" al area de diseño;
4. Cambiar el ancho del campo según la necesidad;
5. Informar el nombre de la Label;
6. En el elemento "Lookup", seleccionar el registro deseado;
7. Informar la propiedad "Modelo" (atributo de formulario que recibirá el valor del campo clave del lookup);
8. En el campo "Cláusula WHERE adicional", ingrese la sintaxis SQL cuando desee filtrar el resultado de la lista.

## Ejemplo de uso

Vamos a ilustrar la creación de una interfaz de master-detail para permitir al usuario seleccionar un país, un estado del país y una ciudad del estado seleccionado.

- **Lookup 1: País**

Nombre: pais

Descripción: País

Aplicación: My App

Conexión de Base: Neuro DB Connection 

Columna o expresión para campo clave: idpais

Columna o expresión para descripción: nombrepais

FROM y WHERE:

```mysql
FROM pais
```

- **Lookup 2: Estado**

Nombre: Estado

Descripción: Estado

Aplicación: My App

Conexión de Base: Neuro DB Connection 

Columna o expresión para campo clave: idestado

Columna o expresión para descripción: `nombreestado||'('||siglaestadosigla
||')'`

``` mysql
FROM estados
```

- **Lookup 3: Ciudad**

Nombre: estado

Descripción: Estado

Aplicación: My App

Conexão de Banco: Neuro DB Connection

Columna o expresión para campo clave: idciudad

Columna o expresión para descripción: nombreciudad

``` mysql
FROM ciudades
```

- **En el formulario**

Para usar la función de master details, es decir, mostrar datos basados en un elemento seleccionado previamente, puede usar la misma sintaxis SQL del objeto de negocio (como en el ejemplo a continuación);

Ingresar la sintaxis SQL en el campo "Cláusula WHERE adicional" del elemento Lookup;

``` mysql
iduf = ${nameModel.iduf:INTEGER}
```


O ingrasar en el componente Lookup en sí (campo FROM y WHERE);

``` mysql
FROM cidades
WHERE iduf = ${nameModel.iduf:INTEGER}
```
