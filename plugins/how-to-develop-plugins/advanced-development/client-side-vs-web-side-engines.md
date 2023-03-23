# Mecanismos do lado do cliente versus do lado da Web

Os plug-ins do FormIt usam dois mecanismos diferentes do JavaScript:

* O painel que exibe o HTML (lado da Web)
* O lado do cliente (FormIt) faz chamadas para o FormIt e seu kernel de geometria.

Esses dois mecanismos do JavaScript funcionam em processos distintos.

## **Lado do cliente (FormIt) versus lado da Web (HTML)**

O FormIt executa vários mecanismos do JavaScript simultaneamente:

* O aplicativo do FormIt tem seu próprio mecanismo de JavaScript
* Cada barra de ferramentas de plug-in tem seu próprio mecanismo de JavaScript.
* Cada painel de plug-in tem seu próprio mecanismo de JavaScript (Chromium)

Os plug-ins podem especificar onde o JavaScript é carregado:

![](../../../.gitbook/assets/d14.png)

### Lado do cliente (FormIt)

Especificado usando [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8)

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### Lado da Web (HTML)

Especificado usando [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7)

* Os scripts do lado da Web são carregados na página da Web.
* Os scripts do lado da Web podem chamar o JavaScript do lado do cliente (FormIt) usando várias chamadas assíncronas.

## Três métodos para chamar comandos do lado do cliente (FormIt) com base em um plug-in baseado na Web:

### Método 1: FormItInterface.CallMethod

`CallMethod` usa um nome de função e os argumentos que serão executados no lado do FormIt. A função passada será chamada com o resultado da chamada de função.

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

**Prós:**

➕ Nenhum `await` necessário.

**Contras:**

➖ Um retorno de chamada é necessário para obter o resultado e é chamado de “quem sabe quando”.

➖ Os scripts são definidos em dois locais diferentes.

➖ Requer que a lógica de plug-in seja dividida em dois arquivos diferentes.

### **Método 2: FormIt.CallJS**

***Disponível somente no FormIt 2022.1 e versões mais recentes**

O CallJS leva a função JavaScript a ser chamada no lado do FormIt e no objeto arguments.json.

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**Prós:**

➕ O resultado está disponível quando necessário

**Contras:**

➖ **** É preciso decorar todas as chamadas assíncronas com await, esquecer de fazer isso complicará as coisas.

➖ **** Potencialmente mais lento devido a `await`

### **Método 3 (assíncrono/await)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

Com uma chamada assíncrona, o lado da Web chama o lado do FormIt. Essa chamada começa em um processo, é enviada para outro processo e, em seguida, o resultado é retornado ao processo inicial. É por isso que é necessário aguardar.

Somente as APIs do FormIt incorporadas podem ser chamadas por padrão.

**Prós:**

➕ O resultado está disponível quando necessário.

➕ Permite combinar todos os códigos em um arquivo JS executado na Web, sem scripts definidos no manifest.json.

**Contras:**

➖ **** É preciso decorar todas as chamadas assíncronas com `await`, esquecer de fazer isso complicará as coisas.

➖ **** Potencialmente mais lento devido a `await.`

### Método 4 (RegisterAsyncAPI)

***Disponível somente no FormIt 2023.0 e versões mais recentes**

Para chamar uma função definida pelo usuário no lado do FormIt, a função precisa ser registrada. Por exemplo:

**Lado do cliente (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Lado da Web (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

Consulte [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0) para obter um exemplo.

**Prós:**

➕ O resultado está disponível quando necessário.

➕ Permite combinar todos os códigos em um arquivo JS executado na Web, sem scripts definidos no manifest.json.

**Contras:**

➖ **** É preciso decorar todas as chamadas assíncronas com await, esquecer de fazer isso complicará as coisas.

➖ **** Potencialmente mais lento devido a `await.`

##
