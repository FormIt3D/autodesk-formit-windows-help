# Dynamo에서 플러그인 및 API 호출

## **Dynamo와 플러그인 연결**

FormIt 2022.1 이상 버전에서는 다음과 같은 두 개의 새 노드를 통해 Dynamo에서 JavaScript API 및 사용자 함수에 액세스할 수 있습니다.

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

**CallJSAPI** 노드를 사용하면 Dynamo에서 직접 FormIt JavaScript API를 호출할 수 있습니다.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

함수 이름 및 매개변수에 대해서는 JavaScript 설명서를 살펴보십시오. 이 설명서의 경우 [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html)와 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html)(모델링 커널)로 나누어져 있습니다.

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

반대로 **CallPluginJS** 노드를 사용하면 로드된 플러그인 또는 스크립트 편집기 창에서 실행된 스크립트 조각에서 사용자 함수를 호출할 수 있습니다.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
