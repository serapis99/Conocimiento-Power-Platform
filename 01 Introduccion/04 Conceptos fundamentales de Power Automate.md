Para desarrollar flujos en Power Automate, es importante familiarizarse primero con los componentes fundamentales que permiten construir, ejecutar y conectar una automatización.

Además del desencadenador, las plantillas y las conexiones, existen otros conceptos que conviene comprender para saber cómo funciona un flujo desde que se inicia hasta que termina su ejecución.

## Conceptos fundamentales de Power Automate

1. **Desencadenador (Trigger / Gatilho)**: Es el evento o condición que inicia la ejecución de un flujo. Determina cuándo debe comenzar la automatización.

>[!example] Ejemplos:
>- Cuando llega un correo.
>- Cuando se crea un archivo.
>- Cuando se recibe una solicitud.
>- En una fecha y hora programada.
>- Cuando un usuario ejecuta el flujo manualmente.

2. **Plantillas (Templates)**: Son flujos prediseñados que permiten utilizar una automatización existente como punto de partida, en lugar de construirla desde cero.

>[!example] Ejemplo: 
>una plantilla que guarda automáticamente los archivos adjuntos de Outlook en OneDrive.

3. **Conectores (Connectors)**: Permiten que Power Automate se comunique con otros servicios, aplicaciones o plataformas. Existen conectores estándar, premium y otros tipos, dependiendo del servicio y las licencias.

>[!example] Ejemplos: 
>Outlook, Excel, SharePoint, Teams, OneDrive, SQL Server.
    
4. **Conexiones (Connections)**: Son la configuración que permite a Power Automate utilizar un conector para acceder a un servicio mediante una cuenta, autenticación y permisos.

>[!example] Ejemplo: 
>crear una conexión con Outlook utilizando tu cuenta para permitir que un flujo lea o envíe correos.

5. **Acciones (Actions)**: Son las operaciones que el flujo ejecuta después de iniciarse o cuando llega a un determinado paso.

Ejemplos:

- Enviar un correo.
    
- Crear un archivo.
    
- Leer una fila de Excel.
    
- Actualizar un registro.
    
