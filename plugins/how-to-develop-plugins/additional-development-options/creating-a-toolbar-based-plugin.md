# Creación de un módulo de extensión basado en barra de herramientas

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Estructura de un archivo manifest.json de un módulo de extensión basado en barra de herramientas

Un módulo de extensión basado en barra de herramientas contiene un archivo _manifest.json_ con la siguiente estructura:

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

Además de las [propiedades JSON estándar](../advanced-development/general-plugin-setup-in-the-manifest.md), un módulo de extensión basado en barra de herramientas incluye esta propiedad JSON especial:

* "ToolbarURL" indica a FormIt que este módulo es una barra de herramientas y se vincula a la ubicación de otro archivo JSON que describe la funcionalidad de la barra de herramientas.

### Configurar el formato de barra de herramientas con JSON

Después de crear un archivo manifest como el que se ha descrito anteriormente, deberá crear el archivo toolbar.json, que define los botones de la barra de herramientas, sus nombres, el texto, los iconos y la función onClick asignada a cada botón. El archivo JSON de la barra de herramientas presentará el siguiente formato:

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

El archivo toolbar.json incluye las siguientes propiedades JSON:

* "name" representa el nombre de la barra de herramientas general y se utiliza de forma interna para asociar todos los botones al menú único de la barra de herramientas.
* "buttons" representa los botones individuales añadidos dentro de la barra de herramientas. Una barra de herramientas puede tener cualquier número de botones.
* "name" define el nombre interno del botón, que se utiliza para asociar el botón a la barra de herramientas, así como a la función onClick del botón.
* "command" define la función del botón, que puede presentar una de estas dos formas: una función de JavaScript (que puede definirse en una secuencia de comandos incluida en el campo "Scripts" de manifest.json) o un comando de FormIt, por ejemplo, "Dibujar: Círculo". Para obtener una lista de comandos de FormIt, ejecute el módulo de extensión Messages.
* "iconText" establece el texto de la información de herramientas y la descripción en el botón. Si no se ha especificado una dirección URL de icono, el texto creará un icono generado automáticamente de texto con formato.
* "iconURL" se puede establecer para definir un icono personalizado para el botón.

Una vez que se hayan definido todos los botones del archivo toolbar.json, el módulo de extensión está listo para su uso.&#x20;

Si desea definir funciones adicionales de JavaScript, añádalas en la misma carpeta que el archivo manifest.json. Asegúrese de añadir la referencia de archivo al campo "Scripts" del archivo manifest para que FormIt pueda encontrar los archivos.
