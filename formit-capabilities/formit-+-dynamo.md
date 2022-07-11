---
description: Computational Design in FormIt
---

# FormIt et Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt pour Windows intègre Dynamo pour des workflows de conception informatique incroyables.

## Nouveautés de FormIt et Dynamo

### **Graphiques de données, envoi de niveaux vers Excel et contrôle de facettage**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) permet d’exécuter des graphiques Dynamo [ sans nœud SendToFormIt](formit-+-dynamo.md#graph-types), ajoute la possibilité d’[envoyer des niveaux FormIt vers Excel](formit-+-dynamo.md#send-formit-levels-to-excel) et ajoute le contrôle de [facettage de courbe et de surface via les nouveaux nœuds FormItGroupOptions](../tool-library/curve-+-surface-faceting.md).

### **Saisie des cotes et accès anticipé à l’API JS**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) permet d’utiliser les [cotes FormIt connues comme entrées](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes), présente les [options au niveau de l’objet](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes) et offre un aperçu de l’[accès à l’API JavaScript](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes). Pour télécharger cette version, [cliquez ici](https://formit.autodesk.com/page/download).

### **Plusieurs nœuds SendToFormIt**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) permet d’utiliser [plusieurs nœuds SendToFormIt et graphiques Dynamo imbriqués](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

### **Nœud SelectFromFormIt**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) ajoute le nœud [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) et permet d’ouvrir des sessions toujours connectées, de modifier plusieurs instances, etc.

## Mise en route

Découvrez l’interface et liez vos répertoires Dynamo à FormIt.

### **Configuration initiale**

Vous utilisez FormIt et Dynamo pour la première fois ? Vous devrez peut-être d’abord [configurer votre système](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes), afin d’afficher la zone de dessin 3D dans Dynamo.

### **Groupe de fonctions Dynamo**

Utilisez le groupe de fonctions Dynamo pour lancer Dynamo, placer des groupes Dynamo et modifier des graphiques Dynamo :

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **Ajout et gestion de répertoires Dynamo locaux**

* Le groupe de fonctions Dynamo fonctionne de la même manière que la [bibliothèque de contenu](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library), ce qui vous permet de lier et de gérer des répertoires locaux contenant des fichiers Dynamo.
* Cliquez sur le bouton « Associer un répertoire » dans le groupe de fonctions Dynamo, puis cliquez de nouveau sur (+) dans la boîte de dialogue Préférences pour sélectionner un répertoire à lier à FormIt : <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* Basculez entre les répertoires liés à l’aide de la liste déroulante :

![](../.gitbook/assets/dynamo\_dropdown.png)

* Vous pourrez uniquement afficher les fichiers et sous-dossiers .dyn via le groupe de fonctions Dynamo.
* Utilisez la barre de filtre pour filtrer les fichiers et sous-dossiers Dynamo afin de trouver facilement ce dont vous avez besoin :

![](../.gitbook/assets/dynamo\_filter.png)

## Différentes façons d’utiliser Dynamo

Créez et modifiez des graphiques dans Dynamo ou ajustez les paramètres dans FormIt sans jamais voir le graphique. Ou faites les deux à la fois !

### **Types de graphiques**

FormIt prend en charge trois types de graphiques Dynamo :

* Graphique de données : les graphiques de données n’ont pas de nœud _SendToFormIt_ et sont utilisés pour faire apparaître des données ou les transmettre via FormIt. Par exemple, vous pouvez utiliser des graphiques de données pour envoyer des données vers Excel ou calculer des données non géométriques et les afficher dans un nœud Watch.
* Graphique de géométrie : ces graphiques produisent immédiatement une géométrie et doivent être placés dans la zone de dessin pour voir leurs paramètres. Après avoir cliqué sur la miniature, la géométrie s’affiche sur le curseur pour être placée dans la scène 3D. Ce graphique requiert la présence et la réception d’au moins un nœud _SendToFormIt_ à la fin du graphique.
* Graphique de sélection : ces graphiques requièrent des sélections FormIt avant l’exécution. Une invite s’affiche dans le coin supérieur gauche de FormIt pour indiquer les éléments à sélectionner. Une fois la sélection indiquée, le graphique s’exécute et génère la géométrie en fonction de celle-ci. Ce graphique requiert la présence et la réception d’au moins un nœud _SendToFormIt_ à la fin du graphique.

