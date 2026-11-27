---
titulo: "Flujos de aprobaciones en Power Automate"
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
  - "Flujos de aprobaciones en Power Automate"
---
# Flujos de aprobaciones en Power Automate

Power Automate permite implementar flujos de aprobaciones para gestionar procesos que requieren la autorización o validación de una o varias personas antes de continuar con una operación.

Son especialmente útiles en procesos empresariales como:

- Aprobación de solicitudes de vacaciones.
- Autorización de compras.
- Validación de documentos.
- Aprobación de gastos.
- Autorización de solicitudes internas.

### 1. Requisitos para los aprobadores

Las personas que reciben una solicitud de aprobación deben contar con una identidad compatible con Microsoft Entra ID.

Hay dos escenarios:

- Usuarios internos: pueden recibir y responder solicitudes de aprobación utilizando su cuenta organizacional.
- Usuarios externos: pueden participar si son invitados al entorno de Microsoft Entra ID como usuarios B2B y cumplen los requisitos de licencia, invitación y acceso.

> [!important] Importante:
> Los usuarios invitados externos tienen algunas limitaciones. Por ejemplo, no pueden responder directamente desde los correos interactivos de Outlook; deben ingresar al portal de Power Automate para gestionar la aprobación.

![](Adjuntos/Pasted%20image%2020261126080833.png)

### 2. Acción de aprobación

Power Automate ofrece diferentes acciones para gestionar las aprobaciones.

Una de las más completas y sencillas de utilizar es:

`Iniciar y esperar una aprobación`

Esta acción realiza dos operaciones:

1. Crea y envía una solicitud de aprobación a las personas correspondientes.
2. Espera hasta que se cumplan las condiciones de aprobación configuradas antes de continuar con las siguientes acciones del flujo.

>[!example] Por ejemplo:
>podemos utilizarla para detener un proceso de compra hasta que el responsable autorice la solicitud.

### 3. Tipos de aprobación

Al configurar la acción, debemos seleccionar el tipo de aprobación que se ajuste a nuestras necesidades.

| Tipo de aprobación                                       | Funcionamiento                                                                                                                |
| -------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Aprobar/Rechazar - Todos deben aprobar                   | Todos los participantes deben aprobar para completar satisfactoriamente la solicitud. Si uno rechaza, se considera rechazada. |
| Aprobar/Rechazar - El primero en responder               | La respuesta del primer participante que responda determina el resultado.                                                     |
| Respuestas personalizadas - Esperar todas las respuestas | Todos los participantes deben responder, utilizando las opciones personalizadas configuradas.                                 |
| Respuestas personalizadas - Esperar una respuesta        | La primera respuesta recibida completa la aprobación.                                                                         |

También existen aprobaciones secuenciales, donde los participantes deben aprobar en un orden determinado. Por ejemplo, primero un supervisor y después un gerente.

### 4. Configuración de la aprobación

Una vez seleccionado el tipo de aprobación, debemos completar los campos correspondientes.

Los principales son:

| Campo                   | Descripción                                                       |
| ----------------------- | ----------------------------------------------------------------- |
| Título                  | Nombre o asunto de la solicitud de aprobación.                    |
| Asignado a              | Correo electrónico o identidad de las personas que deben aprobar. |
| Detalles                | Información adicional que necesita conocer el aprobador.          |
| Vínculo del elemento    | Enlace al documento, registro o recurso que se desea aprobar.     |
| Descripción del vínculo | Texto descriptivo que acompaña al enlace.                         |

En el campo de detalles podemos incorporar contenido dinámico procedente de los pasos anteriores del flujo.

### 5. Recepción y respuesta de la aprobación

Una vez configurada y ejecutada la acción, Power Automate envía una notificación a los aprobadores.

Estos podrán consultar la información proporcionada y responder según las opciones disponibles en el tipo de aprobación seleccionado.

La acción devuelve información que podemos utilizar en los siguientes pasos del flujo, como:

- Resultado de la aprobación.
- Persona que respondió.
- Fecha de respuesta.
- Comentarios del aprobador.
- Respuestas individuales.

>[!example] Por ejemplo
>podemos agregar una condición después de la aprobación:
>- Si el resultado es `Approve`, continuar con el proceso.
>- Si el resultado es `Reject`, ejecutar acciones para informar del rechazo o actualizar el estado de la solicitud.

> [!tip] tip
> Una buena práctica es utilizar el resultado de la aprobación para controlar el resto del flujo. De esta manera, podemos automatizar las acciones posteriores sin necesidad de realizar verificaciones manuales.

![](Adjuntos/Pasted%20image%2020261126082213.png)

