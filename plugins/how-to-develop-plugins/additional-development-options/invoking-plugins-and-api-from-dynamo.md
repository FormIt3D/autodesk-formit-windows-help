# Dynamo からプラグインと API を呼び出す

## **Dynamo を使用してプラグインを接続する**

FormIt 2022.1 以降では、2 つの新しいノードを介して Dynamo から JavaScript API およびカスタム関数にアクセスできるようになりました。

### **CallJSAPI**<a href="#calljsapi" id="calljsapi"></a>

**CallJSAPI** ノードを使用すると、Dynamo から FormIt JavaScript API を直接呼び出すことができます。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallJSAPI-GetTotalGrossArea.png)

関数名とパラメータについては、JavaScript に関するドキュメントを参照してください。このドキュメントは、[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) と [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (モデリング カーネル)の 2 つに分かれています。

### **CallPluginJS**<a href="#callpluginjs" id="callpluginjs"></a>

一方、**CallPluginJS** ノードを使用すると、ロード済みのプラグインからカスタム関数を呼び出したり、スクリプト エディタ ウィンドウから実行されたスクリプトのスニペットを呼び出すことができます。

![](https://formit.autodesk.com/page/formit-dynamo/dynamo-formitCallPluginJS.png)