![](../.gitbook/assets/dynamo-graph-types.png)

### **Graphique de géométrie : placer un groupe Dynamo dans FormIt**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* Dans le groupe de fonctions Dynamo, cliquez sur la miniature du graphique Dynamo que vous souhaitez exécuter.
   * Vous pouvez utiliser les exemples intégrés ou [lier une bibliothèque](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) de vos propres fichiers Dynamo.
* Lorsque vous placez la géométrie dans FormIt, une copie du graphique Dynamo est incorporée dans le fichier FormIt.
   * Pour générer une géométrie, un nœud [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) doit être associé aux nœuds de géométrie de sortie dans le graphique.
* La géométrie du nœud SendToFormIt sera disponible sur le curseur pour le placement.
   * Lorsque le graphique comporte des nœuds [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) marqués comme entrés, FormIt demande d’abord la sélection (chaque nœud de sélection dans l’ordre vertical), puis génère la géométrie à l’emplacement approprié par rapport à la sélection.
* Une copie du fichier Dynamo d’origine est désormais intégrée au groupe FormIt et indépendante du graphique source.
* Lors du placement, le groupe de fonctions Propriétés bascule automatiquement pour afficher les paramètres disponibles.

### **Graphique de géométrie : modifier les paramètres**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Après avoir placé un groupe Dynamo, sélectionnez-le et basculez vers le groupe de fonctions Propriétés, ou double-cliquez sur le groupe pour basculer automatiquement sur Propriétés.
   * Tous les nœuds d’entrée marqués comme entrés dans Dynamo sont répertoriés ici.
   * [**Les nœuds d’entrée SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) s’affichent sous forme de boutons dans la partie supérieure et peuvent être utilisés pour mettre à jour la sélection utilisée pour piloter le graphique.
   * FormIt prend en charge les nœuds d’entrée suivants : les curseurs de nombres, les curseurs d’entiers, les bascules booléennes et les champs de nombre/chaîne.
* Modifiez les entrées dans FormIt, puis cliquez sur Exécuter. Le bouton Exécuter devient bleu pour indiquer que les paramètres ont été modifiés et que le graphique doit être exécuté.
   * Dynamo s’exécute en arrière-plan pour traiter les modifications et renvoyer la géométrie mise à jour dans FormIt.
   * Dans FormIt 2022 et versions ultérieures, la première exécution à partir du groupe de fonctions Propriétés active une instance Dynamo dédiée, ce qui accélère considérablement les modifications ultérieures.
   * Vous pouvez continuer à utiliser FormIt pendant que Dynamo est en cours d’exécution.&#x20;
* Notez que toutes les géométries à l’intérieur de chaque groupe SendToFormIt seront supprimées et remplacées lors de l’exécution du graphique Dynamo.

### Graphique de données : envoyer les niveaux FormIt vers Excel

Dans FormIt 2023 et versions ultérieures, vous pouvez utiliser Dynamo pour envoyer des niveaux FormIt vers Excel :&#x20;

* Téléchargez l’[exemple de graphique Dynamo ici](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn).
* Faites pointer la palette Dynamo vers le répertoire local où le graphique Dynamo a été enregistré.
* Cliquez avec le bouton droit de la souris sur la miniature, puis choisissez _Modifier le graphique incorporé._
* Créez une feuille de calcul Excel vide quelque part.
* Modifiez le champ Emplacement de la feuille de calcul pour utiliser le chemin d’accès à la feuille de calcul Excel.
* Modifiez les autres champs de votre choix, tels que Nom de la feuille.
* Fermez Dynamo et enregistrez le graphique.

