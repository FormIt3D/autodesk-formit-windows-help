# Configuration générale de plug-in dans le fichier manifest

Les plug-ins FormIt sont constitués d’un composant principal clé appelé fichier _manifest.json_.&#x20;

Le fichier manifest est un [objet JSON](https://www.json.org/json-fr.html) qui indique à l’infrastructure FormIt les fichiers à récupérer et le type de plug-in à créer.

### Propriétés et structure de manifest.json

Un fichier manifest.json présente la structure suivante. Il possède des propriétés supplémentaires selon qu’il s’agit d’un [plug-in basé sur une barre d’outils](../additional-development-options/creating-a-toolbar-based-plugin.md) ou d’un [plug-in basé sur un groupe de fonctions HTML](../additional-development-options/creating-an-html-panel-plugin.md).

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

Un plug-in typique inclut les propriétés JSON suivantes :

* « PluginName »·représente le nom du plug-in à des fins internes et la plupart des fins d’affichage, y compris pour [Plugin Manager.](../../how-to-use-plug-ins.md#plugin-manager)
* « PluginType » représente le type de plug-in, ce qui permet aux utilisateurs de savoir dans la description de [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) ce qu’ils doivent rechercher lorsqu’ils installent le plug-in.
* « PluginDescription » est affiché dans [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) pour communiquer les fonctionnalités du plug-in.
* « Scripts » répertorie les scripts externes requis associés au plug-in qui seront chargés dans l’application FormIt et peuvent être exécutés lorsque la fonctionnalité de plug-in est appelée.

![](<../../../.gitbook/assets/image (5).png>)

Démarrez le développement de votre plug-in en créant un fichier manifest.json dans votre dossier de plug-in. Vous devez ensuite décider si vous créez un plug-in basé sur une barre d’outils ou un groupe de fonctions.

![](<../../../.gitbook/assets/image (36).png>)

**Remarque :** l’utilisation de PLUGINLOCATION dans le fichier manifest.json ci-dessus est essentielle et sensible à la casse. FormIt remplacera PLUGINLOCATION par l’emplacement du serveur pour le plug-in.
