# 从 Dynamo 调用插件和 API

## **将插件与 Dynamo 连接**

FormIt 2022.1 及更高版本允许从 Dynamo 通过两个新节点访问 JavaScript API 和自定义函数：

### **CallJSAPI**<a href="#calljsapi" id="calljsapi"></a>

**CallJSAPI** 节点允许直接从 Dynamo 调用 FormIt JavaScript API。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

有关函数名称和参数，请查看我们的 JavaScript 文档，该文档分为两个部分：[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) 和 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html)（建模内核）。

### **CallPluginJS**<a href="#callpluginjs" id="callpluginjs"></a>

相反，**CallPluginJS** 节点允许调用已加载的插件或从“脚本编辑器”窗口执行的脚本片段中的自定义函数。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
