# 測試一個結合 HTML 面板和工具列的外掛程式

您可以使用 FormIt for Windows 中內建的[腳本編輯器](../advanced-development/setting-up-formit-for-development.md)，輕鬆測試進行中的外掛程式

我們建議在測試時使用 `FormIt.LoadPlugin("URL");`，為此工作階段暫時載入外掛程式 (重新啟動 FormIt 後，外掛程式就會消失)。&#x20;

測試完成後，您可以使用 `FormIt.InstallPlugin("URL");` 在工作階段之間保留外掛程式。

**FormIt for Windows v17 和更高版本**

****

### **工具列外掛程式**

將外掛程式載入 FormIt，以查看最新的使用者介面並測試最新功能：

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

進行一些變更，然後使用上述指令再次載入外掛程式。

測試時，您可以在目前工作階段中載入同一個外掛程式的多個執行個體，每個執行個體都有自己的使用者介面。

請務必使用最新的使用者介面執行個體，以確保您正在測試最新的變更。



### **HTML 面板外掛程式**

將外掛程式載入 FormIt，以查看最新的使用者介面並測試最新功能：

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

進行一些變更，然後只需對面板按一下右鍵並選擇「硬重新載入」，即可重新載入有最新 HTML、CSS 和腳本的面板。

****

### **使用 Plugin Manager 預覽外掛程式**

載入外掛程式後，請參閱本指南[先前的章節](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md)。

****

### **強制清除 .JSON 檔案的網頁快取**

如果修改外掛程式或儲存庫的 manifest.json 檔案內的標題或描述，您可能需要在 FormIt for Windows 中強制清除快取，才能在下次重新載入 Plugin Manager 時看到這些變更生效。

FormIt for Windows 會將其網頁快取儲存在此處，您必須在 Windows 檔案總管中啟用隱藏的項目，才能看到「AppData」資料夾。

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

若要刪除網頁快取，只需刪除上面的「Default」資料夾，然後重新載入 Plugin Manager，就能看到更新的標題和描述。
