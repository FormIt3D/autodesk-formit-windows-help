# Gestion des versions

Lorsque vous développez et mettez à jour votre plug-in, vous devrez peut-être gérer les versions du code à un moment donné.

Par exemple, les API FormIt peuvent changer d’une version à l’autre. Même si vous souhaitez que la nouvelle version de votre plug-in utilise les nouvelles API FormIt ou WSM, vous voulez également que le plug-in continue à fonctionner dans les versions antérieures des clients.

À partir de FormIt **18.0**, vous pouvez implémenter la gestion des versions de votre plug-in en 3 étapes simples :

* Ajoutez un fichier _versions.json_ à la racine de votre répertoire de plug-ins.
* Spécifiez chaque version de FormIt compatible, ainsi que le répertoire contenant ces fichiers de plug-in, dans le fichier _versions.json_.
* Utilisez le numéro de version interne de FormIt, ou « numéro de build », dans FormIt sous Infos > À propos.



### Comment organiser la gestion des versions de votre plug-in

Organisez vos fichiers et répertoires de plug-in pour qu’ils correspondent au fichier _versions.json_.

Votre fichier _versions.json_ doit ressembler à ceci :

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

Les chemins ci-dessus _v18\_0_ et _v19\_0_ doivent être des sous-chemins valides à partir de la racine de votre répertoire/référentiel.

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

Une bonne gestion consiste à déplacer votre code de plug-in dans des sous-répertoires. En utilisant le fichier _versions.json_ ci-dessus, une structure de répertoire se présenterait comme suit :

* **versions.json** (fichier)
* **v18\_0** (répertoire)

   * **manifest.json** (fichier)
   * **plugin.html** (fichier)
   * **plugin.js** (fichier)


* **v19\_0** (répertoire)
   * **manifest.json** (fichier)
   * **plugin.html** (fichier)
   * **plugin.js** (fichier)

Les propriétés facultatives de la version sont « exactVersion » et « lastVersion ». « exactVersion » indique que la version doit correspondre exactement à la version de FormIt. « lastVersion » indique la dernière version autorisée à s’exécuter dans FormIt.\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

Il est également possible d’utiliser les branches/tags/commits git pour vos chemins d’accès.

Si vous travaillez avec une version bêta ou préliminaire de FormIt, et si vous souhaitez tester les modifications apportées à un plug-in qui fonctionne uniquement avec la version préliminaire :

* Suivez les étapes ci-dessus, à l’exception de l’utilisation du nom de fichier _versions\_pre_release.json_.
* Si vous validez _versions\_pre-release_ dans votre référentiel, vous devrez le supprimer après publication de cette version préliminaire de FormIt.
   * Dans le cas contraire, les futures versions préliminaires de FormIt chargeront le plug-in à partir d’un emplacement qui pourrait être obsolète ou destiné à une version antérieure.
