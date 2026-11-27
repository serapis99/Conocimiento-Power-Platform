---
titulo: "OneDrive en Power Automate"
tipo: concepto
nivel: 🌱
estado: activo
fecha_creacion: "2026-11-26"
ultimo_repaso: "2026-11-26"
frecuencia_repaso: 1
nivel_dominio: bajo
tags:
  - software
  - automatizacion
aliases:
  - "OneDrive en Power Automate"
---
# OneDrive en Power Automate

Cuando queremos utilizar archivos almacenados en OneDrive desde Power Automate, debemos identificar que existen dos modalidades principales:

### 1. OneDrive Personal

Es el servicio de almacenamiento en la nube asociado a una cuenta personal de Microsoft.

Generalmente utiliza cuentas como:

- Outlook.com.
- Hotmail.com.
- Live.com.

Está orientado al almacenamiento y administración de archivos personales.

### 2. OneDrive para la Empresa (OneDrive for Business)

Es el servicio de almacenamiento en la nube asociado a una cuenta profesional o educativa de Microsoft 365.

Se utiliza principalmente en organizaciones para almacenar, administrar y compartir documentos relacionados con las actividades empresariales.

El almacenamiento está asociado a la organización y sujeto a sus políticas de administración y seguridad.

### 3. Diferencias en Power Automate

Al momento de crear una conexión en Power Automate debemos seleccionar el conector correspondiente:

| Característica | OneDrive | OneDrive for Business |
|---|---|---|
| Tipo de cuenta | Personal | Profesional o educativa |
| Identidad | Cuenta Microsoft personal | Cuenta organizacional |
| Conector | OneDrive | OneDrive for Business |
| Uso principal | Archivos personales | Archivos empresariales |
| Acceso | Cuenta personal | Cuenta autorizada por la organización |

### 4. Actividades disponibles

Ambos conectores permiten realizar operaciones similares sobre los archivos.

Algunos ejemplos son:

- Crear archivos.
- Obtener el contenido de un archivo.
- Buscar archivos.
- Eliminar archivos.
- Copiar archivos.
- Mover o cambiar el nombre de archivos.
- Obtener metadatos.
- Convertir archivos a otros formatos.

Sin embargo, las acciones, los desencadenadores y algunas limitaciones pueden variar entre los dos conectores.

### Consideraciones importantes

- Debemos seleccionar el conector según el tipo de cuenta que queremos utilizar.
- La conexión debe autenticarse con una cuenta compatible con el conector seleccionado.
- OneDrive Personal y OneDrive para la Empresa mantienen almacenamientos independientes.
- No podemos combinar ambas cuentas en una sola; podemos utilizarlas en paralelo.
- En entornos empresariales, el acceso también puede estar condicionado por las políticas de seguridad de la organización.