# Plug-in Manage Cameras (Gérer les caméras)

_Dans ce chapitre, nous allons utiliser certains des plug-ins fournis avec FormIt afin d’améliorer le fichier_ _**Encode Campus Sample Model.axm**. Si ce n’est pas déjà fait, vous pouvez télécharger le fichier à partir des _[_jeux de données Partie II FormIt Primer_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

Tout au long du guide, nous avons utilisé les scènes comme des outils précieux afin de naviguer et de contrôler la visibilité dans l’ensemble du modèle. Ce plug-in permet d’afficher et de modifier l’élévation de la caméra actuelle, d’exporter les caméras de chaque scène en tant qu’objets 3D et de copier ces scènes entre les modèles.

1. Tout d’abord, nous allons ajuster la scène **Eye Level – Long Alley** (Au niveau du regard – Longue allée) de sorte que sa caméra soit réellement au niveau du regard :

1. Si ce n’est pas déjà fait, double-cliquez sur la scène **Eye Level – Long Alley** (Au niveau du regard – Longue allée) dans la **palette Scènes** pour y revenir.
2. Cliquez sur l’icône en forme d’appareil photo avec une icône d’engrenage pour ouvrir la **palette Gérer les caméras**.
3. Définissez la valeur de **Hauteur au-dessus du sol** sur **5 pi–8 po**.

![](<../../.gitbook/assets/6 (6) (1).png>)

_**Remarque :**_ _si votre modèle possède des niveaux, ce plug-in affiche également la hauteur au-dessus du niveau le plus proche sous la_ _**Caméra principale**._

2 – Ensuite, procédez comme suit :

1. Revenez à la **palette Scènes**.
2. Assurez-vous que la scène **Eye Level – Long Alley** (Au niveau du regard – Longue allée) est toujours sélectionnée (sinon, cliquez une fois dessus pour la sélectionner).
3. Cliquez sur le bouton **Mettre à jour la scène** pour enregistrer la nouvelle hauteur de caméra dans cette scène.

![](<../../.gitbook/assets/7 (1) (1).png>)

_**Remarque :**_ _vous pouvez également ajuster l’angle et la position de la caméra d’une scène en activant le bouton_ _**Modifier les caméras de la scène**_ _situé dans la partie supérieure de la_ _**palette Scènes**_ _(entre les boutons de mise à jour et de lecture)._

3 – Exportons ensuite nos scènes vers un nouveau modèle. Tout d’abord, nous devons créer des objets caméra pour toutes les scènes à l’aide du plug-in **Manage Cameras** (Gérer les caméras) :

1. Ouvrez à nouveau la **palette Gérer les caméras**.
2. Assurez-vous que l’option **Copier les caméras dans le Presse-papiers** est sélectionnée.
3. Cliquez sur le bouton **Exporter les scènes vers les caméras**. Cette opération peut prendre quelques secondes.
4. Si la zone de dessin devient entièrement blanche, c’est parce que votre **caméra principale** était alignée avec l’une des caméras de la scène. **Utilisez l’outil Zoom (Z)** pour effectuer un zoom arrière jusqu’à ce que vous puissiez distinguer les 3 bâtiments principaux et les nouveaux objets de caméra. Notez que les objets caméra sont automatiquement placés dans un grand groupe nommé **Cameras** (Caméras). Dans ce groupe, chaque caméra est placée dans son propre groupe avec le même nom que les scènes à partir desquelles elle a été créée.

![](<../../.gitbook/assets/8 (7) (1).png>)

4 – Copions ces scènes dans un nouveau modèle. Étant donné que les données de caméra ont été enregistrées dans le Presse-papiers, il ne reste pas grand-chose à faire :

1. **Enregistrez** **(Ctrl + S)** votre modèle actuel, puis fermez-le.
2. Pour commencer une nouvelle esquisse vide, sélectionnez **Nouvelle esquisse (Ctrl + N)** dans la liste déroulante **Fichier** de la barre du **menu principal**.
3. Ouvrez le plug-in **Manage Cameras** (Gérer les caméras), s’il n’est pas déjà ouvert, et assurez-vous que l’option **Rechercher les caméras dans le Presse-papiers** est sélectionnée.
4. Cliquez sur le bouton **Importer des scènes à partir de caméras** situé dans la partie inférieure du plug-in. Les scènes de l’autre modèle sont importées. Pour vérifier, ouvrez la **palette Scènes** et/ou activez le calque **Camera** (Caméra). Vous pouvez constater que toutes les scènes et tous les objets de caméra 3D ont été importés dans ce modèle.

![](<../../.gitbook/assets/9 (7) (1).png>)
