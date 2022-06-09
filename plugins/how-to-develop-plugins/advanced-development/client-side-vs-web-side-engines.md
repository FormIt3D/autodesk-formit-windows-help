# Motori lato client e lato Web

I plug-in di FormIt utilizzano due motori JavaScript distinti:&#x20;

* Il pannello che visualizza il codice HTML (lato Web)
* Il lato client (FormIt) che effettua chiamate a FormIt e al relativo kernel di geometria.&#x20;

Questi due motori JavaScript funzionano in processi distinti.

## **Lato client (FormIt) e lato Web (HTML)**

FormIt esegue più motori JavaScript contemporaneamente:

* L'applicazione FormIt dispone di un motore JavaScript.
* Ogni barra degli strumenti del plug-in ha il suo motore JavaScript.
* Ogni pannello del plug-in ha il suo motore JavaScript (Chromium).

I plug-in possono specificare la posizione in cui viene caricato JavaScript:

![](../../../.gitbook/assets/d14.png)

### Lato client (FormIt)

Specificato utilizzando [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8)

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]

```

### Lato Web (HTML)

Specificato utilizzando [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7)

* Gli script lato Web vengono caricati dalla pagina Web.
* Gli script lato Web possono richiamare JavaScript lato client (FormIt) utilizzando più chiamate asincrone.

## Tre metodi per chiamare i comandi lato client (FormIt) da un plug-in basato sul Web:

### Metodo 1: FormItInterface.CallMethod

`CallMethod` utilizza un nome di funzione e gli argomenti che verranno eseguiti sul lato FormIt.  La funzione trasferita verrà chiamata con il risultato della chiamata di funzione.

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

**Vantaggi:**&#x20;

➕ Non è necessaria la parola chiave `await`.&#x20;

**Svantaggi:**&#x20;

➖ È necessario un callback per ottenere il risultato e viene chiamato "chi sa quando".&#x20;

➖ Gli script vengono definiti in due posizioni diverse.&#x20;

➖ Richiede di suddividere la logica del plug-in in due file diversi.

### **Metodo 2: FormIt.CallJS**&#x20;

**\*Disponibile solo in FormIt 2022.1 e versioni successive**

CallJS utilizza la funzione JavaScript da richiamare sul lato FormIt e l'oggetto arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);

```

**Vantaggi:**&#x20;

➕ Il risultato è disponibile quando necessario.

**Svantaggi:**&#x20;

➖ **** È necessario modificare tutte le chiamate asincrone con await; in caso contrario, ciò potrebbe provocare problemi.

➖ **** Si potrebbe verificare un rallentamento delle prestazioni a causa di `await`.

### **Metodo 3 (asincrono/in attesa)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Con una chiamata asincrona, il lato Web chiama il lato FormIt. Questa chiamata inizia in un processo, viene inviata ad un altro processo, quindi il risultato viene ritrasferito al processo iniziale. Per questo motivo è necessaria la parola chiave await.&#x20;

Per default è possibile richiamare solo le API di FormIt incorporate.

**Vantaggi:**&#x20;

➕ Il risultato è disponibile quando necessario.&#x20;

➕ Consente di combinare tutto il codice in un unico file JS eseguito dal lato Web, senza script definiti in manifest.json.

**Svantaggi:**&#x20;

➖ **** È necessario modificare tutte le chiamate asincrone con `await`; in caso contrario, ciò potrebbe provocare problemi.&#x20;

➖ **** Si potrebbe verificare un rallentamento delle prestazioni a causa di `await.`.

### Metodo 4 (RegisterAsyncAPI)&#x20;

**\*Disponibile solo in FormIt 2023.0 e versioni successive**&#x20;

Per chiamare una funzione definita dall'utente sul lato FormIt, è necessario registrare la funzione. Ad esempio:&#x20;

**Lato client (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Lato Web (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Vedere [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0) per un esempio.

**Vantaggi:**&#x20;

➕ Il risultato è disponibile quando necessario.&#x20;

➕ Consente di combinare tutto il codice in un unico file JS eseguito dal lato Web, senza script definiti in manifest.json.

**Svantaggi:**&#x20;

➖ **** È necessario modificare tutte le chiamate asincrone con await; in caso contrario, ciò potrebbe provocare problemi.&#x20;

➖ **** Si potrebbe verificare un rallentamento delle prestazioni a causa di `await.`.

##
