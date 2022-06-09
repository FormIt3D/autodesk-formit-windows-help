# 创建基于工具栏的插件

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### 基于工具栏的插件 manifest.json 的结构

基于工具栏的插件有一个 _manifest.json_ 文件，其结构如下所示：

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

除了[标准 JSON 特性](../advanced-development/general-plugin-setup-in-the-manifest.md)之外，基于工具栏的插件还包括以下特殊 JSON 特性：

* “ToolbarURL”告知 FormIt 此插件是一个工具栏，并链接到描述该工具栏功能的另一个 JSON 文件的位置。

### 使用 JSON 配置工具栏格式

在创建如上所述的 manifest 文件后，需要创建 toolbar.json 文件，该文件定义工具栏按钮、其名称、文字、图标以及指定给每个按钮的 onClick 函数。该工具栏的 JSON 文件将具有以下格式：

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

该 toolbar.json 文件包括以下 JSON 特性：

* “name”表示整个工具栏的名称，并在内部用于将所有按钮都关联到单个工具栏菜单。
* “buttons”表示在工具栏内添加的各个按钮。工具栏可以包含任意数量的按钮。
* “name”定义按钮的内部名称，该名称用于将按钮关联到工具栏以及关联到按钮的 onClick 函数。
* “command”定义按钮的函数，该函数可以采用以下两种形式之一：JavaScript 函数（可以在 manifest.json 的“Scripts”字段中包含的脚本中定义）或 FormIt 命令（例如，“Draw: Circle”）。通过运行消息插件，可以获取 FormIt 命令列表。
* “iconText”设置按钮中的工具提示和描述文字。如果未提供图标 URL，则该文本将创建一个自动生成的格式化文字图标。
* “iconURL”可以设置为定义按钮的自定义图标。

在 toolbar.json 文件中完成定义所有按钮后，插件即可开始使用。&#x20;

如果要定义任何其他 JavaScript 函数，请将它们添加到 manifest.json 文件所在的同一个文件夹中。请务必将文件引用添加到 manifest 文件的“Scripts”字段，以便 FormIt 可以找到这些文件。
