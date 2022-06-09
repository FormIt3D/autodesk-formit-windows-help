# アドインを作成する

アドインとはプラグインのことですが、新しい JavaScript API を公開する DLL のロードも行います。&#x20;



### FormIt API をダウンロードする

FormIt をサポートする DLL をビルドするには、FormIt API が必要です。FormIt API は、[ Autodesk デベロッパー ネットワーク](https://www.autodesk.co.jp/developer-network/overview)からダウンロードできます。ダウンロードを行うにはログインが必要です。&#x20;

ログインすると、SOFTWARE から FormIt API を取得できるようになります。

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

アドインで、[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) および [FormIt モデリング カーネル C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html) にアクセスできます。

アドインは次のような構造になっています。

```
            // FormIt looks for REGISTERAPIMETHODS to load new JS APIs
            REGISTERAPIMETHODS
            {
                // Declare new namespace for the new JS APIs
                REGISTERNAMESPACE("HelloDLL")
                // Create a JS API with no arguments
                APIMETHOD(HelloDLL, API1, "") {}
                // Create a JS API with 1 argument
                APIMETHOD(HelloDLL, API2, "arg1") {}
                // Create a JS API with 2 argument
                APIMETHOD(HelloDLL, API3, "arg1, arg2") {}
                ...
                ...
            }

```

引数を C++ 変数に変換するには、SCRIPTCONVERTER を使用します。

```
            // Create a JS API with 2 argument
            APIMETHOD(HelloDLL, API3, "arg1, arg2")
            {
                // NOTE: The arg names above ^^^^ have to match the args in the macros below.
                // arg1 expects a bool
                SCRIPTCONVERTER(bool, arg1);
                // arg2 expects an int
                SCRIPTCONVERTER(int, arg2);
                return JSON_UNDEFINED;
            }

```

JSON\_UNDEFINED か任意の JSON オブジェクトのいずれかを返すことができます。to\_json を使用して、C++ 変数を json に変換します。

```
            // Create a JS API with 2 argument
            APIMETHOD(HelloDLL, API3, "arg1, arg2")
            {
                // NOTE: The arg names above ^^^^ have to match the args in the macros below.
                // arg1 expects a bool
                SCRIPTCONVERTER(bool, arg1);
                // arg2 expects an int
                SCRIPTCONVERTER(int, arg2);

                std::string myValue = "Test";
                return to_json(myValue);
            }

```

DLL で必要なすべての JS API を定義したら、プラグインは、どの DLL のロードが必要かを FormIt に伝える必要があります。これは、[manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8) で行います。

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) は動作の一例です。アドインの作成方法がわかります。

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) も動作の一例ですが、[FormIt モデリング カーネル C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html) を使用するアドインの作成方法がわかります。
