# Вызов подключаемых модулей и API из Dynamo

## **Подключение подключаемых модулей с помощью Dynamo**

В FormIt 2022.1 и более поздних версиях к API-интерфейсам и пользовательским функциям JavaScript можно получить доступ из Dynamo с помощью двух новых узлов.

### **CallJSAPI** <a href="#calljsapi" id="calljsapi"></a>

Узел **CallJSAPI** позволяет вызывать API-интерфейсы JavaScript, доступные в FormIt, непосредственно из Dynamo.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

Информацию об именах функций и параметрах можно найти в документации по JavaScript, которая разделена на две части: [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) и [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (ядро моделирования).

### **CallPluginJS** <a href="#callpluginjs" id="callpluginjs"></a>

В свою очередь, узел **CallPluginJS** позволяет вызывать пользовательские функции из загруженного подключаемого модуля или фрагмента сценария, который был выполнен из окна редактора сценариев.

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
