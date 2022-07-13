# 设置 FormIt 以供开发

为了在 FormIt 桌面应用程序中测试和构建插件，您需要 FormIt for Windows v17.0 或更高版本。

### **显示脚本编辑器和脚本输出**

在 FormIt 的顶部菜单中，转到顶部菜单中的 **“窗口”**，然后选中 **“脚本编辑器”** 和 **“脚本输出”** 框。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

“脚本编辑器”和“脚本输出”面板将显示在 FormIt 窗口的底部。

使用底部的按钮在“脚本编辑器”和“脚本输出”之间切换。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

还可以并排排列这两个面板。单击右上角“x”旁边的按钮以拆离其中一个面板，然后将面板拖放到彼此相邻的位置：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **脚本编辑器(Script Editor)**

“脚本编辑器”提供了一个简单的开发环境，在其中可以编写和测试代码。

“脚本编辑器”将编写的代码存储在 FormIt.exe 文件所在目录中的 scratch.js 文件中。

顶部有两个按钮：

**运行** ![](<../../../.gitbook/assets/image (8).png>)：在窗口中执行已编写的所有代码。

**运行选择** ![](<../../../.gitbook/assets/image (52).png>)：仅执行选定/亮显的代码行。

### **脚本输出**

“脚本输出”窗口会显示从插件打印到控制台的任何消息。

可以通过在“脚本编辑器”中运行 `console.clear();` 来清除输出。

## 使用样例插件

在[克隆存储库](cloning-a-sample-plugin.md)并[设置 Web 服务器](hosting-a-plugin-on-a-local-server.md)后，现在可以使本地插件显示在 FormIt 中。

可以加载或安装任何插件，但出于本练习的目的，您将安装基于面板的插件和基于工具栏的插件。我们假定您的 npm http-server 正在托管两个示例存储库的端口 8080 上运行。

### **加载与安装**

`FormIt.LoadPlugin();` 仅为当前任务加载插件。当应用程序关闭并重新启动时，插件将自动卸载。

对于仅在当前任务中进行的测试，这是一个非常适用于临时显示插件的选项。

`FormIt.InstallPlugin();` 使用注册表项使插件持久存在。这非常适用于在任务之间经常使用的插件。

在 Windows 上，以下注册表项用于持久化插件：

* 插件：Computer\HKEY\_CURRENT\_USER\Software\Autodesk\FormIt 360\Plugins\InstalledPlugins

使用 `FormIt.UninstallPlugin();` 进行卸载。

在以下示例中，除非另有说明，否则可以随意使用_安装_或_加载_，具体取决于您是否希望练习结果保持不变。

### **工具栏插件样例：翻转路径**

在“脚本编辑器”中，输入以下内容：

如果运行的是本地服务器：

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

如果从 [FormIt GitHub 存储库](https://github.com/FormIt3D/)加载（需要连接 Internet）：

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

您应该会看到“翻转路径”工具栏显示在应用程序窗口的顶部：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **HTML 面板插件样例：特性+**

在“脚本编辑器”中，输入以下内容：

如果运行的是本地服务器：

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

如果从 [FormIt GitHub 存储库](https://github.com/FormIt3D/)加载（需要连接 Internet）：

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

您应该会看到“特性+”面板显示在应用程序窗口的右侧：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **模态和无模态对话框插件样例**

对话框插件是唯一的：只能加载，不能安装。

在“脚本编辑器”中，输入以下内容：

如果运行的是本地服务器：

* 模态：`FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* 无模态：`FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

如果从 [FormIt GitHub 存储库](https://github.com/FormIt3D/)加载（需要连接 Internet）：

* 模态：`FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* 模态：`FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

您应该看到“您好，块！”面板（来自 HTML 面板示例）在屏幕上显示为模式或无模式对话框。
