# Débogage

Le débogage d’un plug-in FormIt nécessite différentes procédures selon le moteur que vous déboguez. (Pour plus d’informations sur les moteurs, consultez la [section précédente](client-side-vs-web-side-engines.md).)

### **Débogage côté client (FormIt)**

Pour déboguer du code FormIt, qui s’applique aux plug-ins basés sur les barres d’outils et les groupes de fonctions, vous pouvez ajouter une ligne dans le code pour faire apparaître le débogueur JS intégré de l’application de bureau :

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Débogage côté Web (HTML)**

Les plug-ins FormIt basés sur des groupes de fonctions permettent un débogage HTML de l’interface utilisateur, car les groupes de fonctions sont essentiellement des sites Web HTML avec des styles et des scripts.

Pour déboguer du code HTML pour les plug-ins intégrés à un groupe de fonctions, y compris les scripts et les styles :

* **FormIt pour Windows 2021.1 et versions ultérieures**
   * Cliquez avec le bouton droit de la souris sur la page HTML du plug-in et cliquez sur Déboguer pour afficher le débogueur HTML intégré de l’application.

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt pour le Web**
   * Utilisez le raccourci F12 ou Ctrl + Maj + I pour afficher le débogueur HTML du navigateur.

![](../../../.gitbook/assets/debugonweb.gif)

