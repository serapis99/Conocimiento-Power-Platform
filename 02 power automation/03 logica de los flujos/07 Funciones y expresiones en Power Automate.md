---
titulo: Funciones y expresiones en Power Automate
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
  - Funciones y expresiones en Power Automate
---
# Funciones y expresiones en Power Automate

## 1. ¿Qué son las funciones?

Las funciones de Power Automate permiten manipular, transformar, evaluar y procesar información dentro de un flujo.

Se utilizan mediante expresiones que pueden incorporarse en diferentes actividades, como condiciones, inicialización de variables, composición de datos y otras acciones.

Microsoft organiza las funciones de expresiones en nueve categorías principales.

## 2. Categorías de funciones

### 2.1. Funciones de cadena (String)

Permiten trabajar con cadenas de texto: unirlas, dividirlas, buscar contenido, reemplazar caracteres y modificar su formato.

Algunas funciones:

| Función | Descripción |
|---|---|
| `concat()` | Une varias cadenas de texto. |
| `split()` | Divide una cadena utilizando un separador. |
| `substring()` | Extrae una parte de una cadena. |
| `replace()` | Reemplaza una parte del texto. |
| `toLower()` | Convierte el texto a minúsculas. |
| `toUpper()` | Convierte el texto a mayúsculas. |
| `trim()` | Elimina espacios al inicio y al final. |
| `indexOf()` | Busca la posición de un texto. |

Ejemplo:

```text
toUpper('power automate')
```

Resultado:

```text
POWER AUTOMATE
```

### 2.2. Funciones de colección (Collections)

Permiten trabajar con colecciones de elementos, principalmente matrices (Arrays).

Se utilizan para consultar, combinar, contar y manipular elementos de una colección.

Algunas funciones:

| Función | Descripción |
|---|---|
| `contains()` | Comprueba si una colección contiene un elemento. |
| `empty()` | Comprueba si una colección está vacía. |
| `first()` | Obtiene el primer elemento. |
| `last()` | Obtiene el último elemento. |
| `length()` | Devuelve la cantidad de elementos. |
| `join()` | Une los elementos de una matriz en una cadena. |
| `union()` | Combina colecciones y elimina duplicados. |
| `intersection()` | Obtiene los elementos comunes entre colecciones. |

Ejemplo:

```text
length(createArray('Juan', 'Pedro', 'Ana'))
```

Resultado:

```text
3
```

### 2.3. Funciones lógicas (Logical comparison)

Permiten evaluar condiciones y realizar comparaciones entre valores.

Son especialmente útiles en las actividades `Condición` y `Hacer hasta`.

Algunas funciones:

| Función | Descripción |
|---|---|
| `and()` | Comprueba si todas las condiciones son verdaderas. |
| `or()` | Comprueba si al menos una condición es verdadera. |
| `not()` | Invierte el resultado lógico. |
| `equals()` | Comprueba si dos valores son iguales. |
| `greater()` | Comprueba si un valor es mayor que otro. |
| `greaterOrEquals()` | Comprueba si un valor es mayor o igual. |
| `less()` | Comprueba si un valor es menor que otro. |
| `lessOrEquals()` | Comprueba si un valor es menor o igual. |

Ejemplo:

```text
and(
    greater(variables('Ventas'), 1000),
    greater(variables('Clientes'), 50)
)
```

La expresión devuelve `true` cuando ambas condiciones se cumplen.

### 2.4. Funciones de conversión (Conversion)

Permiten transformar un dato de un tipo a otro.

Son especialmente importantes cuando trabajamos con información proveniente de Excel, SharePoint u otras aplicaciones.

Algunas funciones:

| Función | Descripción |
|---|---|
| `string()` | Convierte un valor en texto. |
| `int()` | Convierte un valor en entero. |
| `float()` | Convierte un valor en decimal. |
| `bool()` | Convierte un valor en booleano. |
| `array()` | Convierte un valor en una matriz. |
| `json()` | Interpreta una cadena como JSON. |
| `xml()` | Convierte un valor en XML. |
| `base64()` | Codifica un valor en Base64. |

Ejemplo:

```text
float('125.75')
```

Resultado:

```text
125.75
```

### 2.5. Funciones matemáticas (Math)

Permiten realizar operaciones matemáticas y trabajar con valores numéricos.

Algunas funciones:

| Función | Descripción |
|---|---|
| `add()` | Suma dos números. |
| `sub()` | Resta dos números. |
| `mul()` | Multiplica dos números. |
| `div()` | Divide dos números. |
| `mod()` | Obtiene el residuo de una división. |
| `max()` | Obtiene el valor máximo. |
| `min()` | Obtiene el valor mínimo. |
| `rand()` | Genera un número aleatorio. |
| `pow()` | Eleva un número a una potencia. |
| `range()` | Genera una matriz de números consecutivos. |

