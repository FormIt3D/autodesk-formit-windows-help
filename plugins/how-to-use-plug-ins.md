# 플러그인 사용 방법

![](<../.gitbook/assets/g3 (1).gif>)

## Plugin Manager

FormIt Plugin Manager는 한 곳에서 플러그인을 검색하고 관리할 수 있는 도구입니다.

FormIt이 인터넷에 액세스할 수 있는 경우, FormIt을 시작하면 Plugin Manager가 자동으로 로드됩니다.

앱 오른쪽에 있는 해당 탭 아이콘![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG)을 클릭하여 액세스합니다.

![](../.gitbook/assets/c1.PNG)

## 플러그인 카테고리

Plugin Manager는 사용자가 가장 관심 있는 플러그인을 찾을 수 있도록 플러그인이 카테고리로 정리되어 있습니다.

![](../.gitbook/assets/d16.png)

**설치된 플러그인:** 사용자가 이미 설치한 플러그인입니다.&#x20;

**권장 플러그인:** FormIt 팀에서 FormIt의 핵심 기능을 확장하고 새 워크플로우를 잠금 해제하기 위해 권장하는 플러그인입니다. FormIt 팀의 승인을 받은 후 커뮤니티에서 개발한 플러그인이 여기에 표시됩니다.\GitHub 태그: _formit-plugin-recommended_

**공용 플러그인:** 커뮤니티에서 빌드한 플러그인입니다. 이 카테고리의 플러그인은 FormIt 팀에서 검토하거나 승인하지 않은 플러그인입니다. \GitHub 태그: _formit-plugin_

**개발자 플러그인**: 새 FormIt 플러그인의 생성을 지원하기 위해 커뮤니티에서 빌드한 플러그인입니다. \GitHub 태그: _formit-plugin-developers_

## 개인 또는 로컬 플러그인 추가

[자체 플러그인을 개발](how-to-develop-plugins/)하는 경우 패널 하단의 필드에 개인 URL을 추가하고 (+)를 클릭하면 됩니다.

![](../.gitbook/assets/d4.PNG)

개인 또는 로컬 플러그인 추가에 대한 자세한 내용은 [Plugin Manager에서 플러그인 미리보기를 참고하십시오. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Plugin Manager 재설정

Plugin Manager는 Windows의 레지스트리 키를 사용하여 설치된 리포지토리 및 플러그인을 저장합니다. Plugin Manager를 기본값으로 재설정해야 하는 경우 다음 레지스트리 키를 삭제합니다.

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ 주: 이렇게 하면 사용자가 추가한 모든 리포지토리와 플러그인이 설치제거되어 내장 리포지토리와 플러그인만 포함하도록 Plugin Manager가 재설정됩니다.

## 플러그인 설치

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager)에는 여러 플러그인이 다양한 카테고리로 정리되어 있습니다. 각 플러그인에는 이름, 설명, GitHub 링크 및 설치 토글이 있습니다.&#x20;

![](../.gitbook/assets/d5.PNG)

플러그인을 설치하려면 플러그인 이름 옆에 있는 토글을 켜기만 하면 됩니다.&#x20;

![](../.gitbook/assets/d6.png)

선택한 플러그인의 아이콘이 오른쪽 패널에 나타납니다. 이 아이콘을 클릭하여 플러그인의 UI를 표시합니다.

![](../.gitbook/assets/d7.PNG)

## 플러그인 사용

각 플러그인에는 개발자가 정의한 고유한 UI가 있습니다. 일반적으로 플러그인에는 사용 방법에 대한 지침 세트, 매개변수(텍스트 상자, 슬라이더, 확인란 등) 세트 및 실행을 위한 하나 이상의 버튼이 있습니다.

Plugin Manager: 2D 코너 모깍기에서 좀 더 단순한 예 중 하나를 사용해 보겠습니다. 먼저 Plugin Manager의 권장 섹션에서 플러그인을 로드합니다. 그런 다음, 개발자가 제공한 지침에 따라 모깎기 반지름을 설정하고 모깎기할 면 그룹을 선택한 다음, 코너 모깎기 버튼을 클릭합니다.

![](../.gitbook/assets/g4.gif)

##

