# 测试组合的 HTML 面板和工具栏插件

可以使用 FormIt for Windows 中内置的[脚本编辑器](../advanced-development/setting-up-formit-for-development.md)，轻松测试正在处理的插件

建议您在测试时使用 `FormIt.LoadPlugin("URL");`，这会为此任务暂时加载插件（重新启动 FormIt 时，插件会消失）。&#x20;

完成测试后，可以使用 `FormIt.InstallPlugin("URL");` 在任务之间保留该插件。

**FormIt for Windows v17 及更高版本**

****

### **工具栏插件**

将插件加载到 FormIt 中，以查看最新 UI 并测试最新功能：

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

进行一些更改，然后使用上述命令再次加载插件。

在测试时，可以在当前任务中加载同一插件的多个实例，每个实例都具有其自己的 UI。

请务必使用最新的 UI 实例，以确保测试的是您最新的更改。



### **HTML 面板插件**

将插件加载到 FormIt 中，以查看最新 UI 并测试最新功能：

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

进行一些更改，然后只需在面板上单击鼠标右键并选择“硬重新加载”，即可加载带有最新 HTML、CSS 和脚本的面板。

****

### **使用插件管理器预览插件**

加载插件后，请参见[前一章](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md)以了解本手册。

****

### **强制清除 .JSON 文件的 Web 缓存**

如果在 manifest.json 文件中修改插件或存储库的标题或描述，则可能需要在 FormIt for Windows 中强制清除缓存，以便在下次重新加载“插件管理器”时看到这些更改生效。

FormIt for Windows 将其 Web 缓存存储在此处，您需要在“Windows 资源管理器”中启用隐藏的项目才能看到“AppData”文件夹。

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

要删除 Web 缓存，只需删除上面的“Default”文件夹，然后重新加载“插件管理器”以查看更新的标题和描述。
