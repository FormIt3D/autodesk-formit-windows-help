# Allgemeine Plugin-Einrichtung im Manifest 

FormIt-Plugins bestehen aus einer wichtigen Kernkomponente, der so genannten _manifest.json_-Datei.

Die Manifestdatei ist ein [JSON-Objekt](http://www.json.org), das der FormIt-Infrastruktur mitteilt, welche Dateien abgerufen und welche Plugins erstellt werden sollen.

### Manifest.json-Struktur und -Eigenschaften

Eine manifest.json-Datei hat folgende Struktur. Sie verfügt über zusätzliche Eigenschaften, je nachdem, ob es sich um ein [werkzeugkastenbasiertes](../additional-development-options/creating-a-toolbar-based-plugin.md) oder ein [HTML-gruppenbasiertes Plugin](../additional-development-options/creating-an-html-panel-plugin.md) handelt.

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

Ein typisches Plugin enthält die folgenden JSON-Eigenschaften:

* PluginName steht für den Namen des Plugins für interne und die meisten Anzeigezwecke, einschließlich für den [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager).
* PluginType steht für den Typ des Plugins, der Benutzern in der Beschreibung des [Plugin Managers](../../how-to-use-plug-ins.md#plugin-manager) mitteilt, worauf sie bei der Installation des Plugins achten müssen.
* PluginDescription wird im [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) angezeigt, um die Funktionen des Plugins zu kommunizieren.
* Unter Scripts werden die erforderlichen externen Skripte aufgeführt, die dem Plugin zugeordnet sind, das in die FormIt-Anwendung geladen wird. Diese Skripte können ausgeführt werden, wenn die Plugin-Funktionalität aufgerufen wird.

![](<../../../.gitbook/assets/image (5) (1).png>)

Starten Sie die Plugin-Entwicklung, indem Sie eine manifest.json-Datei im Plugin-Ordner erstellen. Als Nächstes müssen Sie entscheiden, ob Sie ein werkzeugkastenbasiertes oder ein gruppenbasiertes Plugin erstellen möchten.

![](<../../../.gitbook/assets/image (36).png>)

**Anmerkung:** Die Verwendung von PLUGINLOCATION in der gesamten oben aufgeführten manifest.json-Datei ist wichtig, und es wird die Groß- und Kleinschreibung berücksichtigt. FormIt ersetzt PLUGINLOCATION durch den Serverspeicherort für das Plugin.
