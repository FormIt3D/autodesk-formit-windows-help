# 결합된 HTML 패널 및 도구막대 플러그인 작성

단일 _manifest.json_을 사용하면 도구막대와 HTML 패널 모두를 초기화하여 동일한 디렉토리에서 로드된 다양한 UI 유형 및 도구를 제공할 수 있습니다.

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
