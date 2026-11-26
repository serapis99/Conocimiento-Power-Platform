---
titulo: Enviar tablas HTML y CSV por correo electrónico en Power Automate
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
  - Enviar tablas HTML y CSV por correo electrónico en Power Automate
---
# Enviar tablas HTML y CSV por correo electrónico en Power Automate

En este ejemplo integramos las operaciones de datos con la acción de envío de correo electrónico, utilizando los resultados de **Crear tabla HTML** y **Crear tabla CSV**.

El objetivo es enviar un correo que muestre los datos directamente en el cuerpo del mensaje y, adicionalmente, permita descargar la información como un archivo CSV.

## 1. Incorporar la tabla HTML en el cuerpo del mensaje

En la acción de envío de correo electrónico, agregamos la salida de **Crear tabla HTML** en el campo **Cuerpo (Body)**.

De esta manera, el destinatario podrá visualizar los registros directamente en el correo, sin necesidad de descargar un archivo.

Para que la tabla se muestre correctamente, debemos asegurarnos de que el mensaje se envíe interpretando el contenido como HTML.

## 2. Adjuntar la tabla CSV como archivo

En la misma acción de envío de correo electrónico, agregamos un nuevo archivo adjunto.

Configuramos los siguientes campos:

- **Nombre del archivo adjunto:** nombre que tendrá el archivo que recibirá el destinatario.
- **Contenido del archivo adjunto:** salida de la acción Crear tabla CSV.

### Nombre dinámico del archivo

Una característica interesante es que podemos utilizar contenido dinámico y expresiones para construir el nombre del archivo.

Por ejemplo, podemos incorporar la fecha de generación para identificar cuándo se creó:

```text
Reporte_2026-11-25.csv
```

Para generar automáticamente la fecha actual podemos utilizar:

```text
formatDateTime(utcNow(), 'yyyy-MM-dd')
```

Y construir el nombre completo mediante:

```text
concat(
    'Reporte_',
    formatDateTime(utcNow(), 'yyyy-MM-dd'),
    '.csv'
)
```

### Importancia de la extensión

Es fundamental incluir la extensión correspondiente al formato del archivo.

Por ejemplo:

- `Reporte.csv`
- `Reporte.xlsx`
- `Reporte.html`
- `Reporte.txt`

Si omitimos la extensión, el archivo puede llegar sin una identificación clara del formato, dificultando que el destinatario sepa con qué aplicación abrirlo.

La extensión no convierte el contenido: debemos asegurarnos de que coincida con el formato real del archivo.

## 3. Resultado del flujo

Al finalizar, el destinatario recibe un correo electrónico con dos elementos:

1. **Tabla HTML:** permite consultar visualmente los registros directamente en el cuerpo del mensaje.
2. **Archivo CSV adjunto:** permite descargar, almacenar y procesar los datos mediante aplicaciones compatibles.

> [!important] Consideración
> El formato de las fechas debe definirse antes de generar las tablas si queremos que tanto el correo electrónico como el archivo CSV presenten la información de manera consistente.