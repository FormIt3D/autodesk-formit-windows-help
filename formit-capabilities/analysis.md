---
description: >-
  Pour commencer un workflow BIM, évaluez les performances des éléments dès le début du processus de conception.
---

# Analyse d’ensoleillement et d’énergie

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## Analyse d’énergie dans FormIt

Analysez votre modèle de bâtiment pour mesurer son efficacité énergétique en amont du processus de conception.

[Afficher vos projets Insight](https://gbs.autodesk.com/OneEnergy/Insight)

## Analyse d’énergie avec Insight

Avec un abonnement **FormIt Pro** via la collection [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), vous avez accès à l’analyse d’énergie avec **Insight :**

* Analysez les modèles de conception dès les premières étapes avec le moteur d’analyse de Green Building Studio.
* Connectez-vous à une vue de tableau de bord des résultats de l’analyse pour comparer les options de votre conception.
* Ajustez les widgets de facteur d’analyse d’énergie, tels que le rapport fenêtre-mur, l’orientation du bâtiment, etc.
* Résumez l’impact énergétique de votre bâtiment avec un seul chiffre calculé comme coût par surface.
* Enregistrez les résultats de l’analyse d’énergie pour les consulter ultérieurement avec les clients et les autres parties prenantes.

## Nouveautés de FormIt et Insight<a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Améliorations apportées à la fiabilité d’Insight** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) recherche désormais les problèmes de modèle courants dans votre modèle avant le lancement d’Insight et corrige les erreurs courantes d’Insight pour une expérience plus fiable.
* FormIt 2021 améliore également la fiabilité de la connexion FormIt et Insight, en corrigeant de nombreux problèmes connus et en améliorant les taux de réussite des exécutions.

## Mise en route <a href="#insight-getting-started" id="insight-getting-started"></a>

### **Comment ça marche ?** <a href="#how-it-works" id="how-it-works"></a>

* L’analyse d’énergie d’Insight télécharge les données de votre modèle FormIt et exécute plusieurs centaines d’analyses dans le cloud pour déterminer les différents scores énergétiques
* L’analyse d’énergie utilise Revit pour analyser votre modèle. De la même manière que lors de l’envoi de données FormIt vers Revit, vous devez [vous assurer que votre modèle FormIt est étanche et multiple](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **Préparation du modèle FormIt** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight utilisera toute géométrie visible dans votre esquisse FormIt
  * Assurez-vous que l’enveloppe du bâtiment que vous souhaitez analyser est la seule géométrie visible
  * Placez la géométrie de support (éléments d’environnement, de mobilier et de site, par exemple) sur un [calque](../tool-library/layers.md) distinct et désactivez le calque
* Insight fonctionne mieux avec un modèle de bâtiment simple et solide
  * Assurez-vous que le volume du bâtiment est [solide et étanche](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * Si votre conception de bâtiment comporte déjà des ouvertures pour les fenêtres et les portes, il est préférable de créer un volume sans ouvertures spécifiquement pour l’analyse d’énergie et de masquer la version plus détaillée à l’aide des calques
* Le volume du bâtiment simple doit être associé à l’option [Niveaux](../tool-library/levels-and-area.md)
* Le modèle FormIt doit disposer d’un [emplacement](../tool-library/setting-location.md) défini

![](../.gitbook/assets/insight.png)

### **Démarrage de l’analyse d’énergie** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* Recherchez le bouton Analyse d’énergie dans la barre d’outils

![](../.gitbook/assets/generate\_insight.png)

* Cliquez sur « Générer l’analyse » pour lancer le processus
* Les données de modèle visibles sont chargées, et plusieurs centaines de simulations sont exécutées dans le cloud
* Une fois l’opération terminée, un message s’affiche en haut de l’écran, et le menu est mis à jour pour indiquer qu’une nouvelle vue Insight est prête à être affichée
  * Cliquez sur « Afficher l’analyse » pour afficher l’analyse dans votre navigateur Web
  * Vous pouvez également trouver toutes vos informations sur [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight).

## Dépannage <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **Erreurs courantes** <a href="#common-errors" id="common-errors"></a>

* « Impossible de créer le projet Insight. Veuillez réessayer ultérieurement. »
  * Connectez-vous au [tableau de bord Green Building Studio](https://gbs.autodesk.com/GBS/Project), puis redémarrez FormIt
    * Si vous ne parvenez pas à vous connecter ou si la page « Accès refusé » s’affiche, vous devrez peut-être [souscrire un abonnement à Green Building Studio](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
  * Vérifiez que votre modèle est [solide et étanche](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * Recherchez d’éventuels problèmes rencontrés avec les services FormIt dans le [tableau de bord sur l’état général d’Autodesk](https://health.autodesk.com/)
* Pour savoir si l’analyse d’énergie de Green Building Studio s’exécute correctement pour ce projet, consultez le [tableau de bord Green Building Studio](https://gbs.autodesk.com/GBS/Project)
  * La dernière version du projet doit apparaître en haut de la liste et afficher 248 exécutions
  * Si aucune exécution ne s’affiche, [faites-le nous savoir sur les forums FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142) pour que nous vous aidions à résoudre le problème

### **Journaux détaillés** <a href="#detailed-logs" id="detailed-logs"></a>

* Pour accéder aux détails supplémentaires fournis par FormIt Web en cas d’échec de l’analyse d’énergie, effectuez les étapes suivantes :
  * Accéder à [FormIt Web](https://formit.autodesk.com/app)
  * Ouvrez le modèle qui rencontre des problèmes avec l’analyse d’énergie
  * Exécutez Analyse d’énergie
  * Ouvrez les outils de développement (appuyez sur la touche F12 dans Google Chrome ou Firefox)
  * Observez l’onglet Console
  * Copiez ou effectuez une capture d’écran des erreurs, et [signalez-les sur les forums FormIt](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## Analyse d’ensoleillement

Avec un abonnement **FormIt Pro** via la collection [AEC Collection](https://www.autodesk.com/collections/architecture-engineering-construction/overview), vous pouvez visualiser l’impact du soleil sur votre bâtiment :

* Spécifiez les faces pertinentes à analyser pour l’impact solaire.
* Visualisez les résultats en quelques secondes dans la zone de dessin de l’application.
* Placez le curseur de la souris sur un point d’entrée pour afficher les valeurs calculées spécifiques de l’impact solaire.
* Choisissez d’afficher les résultats sous forme d’étude de vitrage mensuelle ou d’étude de faisabilité annuelle du panneau solaire.

En savoir plus sur l’[analyse d’ensoleillement](../tool-library/solar-analysis.md) dans FormIt Pro.
