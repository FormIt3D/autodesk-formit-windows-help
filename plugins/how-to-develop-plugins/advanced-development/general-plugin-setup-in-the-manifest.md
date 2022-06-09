# Manifest 中的一般外掛程式設定

FormIt 外掛程式由稱為 _manifest.json_ 檔案的關鍵核心元件組成。&#x20;

Manifest 檔案是一個 [JSON 物件](http://www.json.org)，可告知 FormIt 基礎架構要擷取的檔案以及要建立的外掛程式類型。

### Manifest.json 結構和性質

Manifest.json 檔案的結構如下。它還有其他性質，取決於是[工具列式](../additional-development-options/creating-a-toolbar-based-plugin.md)或 [HTML 面板式的外掛程式](../additional-development-options/creating-an-html-panel-plugin.md)。

```
{
    "PluginName": "[PluginName]",
    "PluginType": "[PluginType]"
    "PluginDescription": "[PluginDescription]",
    "Scripts": [
        "PLUGINLOCATION/[script1].js",
        "PLUGINLOCATION/[script2].js",
        ...
        "PLUGINLOCATION/[scriptn].js"
    ]
}               
```

典型外掛程式包括以下 JSON 性質：

* 「PluginName」表示外掛程式的名稱，用於內部和大多數顯示用途，包括 [Plugin Manager。](../../how-to-use-plug-ins.md#plugin-manager)
* 「PluginType」表示外掛程式的類型，可讓使用者在 [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) 描述中了解安裝外掛程式時要尋找的內容。
* 「PluginDescription」顯示在 [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) 中，負責傳遞外掛程式的功能。
* 「Scripts」列出與外掛程式關聯的所需外部指令碼，這些外部指令碼將載入 FormIt 應用程式，並可在呼叫外掛程式功能時執行。

![](<../../../.gitbook/assets/image (5).png>)

在外掛程式資料夾中建立 manifest.json 檔案，即可開始開發外掛程式。接下來，您要決定要製作工具列式外掛程式，還是面板式外掛程式。

![](<../../../.gitbook/assets/image (36).png>)

**注意:** 在上述 manifest.json 檔案中使用 PLUGINLOCATION 非常重要，且區分大小寫。FormIt 會以外掛程式的伺服器位置取代 PLUGINLOCATION。
