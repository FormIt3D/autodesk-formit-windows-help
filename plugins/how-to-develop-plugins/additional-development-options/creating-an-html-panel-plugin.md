# 创建 HTML 面板插件

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

显示 HTML 页面的基于面板的插件有一个 _manifest.json_ 文件，其结构如下所示：

```
{
    "PluginName": "Hello Block!",
    "PluginType": "Panel",
    "PluginDescription": "Creates a panel with an HTML form that allows dimensional input for a 3D block which will get generated at the world origin.",
    "Scripts": [
        "PLUGINLOCATION/block.js"
    ],
    "Panel": "PLUGINLOCATION/hello_block.html",
    "PanelIcon": "PLUGINLOCATION/hello_block.png"
}               
```

除了[标准 JSON 特性](../advanced-development/general-plugin-setup-in-the-manifest.md)之外，基于面板的插件还包括以下特殊 JSON 特性：

* “面板”告知 FormIt 此插件是一个面板，并链接到应在该面板中加载的 HTML 文件的位置。
* HTML 文件需要标头中的链接指向相应 JavaScript 文件，以及指向 CSS 文件以进行样式设置。
* HTML 文件将在 FormIt 面板中渲染，就像在浏览器中一样。
* 可以在我们的 [FormIt3D 组织](https://github.com/FormIt3D/)中查看丰富的 HTML 界面示例。
* “PanelIcon”为此插件定义图标，该图标将显示在应用程序右侧的选项卡中。如果未定义，FormIt 会自动使用插件名称的首字母创建一个图标。

完成设置 HTML、CSS 和 JavaScript 文件后，可以通过[加载或安装](../advanced-development/setting-up-formit-for-development.md#load-vs.-install)来开始测试 HTML 面板插件。
