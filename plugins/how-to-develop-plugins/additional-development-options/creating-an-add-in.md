# Создание надстройки

Надстройка — это подключаемый модуль, который также загружает библиотеки DLL, предоставляющие новые API-интерфейсы JavaScript.&#x20;



### Загрузка API FormIt

Для создания файлов DLL, поддерживающих FormIt, требуется API FormIt. API FormIt можно скачать с веб-сайта [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview). Для доступа к разделу загрузок необходимо войти в систему.&#x20;

После входа в систему интерфейс API FormIt будет доступен в разделе «ПРОГРАММНОЕ ОБЕСПЕЧЕНИЕ».

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Надстройка имеет доступ к [API FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) и [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Надстройка имеет следующую структуру.

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

Чтобы получить аргументы в переменные C++, используйте SCRIPTCONVERTER-

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

Может быть возвращен либо JSON\_UNDEFINED, либо любой объект JSON. Для преобразования переменной C++ в JSON используйте to\_json

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

Когда DLL определит все необходимые API-интерфейсы JS, подключаемый модуль должен сообщить FormIt, какие файлы DLL должны быть загружены. Это выполняется в файле [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) — это рабочий пример, в котором описывается процедура создания надстройки.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) — это рабочий пример, в котором описывается процедура создания надстройки с помощью [API-интерфейса ядра моделирования FormIt на базе C++](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
