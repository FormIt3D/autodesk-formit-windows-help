# Vytvoření doplňku

Doplněk je modul plug-in, který také načítá knihovny DLL, zpřístupňující nová rozhraní API jazyka JavaScript.&#x20;



### Stáhnutí rozhraní FormIt API

K vytvoření knihoven DLL, které podporují aplikaci FormIt, je nutné rozhraní FormIt API. Rozhraní FormIt API lze stáhnout z webu [Autodesk Developer Network](https://www.autodesk.com/developer-network/overview). Ke stažení je nutné přihlášení.&#x20;

Po přihlášení je rozhraní FormIt API dostupné v části SOFTWARE.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Doplněk má přístup k rozhraní [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) a [FormIt Modeling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Doplněk má následující strukturu:

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

K načtení argumentů do proměnných C++ použijte příkaz SCRIPTCONVERTER-

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

Vrátit lze buď JSON\_UNDEFINED, nebo libovolný objekt JSON. Pomocí funkce to\_json převeďte proměnnou C++ na json.

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

Jakmile knihovna DLL definuje všechna potřebná rozhraní API JS, musí modul plug-in aplikaci FormIt sdělit, které knihovny DLL je třeba načíst. To se provádí v souboru [manifestu](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) je funkční příklad, který vysvětluje, jak vytvořit doplněk.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) je funkční příklad, který vysvětluje, jak vytvořit doplněk pomocí rozhraní [FormIt Modelling Kernel C++ API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
