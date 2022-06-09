# Wywoływanie wtyczek i interfejsu API z dodatku Dynamo

## **Łączenie wtyczek z dodatkiem Dynamo**

Program FormIt w wersji 2022.1 i nowszych zapewnia dostęp do interfejsów API języka JavaScript i funkcji niestandardowych z dodatku Dynamo za pośrednictwem dwóch nowych węzłów:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Węzeł **CallJSAPI** umożliwia wywoływanie interfejsów API języka JavaScript programu FormIt bezpośrednio z dodatku Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Nazwy funkcji i parametry można znaleźć w dokumentacji języka JavaScript, która jest podzielona na dwie części: [Interfejs API programu FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) oraz [Interfejs API WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (jądro modelowania).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

Natomiast węzeł **CallPluginJS** umożliwia wywoływanie funkcji niestandardowych z wczytanej wtyczki lub fragmentu skryptu wykonywanego z poziomu okna Edytor skryptów.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
