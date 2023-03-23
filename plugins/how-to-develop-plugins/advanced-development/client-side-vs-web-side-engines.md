# Moduly na straně klienta a na straně webu

Moduly plug-in aplikace FormIt využívají dva odlišné moduly jazyka JavaScript:

* Panel zobrazující HTML (na straně webu)
* Klientská strana (FormIt) volá aplikaci FormIt a její geometrické jádro.

Tyto dva moduly jazyka JavaScript využívají různé procesy.

## **Klientská strana (FormIt) vs. webová strana (HTML)**

Aplikace FormIt spustí současně více modulů jazyka JavaScript:

* Aplikace FormIt má vlastní modul jazyka JavaScript.
* Každý panel nástrojů modulu plug-in má vlastní modul JavaScript.
* Každý panel modulu plug-in má vlastní modul JavaScript (Chromium).

Moduly plug-in mohou určovat, kde se JavaScript načte:

![](../../../.gitbook/assets/d14.png)

### Klientská strana (FormIt)

Určeno pomocí souboru [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8).

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### Webová strana (HTML)

Určeno pomocí souboru [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7).

* Skripty na webové straně se načítají z webové stránky.
* Skripty na webové straně mohou volat JavaScript na straně klienta (FormIt) pomocí několika asynchronních volání.

## Existují tři metody volání příkazů na straně klienta (FormIt) z webového modulu plug-in:

### Metoda 1: FormItInterface.CallMethod

`CallMethod` přijímá název funkce a argumenty, které budou spuštěny na straně aplikace FormIt. Předávaná funkce bude volána s výsledkem volání funkce.

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

**Výhody:**

➕ Není nutný parametr `await`.

**Nevýhody:**

➖ K získání výsledku je zapotřebí zpětné volání, které se volá „kdo ví kdy“.

➖ Skripty jsou definovány na dvou různých místech.

➖ Logiku modulu plug-in je nutné rozdělit do dvou různých souborů.

### **Metoda 2: FormIt.CallJS**

***K dispozici pouze ve verzi aplikace FormIt 2022.1 a novějších.**

CallJS převezme funkci jazyka JavaScript, která bude volána na straně aplikace FormIt, a objekt arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**Výhody:**

➕ Výsledek je k dispozici v případě potřeby

**Nevýhody:**

➖ **** Všechna asynchronní volání vyžadují parametr await, pokud na to zapomenete, nebude skript fungovat.

➖ **** Potenciálně pomalejší z důvodu nutnosti použití parametru `await`.

### **Metoda 3 (async/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Při asynchronním volání webová strana volá aplikaci FormIt. Toto volání se spustí v jednom procesu, odešle se do jiného procesu a výsledek se předá zpět do výchozího procesu. Proto je potřeba argument await.

Ve výchozím nastavení lze volat pouze integrovaná rozhraní API aplikace FormIt.

**Výhody:**

➕ Výsledek je k dispozici v případě potřeby.

➕ Umožňuje sloučit veškerý kód do jednoho souboru JS spouštěného ze strany webu bez skriptů definovaných v souboru manifest.json.

**Nevýhody:**

➖ **** Všechna asynchronní volání vyžadují parametr `await`, pokud na to zapomenete, nebude skript fungovat.

➖ **** Potenciálně pomalejší z důvodu nutnosti použití parametru `await.`.

### Metoda 4 (RegisterAsyncAPI)

***K dispozici pouze ve verzi aplikace FormIt 2023.0 a novějších.**

Chcete-li na straně aplikace FormIt volat uživatelem definovanou funkci, je nutné tuto funkci zaregistrovat. Příklad:

**Klientská strana (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Webová strana (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Příklad viz [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0).

**Výhody:**

➕ Výsledek je k dispozici v případě potřeby.

➕ Umožňuje sloučit veškerý kód do jednoho souboru JS spouštěného ze strany webu bez skriptů definovaných v souboru manifest.json.

**Nevýhody:**

➖ **** Všechna asynchronní volání vyžadují parametr await, pokud na to zapomenete, nebude skript fungovat.

➖ **** Potenciálně pomalejší z důvodu nutnosti použití parametru `await.`.

##
