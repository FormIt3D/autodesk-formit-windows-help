# Creación de un complemento

Un complemento es un módulo de extensión que también carga archivos DLL que muestran nuevas API de JavaScript.&#x20;



### Descargar la API de FormIt

Para generar archivos DLL que admitan FormIt, se necesita la API de FormIt. La API de FormIt se puede descargar desde [Autodesk Developer Network](https://www.autodesk.com/developer-network/overview). Es necesario iniciar sesión para acceder a la descarga.&#x20;

Una vez que haya iniciado sesión, la API de FormIt está disponible en SOFTWARE.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Un complemento tiene acceso a la [API de FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) y la [API de C++ de núcleo de modelado de FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Un complemento presenta la siguiente estructura:

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

Para obtener los argumentos en las variables de C++, utilice SCRIPTCONVERTER, como se muestra a continuación:

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

Puede devolverse JSON\_UNDEFINED o cualquier objeto json. Utilice to\_json para convertir la variable C++ en json.

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

Una vez que el archivo DLL defina todas las API de JS necesarias, el módulo de extensión debe indicar a FormIt los archivos DLL que deben cargarse. Esta acción se realiza en el archivo [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) es un ejemplo práctico que explica cómo crear un complemento.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) es un ejemplo práctico que explica cómo crear un complemento con la [API de C++ de núcleo de modelado de FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
