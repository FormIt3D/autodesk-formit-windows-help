# Erstellen eines Zusatzmoduls

Ein Zusatzmodul ist ein Plugin, das auch DLLs lädt, die neue JavaScript-APIs verfügbar machen.&#x20;



### Herunterladen der FormIt-API

Zum Erstellen von DLLs, die FormIt unterstützen, wird die FormIt-API benötigt. Die FormIt-API kann vom [Autodesk Developer Network](https://www.autodesk.com/developer-network/overview) heruntergeladen werden. Für den Zugriff auf den Download ist eine Anmeldung erforderlich.&#x20;

Nach dem Anmelden steht die FormIt-API unter SOFTWARE zur Verfügung.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Ein Zusatzmodul hat Zugriff auf die [FormIt-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) und die [FormIt Modeling Kernel C++-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Ein Zusatzmodul weist folgende Struktur auf:

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

Um die Argumente in C++-Variablen umzuwandeln, verwenden Sie SCRIPTCONVERTER-.

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

Es kann entweder JSON\_UNDEFINED oder ein beliebiges JSON-Objekt zurückgegeben werden. Verwenden Sie to\_json, um die C++-Variable in JSON zu konvertieren.

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

Sobald die DLL alle benötigten JS-APIs definiert, muss das Plugin FormIt mitteilen, welche DLLs geladen werden müssen. Dies erfolgt im [Manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) ist ein Praxisbeispiel, in dem die Erstellung eines Zusatzmoduls erläutert wird.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) ist ein Praxisbeispiel, in dem die Erstellung eines Zusatzmoduls mit der [FormIt Modeling Kernel C++-API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html) erläutert wird.
