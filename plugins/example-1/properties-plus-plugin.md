# Plug-in Properties Plus (Propriétés plus)

_Ce plug-in est une version plus avancée de la_ _**palette Propriétés** standard. Si vous sélectionnez plusieurs groupes et/ou types de géométrie, ce plug-in vous fournit le détail de ce qui a été sélectionné, et vous permet de renommer en bloc des groupes et des occurrences de groupe._

1 **– **Tout d’abord, nous allons examiner les propriétés d’un groupe de portes à partir de notre modèle de base. Rouvrez le fichier **Encode Campus Sample Model.axm** et revenez à la scène **Eye Level – Long Alley** (Au niveau du regard – Longue allée). Pour commencer à utiliser le plug-in **Properties Plus** (Propriétés plus), procédez comme suit :

1. Pour ouvrir la **palette Properties Plus** (Propriétés plus), cliquez sur la propriété portant l’icône « plus ».
2. Assurez-vous que l’option **Mettre à jour lors du changement de sélection** est cochée.
3. Sélectionnez l’un des groupes de portes à double vitre, nommé **Door** (Porte), sur le côté droit de l’allée.
4. Dans la zone **Compteur de sélections**, l’option **Nombre total d’objets** indique qu’un (**1**) objet est sélectionné.
5. Juste en dessous, vous trouverez plus d’informations sur les types d’objets sélectionnés. Dans ce cas, un (**1**) groupe est sélectionné, mais ce groupe comporte quatre (**4**) occurrences dans le modèle.

![](<../../.gitbook/assets/10 (2) (1).png>)

_**Remarque :**_ _il peut s’avérer très pratique de vérifier le nombre d’occurrences du groupe sélectionné pour éviter de modifier accidentellement plusieurs éléments lorsque vous souhaitiez uniquement modifier l’élément sélectionné, mais que vous avez oublié de le rendre unique avant._

2 – Ce plug-in nous permet d’éditer le nom d’une occurrence de groupe ou d’un groupe sans avoir à passer en mode de modification de groupe, et de renommer plusieurs instances à la fois. Comme nous l’avons vu précédemment, chaque groupe a un nom, mais chaque occurrence de ce groupe peut également avoir un nom « d’instance » unique. Étant donné que ce modèle va probablement contenir de nombreux types de portes, il est préférable d’attribuer à ce groupe, et à certaines de ses occurrences, des noms plus spécifiques.

1. Étant donné que le premier groupe de portes vitrées **Door** (Porte) est toujours sélectionné, ajoutez un autre groupe **Door** (Porte) à votre sélection actuelle. Pour ce faire, maintenez la touche **Maj** ou **Ctrl** enfoncée et cliquez une fois sur l’autre groupe de portes à double vitre **Door** (Porte) situé près du premier groupe.
2. Notez que la **palette Properties Plus** (Propriétés plus) a mis à jour le **Compteur de sélections** pour indiquer que deux (**2**) occurrences sont sélectionnées, mais qu’une (**1**) seule **famille** (également appelée groupe) est sélectionnée. (Bien que ce plug-in utilise le terme **Famille**, que les utilisateurs de Revit connaissent, dans ce contexte, il signifie la même chose qu’un groupe FormIt.)
3. Sous la zone **Famille de groupes**, définissez le champ **Nom** sur **Doors – Double Glass Storefront** (Portes – Vitrine à double vitre). Cela permet de mettre à jour le nom du groupe pour toutes les occurrences, où qu’elles se trouvent et peu importe si elles sont sélectionnées ou non, sans avoir à double-cliquer sur le groupe pour le modifier.
4. Comme ces deux occurrences sont des portes dans la zone Groove Coffee, renommez uniquement ces deux occurrences en saisissant **Groove Coffee Door** (Porte Groove Coffee) dans le champ **Nom** sous la zone **Occurrences de groupes multiples**.

**Remarque :** dans la **palette Propriétés** standard, il n’est pas possible de renommer plusieurs occurrences d’un groupe à la fois. Cela peut s’avérer très pratique lorsque vous souhaitez renommer des dizaines ou des centaines d’occurrences du même nom à la fois.

![](<../../.gitbook/assets/11 (6) (1).png>)

_**Remarque :**_ _si vous quittez la palette avec la souris, vous ne pourrez plus modifier la zone de texte sélectionnée. Ceci est vrai pour toutes les palettes. Par conséquent, lorsque vous modifiez des éléments à l’intérieur d’une palette, veillez à maintenir le curseur à l’intérieur du contour de la palette._

3 – Si vous sélectionnez une porte vitrée Groove Coffee ou une autre porte vitrée et que vous examinez ses propriétés dans la **palette Propriétés** standard, vous verrez que le nom du **groupe** a été mis à jour pour chaque occurrence, mais que seule la propriété **Nom** de l’occurrence des portes Groove Coffee est mise à jour par rapport à sa valeur par défaut.

![](<../../.gitbook/assets/12 (3) (1).png>)

4 – Enfin, examinons comment ce plug-in trie différents types d’éléments :

1. Tracez rapidement une **ligne (L)**, un **rectangle (R)** et un **cube (Alt + B)** à l’endroit souhaité dans le modèle. Comme ces éléments sont temporaires, leur emplacement n’a pas d’importance.
2. Rouvrez la **palette Properties Plus** (Propriétés plus) si elle a été fermée, puis appuyez sur **Ctrl + A** pour sélectionner tous les éléments visibles dans le modèle.
3. Dans la zone **Compteur de sélections**, notez que les éléments sélectionnés sont séparés en **arêtes** (lignes), **faces**, **corps**, (formes 3D constituées de faces et d’arêtes, comme le cube)**,** **groupes**, etc.

![](<../../.gitbook/assets/13 (3) (1).png>)

_**Remarque :**_ _ce plug-in détecte également les__ **sommets**, qui peuvent être créés à l’aide d’un autre plug-in appelé_ _**Generate Vertex** (Générer le sommet). Si vous souhaitez faire des essais, installez le_ _**plug-in Generate Vertex**__ (Générer le sommet) et répétez les étapes ci-dessus._
