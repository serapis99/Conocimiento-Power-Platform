
# Formularios en SharePoint

SharePoint permite crear formularios personalizados para facilitar el ingreso de información a una lista, evitando que los usuarios tengan que interactuar directamente con la estructura de la lista.

### Crear un formulario

Para crear un formulario debemos seguir estos pasos:

1. Ingresar a la lista de SharePoint.
2. Seleccionar la opción `Formularios`, ubicada en la barra de comandos.
3. Si la opción no aparece, hacer clic en los tres puntos (`...`) para encontrarla.
4. Seleccionar la opción para crear un nuevo formulario.

### Personalización del formulario

Una vez dentro del editor, podemos configurar diferentes aspectos:

- **Título:** nombre que tendrá el formulario.
- **Descripción:** texto que explica el propósito del formulario.
- **Campos disponibles:** seleccionar qué columnas de la lista podrá diligenciar el usuario.
- **Campos obligatorios:** establecer qué información debe proporcionar el usuario antes de enviar el formulario.
- **Validaciones:** aplicar restricciones para controlar la información ingresada, según las características de las columnas.
- **Orden de los campos:** organizar la disposición de los campos para facilitar su diligenciamiento.

### Funcionamiento

Cuando un usuario completa y envía el formulario, SharePoint crea un nuevo elemento en la lista asociada con la información proporcionada.

Esto permite utilizar los formularios como punto de entrada de información para nuestros procesos automatizados.

**Ejemplo práctico:**

Podemos crear un formulario para registrar solicitudes de compra, donde el usuario diligencie:

- Nombre del solicitante.
- Producto solicitado.
- Cantidad.
- Justificación de la compra.
- Fecha de solicitud.

Al enviar el formulario, se crea un nuevo elemento en la lista de SharePoint. A partir de ese registro podemos utilizar Power Automate para iniciar un flujo de aprobación.
Podemos hacer `Formularios` para ingresar datos a la lista para esto solo debemos dar click en `formularios` si no aparece en la vista de la lista le damos clic a los tres puntos y hay si dar click en `formularios`.

![](Adjuntos/Pasted%20image%2020261126135641.png)

aqui podemos darle un titulo al formulario hacer las validaciones de los campos y elegir que campos puede diligenciar.

![](Adjuntos/Pasted%20image%2020261126135731.png)