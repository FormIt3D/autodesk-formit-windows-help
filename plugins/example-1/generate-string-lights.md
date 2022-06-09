# Génération de guirlandes lumineuses

_Dans ce chapitre, nous allons utiliser certains des plug-ins fournis avec FormIt afin d’améliorer le fichier_ _**Encode Campus Sample Model.axm**. Si ce n’est pas déjà fait, vous pouvez télécharger le fichier à partir des _[_jeux de données Partie II FormIt Primer_](https://formit-help.s3.amazonaws.com/FormIt+Primer+Part+2+Datasets.zip)__

_Ce plug-in intéressant vous permet d’ajouter rapidement des lumières suspendues à votre modèle selon une ligne ou une courbe._

1 – Avant d’ajouter de nouvelles lumières, examinons le résultat souhaité à l’aide d’une scène prédéfinie dans le modèle.

1. Pour accéder à la scène contenant des guirlandes lumineuses, ouvrez la **palette Scènes** et double-cliquez sur la scène intitulée **Eye Level – Short Alley** (Au niveau du regard – Petite allée).
2. Observez les guirlandes lumineuses fournies avec ce modèle. C’est ce que nous allons recréer, mais ailleurs.
3. Dans la **palette Calques**, activez le calque **Helper Geometry** (Géométrie de l’assistant) afin d’afficher les lignes d’origine utilisées pour générer ces guirlandes lumineuses.

![](<../../.gitbook/assets/3 (10).png>)

2 – Naviguons maintenant jusqu’à l’autre allée et ajoutons des lumières. Dans la **palette Scènes**, ouvrez la scène **Eye Level – Long Alley** (Au niveau du regard – Longue allée). Notez que cette allée ne comporte pas encore de guirlandes lumineuses.

3 – Pour créer une nouvelle guirlande lumineuse, procédez comme suit :

1. Pour ouvrir la **palette Generate String Lights** (Générer des guirlandes lumineuses) nouvellement installée, cliquez sur l’icône en forme de guirlande lumineuse. Par défaut, les icônes des nouveaux plug-ins s’affichent dans la partie inférieure.
2. Définissez l’option **Nombre de dispositifs** sur **10**.
3. Double-cliquez sur l’une des lignes d’assistance pour modifier le groupe précréé **String Lights – Long Alley** (Guirlandes lumineuses – Longue allée). Ensuite, cliquez une fois sur l’une des lignes d’assistance prédessinées pour la sélectionner.
4. Cliquez sur le bouton **Générer des guirlandes lumineuses** dans la palette du plug-in, et une nouvelle guirlande lumineuse apparaît. Notez que chaque guirlande lumineuse est créée en tant que groupe unique.

![](<../../.gitbook/assets/4 (6) (1).png>)

_**Remarque :**_ _il est possible que certaines lignes passent par le panneau « Groove Coffee », car le plug-in de guirlandes lumineuses crée une courbe caténaire qui s’affaisse de manière réaliste sous le panneau._

4 – Essayez de créer d’autres guirlandes lumineuses en utilisant l’autre ligne d’assistance prédéfinie et/ou en créant vos propres lignes d’aide. Jouez avec les paramètres du plug-in pour obtenir des résultats différents.

5 – Pour que le modèle reste organisé, une fois l’opération terminée, nous vous recommandons de regrouper toutes les lignes d’assistance et de placer ce groupe sur le calque **Helper Geometry** (Géométrie de l’assistant), et d’affecter tous les groupes de guirlandes lumineuses au calque **Context – Exterior Lighting** (Contexte – Éclairage extérieur). Cela permet de masquer les lignes d’assistance dans les scènes « Eye Level » (Au niveau du regard) où nous ne voulons pas les voir. Lorsque vous avez terminé, les résultats doivent ressembler à la capture d’écran suivante.

![](<../../.gitbook/assets/5 (3) (1).png>)

_**Remarque :**_ _contrairement à la géométrie créée à partir d’un script Dynamo, qui peut être mise à jour et régénérée à l’aide de la_ _**palette Propriétés**, les objets créés par un plug-in sont (pour la plupart) des géométries FormIt standard. Une fois créés, ils peuvent uniquement être modifiés à l’aide des outils de modélisation intégrés de FormIt._
