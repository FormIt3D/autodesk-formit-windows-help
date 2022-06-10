# Llamada a módulos de extensión y API desde Dynamo

## **Conexión de módulos de extensión con Dynamo**

FormIt 2022.1 y versiones posteriores ofrecen acceso a las API de JavaScript y a las funciones personalizadas de Dynamo mediante los dos nuevos nodos siguientes:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

El nodo **CallJSAPI** permite llamar a la API de JavaScript de FormIt directamente desde Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Para obtener información sobre los parámetros y los nombres de función, consulte la documentación de JavaScript que se divide en estas dos partes: [API de FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) y [API WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (núcleo de modelado).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

Por el contrario, el nodo **CallPluginJS** permite llamar a funciones personalizadas de un módulo de extensión cargado o un fragmento de secuencia de comandos que se ha ejecutado desde la ventana del Editor de secuencias de comandos.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
