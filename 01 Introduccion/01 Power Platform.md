---
titulo: Power Platform
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
  - Power Platform
---
# Power Platform

**Microsoft Power Platform** es un conjunto de herramientas orientadas a crear soluciones empresariales, automatizar procesos, analizar datos y desarrollar aplicaciones con poco código (*Low-code*).

Entre sus principales herramientas se encuentran:

| Herramienta | Función principal |
|---|---|
| **Power Apps** | Crear aplicaciones empresariales. |
| **Power Automate** | Automatizar flujos de trabajo y procesos. |
| **Power BI** | Analizar datos y crear informes y dashboards. |
| **Power Pages** | Crear sitios web y portales empresariales. |

## Power Automate

**Power Automate** es una herramienta enfocada en la automatización de flujos de trabajo (*workflows*). Permite conectar aplicaciones, servicios y sistemas para ejecutar tareas automáticamente, reduciendo la intervención humana.

Existen dos modalidades principales de automatización:

- Power Automate Cloud
- Power Automate Desktop

## Power Automate Cloud

Permite crear flujos que se ejecutan en la infraestructura de la nube de Microsoft y conectar diferentes aplicaciones y servicios.

### Características

- **Ejecución en la nube:** los flujos se ejecutan en los servicios de Microsoft, sin depender directamente de que el computador personal esté encendido.
- **Disponibilidad:** pueden ejecutarse automáticamente mediante eventos, horarios programados o desencadenadores.
- **Integración:** permite conectar servicios mediante conectores, API y otros mecanismos de integración.
- **Uso:** automatización de procesos empresariales, notificaciones, aprobaciones, gestión de datos y sincronización entre aplicaciones.

### Ejemplo

Cuando llega un correo con un archivo adjunto, un flujo puede guardar automáticamente el archivo en OneDrive y enviar una notificación a un equipo por Microsoft Teams.

## Power Automate Desktop (PAD)

Permite crear automatizaciones que interactúan directamente con el sistema operativo, las aplicaciones de escritorio y las interfaces gráficas de usuario (GUI).

### Características

- **Ejecución local:** los flujos se ejecutan en una máquina Windows.
- **Dependencia de la máquina:** la ejecución depende de la disponibilidad, configuración y estado del equipo o entorno donde se ejecuta.
- **Integración:** puede interactuar con aplicaciones instaladas, ventanas, archivos, carpetas, navegadores y elementos de interfaz.
- **Uso:** automatizar tareas repetitivas en aplicaciones que no cuentan con API o que requieren interacción mediante interfaz gráfica.

### Ejemplo

Abrir un programa contable, iniciar sesión, consultar información, descargar un reporte y guardar el archivo en una carpeta local.

## Comparación entre las modalidades

| Característica | Power Automate Cloud | Power Automate Desktop |
|---|---|---|
| Entorno de ejecución | Nube | Máquina local o máquina asignada |
| Dependencia del equipo local | No necesariamente | Sí, en ejecución local |
| Integración | API, conectores y servicios | UI, aplicaciones locales, archivos y otros métodos |
| Activación | Eventos, horarios, botones, etc. | Manual, programada o invocada |
| Aplicaciones | Servicios web y cloud | Aplicaciones de escritorio y web |
| Interacción gráfica | No es su enfoque principal | Su principal capacidad |
| Ejemplo | Enviar una notificación al recibir un correo | Abrir Excel y procesar información |

## Integración entre Cloud y Desktop

Ambas modalidades pueden complementarse para crear automatizaciones más completas.

Por ejemplo, un flujo Cloud puede recibir una solicitud, desencadenar un flujo Desktop para procesar información en un programa local y posteriormente recibir el resultado para continuar la automatización en la nube.

## Idea clave para recordar

- **Power Automate Cloud:** automatiza principalmente la comunicación entre servicios, aplicaciones y plataformas.
- **Power Automate Desktop:** automatiza principalmente las acciones que realizaría una persona en un computador.

> [!tip] Analogía
> Cloud es como un coordinador que puede comunicarse con diferentes servicios a través de internet. Desktop es como un trabajador que ejecuta tareas directamente en el computador, interactuando con programas, ventanas, botones y archivos.

## Relación entre conceptos

- **Microsoft Power Platform** → conjunto de herramientas de desarrollo y automatización.
- **Power Automate** → herramienta para automatizar flujos de trabajo.
- **Power Automate Cloud** → automatización de servicios y procesos en la nube.
- **Power Automate Desktop** → automatización de interfaces y aplicaciones de escritorio.
- **RPA** → tecnología que permite automatizar tareas imitando las acciones humanas en sistemas digitales.

