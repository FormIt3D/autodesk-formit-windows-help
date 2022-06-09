# 创建组合的 HTML 面板和工具栏插件

使用单个 _manifest.json_，可以初始化工具栏和 HTML 面板，从而提供各种 UI 类型和工具，所有这些类型和工具均从同一目录加载。

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