- Ejecutar un flujo de escritorio.
    
    [Flowchart Symbols: Included Shapes | ShapeChef](https://images.openai.com/static-rsc-4/YSkeRhn3Xww27JNFG_mLRVLx0c3bwzh1FtW1kG5ND5sv5JQksgA4-eBWB0tMxRln1SgLQafGmmBrT2OPo5eqoceWUs02JAMOOKQCupXKdGdzoL2yZyTDOsvt-Si-mZHwJBCfnLBLBFnv-ctSyUb5Sc9fnQ_qr_uIluBWqqjoxbY?purpose=inline)
    
    6. Condiciones (Conditions)
    
    Permiten evaluar si se cumple una regla y decidir qué camino debe seguir el flujo.
    
    Ejemplo: si el correo contiene la palabra Factura, guardar el adjunto; de lo contrario, ignorarlo.
    
    [6 patterns for a bullet-proof automation](https://images.openai.com/static-rsc-4/g9HmqmM__hocGCU0owBluNuxmNauN3aaTIDEVHk9UyImX7R1wqwBwr7HDdEaUn6rJGFrBgUiX1KlW0N3MTecGDaXDJZiZbftm6RYZ2c8NBrGAgN2Yu5lfiwD1U2czpY0wbPC9_RgThMnLLYCJTkOEc0pXVSIZc_V70Ym7xdffJM?purpose=inline)
    
    7. Bucles (Loops)
    
    Permiten repetir acciones o recorrer una colección de elementos.
    
    Ejemplos:
    
- Aplicar a cada uno (Apply to each): recorrer una lista de elementos.
    
- Do until: repetir acciones hasta que se cumpla una condición.
    
    [AlgoDaily - Initializing Variables and Basic Math Operations](https://images.openai.com/static-rsc-4/o4juM2UG9cK1h5SjI68IDbg5jOk0w-wdYkcRibekiWq4q6PPItanaJfe18h8HO30_C1AWdRgX0MtUUgg1qkybNnGih7oh4xRkxxjFGM7tm_WXJCxk2auDdzui7FSVBoUksrnSI71E-gDPldV2eMwduJhpXCvjH7GznyysY1A6IY?purpose=inline)
    
    8. Variables (Variables)
    
    Permiten almacenar temporalmente información durante la ejecución del flujo para utilizarla, modificarla o acumular resultados.
    
    Ejemplos: texto, números, booleanos, arrays y objetos.
    
    [What is data mapping? Data mapping explained (with examples)](https://images.openai.com/static-rsc-4/jivq48zf6GMVLP0be1aaG_BY5z8CrN3-6Zo4HA0LsSH9Sn_Z2f1frYdZD2L3otjI3nLBQzjSeqU-qHitv67Crz15ve98QZiWvOIeuLufeRGDg3y6Qp_-ZYInqLn-mBs5AzFqFMDu4JpY2EHkfH7quWy0pv1E6Nwf4mxdoYGkmBo?purpose=inline)
    
    9. Expresiones (Expressions)
    
    Permiten transformar, evaluar y manipular datos dentro de los flujos mediante funciones y operaciones.
    
    Ejemplos de uso:
    
- Manipular fechas.
    
- Convertir texto.
    
- Obtener valores específicos.
    
- Comparar datos.
    
- Concatenar cadenas.
    
    [Make Product Explainer Videos with Sora 2, Kling and Veo in Minutes | Pexo](https://images.openai.com/static-rsc-4/1W0n70y5FMkCBcnBKodKHNvCGCwTjCwBDIsfdoAiYnNif4rN4S6KuXP-PlP3rLkl_KGyHQ0wYDmmfMlO2w1-m9P4bCrnHQKmUv1CQjnH8Yn5xKhbNGgpDK6NglhzXVE10CPRdA12-6ITaPS2sHYAZ8P1p8fM6H6lsY9cSRySrY0?purpose=inline)
    
    10. Entradas y salidas (Inputs / Outputs)
    
    Permiten recibir información para iniciar o ejecutar un flujo y devolver resultados a otros flujos, procesos o servicios.
    
    Ejemplo: recibir el nombre de un archivo como parámetro y devolver la ruta donde fue almacenado.
    
    [Freshservice Orchestration for IT Workflows & Automation](https://images.openai.com/static-rsc-4/rm29M08fvqhN2PNCGDAWTTPX0y55g-tM9-ojM6d1rpJFo7ZhkIfHU-Qmdywqy4lM08PZDVzazJu5ha1Eepuonhe1nTDEld_A-OfPguUGPBGvuR_Fku6COVF8f4tfYIh0GvFg_ymD9B6x7uO9ocZ3s4_Je38BscgqKHCpWXStJo0?purpose=inline)
    
    11. Historial de ejecuciones (Run history)
    
    Permite consultar las ejecuciones realizadas por un flujo, conocer su estado y revisar qué sucedió durante cada paso.
    
    Estados habituales: correcto, fallido, cancelado o en ejecución.
    
    [CyntraLabs](https://images.openai.com/static-rsc-4/cAeGnZismyzkbqdfzGvfZdZ09TLfJGFxUke8WgIXuygluN7ocrr7dOw4BPVigpE-TvELYSLFPK7q6AHiVr84Wxm-81rMm9hOtFjVkNwVl_GrhbQ8KQLuj9uZ4StYnahMGlKVS_GFHqEA7BsJ5ifn9KcDAexrgHWipuopFxnbwDY?purpose=inline)
    
    12. Manejo de errores (Error handling)
    
    Permite controlar qué debe suceder cuando una acción falla o se presenta una situación inesperada.
    
    Ejemplos: reintentar una acción, capturar un error, registrar el fallo, enviar una notificación o ejecutar una ruta alternativa.