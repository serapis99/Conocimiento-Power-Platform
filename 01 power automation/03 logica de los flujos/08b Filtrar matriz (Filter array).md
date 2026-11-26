---
titulo: Filtrar matriz (Filter array)
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
  - Filtrar matriz (Filter array)
---
# Filtrar matriz (Filter array)

La acción **Filtrar matriz (Filter array)** de Power Automate permite obtener un subconjunto de elementos de una matriz (*array*) mediante condiciones. Cada elemento se evalúa individualmente y solamente aquellos que cumplen los criterios establecidos permanecen en el resultado.

Es especialmente útil cuando necesitamos seleccionar registros específicos de una colección de datos, por ejemplo, filtrar empleados, productos, ventas o registros provenientes de Excel.

## 1. Origen de los datos (From)

El primer paso consiste en indicar de dónde provienen los datos que queremos filtrar.

Debemos recordar que los contenidos dinámicos de Power Automate se agrupan según la actividad que los genera. Por lo tanto, podemos identificar y seleccionar la salida de una actividad anterior.

En este ejemplo utilizaremos la salida (`body`) de la acción **Seleccionar (Select)**.

De esta manera, filtraremos la matriz previamente transformada, en lugar de trabajar directamente con todos los datos originales.

![](01%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125184926.png)

## 2. Condición de filtrado (Query)

En esta sección establecemos las condiciones que deben cumplir los elementos para permanecer en la matriz resultante.

Podemos utilizar expresiones para acceder a las propiedades de cada elemento y realizar comparaciones.

![](01%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125190426.png)

### Función item()

La función `item()` permite acceder al elemento actual que está siendo evaluado durante la iteración.

Para obtener una propiedad específica utilizamos:

```text
item()?['NombreCampo']
```

- `item()`: obtiene el elemento actual.
- `?`: permite acceder a la propiedad de manera segura si el objeto o la propiedad no están disponibles.
- `['NombreCampo']`: identifica la propiedad que queremos consultar.

### Conversión de datos con float()

En ocasiones, los datos provenientes de Excel u otras fuentes pueden llegar representados como texto, aunque conceptualmente sean números.

Para realizar comparaciones numéricas podemos utilizar `float()`, que convierte un valor compatible en un número decimal.

Ejemplo:

```text
float(item()?[' Valor'])
```

Esta expresión obtiene el campo ` Valor` del elemento actual y convierte su contenido a un número decimal.

Es importante respetar el nombre exacto de la propiedad, incluidos los espacios.


## 3. Ejemplo práctico

Supongamos que tenemos una matriz con registros de ventas y queremos conservar únicamente aquellos cuyo importe sea superior a 100.

Podemos utilizar la siguiente expresión:

```text
@greater(float(item()?['Importe']), 100)
```

La expresión realiza las siguientes operaciones:

1. `item()` obtiene el registro actual.
2. `['Importe']` obtiene el importe del registro.
3. `float()` convierte el importe a número decimal.
4. `greater()` comprueba si el importe es superior a 100.

Solamente los registros que cumplan esta condición permanecerán en la matriz resultante.

## 4. Consideraciones importantes

- La entrada de Filtrar matriz debe ser una matriz (*array*).
- `item()` permite acceder a las propiedades del elemento que se está evaluando.
- `float()` permite realizar comparaciones numéricas cuando los valores son convertibles.
- Los nombres de las propiedades deben coincidir exactamente con los de los objetos de entrada.
- Los valores nulos, vacíos o con formatos numéricos incompatibles pueden provocar errores de conversión.
- La acción conserva los objetos originales que cumplen las condiciones; no modifica su estructura.

> [!tip] Recomendación
> Si previamente utilizamos Seleccionar para limpiar y estructurar los datos, podemos utilizar su salida como entrada de Filtrar matriz. Así trabajamos únicamente con las propiedades que necesitamos y simplificamos las condiciones de filtrado.