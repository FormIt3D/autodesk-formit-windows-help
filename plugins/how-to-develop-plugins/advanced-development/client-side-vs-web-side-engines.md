# 客户端与 Web 端引擎

FormIt 插件会利用两个不同的 JavaScript 引擎：

* 显示 HTML（Web 端）的面板
* 客户端 (FormIt) 会调用 FormIt 及其几何图形内核。

这两个 JavaScript 引擎在不同的进程中工作。

## **客户端 (FormIt) 与 Web 端 (HTML)**

FormIt 同时运行多个 JavaScript 引擎：

* FormIt 应用程序有其自己的 JavaScript 引擎
* 每个插件的“工具栏”都有其自己的 JavaScript 引擎。
* 每个插件的“面板”都有其自己的 JavaScript 引擎 (Chromium)

插件可以指定 JavaScript 的加载位置：

![](../../../.gitbook/assets/d14.png)

### 客户端 (FormIt)

使用 [manifest.json](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/manifest.json#L8) 指定

```
    "Scripts": [
        "PLUGINLOCATION/blockFormItSide.js",
        "https://formit3d.github.io/FormItExamplePlugins/SharedPluginFiles/PluginUtils18_0.js"
    ]
```

### Web 端 (HTML)

使用 [index.html](https://github.com/FormIt3D/FormItExamplePlugins/blob/master/HelloBlockAsync/v23\_0/index.html#L7) 指定

* Web 端脚本从网页加载。
* Web 端脚本可以使用多个异步调用，来调用客户端 (FormIt) JavaScript。

## 从基于 Web 的插件调用客户端 (FormIt) 命令的三种方法：

### 方法 1：FormItInterface.CallMethod

`CallMethod` 采用函数名称和将在 FormIt 端运行的参数。传入的函数将随函数调用的结果一起调用。

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

**优点：**

➕ 无需 `await`。

**缺点：**

➖ 需要回调来获取结果，称为“谁知道何时”。

➖ 脚本在两个不同的位置定义。

➖ 需要将插件逻辑拆分为两个不同的文件。

### **方法 2：FormIt.CallJS**

***仅在 FormIt 2022.1 及更高版本中可用**

CallJS 采用要在 FormIt 端调用的 JavaScript 函数和 arguments.json 对象。

```
var args =
{
    "w": 10,
    "l": 10,
    "h": 10
};
var result = await FormIt.CallJS("CreateBlock", args);
```

**优点：**

➕ 结果在需要时可用

**缺点：**

➖ **** 必须使用 await 装饰所有异步调用，忘记这样做会误事。

➖ **** 由于 `await`，速度可能会变慢

### **方法 3（异步/等待）**

```
const pt1 = await WSM.Geom.Point3d(0,0,0);
```

通过异步调用，Web 端将调用 FormIt 端。此调用在一个进程中开始、发送到另一个进程，然后将结果传回起始进程。这就是为什么需要等待的原因。

默认情况下，只能调用内置的 FormIt API。

**优点：**

➕ 结果在需要时可用。

➕ 允许将所有代码都合并到从 Web 端运行的一个 JS 文件中，而无需在 manifest.json 中定义脚本。

**缺点：**

➖ **** 必须使用 `await` 装饰所有异步调用，忘记这样做会误事。

➖ **** 由于 `await.`，速度可能会变慢

### 方法 4 (RegisterAsyncAPI)

***仅在 FormIt 2023.0 及更高版本中可用**

要在 FormIt 端调用用户定义的函数，需要注册该函数。例如：

**客户端 (FormIt)**

```
FormIt.RegisterAsyncAPI("HelloBlockAsync", "CreateBlock", "l, w, h");
// CreateBlock runs from FormIt.
HelloBlockAsync.CreateBlock = function(args)
{
    return { "Result" : "It Worked!!"};
}
```

**Web 端 (HTML)**

```
var result = await HelloBlockAsync.CreateBlock(l, w, h);
```

有关示例，请参见 [HelloBlockAsync](https://github.com/FormIt3D/FormItExamplePlugins/tree/master/HelloBlockAsync/v23\_0)。

**优点：**

➕ 结果在需要时可用。

➕ 允许将所有代码都合并到从 Web 端运行的一个 JS 文件中，而无需在 manifest.json 中定义脚本。

**缺点：**

➖ **** 必须使用 await 装饰所有异步调用，忘记这样做会误事。

➖ **** 由于 `await.`，速度可能会变慢

##
