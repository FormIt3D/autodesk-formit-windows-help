# 매니페스트의 일반 플러그인 설정

FormIt 플러그인은 _manifest.json_ 파일이라는 핵심 구성요소로 이루어져 있습니다.

매니페스트 파일은 가져올 파일과 만들 플러그인 유형을 FormIt 인프라에 설명하는 [JSON 객체](http://www.json.org)입니다.

### Manifest.json 구조 및 특성

manifest.json 파일의 구조는 다음과 같습니다. [도구막대 기반](../additional-development-options/creating-a-toolbar-based-plugin.md) 플러그인인지 또는 [HTML 패널 기반 플러그인](../additional-development-options/creating-an-html-panel-plugin.md)인지에 따라 추가 특성이 있습니다.

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

일반적인 플러그인에는 다음과 같은 JSON 특성이 포함되어 있습니다.

* "PluginName"은 [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager)용을 포함하여 내부용 및 대부분의 화면표시용 플러그인의 이름을 나타냅니다.
* "PluginType"은 플러그인의 유형을 나타내며, 사용자는 [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) 설명을 통해 플러그인을 설치할 때 확인해야 할 사항을 파악할 수 있습니다.
* "PluginDescription"은 플러그인의 기능을 전달하기 위해 [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager)에 표시됩니다.
* "Scripts"는 FormIt 응용프로그램에 로드될 플러그인과 연관된 필수 외부 스크립트를 나열하며, 플러그인 기능이 호출될 때 실행될 수 있습니다.

\![](<../../../.gitbook/assets/image (5) (1).png>)

플러그인 폴더에 manifest.json 파일을 생성하여 플러그인 개발을 시작합니다. 다음으로, 도구막대 기반 플러그인을 만들지 아니면 패널 기반 플러그인을 만들지를 결정해야 합니다.

\![](<../../../.gitbook/assets/image (36).png>)

**주:** 위의 manifest.json 파일 전반에서 PLUGINLOCATION을 사용해야 하며, PLUGINLOCATION은 대소문자를 구분합니다. FormIt은 PLUGINLOCATION을 플러그인의 서버 위치로 대체합니다.
