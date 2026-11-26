---
titulo: creación de un flujo
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
  - creación de un flujo
---
# Creación de flujos en Power Automate

Antes de crear un flujo en Power Automate, debemos identificar en qué ambiente (Environment) vamos a trabajar. Esto es importante para evitar crear automatizaciones en un ambiente de producción cuando nuestro propósito es desarrollar, experimentar o realizar pruebas.

## 1. Seleccionar el ambiente de trabajo

Power Platform permite trabajar con diferentes ambientes, por ejemplo:

- Desarrollo (Development): para crear y modificar flujos.
- Pruebas (Test): para validar que las automatizaciones funcionen correctamente.
- Producción (Production): para ejecutar automatizaciones que ya están destinadas a operar en un entorno real.

Antes de crear un flujo, debemos verificar si tenemos disponible un ambiente de desarrollo o pruebas y seleccionarlo.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261119160124.png)

Si no contamos con el ambiente adecuado, podemos consultar o administrar los ambientes desde el administrador de Power Platform.

- **Ruta de acceso**: [Administrador de Power Platform](https://admin.powerplatform.microsoft.com/home?utm_source=chatgpt.com)
- **Ruta dentro del administrador**:`Administrar → Entornos → Nuevo`

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261119155926.png)

Desde allí podemos consultar los ambientes existentes y, dependiendo de nuestros permisos y licencias, crear uno nuevo.

> [!warning] Precaución\
> Antes de crear cualquier flujo, verifica el ambiente seleccionado. No debemos desarrollar ni realizar pruebas directamente en un ambiente de producción si disponemos de ambientes separados para desarrollo o pruebas.


## 2. Seleccionar el tipo de flujo

Una vez seleccionado el ambiente correcto, podemos dirigirnos a Crear (Create). Allí encontraremos diferentes tipos de flujos, según el propósito de la automatización y la forma en que queremos que se ejecute.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261119160338.png)

1\. **Flujo de nube automatizado (Automated cloud flow)**

Se ejecuta automáticamente cuando ocurre un evento que previamente hemos definido mediante un desencadenador (Trigger).

>[!example] Ejemplos:
>- Cuando recibimos un correo electrónico.
>- Cuando se crea un archivo en SharePoint.
>- Cuando se registra un nuevo elemento en una base de datos.

  2\. **Flujo de nube instantáneo (Instant cloud flow)**

  Se ejecuta cuando un usuario lo activa manualmente o mediante un mecanismo de invocación, dependiendo del desencadenador configurado.

  >[!example] Ejemplos:
  >- Ejecutar un flujo presionando un botón.
  >- Lanzar una automatización manualmente desde Power Automate.
  >- Ejecutar un proceso bajo demanda.

  3\. **Flujo de nube programado (Scheduled cloud flow)**

  Permite ejecutar una automatización de acuerdo con una programación definida, estableciendo fechas, horas o intervalos de repetición.

  >[!example] Ejemplos:
  >- Todos los días a las 8:00 a. m.
  >- Todos los lunes.
  >- Cada 30 minutos.
  >- El primer día de cada mes.

  4\. **Flujo de escritorio (Desktop flow)**

  Permite automatizar tareas en el computador mediante la interacción con aplicaciones, ventanas, elementos de interfaz gráfica, archivos y otros recursos locales.

  >[!example] Ejemplos:
  >- Abrir una aplicación de escritorio.
  >- Escribir información en un programa.
  >- Automatizar un proceso en Excel.
  >- Interactuar con sistemas que no disponen de una integración directa.

  5\. **Minería de procesos (Process mining)**

  Permite analizar procesos a partir de datos de eventos para comprender cómo se ejecutan realmente, identificar desviaciones, cuellos de botella y oportunidades de mejora.

  >[!example] Ejemplos:
  >- Analizar cuánto tarda un proceso en completarse.
  >- Identificar tareas que generan retrasos.
  >- Detectar pasos innecesarios.
  >- Comparar el proceso ideal con el proceso real.

  6\. **Describirlo para diseñarlo (Describe it to design it)**

  Permite describir en lenguaje natural el proceso que queremos automatizar para que la inteligencia artificial nos ayude a generar una propuesta de flujo.

  >[!example] Ejemplo de descripción:
  >Cuando reciba un correo con una factura adjunta, guardar el archivo en una carpeta de OneDrive y enviar una notificación por Teams indicando que la factura fue recibida.
  >
  >A partir de la descripción, la herramienta puede interpretar los pasos del proceso y proponer un flujo con acciones y componentes que posteriormente podemos revisar y modificar.

## 3. El tipo de flujo determina su configuración

Dependiendo del tipo de flujo que seleccionemos, Power Automate nos solicitará una configuración diferente.

| Tipo de flujo              | Configuración inicial habitual                                                  |
| -------------------------- | ------------------------------------------------------------------------------- |
| Automatizado               | Definir o seleccionar el desencadenador que iniciará el flujo.                  |
| Instantáneo                | Configurar el mecanismo de activación manual o bajo demanda.                    |
| Programado                 | Establecer fecha de inicio, hora, frecuencia e intervalo de ejecución.          |
| Desktop                    | Crear el flujo de escritorio y definir las acciones que ejecutará en el equipo. |
| Minería de procesos        | Seleccionar o cargar los datos del proceso que se van a analizar.               |
| Describirlo para diseñarlo | Escribir en lenguaje natural qué proceso queremos automatizar.                  |

Una vez configurado el tipo de flujo, podemos comenzar a agregar acciones, conexiones, condiciones, variables y demás componentes necesarios para construir nuestra automatización.