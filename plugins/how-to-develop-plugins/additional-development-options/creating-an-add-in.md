# Création d’un add-in

Un add-in est un plug-in qui charge également les DLL qui exposent les nouvelles API JavaScript.&#x20;



### Télécharger l’API FormIt

Pour créer des DLL prenant en charge FormIt, l’API FormIt est nécessaire. L’API FormIt peut être téléchargée sur le site [Autodesk Developers Network](https://www.autodesk.com/developer-network/overview). Une connexion est nécessaire pour accéder au téléchargement.&#x20;

Une fois que vous êtes connecté, l’API FormIt est disponible sous LOGICIEL.

&#x20;

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIDownload.jpg)

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FormItAPIMenuItem.jpg)

Un add-in a accès à l’[API FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/index.html) et à l’[API FormIt Modeling Kernel C++ ](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).

Un add-in a la structure suivante :

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

Pour obtenir les arguments dans les variables C++, utilisez SCRIPTCONVERTER-

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

JSON\_UNDEFINED ou tout autre objet JSON peut être renvoyé. Utiliser to\_json pour convertir votre variable C++ en JSON

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

Une fois que la DLL définit toutes les API JS nécessaires, le plug-in doit indiquer à FormIt les DLL à charger. Cette opération est effectuée dans le fichier [manifest](https://github.com/FormIt3D/HelloAddIn/blob/main/v22\_0/manifest.json#L8).

```
        "DLLs" : ["PLUGINLOCATION/MyClass.dll", "PLUGINLOCATION/HelloDLL.dll"]

```

[HelloAddIn](https://github.com/FormIt3D/HelloAddIn) est un exemple qui explique comment créer un add-in.

[HelloWSMAddIn](https://github.com/FormIt3D/HelloWSMAddIn) est un exemple qui explique comment créer un add-in avec l’[API FormIt Modeling Kernel C++](https://formit3d.github.io/FormItExamplePlugins/docs/FormItCPPAPI/group\_\_mod\_\_wsm\_\_api\_\_ref.html).
