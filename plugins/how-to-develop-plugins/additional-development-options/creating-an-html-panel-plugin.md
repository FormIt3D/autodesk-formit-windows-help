# HTML 패널 플러그인 작성

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

HTML 페이지를 표시하는 패널 기반 플러그인에는 다음 구조의 _manifest.json_ 파일이 있습니다.

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

패널 기반 플러그인에는 [표준 JSON 특성](../advanced-development/general-plugin-setup-in-the-manifest.md) 외에도 다음과 같은 특수한 JSON 특성이 포함되어 있습니다.

* "패널"은 이 플러그인이 패널이면서 패널에 로드해야 하는 HTML 파일 위치에 대한 링크임을 FormIt에 알려줍니다.
* HTML 파일의 헤더에는 스타일 지정을 위한 CSS 파일뿐만 아니라 적절한 JavaScript 파일에 대한 링크가 있어야 합니다.
* HTML 파일은 브라우저에서와 마찬가지로 FormIt 패널에서 렌더링됩니다.
* [FormIt3D 조직](https://github.com/FormIt3D/)에서 서식 있는 HTML 인터페이스의 예를 볼 수 있습니다.
* "PanelIcon"은 응용프로그램 오른쪽의 탭에 표시할 이 플러그인의 아이콘을 정의합니다. 정의되지 않은 경우 FormIt은 플러그인 이름의 이니셜을 사용하여 자동 아이콘을 생성합니다.

HTML, CSS 및 JavaScript 파일이 설정되면 HTML 패널 플러그인을 [로드하거나 설치](../advanced-development/setting-up-formit-for-development.md#load-vs.-install)하여 HTML 패널 플러그인 테스트를 시작할 수 있습니다.
