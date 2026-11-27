# Crear un chat en Microsoft Teams sin una conversación previa

Microsoft Teams permite iniciar conversaciones con otros empleados sin necesidad de haber intercambiado mensajes anteriormente.

Esto resulta útil cuando necesitamos contactar a una persona por primera vez o enviarle información directamente.

### 1. Enviar mensajes mediante Power Automate

Una de las acciones disponibles es:

**`Publicar un mensaje en un chat o canal`**

Para enviar un mensaje directamente a un empleado sin necesitar una conversación previa, debemos configurar:

| Campo | Configuración |
|---|---|
| Publicar como | Bot de Flow |
| Publicar en | Chat con Flow bot |
| Destinatario | Correo electrónico del empleado |
| Mensaje | Contenido que queremos enviar |

Esta configuración permite enviar notificaciones individuales sin tener que crear previamente una conversación entre los usuarios.

**Ejemplo práctico:**

Cuando un empleado registre una solicitud en SharePoint, Power Automate puede enviarle automáticamente un mensaje de Teams para confirmar que su solicitud fue recibida.

### 4. Crear un chat grupal nuevo

Si necesitamos iniciar una conversación con varias personas, podemos utilizar la acción `Crear un chat`.

Posteriormente, podemos utilizar `Publicar un mensaje en un chat o canal` para enviar el primer mensaje al chat recién creado.