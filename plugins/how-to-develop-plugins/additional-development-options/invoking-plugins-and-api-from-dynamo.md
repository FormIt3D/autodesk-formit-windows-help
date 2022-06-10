# Invocar plug-ins e a API no Dynamo

## **Conectar plug-ins ao Dynamo**

O FormIt 2022.1 e versões mais recentes oferecem acesso a APIs de JavaScript e funções personalizadas do Dynamo por meio de dois novos nós:

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

O nó **CallJSAPI** permite que você chame APIs de JavaScript do FormIt diretamente do Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Para nomes de funções e parâmetros, dê uma olhada em nossa documentação JavaScript, que é dividida em duas partes: [API do FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) e [API do WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (kernel de modelagem).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

De outra forma, o nó **CallPluginJS** permite chamar funções personalizadas de um plug-in carregado ou de um fragmento de script que foi executado na janela do Editor de script.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
