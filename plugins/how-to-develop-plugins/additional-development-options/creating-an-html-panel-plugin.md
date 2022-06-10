# Creación de un módulo de extensión de panel HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Un módulo de extensión basado en panel que muestra una página HTML presenta un archivo _manifest.json_ con la siguiente estructura:

```
{
    "PluginName": "Hello Block!",
    "PluginType": "Panel",
    "PluginDescription": "Creates a panel with an HTML form that allows dimensional input for a 3D block which will get generated at the world origin.",
    "Scripts": [
        "PLUGINLOCATION/block.js"
    ],
    "Panel": "PLUGINLOCATION/hello_block.html",
    "PanelIcon": "PLUGINLOCATION/hello_block.png"
}               
```

Además de las [propiedades JSON estándar](../advanced-development/general-plugin-setup-in-the-manifest.md), un módulo de extensión basado en panel incluye estas propiedades JSON especiales:

* "Panel" indica a FormIt que este módulo es un panel y se vincula a la ubicación del archivo HTML que se debe cargar en el panel.
* El archivo HTML necesitará vínculos en el encabezado a los archivos JavaScript correspondientes, así como a un archivo CSS para aplicar estilos.
* El archivo HTML se renderizará en el panel de FormIt del mismo modo que en un navegador.
* Puede ver ejemplos de interfaces HTML enriquecidas en nuestra [organización de FormIt3D](https://github.com/FormIt3D/).
* "PanelIcon" define un icono para que este módulo de extensión aparezca en la ficha de la derecha de la aplicación. Si no se define, FormIt crea un icono automático con las iniciales del nombre del módulo de extensión.

Una vez que haya configurado los archivos HTML, CSS y JavaScript, puede comenzar a probar el módulo de extensión de panel HTML. Para ello, [cárguelo o instálelo](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
