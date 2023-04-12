# 設定 FormIt 以進行開發

若要在 FormIt 桌面應用程式中測試和建置外掛程式，您需要 FormIt for Windows v17.0 或更高版本。

### **顯示腳本編輯器和腳本輸出**

在 FormIt 的頂端功能表中，移至頂端功能表的 **「視窗」**，勾選 **「腳本編輯器」** 和 **「腳本輸出」** 方塊。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

「腳本編輯器」和「腳本輸出」面板會顯示在 FormIt 視窗的底部。

使用底部的按鈕在「腳本編輯器」和「腳本輸出」之間切換。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

您也可以並排兩個面板。按一下右上角「x」旁邊的按鈕可分離其中一個面板，然後拖放面板到彼此旁邊：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **腳本編輯器**

腳本編輯器提供一個簡單的開發環境，您可以在其中編寫和測試程式碼。

腳本編輯器將編寫的程式碼儲存在 FormIt.exe 檔案所在的目錄中的 scratch.js 檔案內。

頂端有兩個按鈕：

**執行** \![](<../../../.gitbook/assets/image (8) (1).png>)：執行視窗中編寫的所有程式碼。

**執行選取項目** \![](<../../../.gitbook/assets/image (52).png>)：僅執行選取的/亮顯的程式碼行。

### **腳本輸出**

「腳本輸出」視窗會顯示任何來自外掛程式而列印到主控台的訊息。

您可以在腳本編輯器中執行 `console.clear();` 清除輸出。

## 使用範例外掛程式

在[複製儲存庫](cloning-a-sample-plugin.md)並[設定網頁伺服器](hosting-a-plugin-on-a-local-server.md)之後，您現在可以取得本端外掛程式在 FormIt 中展示。

您可以載入或安裝任何外掛程式，但為了進行本練習，您將同時安裝面板式外掛程式和工具列式外掛程式。我們將假設您裝載兩個範例儲存庫的 npm http-server 在連接埠 8080 上執行。

### **載入與安裝**

`FormIt.LoadPlugin();` 只會為目前的工作階段載入外掛程式。當應用程式關閉並重新啟動時，外掛程式會自動卸載。

這是一個很適合暫時顯示外掛程式的選項，僅供在目前工作階段中進行測試。

`FormIt.InstallPlugin();` 會讓外掛程式持續使用登錄機碼。這很適合您經常在不同工作階段使用的外掛程式。

在 Windows 中，以下登錄機碼用來保留外掛程式：

* Plugins: Computer\\HKEY_CURRENT_USER\\Software\\Autodesk\\FormIt 360\\Plugins\\InstalledPlugins

使用 `FormIt.UninstallPlugin();` 可解除安裝。

在下列範例中，除非另有說明，否則請根據您是否希望保留練習結果來自由使用_安裝_或_載入_。

### **工具列外掛程式範例：Flip Along**

在腳本編輯器中，執行下列程式碼：

如果執行本端伺服器：

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

如果從 [FormIt GitHub 儲存庫](https://github.com/FormIt3D/)載入 (需要網際網路連線)：

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

您應該會看到「Flip Along」工具列顯示在應用程式視窗的頂端：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **HTML 面板外掛程式範例：Properties Plus**

在腳本編輯器中，執行下列程式碼：

如果執行本端伺服器：

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

如果從 [FormIt GitHub 儲存庫](https://github.com/FormIt3D/)載入 (需要網際網路連線)：

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

您應該會看到「Properties Plus」面板顯示在應用程式視窗的右側：

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **排他式和共存式對話方塊外掛程式範例**

對話方塊外掛程式很獨特：只能載入，無法安裝。

在腳本編輯器中，執行下列程式碼：

如果執行本端伺服器：

* 排他式：`FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* 共存式：`FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

如果從 [FormIt GitHub 儲存庫](https://github.com/FormIt3D/)載入 (需要網際網路連線)：

* 排他式：`FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* 排他式：`FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

您應該會看到 HTML 面板範例中的「Hello Block!」面板在螢幕上顯示為一個排他式或共存式對話方塊。
