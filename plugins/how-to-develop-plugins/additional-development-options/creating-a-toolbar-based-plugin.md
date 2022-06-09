# Erstellen eines werkzeugkastenbasierten Plugins

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Struktur einer manifest.json-Datei für ein werkzeugkastenbasiertes Plugin

Ein werkzeugkastenbasiertes Plugin enthält eine _manifest.json_-Datei mit der folgenden Struktur:

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

Zusätzlich zu den [Standard-JSON-Eigenschaften](../advanced-development/general-plugin-setup-in-the-manifest.md) enthält ein werkzeugkastenbasiertes Plugin die folgende spezielle JSON-Eigenschaft:

* ToolbarURL weist FormIt an, dass es sich bei diesem Plugin um einen Werkzeugkasten handelt, und verweist auf den Speicherort einer anderen JSON-Datei, in der die Funktionen des Werkzeugkastens beschrieben werden.

### Konfigurieren des Werkzeugkastenformats mit JSON

Nach dem Erstellen einer Manifestdatei wie der oben beschriebenen müssen Sie die Datei toolbar.json erstellen, in der die Schaltflächen im Werkzeugkasten, deren Namen, der Text, die Symbole und die den einzelnen Schaltflächen zugewiesenen onClick-Funktionen definiert sind. Die JSON-Datei des Werkzeugkastens hat das folgende Format:

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

Die Datei toolbar.json enthält die folgenden JSON-Eigenschaften:

* name steht für den Namen des gesamten Werkzeugkastens und wird intern verwendet, um alle Schaltflächen mit dem einzelnen Werkzeugkastenmenü zu verknüpfen.
* buttons steht für einzelne Schaltflächen, die im Werkzeugkasten hinzugefügt wurden. Ein Werkzeugkasten kann eine beliebige Anzahl von Schaltflächen enthalten.
* name definiert den internen Namen der Schaltfläche, der verwendet wird, um die Schaltfläche mit dem Werkzeugkasten sowie mit der onClick-Funktion der Schaltfläche zu verknüpfen.
* command definiert die Funktion der Schaltfläche, die in zwei Formen vorliegen kann: eine JavaScript-Funktion (die in einem Skript definiert werden kann, das im manifest.json-Feld Scripts enthalten ist) oder ein FormIt-Befehl, z. B. Zeichnen: Kreis. Sie können eine Liste der FormIt-Befehle abrufen, indem Sie das Nachrichten-Plugin ausführen.
* iconText legt den QuickInfo- und Beschreibungstext für die Schaltfläche fest. Wenn keine Symbol-URL bereitgestellt wird, erstellt der Text ein automatisch generiertes Symbol mit formatiertem Text.
* iconURL kann so eingestellt werden, dass ein benutzerdefiniertes Symbol für die Schaltfläche definiert wird.

Nachdem alle Schaltflächen in der Datei toolbar.json definiert wurden, kann das Plugin verwendet werden.&#x20;

Wenn Sie weitere JavaScript-Funktionen definieren möchten, fügen Sie sie demselben Ordner wie die Datei manifest.json hinzu. Stellen Sie sicher, dass die Dateireferenz auch zum Feld Scripts der Manifestdatei hinzugefügt wird, damit FormIt die Dateien finden kann.
