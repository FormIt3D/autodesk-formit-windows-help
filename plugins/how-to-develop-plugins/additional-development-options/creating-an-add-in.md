# 애드인 작성

애드인은 새 JavaScript API를 표시하는 DLL을 로드하는 플러그인입니다.&#x20;



### FormIt API 다운로드

FormIt을 지원하는 DLL을 빌드하려면 FormIt API가 필요합니다. FormIt API는 [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview)에서 다운로드할 수 있습니다. 다운로드에 액세스하려면 로그인해야 합니다.&#x20;

로그인하면 소프트웨어 아래에서 FormIt API를 다운로드할 수 있습니다.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

애드인은 [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) 및 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html)에 액세스할 수 있습니다.

애드인의 구조는 다음과 같습니다.

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

인수를 C++ 변수로 가져오려면 SCRIPTCONVERTER를 사용합니다.

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

JSON\_UNDEFINED 또는 json 객체를 반환할 수 있습니다. to\_json을 사용하여 C++ 변수를 json으로 변환합니다.

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

DLL이 필요한 모든 JS API를 정의하고 나면 플러그인이 로드해야 하는 DLL을 FormIt에 알려야 합니다. 이 작업은 [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8)에서 수행됩니다.

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn)은 애드인을 만드는 방법을 설명하는 작업 예입니다.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn)은 [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html)를 사용하여 애드인을 만드는 방법을 설명하는 작업 예입니다.
