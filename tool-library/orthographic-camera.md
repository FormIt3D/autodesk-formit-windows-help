# Caméra orthogonale et en perspective

FormIt 2023 inclut plusieurs options de caméra en perspective et orthogonale. Les boutons Orthogonal, Perspective à 2 points et Perspective à 3 points sont disponibles dans le menu de navigation flottant :

![Boutons de vue de caméra Perspective à 3 points (haut), Perspective à 2 points (milieu) et Orthogonal (bas)](../.gitbook/assets/camera-2point-floating-nav-blurred.png)

### Perspective à 3 points

* Il s’agit de la caméra en perspective par défaut. À certains angles de la caméra, les lignes verticales semblent converger vers le haut de la caméra.
* La position de la caméra réglée dans ce mode définit le plan de délimitation de la caméra orthogonale.
* Dans ce mode, Ctrl + zoom permet d’effectuer un zoom à une vitesse constante, sans ralentir lorsque la caméra approche des objets.

### Perspective à 2 points

* Cette caméra est semblable à une perspective à 3 points, mais elle permet de s’assurer que les lignes verticales restent verticales.
* À certains angles de la caméra, la géométrie peut sembler déformée pour maintenir les lignes verticales toujours verticales.
* La position de la caméra réglée dans ce mode définit le plan de délimitation de la caméra orthogonale.
* Dans ce mode, Ctrl + zoom permet d’effectuer un zoom à une vitesse constante, sans ralentir lorsque la caméra approche des objets.
* La perspective à 2 points est également un mode de travail. Vous remarquerez que les lignes verticales restent verticales même lors d'un changement de caméra. Cela peut déformer la scène à certains angles de la caméra

![](../.gitbook/assets/camera-2point-working-mode.gif)

### Orthogonal

* Un mode de projection orthogonale utile pour les diagrammes, les dessins de détail 3D et d’autres graphiques qui ne sont pas en perspective.
* La position de la caméra définie dans l’un des deux modes de perspective définit le plan de délimitation de la caméra orthogonale. Si votre scène est délimitée de manière inattendue, passez en mode perspective et effectuez un zoom arrière, puis revenez en mode orthogonal.

### Utilisation des modes

Les modes de caméra sont tous des modes de travail complets, qui permettent d’accéder aux outils de navigation et de dessin dans le mode de votre choix. Le menu vous permet de basculer facilement entre les différentes caméras. 

![Activation/désactivation des trois modes de caméra : Perspective à 3 points, Perspective à 2 points et Orthogonal.](../.gitbook/assets/perspective-gif.gif)

Une fois que vous avez sélectionné une caméra, tous les autres outils de caméra respectent le mode actif. Par exemple, l’option **Aligner caméra avec face** permet d’aligner la caméra orthogonale sur la face, ce qui génère une vue d’élévation orthogonale.

Si vous accédez manuellement à une vue orthogonale prédéfinie, telle que Vue de dessus ou Vue de face, la caméra orthogonale s’accroche à cette position, facilitant ainsi l’accès à ces vues prédéfinies.

![](../.gitbook/assets/orthoorienttoface.gif)

### Axonométrique

Outre les options de caméra Orthogonal et Perspective disponibles dans la barre d'outils de navigation, FormIt propose une caméra axonométrique disponible uniquement dans le menu Affichage (Windows uniquement) :

<figure><img src="../.gitbook/assets/AxonometricMenu (2).png" alt=""><figcaption></figcaption></figure>

Une fois sélectionnée, cette option place la caméra dans la vue axonométrique :

<figure><img src="../.gitbook/assets/Axonometric (2).png" alt=""><figcaption></figcaption></figure>

### Oblique

FormIt propose également une caméra oblique disponible uniquement dans le menu Affichage (Windows uniquement) :

<figure><img src="../.gitbook/assets/ObliqueMenu.png" alt=""><figcaption></figcaption></figure>

Une fois sélectionnée, cette option place la caméra dans la vue oblique :

<figure><img src="../.gitbook/assets/Oblique (2).png" alt=""><figcaption></figcaption></figure>