Vous pouvez maintenant cliquer sur le fichier d’exemple dans la palette, et il s’exécutera dans FormIt sans générer de géométrie.&#x20;

Les entrées Dynamo s’affichent dans la palette Dynamo et Excel s’ouvre pour afficher les résultats du graphique.&#x20;

Lorsque vous apportez des modifications au modèle, vous pouvez cliquer à nouveau sur la miniature du graphique ou sur le bouton _Exécuter_ pour mettre à jour la feuille de calcul avec les données de niveau de la dernière version de l’esquisse FormIt.

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### Lancement d’une nouvelle fenêtre Dynamo

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* Dans FormIt 2021 et versions ultérieures, si vous cliquez sur le bouton Lancer Dynamo dans le groupe de fonctions Dynamo, une session connectée avec FormIt démarre automatiquement.
   * Cela ouvre un gabarit de graphique dans Dynamo et génère automatiquement la géométrie du modèle dans FormIt.
   * La géométrie obtenue s’affiche dans un nouveau groupe, à l’origine du contexte d’édition de groupe courant. Il est préférable de se trouver dans le contexte de groupe souhaité avant de démarrer Dynamo.&#x20;
   * Le gabarit inclut les nœuds FormIt et des exemples de géométrie. Le réglage des curseurs permet d’ajuster la taille du cube dans les deux applications.
   * À partir de cet emplacement, vous pouvez ouvrir différents graphiques Dynamo ou créer un nouvel emplacement à l’aide de ces composants de base dans le gabarit et enregistrer sous dans Dynamo.

### **Modifier les graphiques incorporés et source**

Les graphiques Dynamo existants peuvent être modifiés de deux manières différentes : en modifiant les graphiques incorporés qui ont déjà été placés dans FormIt ou en modifiant le graphique source enregistré sur votre ordinateur.

### **Graphiques incorporés**

Après avoir placé un objet Dynamo dans FormIt, son graphique sous-jacent est copié et incorporé dans le fichier FormIt courant. La modification de ce graphique dans Dynamo s’effectue via le bouton **Modifier le graphique incorporé**.

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Sélectionnez le groupe Dynamo et passez au groupe de fonctions Propriétés, ou double-cliquez sur le groupe pour basculer automatiquement sur Propriétés.
* Cliquez sur le bouton **Modifier le graphique incorporé**.
* Dans Dynamo, vous remarquerez que le nom du fichier situé dans la partie supérieure contient désormais « (FormIt) », ce qui signifie que vous modifiez un graphique incorporé dans ce fichier FormIt et non le graphique source.
* Assurez-vous qu’un ou plusieurs nœuds [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) sont connectés à la géométrie que vous souhaitez envoyer vers FormIt.
* FormIt affiche les mises à jour de la géométrie en temps réel lorsque vous ajustez le graphique.
* Si vous n’enregistrez pas les modifications dans Dynamo, FormIt revient à la dernière version enregistrée du graphique Dynamo.
* Notez que toutes les géométries à l’intérieur de chaque groupe SendToFormIt seront supprimées et remplacées lors de l’exécution du graphique Dynamo.

### **Graphiques sources**

Les graphiques sources sont affichés dans le groupe de fonctions Dynamo après [avoir lié les répertoires locaux](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started). Ces graphiques sont stockés sur votre ordinateur et peuvent être modifiés dans Dynamo en cliquant sur le bouton Modifier le graphique source.

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Liez un répertoire ](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started) contenant des fichiers Dynamo au groupe de fonctions Dynamo, puis accédez à cet emplacement dans le groupe de fonctions.&#x20;
* Cliquez avec le bouton droit de la souris sur la miniature du graphique Dynamo à modifier (ou cliquez sur la flèche), puis sélectionnez le bouton **Modifier le graphique source**.
* Dynamo se lance avec le graphique demandé ouvert et, dans FormIt, vous voyez apparaître la géométrie de la sortie finale du graphique.
   * Pour les graphiques qui utilisent un ou plusieurs nœuds [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) comme entrée, vous ne pouvez pas voir la géométrie obtenue tant que les nœuds SelectFromFormIt ne sont pas remplis avec des sélections.
