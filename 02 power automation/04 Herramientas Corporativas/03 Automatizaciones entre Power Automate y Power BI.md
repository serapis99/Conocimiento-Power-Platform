---
titulo: "Automatizaciones entre Power Automate y Power BI"
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
  - "Automatizaciones entre Power Automate y Power BI"
---
# Automatizaciones entre Power Automate y Power BI

Power Automate permite integrar procesos automatizados con Power BI, facilitando la administración de datos, la interacción con informes y la consulta de información.

Antes de comenzar, podemos clasificar las diferentes automatizaciones en tres grandes grupos:

## 1. Automatización de datos en Power BI

Consiste en utilizar Power Automate para gestionar y automatizar operaciones relacionadas con los datos que utiliza Power BI.

Algunas aplicaciones son:

- **Actualizar datos:** iniciar la actualización de un modelo semántico cuando ocurre un evento en otra aplicación.
- **Ingresar datos:** incorporar nuevos registros a tablas compatibles de Power BI.
- **Modificar información:** automatizar procesos que afectan los datos utilizados en los informes.
- **Integrar aplicaciones:** obtener información de SharePoint, Excel u otras plataformas para incorporarla a los procesos de análisis.

>[!example] **Ejemplo práctico:**
>Cuando se registra una nueva información en SharePoint, Power Automate puede iniciar la actualización del modelo semántico de Power BI para mantener los informes actualizados.

## 2. Interacción con informes de Power BI

Consiste en utilizar Power Automate para incorporar funcionalidades y acciones que permitan interactuar con los informes.

Algunas aplicaciones son:

- **Ejecutar acciones desde un informe:** utilizar el visual de Power Automate para iniciar flujos directamente desde Power BI.
- **Registrar información:** enviar datos seleccionados desde un informe hacia SharePoint, Excel u otras aplicaciones.
- **Enviar notificaciones:** generar mensajes cuando un usuario ejecuta una acción desde el informe.
- **Automatizar procesos:** utilizar los datos seleccionados en un informe para iniciar procesos empresariales.

>[!example] **Ejemplo práctico:**
>Podemos tener un informe de solicitudes y agregar un botón que permita enviar una solicitud de seguimiento mediante Power Automate.
>- [Automatizaciones entre Power Automate y Power BI](03%20Automatizaciones%20entre%20Power%20Automate%20y%20Power%20BI.md)
>- 

## 3. Consulta de datos en Power BI

Consiste en utilizar Power Automate para consultar información almacenada en los modelos semánticos de Power BI y utilizar los resultados en otros procesos.

Algunas aplicaciones son:

- **Consultar información:** ejecutar consultas DAX para obtener datos específicos de un modelo semántico.
- **Evaluar indicadores:** comprobar si determinados valores cumplen condiciones establecidas.
- **Generar notificaciones:** enviar mensajes cuando un indicador alcanza un valor determinado.
- **Distribuir información:** utilizar los resultados de una consulta para generar correos electrónicos o mensajes de Teams.
- **Automatizar reportes:** obtener información específica y distribuirla periódicamente.

>[!example] **Ejemplo práctico:**
>Podemos crear un flujo que consulte las ventas de una empresa y envíe automáticamente una notificación cuando las ventas de una sucursal estén por debajo de un objetivo establecido.

---

## Consideraciones importantes

- Power Automate puede interactuar con Power BI mediante su conector y otras integraciones, como las API REST.
- Para actualizar un modelo semántico, debemos contar con los permisos necesarios.
- Las consultas directas a modelos semánticos mediante DAX requieren configuraciones y permisos específicos.
- La actualización de los datos no significa necesariamente que todas las visualizaciones abiertas en el navegador se actualicen instantáneamente.
