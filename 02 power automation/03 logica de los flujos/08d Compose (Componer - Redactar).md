---
titulo: "Compose (Componer - Redactar)"
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
  - "Compose (Componer - Redactar)"
---
# Compose (Componer / Redactar)

La acción **Compose (Componer)**, que también puede aparecer como **Redactar** dependiendo del idioma de Power Automate, permite recibir una entrada y generar una salida reutilizable dentro del flujo.

Se utiliza para construir estructuras de datos, almacenar temporalmente valores, concatenar información y realizar transformaciones mediante expresiones.

Aunque puede recibir diferentes tipos de datos, es especialmente útil para construir objetos y matrices JSON.

![Pasted image 20261125213726](Adjuntos/Pasted%20image%2020261125213726.png)

## 1. Construcción de estructuras JSON

Podemos escribir directamente una estructura JSON en la entrada de Compose.
Es importante reconocer los símbolos que definen cada tipo de estructura:

### Objeto (Object)

Se representa mediante llaves `{}` y contiene propiedades organizadas mediante pares de clave y valor.

```json
{
    "Nombre": "Carlos",
    "Edad": 30,
    "Cargo": "Analista"
}
```

### Matriz (Array)

Se representa mediante corchetes `[]` y contiene una colección de elementos.

```json
[
    "Carlos",
    "Ana",
    "Pedro"
]
```

También podemos crear matrices de objetos:

```json
[
    {
        "Nombre": "Carlos",
        "Edad": 30
    },
    {
        "Nombre": "Ana",
        "Edad": 25
    }
]
```

## 2. Anidamiento de objetos y matrices

Una característica importante de JSON es que podemos combinar y anidar objetos y matrices para construir estructuras más complejas.

Por ejemplo, un objeto puede contener una matriz como propiedad:

```json
{
    "Departamento": "Sistemas",
    "Empleados": [
        {
            "Nombre": "Carlos",
            "Cargo": "Analista"
        },
        {
            "Nombre": "Ana",
            "Cargo": "Desarrolladora"
        }
    ]
}
```

También podemos crear matrices que contengan otros objetos con matrices anidadas.

La estructura dependerá de cómo necesitemos organizar y representar la información.

## 3. Consideraciones importantes

- Las llaves `{}` representan objetos.
- Los corchetes `[]` representan matrices.
- Los objetos contienen propiedades mediante pares de clave y valor.
- Las matrices contienen colecciones de elementos.
- Podemos anidar objetos y matrices entre sí.
- Las claves de los objetos deben escribirse entre comillas dobles.
- Los valores de texto también deben utilizar comillas dobles.
- Los números y valores booleanos no necesitan comillas.
- Debemos respetar la sintaxis JSON, incluyendo comas y dos puntos.

> [!tip] Recomendación
> Compose es especialmente útil para construir objetos JSON manualmente cuando necesitamos preparar información para otras acciones, conectores o solicitudes HTTP. Si posteriormente necesitamos interpretar y acceder fácilmente a sus propiedades mediante contenido dinámico, podemos utilizar **Parse JSON (Analizar JSON)**.