Ejemplo:

```text
add(10, 20)
```

Resultado:

```text
30
```

### 2.6. Funciones de fecha y hora (Date and time)

Permiten trabajar con fechas, horas, intervalos y zonas horarias.

Son útiles para calcular vencimientos, establecer fechas límite y determinar cuánto tiempo ha transcurrido entre dos fechas.

Algunas funciones:

| Función | Descripción |
|---|---|
| `utcNow()` | Obtiene la fecha y hora actual en UTC. |
| `formatDateTime()` | Da formato a una fecha y hora. |
| `addDays()` | Agrega días a una fecha. |
| `addHours()` | Agrega horas a una fecha. |
| `addMinutes()` | Agrega minutos a una fecha. |
| `subtractFromTime()` | Resta unidades de tiempo. |
| `dayOfWeek()` | Obtiene el día de la semana. |
| `dayOfMonth()` | Obtiene el día del mes. |
| `dayOfYear()` | Obtiene el día del año. |
| `convertTimeZone()` | Convierte una fecha entre zonas horarias. |
| `parseDateTime()` | Interpreta una cadena como fecha y hora. |

Ejemplo:

```text
formatDateTime(utcNow(), 'dd/MM/yyyy')
```

Resultado: la fecha actual con formato día/mes/año.

### 2.7. Funciones de flujo de trabajo (Workflow)

Permiten acceder a información del propio flujo, sus desencadenadores, sus acciones y sus variables.

Son especialmente útiles para recuperar resultados de actividades anteriores y utilizar información durante la ejecución.

Algunas funciones:

| Función | Descripción |
|---|---|
| `triggerBody()` | Obtiene el contenido del cuerpo del desencadenador. |
| `triggerOutputs()` | Obtiene las salidas del desencadenador. |
| `outputs()` | Obtiene las salidas de una acción. |
| `body()` | Obtiene el cuerpo de una acción. |
| `actions()` | Obtiene información de una acción. |
| `items()` | Obtiene el elemento actual de una iteración identificada. |
| `item()` | Obtiene el elemento actual en una acción repetitiva compatible. |
| `variables()` | Obtiene el valor de una variable. |
| `parameters()` | Obtiene el valor de un parámetro. |
| `workflow()` | Obtiene información del flujo en ejecución. |

Ejemplo:

```text
variables('contador')
```

Devuelve el valor actual de la variable `contador`.

### 2.8. Funciones de análisis de URI (URI parsing)

Permiten analizar y obtener información de una dirección URI o URL.

Son útiles cuando trabajamos con direcciones web, enlaces y parámetros de consulta.

Algunas funciones:

| Función | Descripción |
|---|---|
| `uriHost()` | Obtiene el dominio o servidor de una URI. |
| `uriPath()` | Obtiene la ruta de una URI. |
| `uriPathAndQuery()` | Obtiene la ruta y los parámetros de consulta. |
| `uriPort()` | Obtiene el puerto. |
| `uriQuery()` | Obtiene los parámetros de consulta. |
| `uriScheme()` | Obtiene el protocolo utilizado. |
| `encodeUriComponent()` | Codifica un componente de URI. |
| `decodeUriComponent()` | Decodifica un componente de URI. |

### 2.9. Funciones de manipulación de JSON y XML

Permiten trabajar con estructuras de datos JSON y XML, facilitando la consulta, transformación y modificación de información.

Son especialmente útiles cuando recibimos información de servicios web o API.

Algunas funciones:

| Función | Descripción |
|---|---|
| `json()` | Interpreta una cadena como JSON. |
| `xml()` | Convierte un valor en XML. |
| `xpath()` | Consulta información dentro de un documento XML. |
| `addProperty()` | Agrega una propiedad a un objeto. |
| `setProperty()` | Establece o modifica una propiedad. |
| `removeProperty()` | Elimina una propiedad de un objeto. |

Ejemplo:

```text
json('{"nombre":"Juan","edad":25}')
```

Permite interpretar el texto como un objeto JSON.

## 3. Consideraciones importantes

- Las funciones se escriben utilizando paréntesis y los parámetros correspondientes.
- Algunas funciones reciben cadenas de texto, otras números, fechas, matrices u objetos.
- Podemos combinar varias funciones dentro de una misma expresión.
- Es importante validar los tipos de datos antes de realizar conversiones.
- Las funciones pueden utilizarse para procesar resultados de actividades anteriores.
- No todas las funciones son compatibles con cualquier tipo de dato.
