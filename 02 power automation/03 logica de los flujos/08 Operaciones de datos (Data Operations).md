---
titulo: Operaciones de datos (Data Operations)
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-25
ultimo_repaso: 2026-11-25
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - Operaciones de datos (Data Operations)
---

# Operaciones de datos (Data Operations)

Las **operaciones de datos (Data Operations)** son un conjunto de acciones de Microsoft Power Automate destinadas a manipular, transformar, filtrar, combinar y estructurar datos durante la ejecución de un flujo de automatización.

Permiten procesar información proveniente de diferentes fuentes, como matrices, objetos JSON, respuestas de API y conectores, sin necesidad de implementar ciclos o expresiones complejas para cada operación.

## 1. Manipulación de datos

Acciones destinadas a seleccionar, filtrar y combinar información.

| Acción | Función |
|---|---|
| **Select (Seleccionar)** | Modifica la estructura de los objetos de una matriz. Permite seleccionar, eliminar, agregar o renombrar propiedades. No modifica la cantidad de elementos. |
| **Filter array (Filtrar matriz)** | Obtiene un subconjunto de elementos de una matriz que cumplen determinadas condiciones. |
| **Join (Unir)** | Convierte los elementos de una matriz en una única cadena de texto, utilizando un separador. |

## 2. Operaciones con JSON

Acciones que permiten crear, reutilizar e interpretar estructuras de datos JSON.

| Acción                         | Función                                                                                                                               |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------- |
| **Compose (Componer)**         | Recibe una entrada y genera una salida reutilizable. Puede contener texto, números, matrices, objetos JSON o expresiones.             |
| **Parse JSON (Analizar JSON)** | Interpreta el contenido JSON mediante un esquema y genera propiedades accesibles como contenido dinámico en las acciones posteriores. |

## 3. Operaciones con otros formatos

Acciones que permiten convertir matrices de datos en formatos tabulares para facilitar su presentación, exportación o comunicación con otras aplicaciones.

| Acción | Función |
|---|---|
| **Create CSV table (Crear tabla CSV)** | Convierte una matriz de objetos en una tabla de valores separados por comas (CSV). |
| **Create HTML table (Crear tabla HTML)** | Convierte una matriz de objetos en una tabla utilizando etiquetas HTML. |

## 4. Consideraciones importantes

- **Select y Filter array no son equivalentes:** Select modifica la estructura de los elementos, mientras que Filter array determina cuáles elementos permanecen.
- **Join no combina objetos JSON:** convierte los elementos de una matriz en una cadena de texto.
- **Compose no almacena datos permanentemente:** su salida puede reutilizarse en otras acciones del mismo flujo.
- **Parse JSON requiere un esquema:** este define las propiedades y los tipos de datos que se esperan interpretar.
- **CSV y HTML son formatos de salida:** no son equivalentes a una matriz JSON ni a una base de datos.

> [!tip] Recomendación
> Siempre que sea posible, realiza los filtros y las selecciones directamente en el origen de datos. Si el conector permite recuperar únicamente los registros o columnas necesarios, puedes reducir el volumen de información procesada por el flujo.