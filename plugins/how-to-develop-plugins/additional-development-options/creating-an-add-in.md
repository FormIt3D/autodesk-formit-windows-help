# Creazione di un modulo aggiuntivo

Un modulo aggiuntivo è un plug-in che carica anche le DLL che espongono nuove API JavaScript.&#x20;



### Download dell'API di FormIt

Per creare DLL che supportino FormIt, è necessaria l'API di FormIt. L'API di FormIt può essere scaricata da [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview). Per accedere al download, è necessario eseguire l'accesso.&#x20;

Una volta eseguito l'accesso, l'API di FormIt è disponibile in SOFTWARE.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Un modulo aggiuntivo dispone dell'accesso all'[API di FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) e all'[API C++ del kernel di modellazione di FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Un modulo aggiuntivo presenta la seguente struttura:

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

Per ottenere gli argomenti nelle variabili C++, utilizzare SCRIPTCONVERTER.

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

Può essere restituito JSON\_UNDEFINED o qualsiasi oggetto JSON. Utilizzare to\_json per convertire la variabile C++ in JSON.

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

Una volta definite tutte le API JS necessarie tramite la DLL, il plug-in deve indicare a FormIt quali DLL devono essere caricate. Questa operazione viene eseguita nel file [manifesto]( https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) è un esempio pratico che spiega come creare un modulo aggiuntivo.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) è un esempio pratico che spiega come creare un modulo aggiuntivo con l'[API C++ del kernel di modellazione di FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
