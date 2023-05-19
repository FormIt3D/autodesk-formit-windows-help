# Configuración general de módulos de extensión en el archivo manifest 

Los módulos de extensión de FormIt están formados por un componente central clave que recibe el nombre de archivo _manifest.json_.

El archivo manifest es un [objeto JSON](http://www.json.org) que indica a la infraestructura de FormIt los archivos que se deben recuperar y el tipo de módulo de extensión que se debe crear.

### Propiedades y estructura del archivo manifest.json

Un archivo manifest.json presenta la siguiente estructura. Tiene propiedades adicionales en función de si se trata de un [módulo de extensión basado en barra de herramientas](../additional-development-options/creating-a-toolbar-based-plugin.md) o un [módulo de extensión basado en panel HTML](../additional-development-options/creating-an-html-panel-plugin.md).

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

Un módulo de extensión típico incluye estas propiedades JSON:

* "PluginName" representa el nombre del módulo de extensión para fines internos y de visualización, incluido para [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager).
* "PluginType" representa el tipo de módulo de extensión, lo que permite a los usuarios saber en la descripción de [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) lo que deben buscar al instalar el módulo de extensión.
* "PluginDescription" se muestra en [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) para indicar las funciones del módulo de extensión.
* "Scripts" muestra las secuencias de comandos externas necesarias asociadas con el módulo de extensión que se cargará en la aplicación FormIt y que pueden ejecutarse cuando se llame a las funciones del módulo de extensión.

![](<../../../.gitbook/assets/image (5) (1).png>)

Para empezar a desarrollar el módulo de extensión, cree un archivo manifest.json en la carpeta del módulo de extensión. A continuación, deberá decidir si va a crear un módulo de extensión basado en barra de herramientas o panel.

![](<../../../.gitbook/assets/image (36).png>)

**Nota:** El uso de PLUGINLOCATION en todo el archivo manifest.json anterior es esencial y distingue entre mayúsculas y minúsculas. FormIt reemplazará PLUGINLOCATION por la ubicación del servidor para el módulo de extensión.
