---
titulo: Crear tablas CSV y HTML (Create CSV table / Create HTML table)
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
  - Crear tablas CSV y HTML (Create CSV table / Create HTML table)
---
# Crear tablas CSV y HTML (Create CSV table / Create HTML table)

Las acciones **Crear tabla CSV** y **Crear tabla HTML** de Power Automate permiten convertir una matriz de objetos en una representación tabular.

Son especialmente útiles para preparar información que posteriormente se enviará por correo electrónico, se exportará a archivos o se presentará en informes.

Ambas acciones tienen un funcionamiento similar: necesitan una matriz de entrada y generan una cadena de texto con el formato correspondiente.

## 1. Origen de los datos (From)

Para ambas acciones necesitamos indicar la matriz que queremos convertir.

En este ejemplo utilizaremos la salida (`body`) de la actividad **Filtrar matriz (Filter array)**.

Así, las tablas contendrán únicamente los registros que cumplen las condiciones establecidas previamente.

## 2. Crear tabla CSV (Create CSV table)

Convierte una matriz de objetos JSON en una tabla CSV (*Comma-Separated Values*), un formato de texto utilizado para representar datos tabulares.

Por defecto, los valores se separan mediante comas (`,`), y los nombres de las propiedades se utilizan como encabezados cuando se configura la generación automática de columnas.

### Configuración

- **Desde (From):** salida de Filtrar matriz.
- **Columnas (Columns):** permite seleccionar entre generación automática o personalizada.

### Cambiar el separador

La acción Crear tabla CSV no dispone de una configuración directa para cambiar la coma por otro delimitador.

Si necesitamos utilizar otro separador, como el punto y coma (`;`), podemos realizar un procesamiento posterior mediante una acción **Compose (Componer)** y la función `replace()`.

Ejemplo:

```text
replace(
    body('Crear_tabla_CSV'),
    ',',
    ';'
)
```

Esta expresión reemplaza las comas por puntos y comas en el resultado generado.

>[!caution] **Precaución:** 
>este método reemplaza todas las comas, incluidas aquellas que puedan formar parte del contenido de una celda. Por tanto, no es recomendable cuando los datos contienen comas internas. En esos casos se necesita una transformación que respete las reglas de escape del formato CSV.

## 3. Crear tabla HTML (Create HTML table)

Convierte una matriz de objetos JSON en una tabla utilizando etiquetas HTML.

Este formato es especialmente útil cuando queremos presentar información dentro de un correo electrónico o una página web.

### Configuración

- **Desde (From):** salida de Filtrar matriz.
- **Columnas (Columns):** permite utilizar columnas automáticas o definirlas manualmente.

La salida generada contiene una estructura HTML con etiquetas como:

- `<table>`: define la tabla.
- `<thead>`: contiene los encabezados.
- `<tbody>`: contiene los registros.
- `<tr>`: representa una fila.
- `<th>`: representa una celda de encabezado.
- `<td>`: representa una celda de datos.

### Aplicar estilos CSS

La acción Crear tabla HTML genera una tabla básica, sin ofrecer una configuración visual avanzada.

Para personalizar su apariencia podemos utilizar CSS (*Cascading Style Sheets*).

Una alternativa es utilizar una acción **Compose (Componer)** después de Crear tabla HTML para modificar la estructura generada y agregar estilos.

Por ejemplo, podemos utilizar `replace()` para modificar la etiqueta de apertura de la tabla:

```text
replace(
    body('Crear_tabla_HTML'),
    '<table>',
    '<table style="width:100%; border-collapse:collapse; font-family:Arial;">'
)
```

También podemos aplicar estilos a los encabezados y las celdas mediante atributos CSS:

```html
<th style="background-color:#333333; color:white; padding:10px;">
    Nombre
</th>

<td style="border:1px solid #dddddd; padding:8px;">
    Carlos
</td>
```

Otra alternativa consiste en construir una estructura HTML personalizada e incorporar la salida de los datos.

>[!important] **Importante:** 
>si la tabla se enviará por correo electrónico, conviene utilizar estilos CSS en línea (`style`) porque los clientes de correo no siempre admiten todas las características de CSS.
>
>Además, en la acción de envío del correo debemos habilitar la opción de contenido HTML (`Is HTML`), cuando esté disponible.

## 4. Diferencias entre ambas acciones

| Característica | CSV | HTML |
|---|---|---|
| Resultado | Texto delimitado | Código HTML |
| Separador predeterminado | Coma | No aplica |
| Encabezados | Sí | Sí |
| Personalización visual | No directamente | Mediante CSS |
| Uso habitual | Exportación e intercambio de datos | Presentación de información |
| Puede utilizarse en correos | Sí | Sí |

> [!tip] Recomendación
> Utiliza CSV cuando necesites exportar o intercambiar información tabular. Utiliza HTML cuando quieras presentar los resultados de manera organizada y visual, especialmente en correos electrónicos.