# Vyvolání modulů plug-in a rozhraní API z aplikace Dynamo

## **Připojení k modulům plug-in pomocí aplikace Dynamo**

Aplikace FormIt 2022.1 a novější nabízí přístup k rozhraním API jazyka JavaScript a uživatelským funkcím z aplikace Dynamo prostřednictvím dvou nových uzlů:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Uzel **CallJSAPI** umožňuje vyvolat rozhraní API jazyka JavaScript aplikace FormIt přímo z aplikace Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Názvy a parametry funkcí naleznete v dokumentaci k jazyku JavaScript, která je rozdělena do dvou částí: [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) a [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (modelovací jádro).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

Naopak uzel **CallPluginJS** umožňuje vyvolat uživatelské funkce z načteného modulu plug-in nebo fragmentu skriptu, který byl proveden z okna Editor skriptů.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
