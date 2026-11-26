---
titulo: Hacer hasta (Do until) en Power Automate
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
  - Hacer hasta (Do until) en Power Automate
---
# Hacer hasta (Do until) en Power Automate

## 1. ¿Qué es Hacer hasta?

La actividad **Hacer hasta (Do until)** pertenece al módulo **Control** de Power Automate y permite repetir un conjunto de acciones hasta que se cumpla una condición determinada.

Es decir, el flujo ejecutará las acciones dentro del bucle y comprobará la condición de salida. Cuando esta se cumpla, dejará de repetir las acciones y continuará con el resto del flujo.

A diferencia de **Aplicar a cada uno**, que recorre una colección de elementos, Hacer hasta repite acciones hasta alcanzar una condición de finalización.

### Ejemplo práctico

Supongamos que queremos consultar periódicamente el estado de una solicitud hasta que sea aprobada.

La lógica sería:

1. Consultar el estado de la solicitud.
2. Comprobar si está aprobada.
3. Si todavía no está aprobada, esperar un tiempo y volver a consultar.
4. Si está aprobada, finalizar el bucle y continuar con el resto del flujo.

## 2. Limitadores de ejecución

Power Automate dispone de limitadores para evitar que un bucle se ejecute indefinidamente.

Los principales parámetros son:

| Parámetro | Descripción |
|---|---|
| Recuento (Count) | Número máximo de iteraciones que puede ejecutar el bucle. |
| Tiempo de espera (Timeout) | Tiempo máximo permitido para ejecutar el bucle. |

La configuración predeterminada permite hasta 60 iteraciones y un tiempo de espera de 1 hora. Estos valores pueden modificarse, respetando los límites máximos de la plataforma.

El bucle finalizará cuando se cumpla la condición o cuando alcance alguno de sus límites.

## 3. ¿Qué hacer si queremos repeticiones infinitas?

Power Automate no permite ejecutar un bucle verdaderamente infinito dentro de una misma ejecución de un flujo en la nube.

Sin embargo, podemos implementar una automatización continua mediante otras estrategias.

### Opción 1. Utilizar un desencadenador de periodicidad (Recurrence)

Podemos crear un flujo programado que se ejecute automáticamente cada cierto intervalo de tiempo.

Por ejemplo:

- Cada minuto.
- Cada 5 minutos.
- Cada hora.
- Una vez al día.

De esta manera, el flujo se ejecutará periódicamente sin necesitar un bucle infinito.

Esta es generalmente la alternativa más recomendable cuando queremos realizar comprobaciones recurrentes.

### Opción 2. Utilizar varios flujos encadenados

Podemos dividir el proceso en diferentes ejecuciones.

Cuando un flujo termina, puede iniciar otro mediante un mecanismo de comunicación entre flujos, como un flujo secundario o un desencadenador HTTP.

Esta alternativa es útil para procesos prolongados que necesitan conservar su estado entre ejecuciones.

>[!important] **Importante:** 
>Estas alternativas tampoco representan una ejecución ilimitada sin restricciones. Siguen sujetas a los límites de duración, solicitudes y capacidad de Power Automate.

## 4. ¿En qué situaciones utilizar Hacer hasta?

Esta actividad resulta especialmente útil cuando no conocemos exactamente cuántas veces debemos repetir una operación, porque dependemos de una condición que puede cambiar durante la ejecución.

Algunos ejemplos son:

| Situación | Funcionamiento |
|---|---|
| Esperar una aprobación | Consultar el estado hasta que una solicitud sea aprobada o rechazada. |
| Consultar procesos | Revisar periódicamente si un proceso externo terminó. |
| Esperar la generación de un archivo | Comprobar si un archivo ya está disponible. |
| Supervisar una operación | Consultar el estado de una tarea hasta que finalice. |
| Esperar una respuesta | Repetir una consulta hasta recibir la información esperada. |
| Procesar información | Repetir operaciones hasta alcanzar un resultado determinado. |
