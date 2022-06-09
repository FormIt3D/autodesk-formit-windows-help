# 除錯

除錯 FormIt 外掛程式需要不同的程序，取決於您正在除錯的引擎。(如需引擎的更多資訊，請參閱[上一節](client-side-vs-web-side-engines.md))

### **用戶端 (FormIt) 除錯**

若要在 FormIt 端程式碼 (也適用於工具列式和面板式外掛程式) 中除錯，您可以在程式碼中加入一行，以跳出桌面應用程式的內建 JS 除錯器：

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **網頁端 (HTML) 除錯**

面板式 FormIt 外掛程式提供 HTML 式的使用者介面除錯，因為面板本質上是具有樣式設定和指令碼的 HTML 網站。

若要對建置為面板的外掛程式的 HTML 端程式碼 (包括指令碼和樣式設定) 除錯：

* **FormIt for Windows 2021.1 和更高版本**
   * 在外掛程式 HTML 頁面上按一下右鍵，然後按一下「除錯」以顯示應用程式的內建 HTML 除錯器。

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt for Web**
   * 使用快速鍵 F12 或 Ctrl + Shift + I 可帶出瀏覽器的 HTML 除錯器。

![](../../../.gitbook/assets/debugonweb.gif)

