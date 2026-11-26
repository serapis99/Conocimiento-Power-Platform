---
titulo: Agregar acciones al flujo
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
  - Agregar acciones al flujo
---
## Agregar acciones al flujo

Una vez que tenemos configurado el desencadenador, podemos comenzar a agregar las acciones que ejecutará nuestro flujo.

En Power Automate podemos encontrar acciones que operan internamente dentro del flujo y otras que permiten conectarnos con aplicaciones, servicios o plataformas externas.

### Tipos de acciones

- **Acciones internas**: permiten realizar operaciones dentro de la lógica del flujo, como crear variables, establecer condiciones, realizar bucles, manipular datos o ejecutar operaciones.
- **Acciones de conectores externos**: permiten interactuar con otros servicios y aplicaciones, como Outlook, Excel, SharePoint, Teams, entre otros.

## Ejemplo: Enviar un correo electrónico (V2)

En este caso utilizaremos la acción Enviar un correo electrónico (V2) — Send an email (V2), perteneciente al conector de Outlook.

Esta acción nos permite enviar un correo electrónico desde una cuenta conectada, especificando los destinatarios, el asunto y el contenido del mensaje.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121084149.png)

### Configuración de la acción

Para utilizar esta acción, necesitamos tener creada o establecer una conexión (Connection) con el servicio de correo electrónico correspondiente.

La conexión permite autenticar nuestra cuenta y autorizar a Power Automate a utilizar el servicio para realizar operaciones, en este caso, enviar correos electrónicos.

Los campos habituales de esta acción son:

| Campo            | Descripción                           |
| ---------------- | ------------------------------------- |
| To (Para)        | Dirección de correo del destinatario. |
| Subject (Asunto) | Asunto del mensaje.                   |
| Body (Cuerpo)    | Contenido del correo electrónico.     |
| CC               | Destinatarios en copia.               |
| BCC              | Destinatarios en copia oculta.        |

Una vez establecida la conexión, podemos completar los campos de la acción y continuar construyendo nuestro flujo.

## Guardar el flujo

Cuando ya tenemos configurados los componentes básicos:

- El desencadenador (Trigger), que inicia la ejecución.
- La acción (Action), que define la operación que realizará el flujo.
- La conexión (Connection), que permite acceder al servicio externo.

Podemos proceder a guardar el flujo haciendo clic en Guardar (Save).

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121084441.png)

Guardar permite conservar la configuración y los cambios realizados en nuestro flujo.

> [!tip] Lo que hemos construido\
> Tenemos un flujo de nube instantáneo que puede iniciarse manualmente y ejecutar una acción de envío de correo electrónico a través de una conexión con Outlook.

El siguiente paso en nuestro aprendizaje sería ejecutar el flujo (Test / Run) para comprobar que el desencadenador funciona, que la conexión está correctamente configurada y que el correo se envía al destinatario esperado.