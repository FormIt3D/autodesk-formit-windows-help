# 建立一個結合 HTML 面板和工具列的外掛程式

使用單一個 _manifest.json_，您可以初始化工具列和 HTML 面板，提供各種使用者介面類型和工具，所有內容都從同一個目錄載入。

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
