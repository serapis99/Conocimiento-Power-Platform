---
titulo: Flujo de nube instantáneo
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-19
ultimo_repaso: 2026-11-19
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - Flujo de nube instantáneo
---
# Creación de un flujo de nube instantáneo

## 1. Seleccionar el desencadenador

Cuando creamos un flujo de nube instantáneo (Instant cloud flow), debemos seleccionar el desencadenador que determinará cómo se iniciará la automatización.

Para este ejemplo seleccionaremos:

`Desencadenar un flujo manualmente (Manually trigger a flow)`

Este desencadenador permite que un usuario inicie el flujo manualmente, por ejemplo, presionando el botón Ejecutar (Run) desde Power Automate.

A continuación:

1. Seleccionamos el desencadenador.
2. Asignamos un nombre al flujo.
3. Hacemos clic en Crear (Create).

![Pasted image 20261119162602](Adjuntos/Pasted%20image%2020261119162602.png)

## 2. Configurar el desencadenador

Una vez creado el flujo, podemos seleccionar el bloque del desencadenador para consultar y modificar sus propiedades.

Entre las configuraciones disponibles encontramos:

- Nombre del desencadenador: permite identificar el componente dentro del diseñador.
- Entradas (Inputs): permiten definir información que el usuario deberá proporcionar al ejecutar el flujo.

![Pasted image 20261119163338](Adjuntos/Pasted%20image%2020261119163338.png)


### Agregar entradas (Inputs)

Una de las características importantes de este desencadenador es que permite solicitar información al usuario antes de ejecutar el flujo.

Podemos agregar diferentes tipos de entradas, dependiendo de la información que necesite nuestra automatización.

| Tipo de entrada            | Descripción                                 | Ejemplo                           |
| -------------------------- | ------------------------------------------- | --------------------------------- |
| Texto (Text)               | Recibir una cadena de texto.                | Nombre de un cliente.             |
| Sí/No (Yes/No)             | Recibir un valor booleano.                  | ¿Aprobar solicitud?               |
| Número (Number)            | Recibir un valor numérico.                  | Cantidad de registros.            |
| Correo electrónico (Email) | Recibir una dirección de correo.            | Destinatario de una notificación. |
| Fecha (Date)               | Recibir una fecha.                          | Fecha de procesamiento.           |
| Archivo (File)             | Permitir que el usuario adjunte un archivo. | Un documento Excel.               |

### Ejemplo práctico: recibir un archivo Excel

Imaginemos que queremos crear un flujo que procese información almacenada en Excel.

Podemos configurarlo de la siguiente manera:

1. Agregar una entrada de tipo Archivo (File) al desencadenador.
2. Cuando el usuario ejecute el flujo, deberá proporcionar el archivo Excel.
3. El flujo recibirá el archivo como entrada.
4. Utilizaremos las acciones correspondientes para acceder a su contenido.
5. Podemos utilizar List rows present in a table para obtener los registros de una tabla de Excel.
6. Finalmente, utilizaremos Apply to each para recorrer los registros y procesarlos individualmente.

> [!important] Concepto importante\
> Recibir un archivo Excel no significa que Power Automate recorra automáticamente sus filas. Primero debemos acceder al contenido del archivo y utilizar las acciones correspondientes para obtener los registros.
