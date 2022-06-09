# Création d’un plug-in de groupe de fonctions HTML

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

Un plug-in basé sur un groupe de fonctions qui affiche une page HTML contient un fichier _manifest.json_ avec la structure suivante :

```
{
    "PluginName": "Hello Block!",
    "PluginType": "Panel",
    "PluginDescription": "Creates a panel with an HTML form that allows dimensional input for a 3D block which will get generated at the world origin.",
    "Scripts": [
        "PLUGINLOCATION/block.js"
    ],
    "Panel": "PLUGINLOCATION/hello_block.html",
    "PanelIcon": "PLUGINLOCATION/hello_block.png"
}               
```

Outre les [propriétés JSON standard](../advanced-development/general-plugin-setup-in-the-manifest.md), un plug-in basé sur un groupe de fonctions inclut les propriétés JSON spéciales suivantes :

* « Panel » indique à FormIt que ce plug-in est un groupe de fonctions et qu’il est lié à l’emplacement du fichier HTML qui doit être chargé dans le groupe de fonctions.
* L’en-tête du fichier HTML doit contenir des liens vers les fichiers JavaScript appropriés et vers un fichier CSS pour les styles.
* Le fichier HTML sera rendu dans le groupe de fonctions FormIt comme dans un navigateur.
* Vous pouvez voir des exemples d’interfaces HTML enrichies dans notre [organisation FormIt3D](https://github.com/FormIt3D/).
* « PanelIcon » définit une icône pour que ce plug-in apparaisse dans l’onglet sur le côté droit de l’application. Si non défini, FormIt crée une icône automatique en utilisant les initiales du nom du plug-in.

Une fois vos fichiers HTML, CSS et JavaScript configurés, vous pouvez commencer à tester votre plug-in de groupe de fonctions HTML [en le chargeant ou en l’installant](../advanced-development/setting-up-formit-for-development.md#load-vs.-install).
