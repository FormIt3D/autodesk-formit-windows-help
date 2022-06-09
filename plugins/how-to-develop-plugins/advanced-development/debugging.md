# 调试

调试 FormIt 插件需要不同的过程，具体取决于您正在调试的引擎。（有关引擎的详细信息，请查看[上一节](client-side-vs-web-side-engines.md)）

### **客户端 (FormIt) 调试**

要在 FormIt 端代码（适用于基于工具栏和面板的插件）中进行调试，可以在代码中添加一行来弹出桌面应用程序的内置 JS 调试器：

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Web 端 (HTML) 调试**

基于面板的 FormIt 插件提供基于 HTML 的 UI 调试，因为这些面板从根本上来说都是带有样式设置和脚本的 HTML 网站。

要调试内置到面板的插件的 HTML 端代码（包括脚本和样式设置），请执行以下操作：

* **FormIt for Windows 2021.1 及更高版本**
   * 在插件 HTML 页面上单击鼠标右键，然后单击“调试”以显示应用程序的内置 HTML 调试器。

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt for Web**
   * 使用快捷键 F12 或 Ctrl+Shift+I，可调出浏览器的 HTML 调试器。

![](../../../.gitbook/assets/debugonweb.gif)

