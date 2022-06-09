# Creazione di un plug-in della barra degli strumenti e di un plug-in del pannello HTML combinati

Con un singolo file _manifest.json_, è possibile inizializzare una barra degli strumenti e un pannello HTML, offrendo una serie di tipi e strumenti dell'interfaccia utente, tutti caricati dalla stessa directory.

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
