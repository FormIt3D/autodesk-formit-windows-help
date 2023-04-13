# 3D Context Creator

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## Présentation

3D Context Creator est un plug-in facile à utiliser qui permet de générer des bâtiments en contexte en 3D dans FormIt. 

Ce plug-in vous permet de visualiser le site du projet dans son contexte et de prendre des décisions avisées dès les premières phases du processus de conception.

Ce plug-in récupère des données d’[Open Street Map](https://www.openstreetmap.org/about) pour les transformer en géométries FormIt. Le code source de ce plug-in est disponible sur [Github](https://github.com/matterlab-co/FormIt-Context-Plugin).

## Fonctionnement

Pour l’installer, il suffit de l’activer sur le bouton du plug-in dans le gestionnaire de plug-in comme avec n’importe quel autre plug-in.

![](../../.gitbook/assets/contextcreator3.png)

Une fois activé, le plug-in doit apparaître sur le côté droit de l’application et être prêt à l’emploi.

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

Si votre site ne dispose pas encore d’un emplacement, vous pouvez cliquer sur le lien **Définir l’emplacement...** pour spécifier un emplacement et définir la limite qui sera utilisée pour générer un contexte 3D.

Une fois que vous avez défini votre emplacement, l’outil 3D Context Creator est mis à jour avec l’emplacement actuel et le bouton est activé :

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

L’outil 3D Context Creator utilisera simplement les dimensions de l’image satellite pour générer un contexte 3D. Il vous suffit de cliquer sur **Générer un contexte 3D**.

Selon l’étendue de l’image satellite et la complexité des bâtiments, la génération peut prendre quelques secondes.

Les bâtiments en contexte en 3D sont automatiquement placés dans une occurrence de groupe et sur un calque appelé « Bâtiments en contexte ». Vous pouvez activer ou désactiver la visibilité du contexte à l’aide de ce calque.

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

Si vous décidez par la suite de modifier votre emplacement ou d’ajuster l’étendue de l’image satellite, vous pouvez cliquer à nouveau sur **Générer un contexte 3D** pour régénérer les bâtiments. 

_Sachez qu’une fois le contexte généré à nouveau, l’occurrence de groupe contenant les bâtiments sera remplacée par une nouvelle occurrence. Les modifications apportées aux bâtiments seront donc perdues._ Pour éviter cela, vous pouvez dissocier le conteneur du contexte, puis le regrouper.

## **Quelques exemples**

Essayez de deviner quelles villes emblématiques sont représentées dans les contextes suivants :

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
