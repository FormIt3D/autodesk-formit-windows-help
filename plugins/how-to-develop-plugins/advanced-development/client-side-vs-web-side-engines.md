# Mechanizmy po stronie klienta i po stronie WWW

We wtyczkach programu FormIt wykorzystywane są dwa różne mechanizmy JavaScript:&#x20;

* Panel wyświetlający HTML (po stronie WWW)
* Strona klienta (program FormIt) wywołuje program FormIt i jego jądro geometrii.&#x20;

Te dwa mechanizmy JavaScript działają w odrębnych procesach.

## **Strona klienta (FormIt) i strona WWW (HTML)**

Program FormIt uruchamia wiele mechanizmów JavaScript jednocześnie:

* Aplikacja FormIt ma własny mechanizm JavaScript
* Każdy pasek narzędzi wtyczki ma własny mechanizm JavaScript.
* Każdy panel wtyczki ma własny mechanizm JavaScript (Chromium)

Wtyczki mogą określać, gdzie wczytywany jest kod JavaScript:

![](../../../.gitbook/assets/d14.png)

### Strona klienta (FormIt)

Jest to określane przy użyciu pliku [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8)

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]

```

### Strona WWW (HTML)

Jest to określane przy użyciu pliku [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7)

* Skrypty po stronie WWW są wczytywane ze strony internetowej.
* Skrypty po stronie WWW mogą wywoływać kod JavaScript po stronie klienta (FormIt) za pomocą wielu wywołań asynchronicznych.

## Trzy metody wywoływania poleceń po stronie klienta (FormIt) z poziomu wtyczki opartej na technologii WWW:

### Metoda 1. FormItInterface.CallMethod

`CallMethod` pobiera nazwę funkcji i argumenty, które będą uruchamiane po stronie programu FormIt. Przekazana funkcja zostanie wywołana z wynikiem wywołania funkcji.

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

**Zalety:**&#x20;

➕ Nie potrzeba `await`.&#x20;

**Wady:**&#x20;

➖ Do uzyskania wyniku potrzebne jest wywołanie zwrotne, o którym nie wiadomo, kiedy nastąpi.&#x20;

➖ Skrypty są zdefiniowane w dwóch różnych miejscach.&#x20;

➖ Logika wtyczki musi być podzielona między dwa różne pliki.

### **Metoda 2. FormIt.CallJS**&#x20;

**\*Jest to dostępne tylko w programie FormIt 2022.1 i nowszych wersjach**

Funkcja CallJS przyjmuje funkcję JavaScript do wywołania po stronie programu FormIt i obiekt arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);

```

**Zalety:**&#x20;

➕ Wynik jest dostępny, gdy jest potrzebny

**Wady:**&#x20;

➖ **** Wszystkie wywołania asynchroniczne należy opatrzyć „await”: pominięcie tego spowoduje bałagan.

➖ **** Metoda jest potencjalnie wolniejsza z `await`

### **Metoda 3 (asynchronicznie z oczekiwaniem)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Po stronie WWW następuje wywołanie asynchroniczne strony programu FormIt. To wywołanie rozpoczyna się w jednym procesie, zostaje wysłane do innego procesu, a jego wynik zostaje przekazany z powrotem do procesu początkowego. Dlatego też potrzebne jest oczekiwanie.&#x20;

Domyślnie można wywoływać tylko wbudowane interfejsy API programu FormIt.

**Zalety:**&#x20;

➕ Wynik jest dostępny, gdy jest potrzebny.&#x20;

➕ Umożliwia połączenie całego kodu w jednym pliku JS uruchamianym po stronie WWW, bez definiowania skryptów w pliku manifest.json.

**Wady:**&#x20;

➖ **** Wszystkie wywołania asynchroniczne należy opatrzyć `await`: pominięcie tego spowoduje bałagan.&#x20;

➖ **** Metoda jest potencjalnie wolniejsza z `await.`

### Metoda 4 (RegisterAsyncAPI)&#x20;

**\*Jest to dostępne tylko w programie FormIt 2023.0 i nowszych wersjach**&#x20;

Aby można było wywoływać funkcję zdefiniowaną przez użytkownika po stronie programu FormIt, ta funkcja musi być zarejestrowana. Na przykład:&#x20;

**Strona klienta (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Strona WWW (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Aby zapoznać się z przykładem, zobacz [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0).

**Zalety:**&#x20;

➕ Wynik jest dostępny, gdy jest potrzebny.&#x20;

➕ Umożliwia połączenie całego kodu w jednym pliku JS uruchamianym po stronie WWW, bez definiowania skryptów w pliku manifest.json.

**Wady:**&#x20;

➖ **** Wszystkie wywołania asynchroniczne należy opatrzyć „await”: pominięcie tego spowoduje bałagan.&#x20;

➖ **** Metoda jest potencjalnie wolniejsza z `await.`

##
