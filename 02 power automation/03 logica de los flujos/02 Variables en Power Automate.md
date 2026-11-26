---
titulo: Variables en Power Automate
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
  - Variables en Power Automate
---
# Variables en Power Automate

## 1. ¿Qué es una variable?

Una variable es un espacio de almacenamiento que permite guardar información temporalmente durante la ejecución de un flujo.

Su contenido puede consultarse, modificarse y utilizarse en diferentes acciones del flujo.

Las variables permiten, por ejemplo:

- Almacenar resultados de operaciones.
- Contabilizar elementos de un bucle.
- Guardar textos y valores numéricos.
- Almacenar colecciones de datos.
- Controlar condiciones y procesos.
    
## 2. Estructura de una variable

Una variable se compone de tres elementos:

|Elemento|Descripción|
|---|---|
|Nombre|Identificador utilizado para reconocer la variable.|
|Tipo|Define la clase de información que puede almacenar.|
|Valor|Información almacenada en la variable.|

Ejemplo:

```
Nombre: contador
Tipo: Integer
Valor: 0
```

## 3. Tipos de datos

Power Automate permite trabajar con los siguientes tipos de datos:

|Tipo|Descripción|Ejemplo|
|---|---|---|
|Boolean|Valor lógico verdadero o falso.|`true`|
|Integer|Número entero, sin decimales.|`25`|
|Float|Número decimal.|`3.14`|
|String|Cadena de caracteres o texto.|`"Hola mundo"`|
|Object|Conjunto de propiedades organizadas mediante pares clave-valor.|`{"nombre":"Juan","edad":25}`|
|Array|Colección ordenada de elementos.|`[1, 2, 3]`|

## 4. Nomenclatura de variables

La nomenclatura consiste en establecer convenciones para asignar nombres a las variables.

Se recomienda:

- Utilizar nombres descriptivos.
- Evitar espacios y caracteres especiales.
- Mantener una convención uniforme.
- Utilizar nombres que representen el contenido almacenado.
    
Ejemplos:

|Variable|Propósito|
|---|---|
|`contador`|Almacenar un conteo.|
|`nombreUsuario`|Almacenar un nombre.|
|`totalVentas`|Almacenar un importe.|
|`esActivo`|Almacenar un valor booleano.|
|`listaProductos`|Almacenar una colección.|
|`datosCliente`|Almacenar un objeto.|

Una convención opcional es utilizar prefijos para identificar el tipo de dato:

|Prefijo|Tipo|Ejemplo|
|---|---|---|
|`str`|String|`strNombre`|
|`int`|Integer|`intContador`|
|`flt`|Float|`fltPrecio`|
|`bool`|Boolean|`boolActivo`|
|`obj`|Object|`objCliente`|
|`arr`|Array|`arrProductos`|

## 5. Gestión de variables en Power Automate

Para trabajar con variables en Power Automate, buscamos las acciones de la categoría **Variables**.

Las dos acciones fundamentales son:

### 5.1. Inicializar variable (Initialize variable)

Permite crear una variable y definir sus propiedades iniciales.

Sus parámetros son:

- **Nombre:** identificador de la variable.
- **Tipo:** tipo de dato que almacenará.
- **Valor:** contenido inicial de la variable.
    
Ejemplo:

```
Nombre: contador
Tipo: Integer
Valor: 0
```

La inicialización se realiza antes de utilizar la variable. En los flujos en la nube, las variables deben inicializarse en el nivel global, no dentro de condiciones, ámbitos o bucles.

### 5.2. Establecer variable (Set variable)

Permite modificar el valor de una variable previamente inicializada.
Sus parámetros son:

- **Nombre:** variable que se desea modificar.
- **Valor:** nuevo contenido que se le asignará.

Ejemplo:

```
Nombre: contador
Valor: 10
```

Si anteriormente la variable tenía el valor `0`, después de ejecutar esta acción tendrá el valor `10`.

## 6. Diferencia entre inicializar y establecer una variable

|Inicializar variable|Establecer variable|
|---|---|
|Crea la variable.|Modifica una variable existente.|
|Define el nombre.|Selecciona una variable creada.|
|Define el tipo de dato.|Conserva el tipo de dato.|
|Permite establecer el valor inicial.|Asigna un nuevo valor.|

## 7. Otras acciones para trabajar con variables

Además de las dos acciones principales, Power Automate dispone de otras acciones:

|Acción|Función|
|---|---|
|Incrementar variable|Aumenta un valor numérico.|
|Disminuir variable|Reduce un valor numérico.|
|Anexar a variable de cadena|Agrega texto al final de una cadena.|
|Anexar a variable de matriz|Agrega elementos al final de un array.|

## 8. Consideraciones importantes

- Las variables de los flujos en la nube tienen alcance global dentro del flujo que las crea.
- Una variable conserva su valor entre las iteraciones de un bucle.
- El valor asignado debe ser compatible con el tipo de dato de la variable.
- Cada variable requiere su propia acción de inicialización.
- Cuando se utilizan variables en bucles ejecutados en paralelo, pueden producirse resultados inesperados. Si se necesita un resultado predecible, se recomienda ejecutar las iteraciones secuencialmente.