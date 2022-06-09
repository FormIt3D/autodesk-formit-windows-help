# 결합된 HTML 패널 및 도구막대 플러그인 테스트

Windows용 FormIt에서 기본으로 제공되는 [스크립트 편집기](../advanced-development/setting-up-formit-for-development.md)를 사용하여 진행 중인 플러그인을 손쉽게 테스트할 수 있습니다.

테스트할 때는 `FormIt.LoadPlugin("URL");`을 사용하는 것이 좋습니다. 이 플러그인은 이 세션을 위해 임시로 로드되며, FormIt을 다시 시작하면 플러그인이 사라집니다.&#x20;

테스트가 완료되면 `FormIt.InstallPlugin("URL");`을 사용하여 세션 간에 플러그인을 유지할 수 있습니다.

**Windows 17 이상 버전용 FormIt**

****

### **도구막대 플러그인**

플러그인을 FormIt에 로드하여 최신 UI를 보고, 최신 기능을 테스트합니다.

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

몇몇 사항을 변경한 다음, 위의 명령을 사용하여 플러그인을 다시 로드합니다.

테스트할 때 현재 세션에서 동일한 플러그인의 여러 인스턴스(instance)를 로드할 수 있으며, UI는 각각 고유합니다.

최신 UI 인스턴스(instance)를 사용하여 최신 변경 사항을 테스트해야 합니다.



### **HTML 패널 플러그인**

플러그인을 FormIt에 로드하여 최신 UI를 보고, 최신 기능을 테스트합니다.

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

몇몇 사항을 변경한 다음, 패널을 마우스 오른쪽 버튼으로 클릭하고 "하드 다시 로드"를 선택하여 최신 HTML, CSS 및 스크립트가 포함된 패널을 다시 로드합니다.

****

### **Plugin Manager를 사용하여 플러그인 미리보기**

플러그인이 로드되면 이 안내서의 [이전 장](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md)을 참고하십시오.

****

### **.JSON 파일에 대한 웹 캐시 강제로 지우기**

플러그인 또는 리포지토리에 대한 manifest.json 파일 내에서 제목 또는 설명을 수정할 경우, 다음번에 Plugin Manager를 다시 로드할 때 해당 변경 사항이 적용되도록 하려면 Windows용 FormIt에서 캐시를 강제로 지워야 할 수 있습니다.

Windows용 FormIt은 웹 캐시를 여기에 저장하므로 Windows 탐색기에서 숨겨진 항목을 사용하도록 설정하여 AppData 폴더를 표시해야 합니다.

* C:\사용자\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

웹 캐시를 삭제하려면 위의 "Default" 폴더를 삭제한 다음, Plugin Manager를 다시 로드하여 업데이트된 제목 및 설명을 확인하면 됩니다.
