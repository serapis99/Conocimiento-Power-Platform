---
titulo: Operaciones de datos (Data Operations)
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-25
ultimo_repaso: 2026-11-25
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - Seleccionar (Select)
---
# Seleccionar (Select)

La acción **Seleccionar (Select)** de Power Automate permite modificar la estructura de los objetos que componen una matriz (*array*), eligiendo qué campos conservar, cambiando sus nombres y transformando sus valores.

Su principal utilidad es simplificar los datos recibidos de otras aplicaciones, conservando únicamente la información necesaria para las siguientes etapas del flujo.

## 1. ¿Para qué sirve?

Al obtener información de fuentes como Excel, SharePoint o una API, podemos recibir objetos con campos adicionales que no necesitamos procesar.

Por ejemplo, una consulta a Excel puede devolver registros con propiedades como:

```json
{
    "@odata.etag": "",
    "ItemInternalId": "2e10c0c3-4e01-4c0f-954c-dea085b1473c",
    "Nombre": "Carlos",
    "Correo": "carlos@ejemplo.com",
    "Cargo": "Analista",
    "Departamento": "Sistemas"
}
```

Si nuestro flujo únicamente necesita el nombre y el correo electrónico, podemos utilizar **Seleccionar** para conservar esos campos y descartar los demás.

El resultado sería:

```json
{
    "Nombre": "Carlos",
    "Correo": "carlos@ejemplo.com"
}
```

De esta manera obtenemos una estructura más limpia, sencilla y fácil de utilizar en las siguientes acciones.

## 2. Configuración de la acción

La acción cuenta principalmente con dos elementos:

### Desde (From)

Indica la matriz de datos sobre la que se realizará la transformación.

Normalmente se utiliza el contenido dinámico **value** de una acción anterior, como Listar las filas presentes en una tabla de Excel.

Es importante proporcionar una matriz de objetos y no un objeto individual.

### Asignación de campos (Map)

En esta sección definimos los campos que tendrá cada objeto de salida mediante pares de clave y valor.

- **Clave:** nombre que tendrá la propiedad en el nuevo objeto.
- **Valor:** dato de origen o expresión que proporcionará su contenido.

Por ejemplo:

| Clave | Valor |
|---|---|
| Nombre | `item()?['Nombre']` |
| Correo | `item()?['Correo']` |
| Área | `item()?['Departamento']` |

El resultado será una nueva matriz con los campos definidos.

![](02%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125181613.png)

## 3. Transformación y limpieza de datos

Una característica importante de Seleccionar es que no se limita a conservar campos existentes. También permite aplicar expresiones para transformar los valores durante el proceso.

Por ejemplo:

| Operación | Expresión |
|---|---|
| Eliminar espacios al inicio y al final | `trim(item()?['Nombre'])` |
| Convertir texto a minúsculas | `toLower(item()?['Correo'])` |
| Convertir texto a mayúsculas | `toUpper(item()?['Nombre'])` |
| Convertir un valor a texto | `string(item()?['Identificacion'])` |

Esto permite realizar un preprocesamiento de los datos antes de utilizarlos en otras acciones.

## 4. Características y limitaciones

- Trabaja sobre matrices de objetos.
- Permite seleccionar y descartar propiedades.
- Permite cambiar los nombres de las propiedades.
- Permite crear nuevas propiedades.
- Permite transformar los valores mediante expresiones.
- Mantiene la cantidad original de elementos de la matriz.
- No permite filtrar registros según condiciones; para ello se utiliza **Filter array**.

> [!important] Diferencia importante
> Seleccionar modifica la estructura de los objetos, pero no elimina registros de la matriz. Si necesitamos excluir registros completos según determinadas condiciones, debemos utilizar Filtrar matriz (Filter array).


