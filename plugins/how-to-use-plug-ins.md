# 如何使用插件

![](<../.gitbook/assets/g3 (1).gif>)

## 插件管理器

“FormIt 插件管理器”是您发现和管理插件的一站式工具。

只要 FormIt 可以访问 Internet，则当 FormIt 启动时就会自动加载“插件管理器”。

通过单击应用程序右侧的选项卡图标![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG)访问它：

![](../.gitbook/assets/c1.PNG)

## 插件类别

插件管理器会将插件组织到不同的类别中，以帮助您查找最感兴趣的插件。

![](../.gitbook/assets/d16.png)

**已安装的插件：** 用户已安装的插件。&#x20;

**推荐的插件：** FormIt 团队推荐用于扩展 FormIt 的核心功能和解锁新工作流的插件。社区开发的插件在获得 FormIt 团队批准后会显示在此处。\
GitHub 标记：_formit-plugin-recommended_

**公共插件：** 由社区构建的插件。此类别中的插件尚未由 FormIt 团队审阅或批准。\
GitHub 标记：_formit-plugin_

**面向开发人员的插件**：由社区构建的插件，可用于创建新的 FormIt 插件。\
GitHub 标记：_formit-plugin-developers_

## 添加私有或本地插件

如果您正在[开发自己的插件](how-to-develop-plugins/)，可以将其私有 URL 添加到面板底部的字段中，然后单击 (+)：

![](../.gitbook/assets/d4.PNG)

有关如何添加私有或本地插件的详细信息，请参见[在插件管理器中预览插件。](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## 重置插件管理器

“插件管理器”使用 Windows 上的注册表项，来存储您安装的储存库和插件。 如果需要将“插件管理器”重置为其默认值，请删除以下注册表项：

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ 注意：这将卸载用户添加的所有存储库和插件，从而重置“插件管理器”以仅包含内置的存储库和插件。

## 安装插件

[插件管理器](how-to-use-plug-ins.md#plugin-manager)包含许多插件，它们组织在不同类别下。每个插件都有一个名称、描述、GitHub 链接和安装开关。&#x20;

![](../.gitbook/assets/d5.PNG)

要安装某个插件，只需打开该插件名称旁边的开关。&#x20;

![](../.gitbook/assets/d6.png)

选定插件的图标将显示在右侧面板中。单击它可显示插件的 UI。

![](../.gitbook/assets/d7.PNG)

## 使用插件

每个插件都有一个由其开发人员定义的唯一 UI。一个插件通常有一组关于如何使用它的说明、一组参数（文本框、滑块、复选框等），以及一个或多个执行它的按钮。

举个例子，我们将使用“插件管理器”中一个较简单的示例：圆角二维角点。首先，我们从“插件管理器”的“推荐”部分中加载插件。然后，按照开发人员提供的说明，我们设置圆角半径、选择一组要圆角化的面，然后单击“圆角”按钮。

![](../.gitbook/assets/g4.gif)

##

