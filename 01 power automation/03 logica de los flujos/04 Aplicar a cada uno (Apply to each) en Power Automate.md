---
titulo: Aplicar a cada uno (Apply to each) en Power Automate
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
  - Aplicar a cada uno (Apply to each) en Power Automate
---
# Aplicar a cada uno (Apply to each) en Power Automate

## 1. ¿Qué es Aplicar a cada uno?

La actividad **Aplicar a cada uno (Apply to each)** pertenece al módulo **Control** de Power Automate y permite recorrer una colección de elementos, ejecutando una o varias acciones por cada registro.

Es especialmente útil cuando trabajamos con datos provenientes de Excel, SharePoint, bases de datos u otras aplicaciones.

## 2. Ejemplo práctico: recorrer registros de Excel

Supongamos que tenemos un archivo de Excel con información de empleados y sus ventas. Queremos comprobar si cada persona cumplió su meta y enviarle un correo dependiendo del resultado.

### Paso 1. Obtener los registros de Excel

Utilizamos la actividad **Enumerar las filas de una tabla (List rows present in a table)** del conector Excel Online (Business).

Esta acción devuelve los registros almacenados en una tabla de Excel.

### Paso 2. Recorrer la colección

Agregamos la actividad **Aplicar a cada uno (Apply to each)**.

En sus parámetros, específicamente en **Seleccionar una salida de los pasos anteriores**, seleccionamos la colección `value` que devuelve la actividad de Excel.

De esta manera, Power Automate recorrerá cada registro individualmente.

### Paso 3. Agregar una condición

Dentro de la actividad Aplicar a cada uno, podemos agregar otras actividades. En este caso, incorporamos una actividad **Condición (Condition)** para comprobar si cada empleado cumplió su meta de ventas.

Supongamos que la meta es de 1000.

Utilizamos la función `float()` para convertir el campo de ventas a un número decimal:

```text
float(items('Apply_to_each')?['Ventas'])
```

Después, configuramos la condición:

```text
Ventas > 1000
```

Esto permite comparar correctamente el valor numérico de las ventas con la meta establecida.

### Paso 4. Enviar correos electrónicos

Dentro de las ramas de la condición agregamos la actividad **Enviar un correo electrónico (V2)**.

- **Si verdadero:** enviamos un correo notificando al empleado que cumplió su meta.
- **Si falso:** enviamos un correo informando que no alcanzó la meta.

Estas acciones se ejecutarán para cada empleado que se procese dentro del bucle.

## 3. Trabajar con fechas provenientes de Excel

Cuando trabajamos con fechas provenientes de Excel, podemos encontrarnos con valores que no tienen el formato esperado.

Para dar formato a un valor de fecha y hora utilizamos la función:

```text
formatDateTime()
```

Ejemplo:

```text
formatDateTime(
    items('Apply_to_each')?['Fecha'],
    'dd/MM/yyyy'
)
```

Esta expresión permite presentar la fecha en formato día/mes/año, siempre que el valor de entrada sea una fecha reconocible por Power Automate.

### 3.1. Convertir fechas seriales de Excel

Excel puede almacenar las fechas como números seriales. Por ejemplo, un valor como `45292` representa una fecha mediante la cantidad de días transcurridos desde una fecha de referencia.

En estos casos, `formatDateTime()` no puede interpretar directamente el número serial como una fecha.

Para solucionarlo, utilizamos la función `addDays()` junto con la fecha base `1899-12-30`.

**Expresión:**

```powerautomate
formatDateTime(
    addDays(
        '1899-12-30',
        int(items('Apply_to_each')?['Fecha'])
    ),
    'dd/MM/yyyy'
)
```

**¿Cómo funciona?**

1. `items('Apply_to_each')?['Fecha']`: obtiene el valor de la columna Fecha del registro actual.
2. `int()`: convierte el número serial en un entero.
3. `addDays()`: suma la cantidad de días del número serial a la fecha base `1899-12-30`.
4. `formatDateTime()`: presenta el resultado en el formato `dd/MM/yyyy`.

>[!important] **Importante:** 
>esta expresión está pensada para fechas seriales del sistema de fechas 1900 de Excel. Al utilizar `int()`, se descarta la parte decimal del número serial, por lo que no se conserva la hora. Si necesitamos conservarla, debemos convertir también la fracción del día.

Además, no todas las fechas provenientes de Excel necesitan esta conversión. Si el conector ya devuelve una fecha en formato ISO 8601, podemos utilizar directamente `formatDateTime()`.

## 4. Recomendaciones al trabajar con colecciones

Es recomendable validar y convertir los tipos de datos antes de utilizarlos en condiciones u operaciones matemáticas.

Esto se debe a que los datos provenientes de otras aplicaciones o conectores pueden recibirse como cadenas de texto, valores numéricos, fechas o valores nulos.

Algunas funciones útiles son:

| Función | Propósito |
|---|---|
| `float()` | Convierte un valor en número decimal. |
| `int()` | Convierte un valor en número entero. |
| `string()` | Convierte un valor en texto. |
| `formatDateTime()` | Da formato a valores de fecha y hora. |
| `parseDateTime()` | Interpreta una cadena de texto como fecha y hora. |
| `addDays()` | Suma o resta días a una fecha. |

>[!note] **Nota:** 
>antes de realizar conversiones, debemos comprobar que los valores no sean nulos o estén vacíos, ya que algunas funciones pueden generar errores si reciben datos no válidos.