* La géométrie obtenue s’affiche dans un nouveau groupe, à l’origine du contexte d’édition de groupe courant.
   * Il est préférable de vous trouver dans le contexte de groupe souhaité avant de cliquer sur Modifier le graphique source.
* Lorsque vous avez terminé la modification, enregistrez et fermez Dynamo. Dans FormIt, le graphique source a été copié et incorporé dans le fichier FormIt.
   * Si vous devez apporter d’autres modifications au **graphique source**, supprimez la copie incorporée et effectuez à nouveau ces étapes.

### **Contrôle de facettage de courbe et de surface**

*   À partir de FormIt 2023, vous pouvez contrôler le facettage des courbes et des surfaces attachées aux nœuds SendToFormIt à l’aide des nœuds FormItGroupOptions, SetCurveFacetingCount et SetSurfaceFacetingCount.

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* Ces nœuds remplacent les paramètres de facettage de surface et de courbe globaux, qui sont définis sous Modifier -> Préférences -> Unités et Précision.
* Cette option est très utile si votre graphique Dynamo doit générer des objets incurvés à l’aide de valeurs de facettage spécifiques, ce qui évite de modifier le paramètre global pour chaque graphique Dynamo exécuté dans la session en cours.

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* Vous pouvez également définir globalement les paramètres de facettage dans Modifier -> Préférences -> Unités et Précision
* Après avoir ajusté la qualité de facettage dans Préférences, réexécutez le graphique pour utiliser les nouveaux paramètres de facettage globaux.

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[En savoir plus sur les paramètres de facettage de courbe et de surface dans FormIt.](https://windows.help.formit.autodesk.com/v/french/tool-library/curve-+-surface-faceting)

## Utilisation de groupes FormIt avec Dynamo

Exploitez la puissance des groupes FormIt pour une meilleure organisation de la géométrie Dynamo et des workflows incroyables.

### **Groupes et nœud SelectFromFormIt**

* Lorsque vous sélectionnez la géométrie d’un nœud [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes), il est utile de stocker la géométrie dans un groupe FormIt et de sélectionner le groupe à la place.
   * Cela vous donne la flexibilité de modifier le contenu du groupe FormIt sélectionné, puis de simplement réexécuter le graphique qui référence le groupe pour voir le résultat mis à jour.
* Si vous sélectionnez une géométrie non groupée, les modifications apportées à cette géométrie peuvent entraîner l’affichage de FormIt vous demandant de sélectionner à nouveau la géométrie lors de la prochaine exécution du graphique.

### **Génération de géométries en groupes**

* Lorsqu’un graphique Dynamo est exécuté dans FormIt, ses résultats géométriques sont contenus dans un groupe FormIt.
* Chaque nœud [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) du graphique crée un sous-groupe qui contient la géométrie du port d’entrée du nœud.
* Après la génération d’un objet Dynamo dans FormIt, l’intégralité du graphique et ses paramètres sont incorporés en tant que copie dans le fichier FormIt.
* Lorsque le graphique est exécuté, la géométrie à l’intérieur de chaque sous-groupe est supprimée et régénérée.
   * Soyez prudent lorsque vous modifiez la géométrie ou peignez des surfaces dans des sous-groupes, car ces modifications seront perdues lors de la prochaine exécution du graphique Dynamo.
   * Toutefois, si vous peignez des sous-groupes (sans géométrie à l’intérieur) avec des matériaux FormIt, ces matériaux sont conservés entre les exécutions. Voir ci-dessous.

### **Utilisation des groupes et des matériaux**

* Lorsque vous utilisez plusieurs nœuds **SendToFormIt**, vous pouvez les organiser par matériau, de sorte que vous pouvez peindre différents sous-groupes FormIt avec différents matériaux.
* Dans cet exemple, un bâtiment entier est généré à partir de plans simples dans FormIt. Chaque composant de construction nécessitant des matériaux uniques obtient son propre nœud **SendToFormIt** :

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* Après l’application de matériaux à chacun des sous-groupes, les matériaux sont conservés entre les exécutions de Dynamo :

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Imbrication de groupes Dynamo**

* Vous pouvez utiliser le nœud **SelectFromFormIt** pour sélectionner les résultats de sous-groupe d’un graphique Dynamo afin de contrôler les résultats d’un autre graphique.&#x20;
* En se basant sur l’exemple ci-dessus, la sortie de vitrage du graphique du générateur de bâtiment est utilisée comme géométrie de sélection pour l’exemple de mur-rideau de vitrine intégré :

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* Lorsque la forme du bâtiment est modifiée, il vous suffit de sélectionner le groupe de systèmes de meneaux, puis de cliquer sur Exécuter dans le groupe de fonctions Propriétés.
   * Bien que le contenu du groupe de vitres ait changé, le groupe lui-même n’a pas changé. Il n’est donc pas nécessaire de sélectionner à nouveau la vitre lors de la réexécution du graphique.
* Le modèle ci-dessus est disponible dans FormIt 2022 et versions ultérieures en tant que « Création de plans de toit » dans le sous-dossier **Volumes de bâtiment** du dossier **Exemple Dynamo**.
* Associé aux fonctionnalités étendues de FormIt, Dynamo vous permet de créer et d’ajuster une conception entièrement paramétrique, avec des matériaux et une logique imbriquée, dans le contexte riche d’un puissant outil de modélisation conceptuelle :

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **Comportement standard des groupes FormIt toujours applicable**

* Outre les éléments décrits ci-dessus, les groupes Dynamo dans FormIt fonctionnent selon les mêmes règles que les autres groupes :
   * Le placement d’un nouvel objet Dynamo à partir du groupe de fonctions Dynamo crée un groupe unique et n’a aucune incidence sur les instances du même objet déjà placé dans l’esquisse.
   * Les opérations de copier-coller des groupes Dynamo les maintiennent identiques. Toute modification apportée au graphique Dynamo d’une copie met également à jour la géométrie dans ses instances identiques, sauf si elles sont rendues uniques.
   * Vous pouvez rendre les groupes Dynamo uniques à l’aide du raccourci MU ou via le menu contextuel :

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## Nœuds FormIt essentiels

Voici les nœuds les plus puissants pour envoyer des données entre FormIt et Dynamo.

### **Nœud SendToFormIt**

* Pour générer des objets Dynamo dans FormIt, attachez les sorties de nœud géométrique souhaitées à l’entrée _geometry_ d’au moins un nœud SendToFormIt :

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions est un nouveau port (facultatif) dans FormIt 2022. Il est détaillé dans la section **Nœuds FormItGroupOptions** ci-dessous.
* Dans FormIt 2021.3 et versions ultérieures, vous pouvez utiliser plusieurs nœuds SendToFormIt pour organiser vos résultats Dynamo en groupes et sous-groupes FormIt ordonnés.
* [Découvrez comment Dynamo fonctionne avec les groupes FormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* Le nœud SendToFormIt respecte l’indicateur de sortie, qui est activé par défaut. Vous pouvez cliquer avec le bouton droit de la souris sur le nœud pour vérifier que :

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* Lorsque cette option est activée, la géométrie attachée à ce nœud SendToFormIt apparaît dans FormIt, à l’intérieur d’un sous-groupe.
* Lorsque cette option est désactivée, aucune géométrie n’est envoyée à FormIt et le sous-groupe correspondant (s’il en existe un) est supprimé.

### **Nœud SelectFromFormIt**

* FormIt 2021 et versions ultérieures permettent de sélectionner une géométrie à partir de FormIt pour l’utiliser comme entrée dans les graphiques Dynamo :

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* Le nom du nœud SelectFromFormIt sera utilisé pour les invites dans FormIt. Vous devez donc le nommer de manière à décrire le type de géométrie FormIt à sélectionner :

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Lorsque vous cliquez sur le bouton Sélectionner depuis FormIt dans l’éditeur graphique Dynamo ou dans le groupe de fonctions Propriétés, FormIt lance un mode d’assistant de sélection pour vous guider dans la sélection de la géométrie :

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* Le nœud SelectFromFormIt respecte l’indicateur d’entrée, qui est activé par défaut. Pour que la sélection fonctionne dans FormIt, il doit être activé. Cliquez avec le bouton droit de la souris sur le nœud à vérifier.

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* Lorsque l’option d’entrée est activée :
   * La miniature du groupe de fonctions Dynamo du graphique indique qu’une sélection est requise :

![](../.gitbook/assets/dynamo\_patharray.png)

* Lors de l’exécution du graphique, l’assistant de sélection FormIt vous guide à travers les sélections de paramètres pour chaque nœud SelectFromFormIt, en commençant par la partie supérieure du graphique.
* Après la première génération, un bouton s’affiche pour chaque nœud SelectFromFormIt dans le groupe de fonctions Propriétés de FormIt.

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* Un clic sur ces boutons lance l’assistant de sélection, qui vous permet de modifier la sélection utilisée pour générer la géométrie finale. Le graphique est automatiquement réexécuté après une nouvelle sélection.

### **Conseils, astuces et remarques**

* Nommez le nœud SelectFromFormIt pour indiquer le type de géométrie attendu. Par exemple, « Sélectionner le contour du site (arêtes) »
   * Vous pouvez sélectionner n’importe quel type de géométrie FormIt, mais il est souvent préférable de contenir la sélection dans un groupe FormIt et de [la sélectionner au lieu de la géométrie brute](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups).
* Si vous devez déplacer les résultats d’un graphique Dynamo basé sur une sélection, il est préférable de déplacer d’abord la géométrie de sélection, puis de relancer le graphique, qui va prendre la géométrie de sélection mise à jour et se repositionner de manière appropriée.&#x20;
   * Vous pouvez également regrouper les résultats Dynamo **et** la sélection, puis déplacer le groupe qui les contient.
* Lorsque la géométrie FormIt est envoyée vers Dynamo, les attributs, matériaux ou groupes imbriqués sont perdus lors du retour de la géométrie dans FormIt.
* Si vous modifiez un graphique basé sur une sélection dans Dynamo et que la géométrie sélectionnée dans FormIt change, vous devrez resélectionner la géométrie en cliquant sur le bouton « Sélectionner depuis FormIt » dans le nœud SelectFromFormIt.&#x20;
* Lorsque vous effectuez une sélection dans FormIt, le [filtre de sélection](https://windows.help.formit.autodesk.com/v/french/tool-library/select-edge-face-or-object#filtrage-de-la-selection) actif est appliqué. Par exemple, si vous souhaitez sélectionner des sommets FormIt, vous devez activer cette option dans le filtre de sélection.

![](../.gitbook/assets/dynamo\_filterselection.png)

## Autres nœuds d’entrée

Il existe un large éventail d’options d’entrée pour faciliter la personnalisation des graphiques Dynamo dans FormIt.

### **Nœud FormItLengthString**

Dans FormIt 2022.1.0 ou une version ultérieure, vous pouvez utiliser le nœud **FormItLengthString** pour spécifier les cotes dans n’importe quel type d’unité FormIt pris en charge (pieds-pouces, pouces, m, cm, mm), quel que soit le paramètre d’unité de FormIt dans l’esquisse active.

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

Comme pour les autres nœuds d’entrée pris en charge, la _chaîne FormItLengthString_ s’affiche dans la palette des propriétés de FormIt lorsqu’elle est marquée comme entrée et, lorsqu’elle est renommée, son nouveau nom s’affiche dans FormIt :

![](../.gitbook/assets/dynamo\_propertiespalette.png)

Chaque instance du nœud _FormItLengthString_ peut être utilisée dans n’importe quel type d’unité, de sorte qu’un seul graphique Dynamo peut utiliser un mélange d’unités, comme illustré ci-dessus.

### **Passage des nombres bruts à FormItLengthString**

Dans FormIt 2022.1.1 et versions ultérieures, le fait de changer un graphique pour utiliser les nœuds FormItLengthString (en plaçant le premier dans un graphique) ou d’utiliser un graphique pour utiliser uniquement des nombres bruts (en supprimant le dernier FormItLengthString) modifie certains comportements lors de la modification d’un graphique dans Dynamo :

* Lorsque vous utilisez le nœud [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) lors de la modification d’un graphique, le passage des nombres bruts au nœud _FormItLengthString_ comme indiqué ci-dessus nécessite de sélectionner à nouveau la géométrie pour chaque nœud _SelectFromFormItNode_, de sorte que les résultats continuent d’être mis à l’échelle correctement dans FormIt.
* Après avoir placé le premier nœud FormItLengthString dans un graphique, tous les nombres du graphique destinés à être des cotes (y compris les entrées de nombre brut) feront référence aux mètres (unité native de Dynamo sous-jacente).
   * Le nœud [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) prend en compte la modification et garantit que la géométrie générée dans FormIt conserve la taille correcte.
   * À l’inverse, la suppression de tous les nœuds FormItLengthString du graphique permet de basculer entre les nombres bruts pour faire référence aux paramètres d’unité de FormIt (ancien comportement).
* La sortie numérique des nœuds _FormItLengthString_ sera également en mètres, mais cela ne modifiera pas la taille des résultats géométriques dans FormIt :

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **Autres nœuds d’entrée pris en charge**

Les nœuds d’entrée Dynamo standard s’affichent dans le groupe de fonctions Propriétés de FormIt lorsque vous les marquez comme entrés dans Dynamo :

* Number Slider
* Curseur d'entier
* Number
* String
* Bascule booléenne

Vous pouvez renommer les nœuds d’entrée (recommandé pour plus de clarté). Leur nouveau nom s’affichera dans FormIt :

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## Autres nœuds de sortie

Différentes méthodes pour afficher les résultats non géométriques de Dynamo à FormIt.

### **Nœud de visualisation**

Les nœuds de visualisation marqués comme sortis s’affichent dans la section « Regarder les sorties de nœud » du groupe de fonctions Propriétés dans FormIt 2022 et versions ultérieures :

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **Afficher les notifications FormIt**

Dans FormIt 2022.1 ou une version ultérieure, vous pouvez afficher les notifications côté FormIt à partir d’un graphique Dynamo à l’aide du nœud **UI.ShowNotification** :&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **Connexion à la console FormIt**

Dans FormIt 2022.1 ou une version ultérieure, vous pouvez enregistrer des données supplémentaires directement dans la console de l’application FormIt (fenêtre Sortie de script) à l’aide du nœud **FormIt.ConsoleLog** :

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## Options de nœuds FormIt

Contrôlez la façon dont les données sont envoyées à FormIt, soit au niveau de la géométrie individuelle, soit au niveau du groupe conteneur.

### **FormItGeometryOptions**

FormIt 2022.1 et versions ultérieures permettent de personnaliser la manière dont les géométries Dynamo individuelles sont envoyées vers FormIt à l’aide des nœuds **FormItGeometryOptions**.

* Spécifiez le calque des géométries individuelles dans le groupe Dynamo généré.
* Spécifiez un attribut de chaîne pour les géométries individuelles dans le groupe Dynamo généré.

Les nœuds _FormItGeometryOptions_ peuvent être utilisés en amont du nœud _SendToFormIt_ :

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 et versions ultérieures permettent de personnaliser la manière dont le groupe Dynamo du nœud _SendToFormIt_ est généré dans FormIt avec des nœuds **FormItGroupOptions**.

* Indiquez si le nœud SendToFormIt envoie la géométrie à FormIt en tant que maillage ou objet.
* Spécifiez le calque du groupe créé par le nœud SendToFormIt.
* Spécifiez un attribut de chaîne pour le groupe créé par le nœud SendToFormIt.

Vous pouvez utiliser n’importe quelle combinaison de nœuds FormItGroupOptions dans n’importe quel ordre en les enchaînant ensemble :

![](../.gitbook/assets/dynamo\_daisychain.png)

## Nœuds de l’API JavaScript

FormIt 2022.1 et les versions ultérieures permettent d’accéder aux API JavaScript et aux fonctions personnalisées de Dynamo via deux nouveaux nœuds :

### **CallJSAPI**

Le nœud **CallJSAPI** vous permet d’appeler des API JavaScript FormIt directement à partir de Dynamo.

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

Pour les noms de fonction et les paramètres, consultez notre documentation JavaScript, divisée en deux parties : [API FormIt](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) et [API WSM](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (noyau de modélisation).

**CallPluginJS**

À l’inverse, le nœud **CallPluginJS** vous permet d’appeler des fonctions personnalisées à partir d’un plug-in chargé ou d’un extrait de script exécuté à partir de la fenêtre de l’éditeur de script.

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## Remarques importantes

### **Configuration système requise**

* Pour utiliser Dynamo dans FormIt, vous devez utiliser [FormIt pour Windows](https://formit.autodesk.com/page/download) v17.0 ou une version ultérieure.
   * L’intégration de FormIt et Dynamo reçoit régulièrement de nouvelles fonctionnalités et des correctifs, de sorte qu’il est toujours préférable de télécharger la dernière mise à jour lorsqu’elle est disponible.
* Vous aurez également besoin de Windows 10. Pour des raisons techniques, les versions antérieures de Windows ne sont plus prises en charge.

**Dépannage**

* Si vous disposez d’un système avec une [carte graphique NVIDIA ou AMD](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/) ou plusieurs cartes graphiques, vous devrez peut-être configurer FormIt et Dynamo pour utiliser votre processeur graphique haute puissance :
   * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
   * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * Si vous disposez d’une carte graphique NVIDIA, [assurez-vous que le panneau de configuration NVIDIA est installé](https://whatsabyte.com/blog/find-nvidia-control-panel/)
   * Utilisez les panneaux de configuration [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) ou [AMD](https://www.amd.com/fr/support/kb/faq/dh-017) pour configurer les applications suivantes de manière à utiliser votre carte graphique distincte :
* Si vous utilisez un paramètre régional autre que l’anglais, vous devrez peut-être définir les paramètres régionaux de Windows 10 sur anglais pour éviter les problèmes avec certains nœuds Dynamo :
   * Dans le menu Démarrer, recherchez « langue » et sélectionnez « Paramètres de langue ».
   * Dans la partie supérieure droite de la boîte de dialogue Langue, cliquez sur « Paramètres de langue d’administration »
   * Cliquez sur le bouton « Modifier les paramètres régionaux du système »
   * Choisissez « Anglais (États-Unis) ».
* Si vous rencontrez des problèmes de génération de résultats dans FormIt lorsque vous travaillez avec de petites géométries ou des nombres réduits, essayez de définir le paramètre de mise à l’échelle Dynamo sur « Petit » :
   * Menu Dynamo > Préférences > Général > Mise à l’échelle de la géométrie >·Petit

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **Obtenir de l’aide**

Besoin d’aide avec FormIt et Dynamo ? [Faites-nous part de vos commentaires sur les forums](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=fr).
