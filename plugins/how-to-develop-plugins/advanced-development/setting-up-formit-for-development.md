# 개발용으로 FormIt 설정

FormIt 데스크톱 앱에서 플러그인을 테스트하고 빌드하려면 Windows 17.0 이상 버전용 FormIt이 필요합니다.

### **스크립트 편집기 및 스크립트 출력 표시**

FormIt의 상단 메뉴에서 상단 메뉴의 **창**으로 이동하여 **스크립트 편집기** 및 **스크립트 출력** 상자를 선택합니다.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

스크립트 편집기 및 스크립트 출력 패널이 FormIt 창의 맨 아래에 나타납니다.

하단에 있는 버튼을 사용하여 스크립트 편집기와 스크립트 출력 간을 전환합니다.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

두 패널을 나란히 배열할 수도 있습니다. 오른쪽 위 모서리에 있는 "x" 옆의 버튼을 클릭하여 패널 중 하나를 분리한 다음, 패널을 끌어서 다른 패널 옆에 놓습니다.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **스크립트 편집기**

스크립트 편집기는 코드를 작성하고 테스트할 수 있는 간단한 개발 환경을 제공합니다.

스크립트 편집기는 작성한 코드를 FormIt.exe 파일이 있는 디렉토리의 scratch.js 파일 내에 저장합니다.

맨 위에는 다음과 같은 두 개의 버튼이 있습니다.

**실행** ![](<../../../.gitbook/assets/image (8).png>): 창에서 작성한 모든 코드를 실행합니다.

**선택사항 실행** ![](<../../../.gitbook/assets/image (52).png>): 선택한/강조 표시된 코드 줄만 실행합니다.

### **스크립트 출력**

스크립트 출력 창에는 플러그인에서 콘솔로 출력된 메시지가 표시됩니다.

스크립트 편집기에서 `console.clear();`을 실행하여 출력을 지울 수 있습니다.

## 샘플 플러그인 작업

[리포지토리를 복제](cloning-a-sample-plugin.md)하고 [웹 서버를 설정](hosting-a-plugin-on-a-local-server.md)하고 나면 로컬 플러그인이 FormIt에 표시되도록 할 수 있습니다.

플러그인을 로드하거나 설치할 수 있지만, 이 연습을 위해 패널 기반 플러그인과 도구막대 기반 플러그인을 모두 설치하겠습니다. 여기서는 npm http-server가 두 예제 리포지토리를 모두 호스팅하고 있는 포트 8080에서 실행 중이라고 가정합니다.

### **로드와 설치**

`FormIt.LoadPlugin();`은 현재 세션에 대해서만 플러그인을 로드합니다. 플러그인은 앱이 닫혔다가 다시 시작될 때 자동으로 언로드됩니다.

현재 세션에서만 테스트할 플러그인을 임시로 나타내는 데 유용한 옵션입니다.

`FormIt.InstallPlugin();`은 레지스트리 키를 사용하여 플러그인이 유지되도록 합니다. 이것은 세션 간에 자주 사용하게 될 플러그인에 유용합니다.

Windows에서는 플러그인을 유지하는 데 다음 레지스트리 키가 사용됩니다.

* 플러그인: Computer\HKEY\_CURRENT\_USER\Software\Autodesk\FormIt 360\Plugins\InstalledPlugins

설치제거하려면 `FormIt.UninstallPlugin();`을 사용합니다.

다음 예에서는 별도의 설명이 없는 한, 연습 결과를 유지할지 여부에 따라  _설치_ 또는 _로드_ 를 자유롭게 사용합니다.

### **도구막대 플러그인 샘플: 반전**

스크립트 편집기에서 다음을 실행합니다.

로컬 서버를 실행하는 경우:

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

[FormIt GitHub 리포지토리](https://github.com/FormIt3D/)에서 로드하는 경우(인터넷 연결 필요):

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

응용프로그램 창의 맨 위에 반전 도구막대가 나타납니다.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **HTML 패널 플러그인 샘플: 특성 더하기**

스크립트 편집기에서 다음을 실행합니다.

로컬 서버를 실행하는 경우:

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

[FormIt GitHub 리포지토리](https://github.com/FormIt3D/)에서 로드하는 경우(인터넷 연결 필요):

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

응용프로그램 창 오른쪽에 특성 더하기 패널이 나타납니다.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **모달 및 모델리스 대화상자 플러그인 샘플**

대화상자 플러그인은 고유하며, 로드할 수만 있고 설치할 수는 없습니다.

스크립트 편집기에서 다음을 실행합니다.

로컬 서버를 실행하는 경우:

* 모달: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* 모델리스: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

[FormIt GitHub 리포지토리](https://github.com/FormIt3D/)에서 로드하는 경우(인터넷 연결 필요):

* 모달: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* 모달: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

HTML 패널 예제의 Hello Block! 패널이 화면에 모달 또는 모델리스 대화상자로 나타납니다.
