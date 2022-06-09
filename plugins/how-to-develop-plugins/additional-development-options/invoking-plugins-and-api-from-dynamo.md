# 從 Dynamo 呼叫外掛程式和 API

## **將外掛程式與 Dynamo 連接**

FormIt 2022.1 和更高版本透過兩個新節點提供從 Dynamo 存取 JavaScript API 和自訂函式的途徑：

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

**CallJSAPI** 節點可讓您直接從 Dynamo 呼叫 FormIt JavaScript API。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

如需函式名稱和參數，請查看我們的 JavaScript 文件，該文件分為兩部分：[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) 和 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (塑型核心)。

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

相反地，**CallPluginJS** 節點可讓您從載入的外掛程式或從「腳本編輯器」視窗執行的腳本片段呼叫自訂函式。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
