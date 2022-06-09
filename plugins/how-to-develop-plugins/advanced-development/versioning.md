# 版本控制

在开发和更新插件时，有时可能需要对代码进行版本控制。

例如，FormIt 的 API 可能在不同版本之间有变化，尽管您可能想要新版本的插件使用新的 FormIt 或 WSM API，但您还希望该插件在旧客户端中能够正常工作。

从 FormIt **v18.0** 开始，可以通过 3 个简单步骤实现插件的版本控制：

* 将 _versions.json_ 文件添加到插件目录的根目录
* 在 _versions.json_ 中，指定每个兼容的 FormIt 版本以及包含这些插件文件的目录
* 使用在 FormIt 中的“信息”>“关于”下找到的 FormIt 内部版本号或“内部版本号”。



### 如何组织插件的版本控制

组织插件文件和目录以匹配 _versions.json_

您的 _versions.json_ 应如下所示：

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

上述路径 _v18\_0_ 和 _v19\_0_ 必须是目录/存储库根目录中的有效子路径。

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

处理此问题的绝佳方法是将插件代码移至子目录中。使用上述 _versions.json_ 时，目录结构将如下所示：

* **versions.json**（文件）
* **v18\_0**（目录）

   * **manifest.json**（文件）
   * **plugin.html**（文件）
   * **plugin.js**（文件）


* **v19\_0**（目录）
   * **manifest.json**（文件）
   * **plugin.html**（文件）
   * **plugin.js**（文件）

版本的可选特性为“exactVersion”和“lastVersion”。“exactVersion”指示版本必须与 FormIt 的版本完全匹配。“lastVersion”指示允许在 FormIt 中运行的上一个版本。\


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

还可以对路径使用 Git 分支/标记/提交。

如果您使用的是 FormIt 的预发布版或 Beta 版，并且想要测试对仅适用于预发布版的插件的更改：

* 请按照上述步骤操作，但使用文件名 _versions\_prerelease.json_
* 如果将 _versions\_prerelease_ 提交到您的存储库，则您会想要在 FormIt 的预发布版发布时将其删除
   * 否则，未来预发布的 FormIt 版本将从可能已过时或适用于旧版本的位置加载插件
