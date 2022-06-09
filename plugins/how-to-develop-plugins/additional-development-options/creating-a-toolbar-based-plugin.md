# 도구막대 기반 플러그인 작성

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### 도구막대 기반 플러그인 manifest.json의 구조

도구막대 기반 플러그인에는 다음 구조의 _manifest.json_ 파일이 있습니다.

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

도구막대 기반 플러그인에는 [표준 JSON 특성](../advanced-development/general-plugin-setup-in-the-manifest.md) 외에도 다음과 같은 특수한 JSON 특성이 포함되어 있습니다.

* "ToolbarURL"은 이 플러그인이 도구막대이면서 도구막대의 기능을 설명하는 다른 JSON 파일 위치에 대한 링크임을 FormIt에 알려줍니다.

### JSON으로 도구막대 형식 구성

위에서 설명한 것과 같은 매니페스트 파일을 작성한 후 도구막대 버튼, 이름, 텍스트, 아이콘 및 각 버튼에 할당된 onClick 함수를 정의하는 toolbar.json 파일을 작성해야 합니다. 도구막대의 JSON 파일은 형식이 다음과 같습니다.

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

toolbar.json 파일에는 다음과 같은 JSON 특성이 포함되어 있습니다.

* "name"은 전체 도구막대의 이름을 나타내며 모든 버튼을 단일 도구막대 메뉴에 연관시키기 위해 내부적으로 사용됩니다.
* "buttons"는 도구막대 내부에 추가된 개별 버튼을 나타냅니다. 도구막대에는 버튼을 원하는 만큼 추가할 수 있습니다.
* "name"은 버튼의 내부 이름을 정의합니다. 이 이름은 버튼을 도구막대 및 버튼의 onClick 함수에 연관시키는 데 사용됩니다.
* "command"는 버튼의 함수를 정의합니다. 이 함수는 JavaScript 함수(manifest.json "Scripts" 필드에 포함된 스크립트에서 정의할 수 있음) 또는 FormIt 명령(예: "Draw: Circle") 중 하나로 나타날 수 있습니다. 메시지 플러그인을 실행하여 FormIt 명령 리스트를 얻을 수 있습니다.
* "iconText"는 버튼에 툴팁 및 설명 문자를 설정합니다. 아이콘 URL이 제공되지 않으면 문자가 서식이 있는 문자의 자동 생성 아이콘을 생성합니다.
* "iconURL"은 버튼의 사용자 아이콘을 정의하도록 설정할 수 있습니다.

toolbar.json 파일에 버튼이 모두 정의되어 있으면 플러그인을 시작할 준비가 된 것입니다.&#x20;

정의하려는 추가 JavaScript 함수가 있는 경우 해당 함수를 manifest.json 파일과 동일한 폴더에 추가합니다. 매니페스트 파일의 "Scripts" 필드에 파일 참조를 추가하여 FormIt에서 파일을 찾을 수 있도록 해야 합니다.
