# Hébergement d’un plug-in sur un serveur local

Pour pouvoir afficher l’aperçu d’un plug-in cloné dans FormIt, vous devez l’héberger sur un serveur local.

### **Afficher le terminal dans l’IDE**

Vous avez la possibilité de démarrer le serveur dans Visual Studio Code, au lieu d’une fenêtre de terminal distincte. \*\*\*\* Avant d’ouvrir un terminal, assurez-vous que le dossier approprié est ouvert dans Visual Studio Code.

Vue > Terminal (ou raccourci Ctrl + \`)

![](<../../../.gitbook/assets/image (11).png>)

### Configurer un serveur HTTP

Un serveur HTTP qui fonctionne bien est le serveur [http-server](https://www.npmjs.com/package/http-server) de npm.

Tout d’abord, vous devez télécharger et installer [NodeJS](https://nodejs.org/fr/), si ce n’est pas déjà fait.

Si des erreurs se produisent au cours des étapes suivantes, essayez de redémarrer votre ordinateur pour terminer l’installation de NodeJS.

Dans l’invite de commande, entrez la commande suivante pour installer globalement le serveur _http-server_ de npm (configuration unique).

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### Démarrer le serveur local

Une fois l’installation terminée, exécutez la commande suivante dans le terminal pour démarrer votre serveur http-server npm :

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

Conseil 1 : en cas de problème d’exécution du serveur http-server (installé globalement ou localement), il peut être utile de l’exécuter directement via npx :

* `npx http-server`

Conseil 2 : pour les utilisateurs de Windows 10/11, si vous rencontrez une erreur lors de l’exécution d’un script sur votre nouvel ordinateur, cela peut être dû à la désactivation des paramètres. Pour remédier à ce problème :

* Lancez le script PowerShell en tant qu’administrateur
* Entrez : `Set-ExecutionPolicy RemoteSigned`

### Développer pour FormIt Web

Pour développer pour FormIt Web, exécutez simplement la commande suivante :

* `http-server --cors`

![](<../../../.gitbook/assets/image (10).png>)

### Vérifier votre serveur

Vous pouvez vérifier votre serveur en accédant à l’adresse suivante dans votre navigateur Web :

* http://localhost:8080

Vous devriez voir les fichiers du dossier de projet dans la fenêtre du navigateur.

\*\*Si vous utilisez un serveur Web différent de npm, l’adresse/le port par défaut peut être différent.

![](<../../../.gitbook/assets/image (41).png>)
