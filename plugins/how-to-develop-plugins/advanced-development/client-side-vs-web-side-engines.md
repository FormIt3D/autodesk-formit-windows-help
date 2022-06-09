# Moteurs côté client et Web

Les plug-ins FormIt utilisent deux moteurs JavaScript distincts :&#x20;

* Groupe de fonctions affichant le code HTML (côté Web)
* Le côté client (FormIt) effectue des appels à FormIt et à son noyau de géométrie.&#x20;

Ces deux moteurs JavaScript fonctionnent selon des processus distincts.

## **Côté client (FormIt) et côté Web (HTML)**

FormIt exécute plusieurs moteurs JavaScript simultanément :

* L’application FormIt possède son propre moteur JavaScript
* Chaque barre d’outils de plug-in possède son propre moteur JavaScript.
* Chaque groupe de fonctions de plug-in possède son propre moteur JavaScript (Chromium).

Les plug-ins peuvent spécifier l’emplacement de chargement du script JavaScript :

![](../../../.gitbook/assets/d14.png)

### Côté client (FormIt)

Spécifié à l’aide de [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8)

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]

```

### Côté Web (HTML)

Spécifié à l’aide de [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7)

* Les scripts côté Web sont chargés à partir de la page Web.
* Les scripts côté Web peuvent appeler le script JavaScript côté client (FormIt) à l’aide de plusieurs appels asynchrones.

## Trois méthodes pour appeler des commandes côté client (FormIt) à partir d’un plug-in Web :

### Méthode 1 : FormItInterface.CallMethod

`CallMethod` prend un nom de fonction et les arguments qui seront exécutés côté FormIt. La fonction transmise sera appelée avec le résultat de l’appel de la fonction.

```
    var args = {
        "w": 10,
        "l": 10,
        "h": 10
    }
    FormItInterface.CallMethod("CreateBlock", args, function(result)
    {
        // Result of the function call
    });
```

**Avantages :**&#x20;

➕ Pas besoin de `await`.&#x20;

**Inconvénients :**&#x20;

➖ Un rappel est nécessaire pour obtenir le résultat et s’appelle « who know when ».&#x20;

➖ Les scripts sont définis à deux emplacements différents.&#x20;

➖ La logique du plug-in doit être divisée en deux fichiers différents.

### **Méthode 2 : FormIt.CallJS**&#x20;

**\*Disponible uniquement dans FormIt 2022.1 et versions ultérieures**

CallJS utilise la fonction JavaScript pour un appel côté FormIt et l’objet arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);

```

**Avantages :**&#x20;

➕ Le résultat est disponible en cas de besoin

**Inconvénients :**&#x20;

➖ **** Vous devez ajouter await à tous les appels asynchrones. Si vous oubliez, rien ne fonctionnera comme prévu.

➖ **** Potentiellement plus lent en raison de `await`

### **Méthode 3 (asynchrone/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Avec un appel asynchrone, le côté Web appelle le côté FormIt. Cet appel commence dans un processus, est envoyé à un autre processus, puis le résultat est transmis au processus de départ. C’est pourquoi await est nécessaire.&#x20;

Seules les API FormIt intégrées peuvent être appelées par défaut.

**Avantages :**&#x20;

➕ Le résultat est disponible en cas de besoin.&#x20;

➕ Permet de combiner tout le code dans un seul fichier JS exécuté côté Web, sans script défini dans manifest.json.

**Inconvénients :**&#x20;

➖ **** Vous devez ajouter `await` à tous les appels asynchrones. Si vous oubliez, rien ne fonctionnera comme prévu.&#x20;

➖ **** Potentiellement plus lent en raison de `await.`

### Méthode 4 (RegisterAsyncAPI)&#x20;

**\*Disponible uniquement dans FormIt 2023.0 et versions ultérieures**&#x20;

Pour appeler une fonction définie par l’utilisateur dans FormIt, la fonction doit être enregistrée. Par exemple :&#x20;

**Côté client (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Côté Web (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Reportez-vous à la rubrique [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0) pour obtenir un exemple.

**Avantages :**&#x20;

➕ Le résultat est disponible en cas de besoin.&#x20;

➕ Permet de combiner tout le code dans un seul fichier JS exécuté côté Web, sans script défini dans manifest.json.

**Inconvénients :**&#x20;

➖ **** Vous devez ajouter await à tous les appels asynchrones. Si vous oubliez, rien ne fonctionnera comme prévu.&#x20;

➖ **** Potentiellement plus lent en raison de `await.`

##
