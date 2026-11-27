---
titulo: "Archivos adjuntos y creación de archivos CSV en Power Automate"
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: "2026-11-26"
ultimo_repaso: "2026-11-26"
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - "Archivos adjuntos y creación de archivos CSV en Power Automate"
---
# Archivos adjuntos y creación de archivos CSV en Power Automate

## 1. Enviar archivos adjuntos desde SharePoint

Power Automate permite utilizar archivos almacenados en SharePoint para adjuntarlos a correos electrónicos o enviarlos a otras aplicaciones.

Para realizarlo, debemos recuperar el contenido del archivo desde su ubicación en SharePoint.

### Procedimiento

1. Seleccionar la acción `Obtener contenido del archivo` (Get file content).
2. Indicar el sitio de SharePoint.
3. Seleccionar el identificador del archivo que queremos recuperar.
4. Utilizar la salida de esta acción en el campo de contenido del archivo adjunto de la acción de correo electrónico.

Al configurar el correo, normalmente debemos proporcionar:

- **Nombre del archivo:** nombre con el que se enviará el adjunto.
- **Contenido del archivo:** contenido binario obtenido desde SharePoint.

De esta manera, podemos adjuntar documentos almacenados en SharePoint sin necesidad de descargarlos manualmente.

>[!example] **Ejemplo práctico:**
>Podemos crear un flujo que, cuando se apruebe una solicitud, obtenga un documento almacenado en SharePoint y lo envíe automáticamente al solicitante mediante un correo electrónico.

## 2. Crear archivos CSV

Power Automate dispone de la acción `Crear tabla CSV` (Create CSV table), que permite transformar una colección de datos en una estructura de texto con formato CSV.

Esta acción resulta útil cuando necesitamos exportar información de listas, tablas o colecciones.

Sin embargo, presenta algunas limitaciones que debemos tener en cuenta.

### Limitaciones

**Separador de columnas**

Por defecto, la acción utiliza la coma (,) como separador de columnas.

No dispone de una opción directa para seleccionar otro delimitador, como el punto y coma (;).

Esto puede generar inconvenientes cuando el archivo se abre en Excel, dependiendo de la configuración regional del equipo.

**Codificación de caracteres**

Los archivos CSV pueden presentar problemas al interpretar caracteres especiales, como:

- ñ
- á
- é
- í
- ó
- ú

Esto ocurre cuando el programa que abre el archivo no interpreta correctamente su codificación.

Por ejemplo, podemos encontrar caracteres extraños en lugar de las tildes o las letras originales.

### Solución para los problemas de codificación

Una alternativa consiste en agregar la marca BOM (Byte Order Mark) correspondiente a UTF-8 al inicio del contenido CSV.

Podemos utilizar la siguiente expresión en una acción `Componer`:

`concat(uriComponentToString('%EF%BB%BF'), body('Crear_tabla_CSV'))`

Posteriormente, utilizamos el resultado para crear el archivo.

Esto ayuda a que aplicaciones como Excel reconozcan correctamente la codificación UTF-8 y puedan interpretar los caracteres especiales.

### Recomendaciones

- Si necesitamos exportar información sencilla, podemos utilizar `Crear tabla CSV`.
- Si necesitamos trabajar con tildes y caracteres especiales, es recomendable agregar el BOM de UTF-8.
- Si necesitamos utilizar un separador diferente de la coma, debemos construir el CSV mediante una estrategia personalizada.
- Si necesitamos conservar formatos, fórmulas, tablas y estilos, es preferible generar un archivo Excel (.xlsx) en lugar de CSV.

>[!important] **Importante:** 
>CSV es un formato de texto plano. No conserva formatos de celdas, colores, fórmulas ni otras características propias de Excel.