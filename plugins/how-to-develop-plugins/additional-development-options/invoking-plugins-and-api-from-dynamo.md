# Richiamo di plug-in e API da Dynamo

## **Connessione di plug-in con Dynamo**

FormIt 2022.1 e versioni successive offre l'accesso alle API JavaScript e alle funzioni personalizzate da Dynamo tramite due nuovi nodi:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Il nodo **CallJSAPI** consente di richiamare le API JavaScript di FormIt direttamente da Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Per i nomi e i parametri delle funzioni, consultare la documentazione su JavaScript, suddivisa in due parti: [API di FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) e [API di WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (kernel di modellazione).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

Al contrario, il nodo **CallPluginJS** consente di richiamare funzioni personalizzate da un plug-in caricato o da un frammento di script eseguito dalla finestra Editor script.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
