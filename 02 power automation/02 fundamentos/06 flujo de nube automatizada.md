---
titulo: flujo de nube automatizada
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-21
ultimo_repaso: 2026-11-21
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - flujo de nube automatizada
---
# Automatización: registrar reuniones de Outlook en Excel

## 1. Crear el flujo de nube automatizado

Nos dirigimos a Power Automate y seleccionamos Crear (Create) → Flujo de nube automatizado (Automated cloud flow).

Este tipo de flujo nos permite ejecutar una automatización cuando ocurre un evento determinado, sin necesidad de que el usuario lo inicie manualmente.

Le asignamos un nombre a nuestro flujo y buscamos el desencadenador correspondiente.

### Seleccionar el desencadenador

**Buscamos la aplicación**: `Office 365 Outlook`

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121110646.png)
Una vez seleccionada, se mostrarán los desencadenadores disponibles para esta aplicación.

**Seleccionamos**: Cuando se crea un evento nuevo (V3)

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121110749.png)

Este desencadenador permite detectar la creación de nuevos eventos en el calendario seleccionado y utilizar la información del evento como datos de entrada para las siguientes acciones del flujo.

## 2. Configurar el desencadenador de Outlook

Una vez agregado el desencadenador, debemos configurar sus propiedades.

| Campo                 | Configuración                                                         |
| --------------------- | --------------------------------------------------------------------- |
| Calendario (Calendar) | Seleccionar el calendario donde queremos detectar los nuevos eventos. |

En este caso seleccionaremos nuestro calendario: [Crear calendario Outlook](02%20power%20automation/02%20fundamentos/06a%20Crear%20calendario%20Outlook.md)


>[!note] Nota:
>Si acabamos de crear el calendario y todavía no aparece en la lista de opciones, debemos actualizar el navegador para que Power Automate recargue la información y detecte el nuevo calendario.

>[!important] Importante: 
>debemos seleccionar el calendario correcto. Si elegimos otro calendario, el flujo se ejecutará cuando se creen eventos en ese calendario, no necesariamente en el que estamos utilizando para la prueba.

## 3. Preparar el archivo Excel

Para almacenar la información de las reuniones utilizaremos Excel Online (Business), que permite interactuar con archivos Excel almacenados en ubicaciones compatibles como SharePoint o OneDrive para la empresa.

Antes de configurar la acción en Power Automate, debemos preparar nuestro archivo.

### Crear el archivo y la tabla

1. Crear un archivo Excel.
2. Guardarlo en un sitio de SharePoint, preferiblemente en una ubicación fácil de encontrar.
3. Crear las columnas que vamos a utilizar para almacenar la información de las reuniones.
4. Convertir los datos en una tabla de Excel.
5. Asignarle un nombre a la tabla.

Para este ejercicio utilizaremos las siguientes columnas:

| Asunto                  | Asistentes             | Fecha      |
| ----------------------- | ---------------------- | ---------- |
| Reunión de seguimiento  | usuario\@empresa.com   | 21/11/2026 |
| Reunión con proveedores | proveedor\@empresa.com | 24/11/2026 |

>[!important] Importante: 
>Power Automate trabaja con las tablas de Excel para identificar las columnas y agregar registros. No basta con escribir los encabezados en las celdas; debemos convertir el rango de datos en una tabla mediante Insertar → Tabla o Ctrl + T.

Podemos asignar un nombre a la tabla, por ejemplo: `Reuniones`

## 4. Agregar la acción de Excel al flujo

Una vez preparado el archivo, volvemos al diseñador de Power Automate y agregamos una nueva acción.

Buscamos: `Excel Online (Business)`

Dentro de las acciones disponibles seleccionamos: Agregar una fila a una tabla (Add a row into a table)

Esta acción permite insertar un nuevo registro en una tabla de Excel utilizando los datos que recibimos del desencadenador de Outlook.

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121220750.png)

### Configurar la acción

Debemos diligenciar los siguientes campos:

| Campo                                       | Descripción                                                                  |
| ------------------------------------------- | ---------------------------------------------------------------------------- |
| Ubicación (Location)                        | Seleccionar el sitio donde se encuentra almacenado el archivo.               |
| Biblioteca de documentos (Document Library) | Seleccionar la biblioteca donde guardamos el Excel, por ejemplo, Documentos. |
| Archivo (File)                              | Seleccionar el archivo Excel que vamos a utilizar.                           |
| Tabla (Table)                               | Seleccionar la tabla creada dentro del Excel.                                |

En nuestro caso, seleccionaremos el sitio de SharePoint donde almacenamos el archivo, la biblioteca Documentos, nuestro archivo Excel y la tabla que creamos previamente.

Una vez seleccionado el archivo y la tabla, Power Automate reconocerá las columnas que componen la tabla y nos mostrará los campos que podemos diligenciar.

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121220611.png)

## 5. Asignar valores dinámicos de Outlook

Debajo de los parámetros de configuración del archivo y la tabla aparecerán los campos correspondientes a las columnas de Excel que creamos.

En este caso:

- Asunto
- Asistentes
- Fecha

Estos campos deben ser diligenciados utilizando la información que recibimos del desencadenador de Outlook.

Para ello utilizaremos el contenido dinámico, identificado generalmente por el icono del rayo o desde el panel Contenido dinámico (Dynamic content).

### Mapeo de datos

| Columna de Excel | Contenido dinámico de Outlook                |
| ---------------- | -------------------------------------------- |
| Asunto           | Subject (Asunto)                             |
| Asistentes       | Required attendees (Asistentes obligatorios) |
| Fecha            | Start (Hora de inicio)                       |

¿Qué es el contenido dinámico?

Es información generada o proporcionada por un desencadenador o una acción anterior, que podemos reutilizar en los siguientes pasos del flujo sin tener que escribir manualmente su valor.

Por ejemplo, cuando Outlook detecta que se ha creado una nueva reunión, el desencadenador devuelve información del evento, como su asunto, fecha de inicio, asistentes y otros datos.

Nosotros seleccionamos esos valores para que Excel los reciba automáticamente.

## 6. Guardar y probar el flujo

Una vez configurado el desencadenador de Outlook y la acción de Excel, guardamos nuestro flujo.

La estructura quedará de la siguiente manera:

Outlook — Cuando se crea un evento nuevo (V3)

Detecta una nueva reunión en el calendario seleccionado

Excel Online — Agregar una fila a una tabla

Registra los datos de la reunión en Excel

### Procedimiento de prueba

1. Guardamos el flujo.
2. Verificamos que esté activado.
3. Nos dirigimos a Outlook.
4. Abrimos el calendario.
5. Creamos una nueva reunión o evento.
6. Diligenciamos el asunto, los asistentes y la fecha.
7. Guardamos la reunión.
8. Esperamos a que Power Automate detecte el evento y ejecute el flujo.
9. Revisamos el historial de ejecuciones para verificar que las acciones se hayan ejecutado correctamente.
10. Abrimos el archivo Excel y comprobamos que se haya agregado una nueva fila con la información de la reunión.

> [!success] Resultado esperado
> Cada vez que se cree un nuevo evento en el calendario seleccionado, Power Automate detectará el evento y registrará la información correspondiente en la tabla de Excel.