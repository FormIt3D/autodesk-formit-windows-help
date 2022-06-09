# 디버깅

FormIt 플러그인을 디버깅하려면 디버깅하는 엔진에 따라 다른 절차를 수행해야 합니다. (엔진에 대한 자세한 내용은 [이전 섹션](client-side-vs-web-side-engines.md)을 참고하십시오.)

### **클라이언트측(FormIt) 디버깅**

도구막대 및 패널 기반 플러그인에 모두 적용되는 FormIt측 코드에서 디버그하려면 코드에 한 줄을 추가하여 데스크톱 응용프로그램에 내장된 JS 디버거를 표시할 수 있습니다.

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **웹측(HTML) 디버깅**

패널 기반 FormIt 플러그인은 패널이 기본적으로 스타일 지정 및 스크립트가 포함된 HTML 웹 사이트이므로 HTML 기반 UI 디버깅을 제공합니다.

스크립트 및 스타일 지정을 포함하여 패널에 내장된 플러그인의 HTML측 코드를 디버그하려면

* **Windows 2021.1 이상 버전용 FormIt**
   * 플러그인 HTML 페이지를 마우스 오른쪽 버튼으로 클릭하고 "디버그"를 클릭하여 응용프로그램에 내장된 HTML 디버거를 표시합니다.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **웹용 FormIt**
   * 바로 가기 F12 또는 Ctrl+Shift+I를 사용하여 브라우저의 HTML 디버거를 불러옵니다.

![](../../../.gitbook/assets/debugonweb.gif)

