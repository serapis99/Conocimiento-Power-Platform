---
titulo: Conceptos fundamentales de Power Automate
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
  - Conceptos fundamentales de Power Automate
---
Para desarrollar flujos en Power Automate, es importante familiarizarse primero con los componentes fundamentales que permiten construir, ejecutar y conectar una automatización.

Además del desencadenador, las plantillas y las conexiones, existen otros conceptos que conviene comprender para saber cómo funciona un flujo desde que se inicia hasta que termina su ejecución.

## Conceptos fundamentales de Power Automate

1. **Desencadenador (Trigger / Gatilho)**: Es el evento o condición que inicia la ejecución de un flujo. Determina cuándo debe comenzar la automatización.

>[!example] Ejemplos:
>- Cuando llega un correo.
>- Cuando se crea un archivo.
>- Cuando se recibe una solicitud.
>- En una fecha y hora programada.
>- Cuando un usuario ejecuta el flujo manualmente.

2. **Plantillas (Templates)**: Son flujos prediseñados que permiten utilizar una automatización existente como punto de partida, en lugar de construirla desde cero.

>[!example] Ejemplo: 
>una plantilla que guarda automáticamente los archivos adjuntos de Outlook en OneDrive.

3. **Conectores (Connectors)**: Permiten que Power Automate se comunique con otros servicios, aplicaciones o plataformas. Existen conectores estándar, premium y otros tipos, dependiendo del servicio y las licencias.

>[!example] Ejemplos: 
>Outlook, Excel, SharePoint, Teams, OneDrive, SQL Server.
    
4. **Conexiones (Connections)**: Son la configuración que permite a Power Automate utilizar un conector para acceder a un servicio mediante una cuenta, autenticación y permisos.

>[!example] Ejemplo: 
>crear una conexión con Outlook utilizando tu cuenta para permitir que un flujo lea o envíe correos.

5. **Acciones (Actions)**: Son las operaciones que el flujo ejecuta después de iniciarse o cuando llega a un determinado paso.

>[!example] Ejemplos:
>- Enviar un correo.
>- Crear un archivo.
>- Leer una fila de Excel.
>- Actualizar un registro.
>- Ejecutar un flujo de escritorio.

6. **Condiciones (Conditions)**: Permiten evaluar si se cumple una regla y decidir qué camino debe seguir el flujo.

>[!example] Ejemplo: 
>si el correo contiene la palabra Factura, guardar el adjunto; de lo contrario, ignorarlo.

7. **Bucles (Loops)**: Permiten repetir acciones o recorrer una colección de elementos.

>[!example] Ejemplos:
>- Aplicar a cada uno (Apply to each): recorrer una lista de elementos.
>- Do until: repetir acciones hasta que se cumpla una condición.
        
8. **Variables (Variables)**: Permiten almacenar temporalmente información durante la ejecución del flujo para utilizarla, modificarla o acumular resultados.

>[!example] Ejemplos: 
>texto, números, booleanos, arrays y objetos.

9. **Expresiones (Expressions)**: Permiten transformar, evaluar y manipular datos dentro de los flujos mediante funciones y operaciones.

>[!example] Ejemplos de uso:
>- Manipular fechas.
>- Convertir texto.
>- Obtener valores específicos.
>- Comparar datos.
>- Concatenar cadenas.

10. **Entradas y salidas (Inputs / Outputs)**: Permiten recibir información para iniciar o ejecutar un flujo y devolver resultados a otros flujos, procesos o servicios.

>[!example] Ejemplo: 
>recibir el nombre de un archivo como parámetro y devolver la ruta donde fue almacenado.

11. **Historial de ejecuciones (Run history)**: Permite consultar las ejecuciones realizadas por un flujo, conocer su estado y revisar qué sucedió durante cada paso.

>[!example] Ejemplo:
>Estados habituales: correcto, fallido, cancelado o en ejecución.

12. **Manejo de errores (Error handling)**: Permite controlar qué debe suceder cuando una acción falla o se presenta una situación inesperada.

>[!example] Ejemplos: 
>reintentar una acción, capturar un error, registrar el fallo, enviar una notificación o ejecutar una ruta alternativa.