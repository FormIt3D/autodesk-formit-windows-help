# Test d’un plug-in combiné de barre d’outils et de groupe de fonctions HTML

Vous pouvez tester facilement vos plug-ins en cours d’utilisation à l’aide de l’[éditeur de scripts](../advanced-development/setting-up-formit-for-development.md) intégré à FormIt pour Windows.

Nous vous recommandons d’utiliser `FormIt.LoadPlugin("URL");` lors des tests, afin de charger les plug-ins temporairement pour cette session (ils disparaîtront au redémarrage de FormIt).&#x20;

Une fois le test terminé, vous pouvez conserver le plug-in entre les sessions à l’aide de `FormIt.InstallPlugin("URL");`.

**FormIt pour Windows 17 et versions ultérieures**

****

### **Plug-ins de barre d’outils**

Chargez votre plug-in dans FormIt pour afficher la dernière interface utilisateur et tester les dernières fonctionnalités :

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Effectuez quelques modifications, puis chargez à nouveau le plug-in à l’aide de la commande ci-dessus.

Vous pouvez charger plusieurs instances du même plug-in dans la session en cours pour le test, chacune avec sa propre interface utilisateur.

Veillez à utiliser la dernière instance de l’interface utilisateur pour vous assurer que vous testez vos dernières modifications.



### **Plug-ins de groupe de fonctions HTML**

Chargez votre plug-in dans FormIt pour afficher la dernière interface utilisateur et tester les dernières fonctionnalités :

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

Effectuez quelques modifications, puis cliquez avec le bouton droit de la souris sur le groupe de fonctions et choisissez Rechargement matériel pour recharger le groupe de fonctions avec les derniers scripts et codes HTML/CSS.

****

### **Aperçu du plug-in à l’aide de Plugin Manager**

Une fois le plug-in chargé, reportez-vous à un [chapitre précédent](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md) de ce guide.

****

### **Forcer l’effacement du cache Web pour les fichiers JSON**

Si vous modifiez le titre ou la description dans le fichier manifest.json d’un plug-in ou d’un référentiel, vous devrez peut-être forcer l’effacement du cache dans FormIt pour Windows afin que ces modifications deviennent effectives la prochaine fois que vous rechargerez Plugin Manager.

FormIt pour Windows stocke son cache Web ici. Vous devez activer les éléments masqués dans l’Explorateur Windows pour afficher le dossier AppData.

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Pour supprimer le cache Web, supprimez simplement le dossier « Default » ci-dessus, puis rechargez Plugin Manager pour voir les titres et descriptions mis à jour.
