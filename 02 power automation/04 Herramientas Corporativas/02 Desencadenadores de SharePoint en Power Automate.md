---
titulo: "Desencadenadores de SharePoint en Power Automate"
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
  - "Desencadenadores de SharePoint en Power Automate"
---
[02a Formularios en SharePoint](02a%20Formularios%20en%20SharePoint.md)# Desencadenadores de SharePoint en Power Automate

Podemos crear flujos automatizados que se inicien a partir de eventos que ocurren en SharePoint.

Para aprender a utilizarlos, comenzaremos con el desencadenador:

**`Cuando se crea un elemento` (When an item is created)**

Este desencadenador pertenece al conector de SharePoint y permite iniciar automáticamente un flujo cuando se agrega un nuevo elemento a una lista de SharePoint.

![](Adjuntos/Pasted%20image%2020261126090507.png)

### Configuración

Para utilizarlo debemos especificar dos campos principales:

- **Dirección del sitio:** sitio de SharePoint donde se encuentra nuestra lista.
- **Nombre de la lista:** lista que queremos supervisar.

Una vez configurado, Power Automate estará pendiente de la creación de nuevos elementos en esa lista.

### Aplicaciones prácticas

Este desencadenador se suele utilizar para automatizar procesos como:

- **Flujos de aprobación:** iniciar un proceso de aprobación cuando un usuario registra una nueva solicitud.
- **Notificaciones:** enviar un correo electrónico o un mensaje de Teams cuando se agrega un nuevo registro.
- **Registro de información:** copiar los datos de un elemento recién creado hacia otra plataforma o base de datos.
- **Asignación de tareas:** crear automáticamente una tarea cuando se registra una nueva solicitud.
- **Integración de aplicaciones:** enviar información de SharePoint hacia otros servicios o aplicaciones.

### Consideraciones importantes

- Este desencadenador se ejecuta cuando se crea un elemento nuevo, no cuando se modifica uno existente.
- Si necesitamos detectar tanto creaciones como modificaciones, debemos utilizar `Cuando se crea o se modifica un elemento`.
- El flujo supervisa únicamente el sitio y la lista que hayamos configurado.
- La ejecución no necesariamente es instantánea; SharePoint puede tardar algunos minutos en detectar y procesar los cambios.

**Ejemplo práctico:**

Imaginemos que tenemos una lista de SharePoint llamada `Solicitudes de compra`.

Cada vez que un empleado registre una nueva solicitud, podemos iniciar automáticamente un flujo que:

1. Obtenga los datos de la solicitud.
2. Envíe una aprobación al responsable de compras.
3. Espere la respuesta del aprobador.
4. Actualice el estado de la solicitud según el resultado.
5. Notifique al empleado si su solicitud fue aprobada o rechazada.

![](Adjuntos/Pasted%20image%2020261126135134.png)

## Link relacionados

- [Formularios en SharePoint](02a%20Formularios%20en%20SharePoint.md)
- [Crear un chat en Microsoft Teams sin una conversación previa](02b%20Crear%20un%20chat%20en%20Microsoft%20Teams%20sin%20una%20conversación%20previa.md)
- 