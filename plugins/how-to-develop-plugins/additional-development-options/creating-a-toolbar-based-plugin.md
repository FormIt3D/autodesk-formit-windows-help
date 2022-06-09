# Création d’un plug-in basé sur une barre d’outils

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### Structure d’un fichier manifest.json de plug-in basé sur une barre d’outils

Un plug-in basé sur une barre d’outils possède un fichier _manifest.json_ avec la structure suivante :

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

Outre les [propriétés JSON standard](../advanced-development/general-plugin-setup-in-the-manifest.md), un plug-in basé sur une barre d’outils inclut cette propriété JSON spéciale :

* « ToolbarURL » indique à FormIt que ce plug-in est une barre d’outils et qu’il est lié à l’emplacement d’un autre fichier JSON qui décrit la fonctionnalité de la barre d’outils.

### Configurer le format de la barre d’outils avec JSON

Après avoir créé un fichier manifest comme celui décrit ci-dessus, vous devez créer le fichier toolbar.json, qui définit les boutons de la barre d’outils, leurs noms, leur texte, les icônes et la fonction onClick affectés à chaque bouton. Le fichier JSON de la barre d’outils aura le format suivant :

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

Le fichier toolbar.json contient les propriétés JSON suivantes :

* « name » représente le nom de la barre d’outils globale et est utilisé en interne pour associer tous les boutons au menu de la barre d’outils unique.
* « buttons » représente les boutons individuels ajoutés à l’intérieur de la barre d’outils. Une barre d’outils peut comporter un nombre quelconque de boutons.
* « name » définit le nom interne du bouton, qui est utilisé pour associer le bouton à la barre d’outils, ainsi qu’à la fonction onClick du bouton.
* « command » définit la fonction du bouton, qui peut prendre l’une des deux formes suivantes : une fonction JavaScript (qui peut être définie dans un script contenu dans le champ « Scripts » du fichier manifest.json) ou une commande FormIt (par exemple, « Dessiner : Cercle »). Vous pouvez obtenir une liste des commandes FormIt en exécutant le plug-in Messages.
* « iconText » définit le texte de l’info-bulle et de la description dans le bouton. Si aucune URL d’icône n’est fournie, le texte crée une icône de texte formaté générée automatiquement.
* « iconURL » peut être configuré pour définir une icône personnalisée pour le bouton.

Une fois que tous les boutons ont été définis dans le fichier toolbar.json, le plug-in est prêt à l’emploi.&#x20;

Si vous souhaitez définir d’autres fonctions JavaScript, ajoutez-les au même dossier que le fichier manifest.json. Veillez à ajouter la référence de fichier au champ « Scripts » du fichier manifest afin que FormIt puisse trouver les fichiers.
