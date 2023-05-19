# Configuration de FormIt pour le développement 

Pour tester et créer des plug-ins dans l’application de bureau FormIt, vous aurez besoin de FormIt pour Windows 17.0 ou version ultérieure.

### **Afficher l’éditeur de script et la sortie du script**

Dans le menu supérieur de FormIt, accédez à **Fenêtre** dans le menu supérieur et cochez les cases **Éditeur de scripts** et **Sortie de script**.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

Les panneaux Éditeur de scripts et Sortie de script s’affichent au bas de la fenêtre FormIt.

Basculez entre l’éditeur de script et la sortie de script à l’aide des boutons situés dans la partie inférieure.

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

Vous pouvez également organiser les deux panneaux côte à côte. Cliquez sur le bouton en regard du « x » dans le coin supérieur droit pour détacher l’un des panneaux, puis faites glisser et déposez les panneaux l’un à côté de l’autre :

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **Éditeur de scripts**

L’éditeur de scripts fournit un environnement de développement simple dans lequel vous pouvez écrire et tester du code.

L’éditeur de scripts stocke le code écrit dans un fichier scratch.js, dans le répertoire contenant le fichier FormIt.exe.

Deux boutons sont disponibles dans la partie supérieure :

**Exécuter** ![](<../../../.gitbook/assets/image (8) (1).png>) : exécute tout le code écrit dans la fenêtre.

**Exécuter la sélection** ![](<../../../.gitbook/assets/image (52).png>) : exécute uniquement les lignes de code sélectionnées/mises en surbrillance.

### **Sortie de script**

La fenêtre Sortie de script affiche tous les messages imprimés sur la console à partir de plug-ins.

Vous pouvez effacer la sortie en exécutant `console.clear();` dans l’éditeur de scripts.

## Utilisation des exemples de plug-ins

Après avoir [cloné un référentiel](cloning-a-sample-plugin.md) et [configuré un serveur Web](hosting-a-plugin-on-a-local-server.md), vous pouvez désormais afficher vos plug-ins locaux dans FormIt.

Vous pouvez charger ou installer n’importe quel plug-in, mais dans le cadre de cet exercice, vous allez installer à la fois un plug-in basé sur un groupe de fonctions et un plug-in basé sur une barre d’outils. Nous supposerons que votre serveur HTTP npm est exécuté sur le port 8080 hébergeant les deux exemples de référentiels.

### **Chargement vs. Installation**

`FormIt.LoadPlugin();` charge le plug-in uniquement pour la session en cours. Le plug-in sera déchargé automatiquement après fermeture et redémarrage de l’application.

C’est une excellente option pour activer temporairement un plug-in pour le test dans la session en cours uniquement.

`FormIt.InstallPlugin();` rend le plug-in persistant à l’aide d’une clé de registre. C’est idéal pour les plug-ins que vous utiliserez fréquemment d’une session à l’autre.

Sous Windows, les clés de registre suivantes sont utilisées pour conserver les plug-ins :

* Plug-ins : Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

Utilisez `FormIt.UninstallPlugin();` pour désinstaller le plug-in.

Dans les exemples suivants, sauf indication contraire, n’hésitez pas à utiliser _Installer_ ou _Charger_, selon que vous souhaitez rendre les résultats de l’exercice persistants ou non.

### **Exemple de plug-in de barre d’outils : Flip Along (Basculer le long)**

Dans l’éditeur de scripts, exécutez les opérations suivantes :

Si vous exécutez un serveur local :

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

Si le chargement est effectué à partir du [référentiel FormIt GitHub](https://github.com/FormIt3D/) (connexion Internet requise) :

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

La barre d’outils Flip Along (Basculer le long) doit s’afficher en haut de la fenêtre de l’application :

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **Exemple de plug-in de groupe de fonctions HTML : Properties Plus (Propriétés plus)**

Dans l’éditeur de scripts, exécutez les opérations suivantes :

Si vous exécutez un serveur local :

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

Si le chargement est effectué à partir du [référentiel FormIt GitHub](https://github.com/FormIt3D/) (connexion Internet requise) :

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

Le groupe de fonctions Properties Plus (Propriétés plus) doit s’afficher sur le côté droit de la fenêtre de l’application :

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **Exemple de plug-in de boîte de dialogue modale ou non modale**

Les plug-ins de boîte de dialogue sont uniques : ils peuvent uniquement être chargés, pas installés.

Dans l’éditeur de scripts, exécutez les opérations suivantes :

Si vous exécutez un serveur local :

* Modale : `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* Non modale : `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

Si le chargement est effectué à partir du [référentiel FormIt GitHub](https://github.com/FormIt3D/) (connexion Internet requise) :

* Modale : `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* Modale : `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

Le panneau Hello Block! de l’exemple de panneau HTML devrait s’afficher sur l’écran comme une boîte de dialogue modale ou non modale.
