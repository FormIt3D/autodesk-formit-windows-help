# Conditions préalables et installation

## Téléchargement et installation

* Téléchargez la dernière version de [FormIt pour Windows](https://formit.autodesk.com/page/download).
* Connectez-vous à votre compte Autodesk ou [créez un compte Autodesk gratuit ici](https://accounts.autodesk.com).
* Le complément FormIt pour Revit est inclus dans Revit 2017 et les versions ultérieures. Vous pouvez également télécharger et installer manuellement le complément [à partir de notre site Web](https://formit.autodesk.com/page/formit-revit).

Les paramètres au niveau de l’application pour FormIt se trouvent à l’emplacement suivant : Computer\\HKEY_CURRENT_USER\\SOFTWARE\\Autodesk\\FormIt 360\\

## Configuration système recommandée

| Configuration requise                    | Détails                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Système d’exploitation**           | <p>Microsoft® Windows® 8, 8.1, 10 ou 11.</p><p><em>Remarque : Parallels Desktop n’est pas officiellement pris en charge en raison de problèmes de performances et de graphismes au niveau des pilotes OpenGL.</em></p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| **UC**                        | <p>Processeur Intel® Pentium®, Xeon® ou i-Series ou équivalent AMD® doté de la technologie SSE2.</p><p>Fréquence la plus élevée possible.</p>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Mémoire**                     | 4 Go de RAM minimum, 8 Go ou plus recommandés.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| **Carte vidéo (GPU)**           | <p>Une carte vidéo NVIDIA ou AMD distincte prenant en charge OpenGL 3.3 est requise. La prise en charge d’OpenGL 4.2 est vivement recommandée.</p><p>Pour les systèmes dotés de cartes vidéo commutables, suivez les instructions du fabricant pour vous assurer que FormIt utilise toujours le processeur graphique dédié afin de profiter de performances optimales. Reportez-vous aux instructions relatives à <a href="https://www.amd.com/en/support/kb/faq/dh-017">AMD</a> et <a href="http://nvidia.custhelp.com/app/answers/detail/a_id/2615/kw/manage%203d%20settings/related/1">NVIDIA</a>.</p><p>Pour des performances et une fiabilité optimales, vérifiez que les pilotes de votre carte vidéo sont à jour à partir du site Web du fabricant ou de Windows Update.</p><p>FormIt affiche un message au démarrage s’il ne parvient pas à utiliser votre carte vidéo en raison de pilotes obsolètes ou d’autres problèmes. Si FormIt ne démarre pas après la mise à jour des pilotes, <a href="https://forums.autodesk.com/t5/formit-forum/bd-p/142">contactez-nous sur les forums</a>.</p> |
| **Espace disque**                 | 1 Go d’espace disque disponible.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| **Connectivité et licences** | <p>Une connexion Internet est requise lors du premier lancement de FormIt, afin de vous connecter à votre compte Autodesk.</p><p>Une connexion Internet est également nécessaire pour charger les plug-ins lors du lancement de FormIt. Si aucune connexion Internet n’est détectée au démarrage, l’application se lance sans plug-ins.</p><p>Un compte Autodesk avec abonnement au cloud FormIt Pro est requis pour exécuter FormIt Pro sous Windows. FormIt Pro est disponible dans le cadre de la collection <a href="https://www.autodesk.com/collections/architecture-engineering-construction/overview"><strong>Autodesk AEC Collection</strong></a>.</p>                                                                                                                                                                                                                                                                                                   |

## Accès hors connexion

Lorsque vous exécutez FormIt pour Windows, vous devez être connecté à Internet pour valider votre licence. Après la première connexion, vous pouvez utiliser l’application hors ligne pendant 30 jours. Ensuite, vous devrez vous connecter pour revalider votre licence.

Lorsque vous utilisez FormIt pour Windows hors ligne, certaines fonctionnalités sont limitées :

* L’outil Définir l’emplacement ne fonctionnera pas, car il nécessite une connexion Internet pour récupérer les données satellite et de terrain à partir de Bing Maps.
  * Toutefois, tout satellite et terrain existant déjà dans le modèle depuis une session en ligne précédente sera conservé.
* Aucun plug-in, y compris Plugin Manager, ne se charge, car le dernier code de GitHub est obtenu à chaque lancement d’application.
  * Solution : si vous chargez tous vos plug-ins en ligne et que vous maintenez la session FormIt en cours lorsque vous passez en mode hors ligne, les plug-ins précédemment chargés resteront et fonctionneront normalement.
* Les exemples de matériaux ne sont pas chargés, car ils proviennent d’un serveur hébergé dans le cloud.
  * Solution : accédez aux dossiers des exemples de catégories de matériaux lorsque vous êtes connecté à Internet. Les dossiers sont téléchargés et stockés sur votre ordinateur et accessibles ultérieurement en mode hors ligne.
* Vous ne pourrez pas enregistrer dans Autodesk Docs ni ouvrir à partir de cet outil, y compris à partir de la bibliothèque de contenu.

## Paramètres PPP Windows recommandés

FormIt pour Windows fonctionne mieux lorsque l’écran d’affichage est défini sur une échelle PPP inférieure ou égale à 125 % dans Windows.

Pour modifier ce paramètre dans Windows 10, procédez comme suit :

* Recherchez « Affichage » dans le menu Démarrer, puis choisissez « Modifier les paramètres d’affichage ».
* Sélectionnez le rectangle représentant l’écran que vous allez utiliser avec FormIt.
* Sous la section « Échelle et présentation » ouvrez la liste déroulante « Taille du texte, des applications et des autres éléments » et sélectionnez une valeur inférieure ou égale à 125 %.

## Dépannage

### Erreur système Windows 10 Pro N

Si vous exécutez FormIt sous Windows 10 Pro N version 1909 ou ultérieure, le message d’erreur suivant peut s’afficher :

\![FormIt.exe System Error on Windows 10](<../.gitbook/assets/windows 10 error message.png>)

Cela est dû à un problème connu avec certaines versions de Windows 10 Pro N. Pour éviter cette erreur, téléchargez le Feature Pack multimédia pour votre version de Windows 10 à l’adresse suivante : [Liste de Feature Packs multimédias pour les éditions de Windows N](https://support.microsoft.com/en-us/topic/media-feature-pack-list-for-windows-n-editions-c1c6fffa-d052-8338-7a79-a4bb980a700a).

### Impossible de se connecter

Lorsque vous tentez de vous connecter à votre compte dans FormIt, la boîte de dialogue de connexion risque de se bloquer, ce qui vous empêche de continuer. Dans ce cas, vous devrez peut-être débloquer *.autodesk.com dans votre pare-feu réseau. Contactez votre service informatique pour obtenir de l’aide.
