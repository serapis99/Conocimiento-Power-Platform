---
titulo: Variables de tipo objeto (Object) en Power Automate
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
  - Variables de tipo objeto (Object) en Power Automate
---
# Variables de tipo objeto (Object) en Power Automate

## 1. ¿Qué es un objeto?

Una variable de tipo **Object** permite almacenar información estructurada mediante pares de clave-valor (`key-value`).

Su funcionamiento es similar al de un diccionario: cada clave identifica un valor que puede ser consultado posteriormente.

Los objetos se utilizan frecuentemente para intercambiar información entre diferentes aplicaciones, consumir API y organizar datos en formato JSON.

## 2. Estructura básica

Un objeto está compuesto por propiedades, donde cada propiedad contiene una clave y un valor.

Ejemplo:

```json
{
    "nombre": "Juan",
    "edad": 25,
    "ciudad": "Bogotá"
}
```

En este ejemplo:

- `nombre`, `edad` y `ciudad` son las claves.
- `"Juan"`, `25` y `"Bogotá"` son los valores.

Podemos acceder a sus propiedades utilizando expresiones:

```text
variables('datosCliente')?['nombre']
```

Resultado:

```text
Juan
```

## 3. Arrays de objetos

Cuando necesitamos almacenar varios objetos dentro de una misma estructura, utilizamos un **Array de objetos**.

Ejemplo:

```json
[
    {
        "nombre": "Juan",
        "edad": 25
    },
    {
        "nombre": "María",
        "edad": 30
    }
]
```

En este caso tenemos una colección de dos objetos.

Podemos acceder a sus elementos mediante su posición:

```text
variables('listaClientes')?[0]?['nombre']
```

Resultado:

```text
Juan
```

Los índices de los arrays comienzan en cero.

## 4. Objetos anidados

Un objeto anidado es aquel que contiene otros objetos dentro de sus propiedades.

Ejemplo:

```json
{
    "nombre": "Juan",
    "edad": 25,
    "direccion": {
        "ciudad": "Bogotá",
        "pais": "Colombia"
    }
}
```

Para acceder a una propiedad del objeto anidado:

```text
variables('datosCliente')?['direccion']?['ciudad']
```

Resultado:

```text
Bogotá
```

## 5. ¿Para qué se utilizan los objetos?

Los objetos son especialmente útiles en Power Automate para:

- **Comunicación entre aplicaciones:** intercambiar información mediante API y servicios web.
- **Organización de datos:** agrupar información relacionada bajo una misma estructura.
- **Consumo de API:** interpretar las respuestas JSON de diferentes servicios.
- **Envío de información:** construir estructuras de datos para enviar a otras aplicaciones.
- **Almacenamiento temporal:** guardar información estructurada durante la ejecución de un flujo.

## 6. Diferencias entre objetos y arrays

| Característica | Object | Array |
|---|---|---|
| Estructura | Pares clave-valor. | Colección ordenada de elementos. |
| Acceso | Mediante el nombre de una propiedad. | Mediante la posición o índice. |
| Ejemplo | `{"nombre":"Juan"}` | `["Juan","María"]` |
| Uso | Representar una entidad o registro. | Almacenar varios elementos. |

**Nota:** un array puede contener objetos, números, cadenas de texto u otros arrays. Asimismo, un objeto puede contener propiedades cuyos valores sean otros objetos o arrays.