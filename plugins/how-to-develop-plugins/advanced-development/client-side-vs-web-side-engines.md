# Comparación entre motores del cliente y motores web

Los módulos de extensión de FormIt utilizan dos motores de JavaScript distintos, como se indica a continuación:&#x20;

* El panel que muestra el código HTML (motor web).
* El motor del cliente (FormIt) realiza las llamadas a FormIt y su núcleo de geometría.&#x20;

Estos dos motores de JavaScript funcionan en procesos distintos.

## **Comparación entre el lado del cliente (FormIt) y el lado web (HTML)**

FormIt ejecuta varios motores de JavaScript simultáneamente, como se indica a continuación:

* La aplicación FormIt cuenta con su propio motor de JavaScript.
* Cada barra de herramientas de módulo de extensión cuenta con su propio motor de JavaScript.
* Cada panel de módulo de extensión cuenta con su propio motor de JavaScript (Chromium).

Los módulos pueden especificar dónde se carga JavaScript, como se muestra a continuación:

![](../../../.gitbook/assets/d14.png)

### Lado del cliente (FormIt)

Se especifica mediante [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8).

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]

```

### Lado web (HTML)

Se especifica mediante [ index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7).

* Las secuencias de comandos del lado web se cargan desde la página web.
* Las secuencias de comandos del lado web pueden llamar al motor de JavaScript del cliente (FormIt) mediante varias llamadas asincrónicas.

## Hay tres métodos disponibles para llamar a comandos del lado del cliente (FormIt) desde un módulo de extensión basado en web, como se indica a continuación:

### Método 1: FormItInterface.CallMethod

`CallMethod` utiliza un nombre de función y los argumentos que se ejecutarán en el lado de FormIt. Se llamará a la función transferida con el resultado de la llamada a la función.

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

**Ventajas:**&#x20;

➕ No se`await` necesita.&#x20;

**Inconvenientes:**&#x20;

➖ Se necesita una llamada para obtener el resultado, que se denomina "quién sabe cuándo".&#x20;

➖ Las secuencias de comandos se definen en dos ubicaciones diferentes.&#x20;

➖ Requiere que la lógica del módulo de extensión se divida en dos archivos.

### **Método 2: FormIt.CallJS**&#x20;

**\* Disponible solo en FormIt 2022.1 y versiones posteriores**

CallJS utiliza la función de JavaScript a la que se va a llamar en el lado de FormIt y el objeto arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);

```

**Ventajas:**&#x20;

➕ El resultado está disponible cuando es necesario.

**Inconvenientes:**&#x20;

➖ **** Es necesario incluir "await" en todas las llamadas asincrónicas; si se olvida de realizar esta tarea, pueden producirse problemas.

➖ **** Posiblemente más lento debido a `await`.

### **Método 3 (async/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Con una llamada asincrónica, el lado web llama al lado de FormIt. Esta llamada se inicia en un proceso, se envía a otro proceso y, a continuación, el resultado se devuelve al proceso inicial. Por eso, es necesario el parámetro "await".&#x20;

Solo se puede llamar por defecto a las API de FormIt integradas.

**Ventajas:**&#x20;

➕ El resultado está disponible cuando es necesario.&#x20;

➕ Permite combinar todo el código en un archivo JS ejecutado desde el lado web sin secuencias de comandos definidas en manifest.json.

**Inconvenientes:**&#x20;

➖ **** Es necesario incluir `await` en todas las llamadas asincrónicas; si se olvida de realizar esta tarea, pueden producirse problemas.&#x20;

➖ **** Posiblemente más lento debido a `await.`.

### Método 4 (RegisterAsyncAPI)&#x20;

**\* Disponible solo en FormIt 2023.0 y versiones posteriores**&#x20;

Para llamar a una función definida por el usuario en FormIt, la función debe estar registrada. Por ejemplo:&#x20;

**Lado del cliente (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Lado web (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Para obtener un ejemplo, consulte [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0).

**Ventajas:**&#x20;

➕ El resultado está disponible cuando es necesario.&#x20;

➕ Permite combinar todo el código en un archivo JS ejecutado desde el lado web sin secuencias de comandos definidas en manifest.json.

**Inconvenientes:**&#x20;

➖ **** Es necesario incluir "await" en todas las llamadas asincrónicas; si se olvida de realizar esta tarea, pueden producirse problemas.&#x20;

➖ **** Posiblemente más lento debido a `await.`.

##
