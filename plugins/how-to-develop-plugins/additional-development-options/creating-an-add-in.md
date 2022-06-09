# 建立增益集

增益集是一種外掛程式，也會載入顯示新 JavaScript API 的 DLL。&#x20;



### 下載 FormIt API

若要建置支援 FormIt 的 DLL，需要 FormIt API。FormIt API 可從 [Autodesk 開發商合作網](https://www.autodesk.com/developer-network/overview)下載。需要登入才能存取下載。&#x20;

登入後，可在「SOFTWARE」下看到 FormIt API。

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

增益集可以存取 [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) 和 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html)。

增益集有下列結構：

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

若要讓引數變成 C++ 變數，請使用 SCRIPTCONVERTER-

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

可以傳回 JSON\_UNDEFINED 或任何 JSON 物件。使用 to\_json 將您的 C++ 變數轉換為 json

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

DLL 定義所有需要的 JS API 後，外掛程式必須告訴 FormIt 需要載入的 DLL。這可在 [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8) 中完成。

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) 是一個說明如何建立增益集的有用範例。

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn)是一個說明如何使用 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html) 建立增益集的有用範例。
