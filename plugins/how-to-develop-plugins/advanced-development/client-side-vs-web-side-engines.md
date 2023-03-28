# 用戶端與網頁端引擎

FormIt 外掛程式使用兩個不同的 JavaScript 引擎：

* 面板顯示 HTML (網頁端)
* 用戶端 (FormIt) 呼叫 FormIt 及其幾何圖形核心。

這兩個 JavaScript 引擎在不同的程序中工作。

## **用戶端 (FormIt) 與網頁端 (HTML)**

FormIt 會同時執行多個 JavaScript 引擎：

* FormIt 應用程式有自己的 JavaScript 引擎
* 每個外掛程式工具列都有自己的 JavaScript 引擎。
* 每個外掛程式面板都有自己的 JavaScript 引擎 (Chromium)

外掛程式可以指定 JavaScript 的載入位置：

![](../../../.gitbook/assets/d14.png)

### 用戶端 (FormIt)

使用 [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8) 指定

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### 網頁端 (HTML)

使用 [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7) 指定

* 網頁端指令碼是從網頁載入。
* 網頁端指令碼可以使用多個非同步呼叫，來呼叫用戶端 (FormIt) JavaScript。

## 從網頁式外掛程式呼叫用戶端 (FormIt) 指令有三種方法：

### 方法 1：FormItInterface.CallMethod

`CallMethod` 使用將在 FormIt 端上執行的函式名稱以及引數。傳入的函式將搭配函式呼叫的結果呼叫。

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

**優點：**

➕ 不需要 `await`。

**缺點：**

➖ 需要回呼才能得到結果，也就是所謂的「沒人知道何時」。

➖ 指令碼定義在兩個不同的位置。

➖ 需要將外掛程式邏輯分為兩個不同的檔案。

### **方法 2：FormIt.CallJS**

***只有 FormIt 2022.1 和更高版本提供**

CallJS 使用要在 FormIt 端呼叫的 JavaScript 函式和 arguments.json 物件。

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**優點：**

➕ 需要時就可以得到結果

**缺點：**

➖ **** 必須使用 await 裝飾所有非同步呼叫，忘記這樣做就會導致事情惡化。

➖ **** 速度可能會因為 `await` 而變慢

### **方法 3 (非同步/等待)**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

網頁端透過非同步呼叫來呼叫 FormIt 端。此呼叫會在一個程序中開始，傳送至另一個程序，然後結果會傳回到開始程序。這就是為什麼需要等待。

預設只能呼叫內建 FormIt API。

**優點：**

➕ 需要時就可以得到結果。

➕ 允許將所有程式碼合併到從網頁端執行的一個 JS 檔案中，不需要在 manifest.json 中定義任何指令碼。

**缺點：**

➖ **** 必須使用 `await` 裝飾所有非同步呼叫，忘記這樣做就會導致事情惡化。

➖ **** 速度可能會因為 `await.` 而變慢

### 方法 4 (RegisterAsyncAPI)

***只有 FormIt 2023.0 和更高版本提供**

若要在 FormIt 端呼叫使用者定義的函式，需要註冊該函式。例如：

**用戶端 (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**網頁端 (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

請參閱 [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0) 查看範例。

**優點：**

➕ 需要時就可以得到結果。

➕ 允許將所有程式碼合併到從網頁端執行的一個 JS 檔案中，不需要在 manifest.json 中定義任何指令碼。

**缺點：**

➖ **** 必須使用 await 裝飾所有非同步呼叫，忘記這樣做就會導致事情惡化。

➖ **** 速度可能會因為 `await.` 而變慢

##
