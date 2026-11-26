---
titulo: "08e Parse JSON (Analizar JSON - Análisis del archivo JSON)"
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: "2026-11-25"
ultimo_repaso: "2026-11-25"
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - "08e Parse JSON (Analizar JSON - Análisis del archivo JSON)"
---
# Parse JSON (Analizar JSON / Análisis del archivo JSON)

La acción **Parse JSON (Analizar JSON)** permite interpretar una estructura JSON para identificar sus propiedades y tipos de datos, facilitando el acceso a sus valores mediante contenido dinámico en las siguientes acciones del flujo.

Es especialmente útil cuando trabajamos con objetos JSON provenientes de Compose, respuestas de API o información recibida desde otras aplicaciones.


## 1. Configuración de la acción

La actividad requiere dos campos principales:

### Content (Contenido)

Contiene el objeto o la estructura JSON que queremos analizar.

Normalmente utilizamos la salida (`Outputs`) de una acción **Compose (Componer)**, aunque también podemos utilizar información procedente de otras actividades.

### Schema (Esquema)

Define la estructura del JSON que vamos a interpretar.

El esquema especifica:

- El tipo de estructura principal.
- Los nombres de las propiedades.
- El tipo de dato de cada propiedad.
- Las estructuras anidadas, cuando existen.

Por ejemplo, para analizar el siguiente objeto:

```json
{
    "nombre": "Carlos",
    "lugar": "Bogotá",
    "fecha": "2026-11-25",
    "participantes": 15
}
```

Necesitamos un esquema como el siguiente:

```json
{
    "type": "object",
    "properties": {
        "nombre": {
            "type": "string"
        },
        "lugar": {
            "type": "string"
        },
        "fecha": {
            "type": "string"
        },
        "participantes": {
            "type": "integer"
        }
    }
}
```

## 2. ¿Cómo obtener el Schema?

Power Automate permite generar automáticamente el esquema a partir de un ejemplo de los datos que vamos a utilizar.

Para hacerlo:

1. Agregamos la actividad **Parse JSON**.
2. En el campo Schema seleccionamos la opción **Utilizar la carga útil de muestra para generar esquema** (*Use sample payload to generate schema*).
3. Proporcionamos un ejemplo del JSON que queremos analizar.
4. Power Automate interpreta el ejemplo y genera automáticamente el esquema correspondiente.
5. Guardamos el esquema generado.

De esta manera no necesitamos construir manualmente toda la estructura JSON del esquema.

>[!important] **Importante:** 
>el ejemplo debe representar adecuadamente la estructura de los datos reales. Si existen propiedades opcionales, matrices u otros tipos de datos, debemos revisar el esquema generado para contemplar esas variaciones.

![Pasted image 20261125214122](Adjuntos/Pasted%20image%2020261125214122.png)
## 3. ¿Qué obtenemos al utilizar Parse JSON?

La principal ventaja de esta acción es que permite acceder a las propiedades del objeto mediante contenido dinámico.

Por ejemplo, después de analizar nuestro JSON, Power Automate reconocerá los siguientes campos:

- `nombre`
- `lugar`
- `fecha`
- `participantes`

Podremos utilizarlos directamente en otras actividades del flujo, como enviar correos electrónicos, crear registros en Excel o SharePoint y construir nuevas estructuras JSON.

Esto evita tener que acceder manualmente a cada propiedad mediante expresiones.

## 4. Consideraciones importantes

- El contenido debe ser un JSON válido.
- El esquema debe corresponder con la estructura del contenido.
- Los tipos de datos deben coincidir con los valores recibidos.
- Las propiedades obligatorias deben estar presentes.
- Si una propiedad puede no existir, debemos contemplar esa posibilidad en el esquema mediante `required`.
- Si una propiedad puede contener valores nulos, debemos permitir explícitamente el tipo `null` en el esquema.

> [!tip] Recomendación
> Una combinación muy útil es utilizar **Compose** para construir una estructura JSON y posteriormente **Parse JSON** para interpretar esa estructura y acceder fácilmente a sus propiedades mediante contenido dinámico.



