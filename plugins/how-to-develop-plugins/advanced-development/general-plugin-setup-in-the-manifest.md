# 清单中的常规插件设置

FormIt 插件由名为 _manifest.json_ 文件的关键核心组件组成。

清单文件是一个 [JSON 对象](http://www.json.org)，它会告知 FormIt 基础架构要获取哪些文件以及要创建哪种插件。

### Manifest.json 结构和特性

manifest.json 文件具有以下结构。它有其他特性，具体取决于它是[基于工具栏的插件](../additional-development-options/creating-a-toolbar-based-plugin.md)还是[基于 HTML 面板的插件](../additional-development-options/creating-an-html-panel-plugin.md)。

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

一个典型插件包括以下 JSON 特性：

* “PluginName”表示插件的名称，适用于内部的大多数显示目的，包括[插件管理器](../../how-to-use-plug-ins.md#plugin-manager)。
* “PluginType”表示插件的类型，让用户在[插件管理器](../../how-to-use-plug-ins.md#plugin-manager)描述中了解他们在安装插件时要查找的内容。
* “PluginDescription”会显示在[插件管理器](../../how-to-use-plug-ins.md#plugin-manager)中，以传达插件的功能。
* “Scripts”会列出与插件相关联的所需外部脚本，这些脚本将加载到 FormIt 应用程序中并可以在调用插件功能时执行。

\![](<../../../.gitbook/assets/image (5) (1).png>)

通过在插件文件夹中创建一个 manifest.json 文件，来开始开发插件。接下来，需要确定是创建基于工具栏的插件还是基于面板的插件。

\![](<../../../.gitbook/assets/image (36).png>)

**注意：**在上述 manifest.json 文件中使用 PLUGINLOCATION 是必不可少的，并且区分大小写。FormIt 会将 PLUGINLOCATION 替换为插件的服务器位置。
