# Utilisation des plug-ins

![](<../.gitbook/assets/g3 (1).gif>)

## Gestionnaire de plug-in

FormIt Plugin Manager est le lieu de référence pour la découverte et la gestion des plug-ins.

Plugin Manager est chargé automatiquement au démarrage de FormIt, à condition que FormIt ait accès à Internet.

Pour y accéder, cliquez sur l’icône de l’onglet ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) située à droite de l’application :

![](../.gitbook/assets/c1.PNG)

## Catégories de plug-ins

Plugin Manager organise les plug-ins en catégories pour vous aider à trouver ceux qui vous intéressent.

![](../.gitbook/assets/d16.png)

**Plug-ins installés :** plug-ins déjà installés par l’utilisateur.&#x20;

**Plug-ins recommandés :** plug-ins recommandés par l’équipe FormIt pour développer les fonctionnalités de base de FormIt et déverrouiller de nouveaux workflows. Les plug-ins développés par la communauté apparaissent ici après avoir été approuvés par l’équipe FormIt.\
Balise GitHub :  _formit-plugin-recommended_

**Plug-ins publics :** plug-ins créés par la communauté. Les plug-ins de cette catégorie n’ont pas été vérifiés ou approuvés par l’équipe FormIt. \
Balise GitHub :  _formit-plugin_

**Plug-ins pour les développeurs :** plug-ins créés par la communauté pour permettre la création d’autres plug-ins FormIt. \
Balise GitHub :  _formit-plugin-developers_

## Ajouter votre plug-in privé ou local

Si vous [développez votre propre plug-in](how-to-develop-plugins/), vous pouvez ajouter son URL privée dans le champ situé en bas et cliquer sur (+) :

![](../.gitbook/assets/d4.PNG)

Pour plus d’informations sur l’ajout de votre plug-in privé ou local, reportez-vous à la rubrique [Aperçu d’un plug-in dans Plugin Manager. ](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Réinitialisation de Plugin Manager

Plugin Manager utilise les clés de registre de Windows pour stocker les référentiels et les plug-ins installés. Si vous devez restaurer les paramètres par défaut de votre Plugin Manager, supprimez la clé de registre suivante :

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ Notez que cette action entraîne la désinstallation de tous les référentiels et plug-ins ajoutés par l’utilisateur, réinitialisant ainsi Plugin Manager afin d’inclure uniquement les référentiels et plug-ins intégrés.

## Installation des plug-ins

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager) comprend un certain nombre de plug-ins, organisés en différentes catégories. Chaque plug-in a un nom, une description, un lien GitHub et un bouton bascule Installer.&#x20;

![](../.gitbook/assets/d5.PNG)

Pour installer un plug-in, il suffit d’activer le bouton bascule situé à côté de son nom.&#x20;

![](../.gitbook/assets/d6.png)

L’icône du plug-in sélectionné s’affiche dans le panneau de droite. Cliquez dessus pour afficher l’interface utilisateur du plug-in.

![](../.gitbook/assets/d7.PNG)

## Utilisation des plug-ins

Chaque plug-in dispose d’une interface utilisateur unique définie par son développeur. Un plug-in contient généralement un ensemble d’instructions sur la façon de l’utiliser, un ensemble de paramètres (zones de texte, curseurs, cases à cocher, etc.) et un ou plusieurs boutons pour l’exécuter.

Par exemple, nous allons utiliser l’un des exemples les plus simples dans Plugin Manager : coins avec congé 2D. Nous allons d’abord charger le plug-in à partir de la section des recommandations de Plugin Manager. Puis, en suivant les instructions fournies par le développeur, nous définissons le rayon du congé, sélectionnons un groupe de faces à raccorder, puis cliquons sur le bouton des coins avec congé.

![](../.gitbook/assets/g4.gif)

##

