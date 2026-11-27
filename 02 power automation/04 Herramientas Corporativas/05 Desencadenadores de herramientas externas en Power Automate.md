---
titulo: "Desencadenadores de herramientas externas en Power Automate"
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
  - "Desencadenadores de herramientas externas en Power Automate"
---
# Desencadenadores de herramientas externas en Power Automate

Power Automate permite integrar herramientas y servicios de otras empresas mediante conectores. Esto nos permite crear automatizaciones que interactúan con aplicaciones externas al ecosistema de Microsoft.

Sin embargo, debemos tener en cuenta que no todos los conectores ofrecen las mismas funcionalidades. Algunos disponen de desencadenadores, mientras que otros solamente permiten ejecutar acciones.

### 1. Desencadenadores de Google

Google cuenta con diferentes conectores disponibles en Power Automate. Algunos de ellos permiten iniciar flujos automáticamente cuando ocurre un evento.

Entre los conectores que podemos utilizar encontramos:

- **Google Calendar:** permite iniciar flujos cuando se agrega, modifica o elimina un evento, entre otras posibilidades.
- **Google Tasks:** permite iniciar flujos cuando se crea una lista de tareas, se agrega una tarea, se completa o llega su fecha de vencimiento.
- **Google Contacts:** permite iniciar flujos cuando se modifica un contacto.

![](Adjuntos/Pasted%20image%2020261126210224.png)

### 2. Google Sheets

También existe un conector para Google Sheets, que permite interactuar con hojas de cálculo.

Sin embargo, tiene una limitación importante: actualmente ofrece acciones, pero no dispone de desencadenadores propios en su conector estándar.

Entre sus acciones encontramos:

- Obtener filas.
- Obtener una fila específica.
- Insertar filas.
- Actualizar filas.
- Eliminar filas.
- Obtener las hojas de un archivo.

Si necesitamos iniciar un flujo cuando se agrega o modifica información en Google Sheets, podemos recurrir a alternativas como las consultas periódicas programadas o integraciones mediante API.

### 3. Consideraciones importantes

- No todos los conectores ofrecen desencadenadores.
- La disponibilidad de acciones y desencadenadores depende de cada conector.
- Algunos conectores tienen limitaciones en sus operaciones.
- Es posible que determinadas integraciones requieran permisos o configuraciones adicionales.
- Antes de diseñar una automatización, debemos revisar la documentación del conector para comprobar qué operaciones están disponibles.

**Conclusión:** Power Automate no se limita a las aplicaciones de Microsoft. Podemos integrar servicios de terceros, aunque debemos revisar las capacidades de cada conector para determinar si podemos iniciar un flujo mediante un evento o si necesitamos utilizar otro mecanismo.