---
titulo: validar el flujo
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
  - validar el flujo
---
# Validar y ejecutar un flujo en Power Automate

Una vez que hemos creado y guardado nuestro flujo, debemos realizar una prueba para comprobar que funciona correctamente y que las acciones se ejecutan según lo esperado.

## 1. Probar el flujo desde el editor

Dentro del editor de nuestro flujo podemos realizar una prueba haciendo clic en Probar (Test).

Al hacerlo, Power Automate nos solicitará confirmar la ejecución y seleccionar la forma en la que se realizará la prueba, según las opciones disponibles para nuestro flujo.

En un flujo instantáneo, podemos iniciar la ejecución manualmente.

Durante la ejecución, el editor nos permite visualizar el comportamiento de las acciones, mostrando cuáles se ejecutaron correctamente y cuáles presentaron errores.

Esto nos permite validar:

- Que el desencadenador inicia correctamente.
- Que las conexiones funcionan.
- Que las acciones se ejecutan.
- Que el flujo produce el resultado esperado.

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121085753.png)

## 2. Ejecutar el flujo desde Mis flujos

Una vez realizadas las pruebas desde el editor, podemos salir de él y volver a nuestro flujo posteriormente desde el módulo Mis flujos (My flows).

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121085827.png)

En esta sección podemos buscar y localizar los flujos que hemos creado.
Al posicionarnos sobre nuestro flujo, se habilitan diferentes opciones, entre ellas:

- **Ejecutar**: Iniciar el flujo
- **Editar**: Modificar el flujo
- **Compartir**: Compartir el flujo

En esta ocasión seleccionaremos Ejecutar (Run) para iniciar nuestro flujo sin necesidad de entrar nuevamente al editor.

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121085901.png)

## 3. Consultar el administrador del flujo

Después de ejecutar el flujo, podemos hacer clic sobre su nombre para acceder a su página de administración o detalles.

Desde allí podemos encontrar diferentes opciones y herramientas para gestionar y supervisar nuestra automatización.

![](02%20power%20automation/02%20fundamentos/Adjuntos/Pasted%20image%2020261121085956.png)

Entre las principales opciones podemos encontrar:

| Opción                                 | Función                                                                                       |
| -------------------------------------- | --------------------------------------------------------------------------------------------- |
| Historial de ejecuciones (Run history) | Consultar las ejecuciones realizadas y sus resultados.                                        |
| Ejecutar (Run)                         | Iniciar manualmente el flujo.                                                                 |
| Editar (Edit)                          | Modificar la estructura, desencadenadores y acciones del flujo.                               |
| Análisis (Analytics)                   | Consultar métricas e información sobre el comportamiento del flujo, según disponibilidad.     |
| Desactivar (Turn off)                  | Deshabilitar temporalmente el flujo para impedir que se ejecute.                              |
| Conexiones (Connections)               | Consultar las conexiones utilizadas por el flujo y su estado, según las opciones disponibles. |

## 4. Historial de ejecuciones (Run history)

El historial de ejecuciones es especialmente importante porque nos permite revisar qué ocurrió cada vez que se ejecutó nuestro flujo.

Al abrir una ejecución podemos inspeccionar sus pasos y consultar información de cada acción, por ejemplo:

- Si la acción se ejecutó correctamente.
- Si presentó algún error.
- Cuánto tiempo tardó en ejecutarse.
- Qué entradas recibió.
- Qué salidas produjo.
- Qué información devolvió el conector.

Esto resulta fundamental cuando estamos desarrollando automatizaciones, ya que nos permite identificar errores y comprender el comportamiento real del flujo.

> [!tip] Concepto clave\
> Crear un flujo no significa que automáticamente esté funcionando como esperamos. Siempre debemos ejecutarlo, validar los resultados y consultar su historial para asegurarnos de que la automatización cumple su propósito.

Así aprendemos también a utilizar las herramientas de administración y monitoreo que ofrece Power Automate, las cuales serán esenciales cuando nuestros flujos sean más complejos y trabajen con información real.