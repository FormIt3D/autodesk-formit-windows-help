# 建立一個 HTML 面板外掛程式

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

顯示 HTML 頁面的面板式外掛程式有一個結構如下的 _manifest.json_ 檔案：

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

除了[標準的 JSON 性質](../advanced-development/general-plugin-setup-in-the-manifest.md)，面板式外掛程式還包括以下特殊的 JSON 性質：

* 「Panel」告訴 FormIt 此外掛程式是一個面板，並連結至應載入面板中的 HTML 檔案位置。
* HTML 檔案的標頭中需要指向相應 JavaScript 檔案的連結，以及用於設定樣式的 CSS 檔案。
* HTML 檔案將在 FormIt 面板中呈現，如同在瀏覽器中一樣。
* 您可以在 [FormIt3D 組織](https://github.com/FormIt3D/)中查看 Rich HTML 介面的範例。
* 「PanelIcon」定義此外掛程式顯示在應用程式右側頁籤中的圖示。如果未定義，FormIt 會使用外掛程式名稱的首字母建立自動圖示。

設定 HTML、CSS 和 JavaScript 檔案後，您可以透過[載入或安裝](../advanced-development/setting-up-formit-for-development.md#load-vs.-install)來開始測試 HTML 面板外掛程式。
