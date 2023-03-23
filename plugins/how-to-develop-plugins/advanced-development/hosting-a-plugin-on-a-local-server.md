# 在本地服务器上托管插件

可以在 FormIt 中预览克隆的插件之前，您需要将其托管在本地服务器上。

### **在 IDE 中查看终端**

可以选择在 Visual Studio Code 中启动服务器，而不是启动单独的终端窗口。**** 在打开终端之前，请确保在 Visual Studio Code 中打开了正确的文件夹。

“视图”>“终端”（或快捷键“Ctrl + \`”）

\![](<../../../.gitbook/assets/image (11) (1).png>)

### 设置 HTTP 服务器

运行良好的 HTTP 服务器是 npm 的 [http-server](https://www.npmjs.com/package/http-server)。

首先，如果尚未安装 [NodeJS](https://nodejs.org/en/)，则需要下载并安装它。

如果在以下步骤中遇到错误，请尝试重新启动计算机以完成 NodeJS 安装。

在命令提示下，输入以下命令以全局安装 npm 的 _http-server_（一次性安装）。

* `npm install http-server -g`

\![](<../../../.gitbook/assets/image (47).png>)

### 启动本地服务器

完成设置后，在终端中运行以下命令来启动 npm http-server：

* `http-server`

\![](<../../../.gitbook/assets/image (84).png>)

提示 1：如果运行 http-server（全局或本地安装）时出现任何问题，则通过 npx 直接运行它可能会有所帮助：

* `npx http-server`

提示 2：对于 Windows 10/11 用户，如果在新计算机上运行脚本时遇到错误，这可能是由于设置被禁用造成的。若要解决此问题，请执行以下操作：

* 以管理员身份启动 PowerShell 脚本
* 输入： `Set-ExecutionPolicy RemoteSigned`

### 为 FormIt Web 开发

要为 FormIt Web 开发，只需改为运行以下命令：

* `http-server --cors`

\![](<../../../.gitbook/assets/image (10) (1).png>)

### 验证服务器

可以通过在 Web 浏览器中导航到以下地址来验证服务器：

* http://localhost:8080

您应该会在浏览器窗口中看到项目文件夹文件。

**如果使用的 Web 服务器与 npm 不同，则默认地址/端口可能不同。

\![](<../../../.gitbook/assets/image (41).png>)
