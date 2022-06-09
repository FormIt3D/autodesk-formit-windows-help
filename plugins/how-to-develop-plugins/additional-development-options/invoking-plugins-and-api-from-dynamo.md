# Aufrufen von Plugins und APIs aus Dynamo

## **Verbinden von Plugins mit Dynamo**

FormIt 2022.1 und neuer bietet über zwei neue Blöcke Zugriff auf JavaScript-APIs und benutzerdefinierte Funktionen aus Dynamo:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Der **CallJSAPI**-Block ermöglicht Ihnen das Aufrufen von FormIt-JavaScript-APIs direkt aus Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Informationen zu Funktionsnamen und Parametern finden Sie in unserer JavaScript-Dokumentation, die in zwei Teile unterteilt ist: [FormIt-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) und [WSM-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (Modellierungs-Kernel).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

Umgekehrt können Sie mit dem **CallPluginJS**-Block benutzerdefinierte Funktionen von einem geladenen Plugin oder einem Skript-Snippet aus aufrufen, das im Skript-Editor-Fenster ausgeführt wird.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
