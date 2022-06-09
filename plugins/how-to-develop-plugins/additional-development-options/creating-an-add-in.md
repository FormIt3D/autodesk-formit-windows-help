# 创建附加模块

附加模块是一个插件，它还会加载可显示新 JavaScript API 的 DLL。&#x20;



### 下载 FormIt API

要构建支持 FormIt 的 DLL，需要 FormIt API。可以从 [Autdesk 开发人员网络](https://www.autodesk.com.cn/developer-network/overview)下载 FormIt API。需要登录才能访问下载。&#x20;

登录后，FormIt API 在“软件”下可用。

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

附加模块有权访问 [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) 和 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html)。

附加模块具有以下结构：

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

要将参数转换为 C++ 变量，请使用 SCRIPTCONVERTER-

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

可以返回 JSON\_UNDEFINED 或任何 json 对象。使用 to\_json 将 C++ 变量转换为 json

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

在 DLL 定义了所有需要的 JS API 后，插件必须告知 FormIt 需要加载哪些 DLL。此操作在 [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8) 中完成。

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) 是一个有效示例，介绍了如何创建附加模块。

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) 是一个有效示例，介绍如何使用 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html) 创建附加模块。
