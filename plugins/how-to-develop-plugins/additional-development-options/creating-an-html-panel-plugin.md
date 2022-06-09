# Creazione di un plug-in del pannello HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Un plug-in basato sul pannello che visualizza una pagina HTML presenta un file _manifest.json_ con la seguente struttura:

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

Oltre alle [proprietà JSON standard](../advanced-development/general-plugin-setup-in-the-manifest.md), un plug-in basato sul pannello include le seguenti proprietà JSON speciali:

* "Panel" indica a FormIt che questo plug-in è un pannello e si collega alla posizione del file HTML che deve essere caricato nel pannello.
* Il file HTML richiede collegamenti, nell'intestazione, ai file JavaScript appropriati, nonché a un file CSS per gli stili.
* Il file HTML verrà sottoposto a rendering nel pannello di FormIt come in un browser.
* È possibile vedere esempi di interfacce HTML complete nel nostro [repository dell'organizzazione di FormIt3D](https://github.com/FormIt3D/).
* "PanelIcon" definisce un'icona per visualizzare questo plug-in nella scheda sul lato destro dell'applicazione. Se non è definita, FormIt crea un'icona automatica utilizzando le iniziali del nome del plug-in.

Una volta impostati i file HTML, CSS e JavaScript, è possibile iniziare a testare il plug-in del pannello HTML [caricandolo o installandolo](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
