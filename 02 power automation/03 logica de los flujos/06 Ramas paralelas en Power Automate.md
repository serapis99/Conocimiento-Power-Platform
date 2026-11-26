---
titulo: Ramas paralelas en Power Automate
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
  - Ramas paralelas en Power Automate
---
# Ramas paralelas en Power Automate

## 1. ¿Qué son los procesos en paralelo?

Power Automate permite crear **ramas paralelas (Parallel branches)** para ejecutar dos o más conjuntos de acciones simultáneamente dentro de un mismo flujo.

Esto significa que, en lugar de esperar a que termine una actividad para comenzar otra, podemos ejecutar varias actividades independientes al mismo tiempo.

### ¿Por qué utilizarlas?

Su principal objetivo es optimizar el tiempo de ejecución de los flujos.

Por ejemplo, si necesitamos enviar un correo electrónico y registrar información en SharePoint, podemos ejecutar ambas actividades en paralelo, sin necesidad de esperar a que una termine para comenzar la otra.

## 2. ¿Cómo crear ramas paralelas?

Para crear una rama paralela:

1. Nos ubicamos en el punto del flujo donde queremos dividir la ejecución.
2. Hacemos clic derecho sobre el signo `+` que aparece entre las actividades.
3. Seleccionamos **Agregar una rama paralela (Add a parallel branch)**.
4. Agregamos las actividades que queremos ejecutar simultáneamente.
5. Podemos agregar más ramas paralelas según las necesidades del proceso.

Cada rama puede contener varias actividades que se ejecutarán secuencialmente dentro de ella, mientras las demás ramas avanzan de manera independiente.

![Pasted image 20261125145255](Adjuntos/Pasted%20image%2020261125145255.png)

## 3. ¿En qué situaciones se suelen utilizar?

Las ramas paralelas son especialmente útiles cuando tenemos actividades que no dependen unas de otras.

Algunos ejemplos:

| Situación | Funcionamiento |
|---|---|
| Enviar notificaciones | Enviar correos electrónicos y mensajes de Teams simultáneamente. |
| Registrar información | Guardar datos en SharePoint y en otra base de datos al mismo tiempo. |
| Solicitudes de aprobación | Enviar una solicitud a diferentes departamentos simultáneamente. |
| Consultar información | Obtener datos de diferentes fuentes al mismo tiempo. |
| Actualizar sistemas | Modificar registros en diferentes aplicaciones sin esperar a que termine cada actualización. |
| Generar reportes | Ejecutar diferentes procesos de recopilación de información simultáneamente. |

### Ejemplo práctico: solicitud de vacaciones

Supongamos que un empleado solicita vacaciones y necesitamos notificar a tres departamentos:

- Recursos Humanos.
- Administración.
- Gerencia.

En lugar de enviar las notificaciones una después de otra, podemos crear tres ramas paralelas para que cada departamento reciba la solicitud simultáneamente.

Cuando las tres ramas hayan terminado, podemos agregar una actividad posterior para registrar que las notificaciones fueron enviadas.

## 4. ¿Qué sucede cuando terminan las ramas paralelas?

Power Automate permite continuar el flujo después de las ramas paralelas.

Cuando agregamos una nueva actividad después del punto donde convergen las ramas, esta esperará a que todas las ramas paralelas correspondientes hayan finalizado.

Por ejemplo:

```text
             Inicio
                |
        +-------+-------+
        |               |
     Rama 1           Rama 2
        |               |
   Enviar correo    Actualizar datos
        |               |
        +-------+-------+
                |
        Registrar resultado
                |
               Fin
```

De esta manera, podemos ejecutar procesos simultáneamente y después continuar con una secuencia común.

## 5. Ventajas y desventajas

### Ventajas

- **Reducción del tiempo de ejecución:** las actividades independientes se ejecutan simultáneamente.
- **Mayor eficiencia:** aprovechamos mejor el tiempo de ejecución del flujo.
- **Organización:** permite separar procesos independientes en diferentes ramas.
- **Flexibilidad:** podemos ejecutar distintas actividades y procesos dentro de cada rama.
- **Escalabilidad del diseño:** facilita la construcción de flujos que requieren múltiples operaciones simultáneas.

### Desventajas

- **Mayor complejidad:** los flujos pueden resultar más difíciles de comprender y mantener cuando tienen muchas ramas.
- **Dependencias entre procesos:** no es recomendable utilizar ramas paralelas cuando una actividad necesita el resultado de otra.
- **Consumo de recursos:** ejecutar varias acciones simultáneamente puede incrementar las solicitudes y el consumo de recursos.
- **Conflictos de información:** si varias ramas modifican simultáneamente el mismo registro o variable, pueden producirse inconsistencias.
- **Manejo de errores:** debemos contemplar qué sucede si una rama falla y las demás finalizan correctamente.

## 6. Consideraciones importantes

- Utilizar ramas paralelas cuando las actividades sean independientes.
- Evitar dependencias entre ramas que necesiten ejecutarse en un orden específico.
- Tener precaución cuando varias ramas modifican una misma variable.
- Recordar que una actividad posterior a la convergencia espera a que finalicen las ramas correspondientes.
- No asumir que las ramas siempre terminarán al mismo tiempo; cada una puede tardar una cantidad diferente.

>[!note] **Nota:** 
>las ramas paralelas no son lo mismo que la concurrencia de `Aplicar a cada uno`. Las primeras permiten dividir el flujo en procesos independientes; la segunda permite procesar varios elementos de una colección simultáneamente.
