# Criar um complemento

Um complemento é um plug-in que também carrega DLLs que expõem novas APIs de JavaScript.&#x20;



### Fazer download da API do FormIt

Para criar DLLs que suportam o FormIt, a API do FormIt é necessária. É possível fazer o download da API do FormIt na [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview). É necessário um login para acessar o download.&#x20;

Depois de conectado, a API do FormIt está disponível em SOFTWARE.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Um complemento tem acesso à [API do FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) e à [API C++ do kernel de modelagem do FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Um complemento tem a seguinte estrutura:

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

Para colocar os argumentos em variáveis C++, use SCRIPTCONVERTER-

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

JSON\_UNDEFINED ou qualquer objeto json pode ser retornado. Use to\_json para converter a variável C++ em json

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

Depois que a DLL está definindo todas as APIs JS necessárias, o plug-in deve informar ao FormIt quais DLLs precisam ser carregadas. Isso é feito no [manifesto](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) é um exemplo de trabalho que explica como criar um complemento.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) é um exemplo de trabalho que explica como criar um complemento com a [API C++ do kernel de modelagem do FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
