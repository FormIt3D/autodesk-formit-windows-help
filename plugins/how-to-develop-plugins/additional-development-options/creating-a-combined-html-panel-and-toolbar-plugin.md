# Erstellen eines kombinierten HTML-Gruppen- und Werkzeugkasten-Plugins

Mit einer einzigen _manifest.json_-Datei können Sie sowohl einen Werkzeugkasten als auch eine HTML-Gruppe initialisieren, die eine Reihe von Benutzeroberflächen-Typen und Werkzeugen bieten, die alle aus demselben Verzeichnis geladen werden.

```
    {
        "PluginName": "Name...",
        "PluginDescription": "Description...",
        "ToolbarEntry": "index.html", <-- This is the "main entry" used to load/define all code used by your toolbar buttons
        "ToolbarButtons": [ <-- Contains an entry for each toolbar button
            {
                "iconText": "TB",
                "iconURL": "circle.png",
                "command": "window.AlertFormItVersion" <-- Javascript that will run in the document defined by ToolbarEntry
            },
            {
                "iconText": "CB",
                "iconURL": "block.png",
                "command": "window.CreateBlock"
            }
        ],
        "Panel": "panel.html", <-- Panel entry point
        "PanelIcon": "block.png" <-- Icon for your panel button
    }

```
