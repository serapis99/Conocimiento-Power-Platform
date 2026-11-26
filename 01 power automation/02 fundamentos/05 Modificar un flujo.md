---
titulo: Modificar un flujo
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: 2026-11-21
ultimo_repaso: 2026-11-21
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - Modificar un flujo
---
# Modificar un flujo: cambiar de instantáneo a programado

En Power Automate podemos editar un flujo existente y modificar su lógica de ejecución. En este caso, cambiaremos nuestro flujo de nube instantáneo por un flujo de nube programado (Scheduled cloud flow), de manera que se ejecute automáticamente según una periodicidad establecida.

## 1. Editar el flujo

Nos dirigimos a Mis flujos (My flows), buscamos nuestro flujo y seleccionamos Editar (Edit) para abrir nuevamente el diseñador.

En esta ocasión, vamos a cambiar el desencadenador que inicia nuestro flujo.

## 2. Eliminar el desencadenador anterior

Nuestro flujo actualmente utiliza el desencadenador:

`Desencadenar un flujo manualmente (Manually trigger a flow)`

Para cambiar su modalidad de ejecución:

1. Seleccionamos el desencadenador actual.
2. Abrimos el menú de opciones (⋮).
3. Seleccionamos Eliminar (Delete).
4. Confirmamos la eliminación cuando el sistema nos lo solicite.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121092018.png)

Al eliminar el desencadenador, estamos quitando el mecanismo que iniciaba el flujo manualmente. Las demás acciones del flujo pueden permanecer en el diseñador, siempre que no dependan de entradas que ya no existan.

## 3. Agregar un nuevo desencadenador: Periodicidad

Una vez eliminado el desencadenador anterior, podemos agregar uno nuevo.

1. Hacemos clic en Agregar un desencadenador (Add a trigger).
2. Buscamos `Periodicidad (Recurrence)`.
3. Seleccionamos el desencadenador correspondiente.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121092146.png)

Este desencadenador permite iniciar el flujo automáticamente de acuerdo con un intervalo o una frecuencia que nosotros definamos.

## 4. Configurar la periodicidad

Una vez agregado el desencadenador, debemos diligenciar los campos de configuración. La interfaz proporciona información sobre los valores aceptados en cada campo.

Entre las principales configuraciones podemos encontrar:

| Campo                              | Descripción                                                                       |
| ---------------------------------- | --------------------------------------------------------------------------------- |
| Interval (Intervalo)               | Cantidad de unidades entre cada ejecución.                                        |
| Frequency (Frecuencia)             | Unidad de tiempo utilizada para la repetición.                                    |
| Time zone (Zona horaria)           | Zona horaria de referencia para la programación.                                  |
| Start time (Hora de inicio)        | Fecha y hora a partir de la cual se programa la ejecución, cuando se configura.   |
| At these hours (A estas horas)     | Permite definir horas específicas de ejecución, según la frecuencia seleccionada. |
| At these minutes (A estos minutos) | Permite definir minutos específicos de ejecución, cuando corresponda.             |

La combinación de estos parámetros permite definir cuándo y con qué frecuencia se ejecutará nuestro flujo.

### Ejemplos de periodicidad

| Configuración | Resultado esperado       |
| ------------- | ------------------------ |
| Cada 1 minuto | Se ejecuta cada minuto.  |
| Cada 1 hora   | Se ejecuta cada hora.    |
| Cada 1 día    | Se ejecuta diariamente.  |
| Cada 1 semana | Se ejecuta semanalmente. |
| Cada 1 mes    | Se ejecuta mensualmente. |

>[!important] Importante: 
>la periodicidad y los campos disponibles pueden variar dependiendo de la frecuencia seleccionada y de la configuración del desencadenador.

![](01%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121093155.png)

## 5. Guardar y verificar

Una vez terminemos de configurar la periodicidad:

1. Hacemos clic en Guardar (Save).
2. Verificamos que el flujo no presente errores de configuración.
3. Confirmamos que el flujo esté activado.
4. Esperamos a que se cumpla el intervalo o la programación establecida.
5. Consultamos el Historial de ejecuciones (Run history) para verificar que se haya ejecutado.

> [!note] Aprendizaje
> En Power Automate, el desencadenador determina cómo comienza un flujo. Si cambiamos el desencadenador, podemos cambiar completamente el comportamiento de la automatización, incluso si conservamos las mismas acciones.

Por lo tanto, nuestro flujo ya no dependerá de que una persona lo ejecute manualmente, sino que quedará configurado para ejecutarse automáticamente según la periodicidad que hayamos establecido.