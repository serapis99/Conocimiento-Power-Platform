---
titulo: Condiciones en Power Automate
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
  - Condiciones en Power Automate
---
# Condiciones en Power Automate

## 1. ¿Qué es una condición?

Dentro del módulo **Control** de Power Automate encontramos la acción **Condición (Condition)**, que permite tomar decisiones mediante la evaluación de condiciones lógicas.

Esta acción permite dividir el flujo en dos caminos de ejecución, dependiendo de si una condición se cumple o no:

- **Si verdadero (If yes):** ejecuta las acciones cuando la condición se cumple.
- **Si falso (If no):** ejecuta las acciones cuando la condición no se cumple.

### Ejemplo práctico

Una empresa desea comprobar si sus ventas superaron los 1000.

La condición sería:

```text
Ventas > 1000
```

El flujo tendrá dos posibles resultados:

- **Verdadero:** si las ventas superan los 1000, se envía una notificación de felicitación.
- **Falso:** si las ventas son iguales o inferiores a 1000, se ejecuta otra acción, como enviar una alerta.

## 2. Configuración de una condición

La acción Condición permite configurar tres elementos:

| Elemento | Descripción |
|---|---|
| Valor izquierdo | Variable o dato que queremos evaluar. |
| Operador | Tipo de comparación que queremos realizar. |
| Valor derecho | Valor con el que queremos comparar. |

### Operadores de comparación

Algunos de los operadores disponibles son:

| Operador | Significado |
|---|---|
| Es igual a | Comprueba si dos valores son iguales. |
| No es igual a | Comprueba si dos valores son diferentes. |
| Es mayor que | Comprueba si un valor supera al otro. |
| Es mayor o igual que | Comprueba si un valor es superior o igual al otro. |
| Es menor que | Comprueba si un valor es inferior al otro. |
| Es menor o igual que | Comprueba si un valor es inferior o igual al otro. |

## 3. Utilizar variables en las condiciones

Cuando necesitamos evaluar una variable que hemos creado previamente, podemos seleccionarla desde el panel de **Contenido dinámico (Dynamic content)**.

Para hacerlo:

1. Seleccionamos el campo donde queremos introducir el valor.
2. Abrimos el panel de contenido dinámico.
3. Buscamos el grupo denominado **Variables**.
4. Seleccionamos el nombre de nuestra variable.

De esta manera, podemos utilizar las variables creadas anteriormente en las comparaciones de nuestras condiciones.

![](02%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125101803.png)

>[!note] **Nota:** 
>debemos asegurarnos de que los tipos de datos sean compatibles. Por ejemplo, para comparar cantidades numéricas es recomendable utilizar variables de tipo Integer o Float, en lugar de String.

## 4. Condiciones lógicas múltiples

Power Automate también permite evaluar varias condiciones dentro de una misma acción.

Para ello podemos utilizar:

- **AND (Y):** todas las condiciones deben cumplirse para obtener un resultado verdadero.
- **OR (O):** al menos una de las condiciones debe cumplirse para obtener un resultado verdadero.

Ejemplo:

```text
Ventas > 1000 AND Clientes > 50
```

La condición será verdadera únicamente cuando las ventas superen los 1000 y el número de clientes sea superior a 50.

![](02%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125102405.png)


