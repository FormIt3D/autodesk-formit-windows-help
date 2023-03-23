# Engines auf der Client- und Web-Seite

FormIt-Plugins verwenden zwei unterschiedliche JavaScript-Engines:

* Die Gruppe, die den HTML-Code anzeigt (Web-Seite)
* Die Client-Seite (FormIt) sendet Aufrufe an FormIt und den Geometrie-Kernel.

Diese beiden JavaScript-Engines arbeiten in unterschiedlichen Prozessen.

## **Client-Seite (FormIt) und Web-Seite (HTML)**

FormIt führt mehrere JavaScript-Engines gleichzeitig aus:

* Die FormIt-Anwendung verfügt über eine eigene JavaScript-Engine.
* Jeder Plugin-Werkzeugkasten verfügt über eine eigene JavaScript-Engine.
* Jede Plugin-Gruppe verfügt über eine eigene JavaScript-Engine (Chromium).

Plugins können festlegen, wo JavaScript geladen wird:

![](../../../.gitbook/assets/d14.png)

### Client-Seite (FormIt)

Durch [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8) angegeben

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### Web-Seite (HTML)

Durch [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7) angegeben

* Web-Seiten-Skripte werden von der Webseite geladen.
* Web-Seiten-Skripte können JavaScript auf der Client-Seite (FormIt) mit mehreren asynchronen Aufrufen anrufen.

## Drei Methoden zum Aufrufen von Client-Seiten-Befehlen (FormIt) von einem webbasierten Plugin:

### Methode 1: FormItInterface.CallMethod

`CallMethod` verwendet einen Funktionsnamen und die Argumente, die auf der FormIt-Seite ausgeführt werden. Die übergebene Funktion wird mit dem Ergebnis des Funktionsaufrufs aufgerufen.

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

**Vorteile:**

➕ Kein `await` erforderlich

**Nachteile:**

➖ Ein Rückruf ist erforderlich, um das Ergebnis zu erhalten. Dieser erfolgt "wann auch immer".

➖ Skripte werden an zwei verschiedenen Stellen definiert.

➖ Plugin-Logik muss in zwei verschiedene Dateien aufgeteilt werden.

### **Method 2: FormIt.CallJS**

***Nur in FormIt 2022.1 und höher verfügbar**

CallJS verwendet die auf der FormIt-Seite aufzurufende JavaScript-Funktion und das arguments.json-Objekt.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**Vorteile:**

➕ Das Ergebnis dann verfügbar, wenn es gebraucht wird.

**Nachteile:**

➖ **** Alle async-Aufrufe müssen mit await ausgezeichnet werden. Wenn dies vergessen wird, gerät alles durcheinander.

➖ **** Möglicherweise langsamer aufgrund von `await`

### **Methode 3 (async/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Bei einem async-Aufruf ruft die Web-Seite die FormIt-Seite auf. Dieser Aufruf startet in einem Prozess, wird an einen anderen Prozess gesendet, und das Ergebnis wird an den Startprozess zurückgegeben. Deshalb ist await notwendig.

Nur integrierte FormIt-APIs können vorgabemäßig aufgerufen werden.

**Vorteile:**

➕ Das Ergebnis ist dann verfügbar, wenn es gebraucht wird.

➕ Ermöglicht die Kombination des gesamten Codes in einer JS-Datei, die über die Web-Seite ausgeführt wird, ohne dass Skripts in manifest.json definiert sind.

**Nachteile:**

➖ **** Alle async-Aufrufe müssen mit `await` ausgezeichnet werden. Wenn dies vergessen wird, gerät alles durcheinander.

➖ **** Möglicherweise langsamer aufgrund von `await.`

### Methode 4 (RegisterAsyncAPI)

***Nur in FormIt 2023.0 und höher verfügbar**

Um eine benutzerdefinierte Funktion auf der FormIt-Seite aufzurufen, muss die Funktion registriert werden. Beispiel:

**Client-Seite (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Web-Seite (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Ein Beispiel finden Sie unter [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0).

**Vorteile:**

➕ Das Ergebnis ist dann verfügbar, wenn es gebraucht wird.

➕ Ermöglicht die Kombination des gesamten Codes in einer JS-Datei, die über die Web-Seite ausgeführt wird, ohne dass Skripts in manifest.json definiert sind.

**Nachteile:**

➖ **** Alle async-Aufrufe müssen mit await ausgezeichnet werden. Wenn dies vergessen wird, gerät alles durcheinander.

➖ **** Möglicherweise langsamer aufgrund von `await.`

##
