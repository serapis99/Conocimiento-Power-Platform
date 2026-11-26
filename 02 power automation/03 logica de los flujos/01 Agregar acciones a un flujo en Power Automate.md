---
titulo: Agregar acciones a un flujo en Power Automate
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
  - Agregar acciones a un flujo en Power Automate
---
# Agregar acciones a un flujo en Power Automate

Power Automate permite construir flujos mediante la incorporación de diferentes acciones. Podemos ir agregándolas progresivamente utilizando el símbolo más (+) que aparece en el diseñador, entre los componentes o al final de un flujo.

De esta manera podemos ampliar una automatización según las necesidades del proceso.

## 1. Límite de acciones

Como referencia, Power Automate permite crear flujos con hasta 500 acciones, sujeto a los límites y restricciones del servicio.

Esto significa que podemos incorporar múltiples actividades dentro de un mismo flujo para realizar procesos más completos.

## 2. Agregar nuevas acciones

Para agregar una actividad:

1. Abrimos nuestro flujo en el diseñador.
2. Ubicamos el símbolo (+) en el lugar donde queremos incorporar una acción.
3. Hacemos clic en él.
4. Seleccionamos Agregar una acción (Add an action).
5. Buscamos la actividad que necesitamos.
6. La seleccionamos y configuramos sus propiedades.

## 3. Ejercicio: consultar el clima y enviar un correo electrónico

En este ejercicio utilizaremos dos actividades:

1\. MSN Weather (Clima)

Permite consultar información meteorológica, como las condiciones actuales del clima para una ubicación.

2\. Enviar un correo electrónico (V2)

Permite enviar un correo electrónico utilizando una conexión configurada con Outlook.

![](02%20power%20automation/03%20logica%20de%20los%20flujos/Adjuntos/Pasted%20image%2020261125093353.png)

> [!important] Idea clave\
> Las acciones de un flujo pueden trabajar de manera encadenada: una actividad obtiene información y otra puede utilizarla para realizar una operación diferente.

>[!note] Nota técnica: 
>el límite de 500 acciones es una referencia del límite de definición del flujo; existen otras restricciones relacionadas con la cantidad de operaciones, duración y ejecución. Además, MSN Weather puede tener limitaciones de disponibilidad o compatibilidad según el conector y el entorno.


