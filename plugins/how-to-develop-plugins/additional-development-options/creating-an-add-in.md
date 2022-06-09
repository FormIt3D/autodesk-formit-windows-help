# Tworzenie dodatku

Dodatek to wtyczka wczytująca również pliki DLL, które ujawniają nowe interfejsy API języka JavaScript.&#x20;



### Pobieranie interfejsu API programu FormIt

Aby można było utworzyć pliki DLL obsługujące program FormIt, wymagany jest interfejs API programu FormIt. Interfejs API programu FormIt można pobrać z witryny [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview). Pobranie jest możliwe dopiero po zalogowaniu się.&#x20;

Po zalogowaniu się interfejs API programu FormIt jest dostępny w obszarze SOFTWARE (OPROGRAMOWANIE).

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Dodatek ma dostęp do [interfejsu API programu FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) oraz [interfejsu API FormIt Modeling Kernel C++](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Dodatek ma następującą strukturę:

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

Aby pobrać argumenty do zmiennych C++, użyj polecenia SCRIPTCONVERTER-

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

Może zostać zwrócony obiekt JSON\_UNDEFINED lub dowolny obiekt json. Za pomocą to\_json przekonwertuj zmienną C++ na json

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

Po zdefiniowaniu przez bibliotekę DLL wszystkich potrzebnych interfejsów API języka JS wtyczka musi poinformować program FormIt, które biblioteki DLL wymagają wczytania. Jest to realizowane w [manifeście](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) to działający przykład, w którym wyjaśniono sposób tworzenia dodatku.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) to działający przykład, w którym wyjaśniono sposób tworzenia dodatku za pomocą [interfejsu API FormIt Modeling Kernel C++](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
