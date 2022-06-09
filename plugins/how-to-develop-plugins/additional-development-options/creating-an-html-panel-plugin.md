# Erstellen eines HTML-Gruppen-Plugins

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Ein gruppenbasiertes Plugin, das eine HTML-Seite anzeigt, verfügt über eine _manifest.json_-Datei mit der folgenden Struktur:

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

Zusätzlich zu den [Standard-JSON-Eigenschaften](../advanced-development/general-plugin-setup-in-the-manifest.md) enthält ein gruppenbasiertes Plugin die folgenden speziellen JSON-Eigenschaften:

* Panel weist FormIt an, dass es sich bei diesem Plugin um eine Gruppe handelt, und verweist auf den Speicherort der HTML-Datei, die in diese Gruppe geladen werden soll.
* Die HTML-Datei benötigt im Header Links zu den entsprechenden JavaScript-Dateien sowie zu einer CSS-Datei für die Stilzuweisung.
* Die HTML-Datei wird in der FormIt-Gruppe wie in einem Browser gerendert.
* Beispiele für komplexe HTML-Schnittstellen finden Sie in unserer [FormIt3D-Organisation](https://github.com/FormIt3D/).
* PanelIcon definiert ein Symbol für dieses Plugin, das auf der Registerkarte auf der rechten Seite der Anwendung angezeigt wird. Wenn nicht definiert, erstellt FormIt ein automatisches Symbol mit den Initialen aus dem Namen des Plugins.

Sobald Ihre HTML-, CSS- und JavaScript-Dateien konfiguriert sind, können Sie mit dem Testen des HTML-Gruppen-Plugins beginnen, indem Sie es [laden oder installieren](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
