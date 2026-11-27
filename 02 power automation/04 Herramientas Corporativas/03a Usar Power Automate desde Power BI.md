---
titulo: Usar Power Automate desde Power BI
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-26
ultimo_repaso: 2026-11-26
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - Usar Power Automate desde Power BI
---

# Usar Power Automate desde Power BI

Power BI permite integrar Power Automate directamente en los informes mediante un objeto visual que funciona como un botón. Esto permite ejecutar flujos automatizados sin necesidad de salir del informe.

### 1. Agregar el objeto visual

En el panel **Visualizaciones** podemos encontrar el objeto visual denominado `Power Automate for Power BI`.

Al seleccionarlo, Power BI agrega un nuevo objeto visual al lienzo del informe. Este objeto será nuestro botón para ejecutar automatizaciones.

![](Adjuntos/Pasted%20image%2020261126160934.png)

### 2. Seleccionar el entorno

El primer paso consiste en seleccionar el entorno de Power Automate donde queremos crear o utilizar nuestro flujo.

El entorno determina dónde se almacenará y administrará la automatización.

![](Adjuntos/seleccionar%20entorno.gif)

### 3. Agregar los datos

Debemos agregar al apartado de datos de Power Automate los campos de Power BI que queremos utilizar como entradas del flujo.

Estos campos pueden proceder de las tablas y visualizaciones del informe.

Una ventaja importante es que podemos utilizar los filtros y las selecciones realizadas por el usuario para enviar información contextual al flujo.

![](Adjuntos/seleccionar%20datos.gif)

### 4. Configurar el flujo

Para configurar el botón debemos seleccionar los tres puntos (`...`) del objeto visual y elegir `Editar`.

Desde esta opción podemos:

- **Utilizar un flujo existente:** seleccionar una automatización que ya hayamos creado y que sea compatible con el objeto visual.
- **Crear un flujo nuevo:** comenzar desde cero mediante la opción `Nuevo`.
- **Utilizar una plantilla:** partir de una automatización prediseñada para adaptarla a nuestras necesidades.

Si creamos un flujo nuevo, podemos incorporar acciones, condiciones y otros elementos de Power Automate.

>[!important] Es importante: 
>utilizar el desencadenador `Power BI button clicked`, que permite iniciar el flujo cuando el usuario presiona el botón del informe.

![](Adjuntos/editar%20flujo.gif)

>[!note] Nota: 
>- recordar que por el momento el flujo se automatiza en la visual clásica.
>- se recomienda mapear los datos para que sea mas facil su manejo cada dato inicia con `Datos de power bi`
>- como objeto principal el objeto se llama `Datos de power bi` ![](Adjuntos/Pasted%20image%2020261126163421.png)

### 5. Aplicar y compartir

Una vez configurado el flujo, debemos guardarlo y seleccionar `Aplicar` para asociarlo con el botón de Power BI.

Posteriormente, podemos compartir el flujo con los usuarios que necesiten ejecutarlo.

Debemos concederles los permisos correspondientes de ejecución. No es necesario darles permisos de edición si únicamente necesitan utilizar el botón.

![](Adjuntos/guardar%20el%20flujo%20y%20activarlo.gif)

### 6. Formatear el botón

Finalmente, podemos personalizar la apariencia del botón desde el panel de formato.

Entre las opciones disponibles encontramos:

- Cambiar el texto del botón.
- Modificar el color de fuente.
- Cambiar el tamaño de la fuente.
- Modificar el color de relleno.
- Ajustar el tamaño y la posición del objeto visual.

### Consideraciones importantes

- El flujo se ejecuta desde el contexto del informe de Power BI; no se puede iniciar directamente desde el portal de Power Automate como un flujo independiente.
- El objeto visual admite un máximo de 1.000 registros.
- Los usuarios que ejecuten el flujo deben tener los permisos correspondientes.
- Los campos agregados al objeto visual pueden utilizarse como contenido dinámico dentro del flujo.
- Para probar el botón mientras editamos el informe, debemos mantener presionada la tecla `Ctrl` mientras hacemos clic sobre él.




