# Appel de plug-ins et d’API à partir de Dynamo

## **Connexion de plug-ins avec Dynamo**

FormIt 2022.1 et les versions ultérieures permettent d’accéder aux API JavaScript et aux fonctions personnalisées de Dynamo via deux nouveaux nœuds :

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Le nœud **CallJSAPI** vous permet d’appeler des API JavaScript FormIt directement à partir de Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Pour les noms de fonction et les paramètres, consultez notre documentation JavaScript, divisée en deux parties : [API FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) et [API WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (noyau de modélisation).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

À l’inverse, le nœud **CallPluginJS** vous permet d’appeler des fonctions personnalisées à partir d’un plug-in chargé ou d’un extrait de script exécuté à partir de la fenêtre de l’éditeur de script.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
