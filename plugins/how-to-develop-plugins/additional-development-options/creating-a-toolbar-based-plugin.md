# 建立工具列式外掛程式

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### 工具列式外掛程式 manifest.json 的結構

工具列式外掛程式有一個結構如下的 _manifest.json_ 檔案：

```
{
    "PluginName": "Flip Along",
    "PluginType": "Toolbar",
    "PluginDescription": "Creates a toolbar with X, Y, and Z buttons to quickly flip selected geometry in the direction of the selected axis.",
    "ToolbarURL": "PLUGINLOCATION/toolbar.json",
    "Scripts": [
        "PLUGINLOCATION/flipalong.js"
    ]
}               
```

除了[標準的 JSON 性質](../advanced-development/general-plugin-setup-in-the-manifest.md)，工具列式外掛程式還包括此特殊的 JSON 性質：

* 「ToolbarURL」告訴 FormIt 此外掛程式是一個工具列，並連結至描述工具列功能的另一個 JSON 檔案的位置。

### 使用 JSON 規劃工具列格式

建立如上所述的 manifest 檔案後，您必須建立 toolbar.json 檔案，定義工具列按鈕、工具列名稱、文字、圖示，以及指定給每個按鈕的 onClick 函式。工具列的 JSON 檔案具有以下格式：

```
{
    "name": "Flip Along Toolbar",
    "buttons": [
        {
            "name": "Flip Along X",
            "command": "FlipAlongPlugin.ButtonX",
            "iconText": "X",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Y",
            "command": "FlipAlongPlugin.ButtonY",
            "iconText": "Y",
            "iconURL": "[Icon URL]"
        },
        {
            "name": "Flip Along Z",
            "command": "FlipAlongPlugin.ButtonZ",
            "iconText": "Z",
            "iconURL": "[Icon URL]"
        }
    ]
}               
```

toolbar.json 檔案包括以下 JSON 性質：

* 「name」表示整個工具列的名稱，在內部使用以將所有按鈕關聯至單一工具列功能表。
* 「buttons」表示在工具列內加入的個別按鈕。工具列可以有任意數量的按鈕。
* 「name」定義按鈕的內部名稱，用於將按鈕關聯至工具列以及按鈕的 onClick 函式。
* 「command」定義按鈕的函式，可以是兩種形式的其中一種：JavaScript 函式 (可在 manifest.json「Scripts」欄位中包含的指令碼中定義)，或 FormIt 指令 (例如「繪製: 圓」)。您可以執行 Messages 外掛程式取得 FormIt 指令的清單。
* 「iconText」設定按鈕中的工具提示和描述文字。如果未提供圖示 URL，則文字將建立格式化文字的自動產生圖示。
* 可以設定「iconURL」以定義按鈕的自訂圖示。

在 toolbar.json 檔案中定義所有按鈕後，外掛程式就準備好了。&#x20;

如果您要定義任何其他 JavaScript 函式，請將其加入與 manifest.json 檔案相同的資料夾。請務必將檔案參考加到 manifest 檔案的「Scripts」欄位，以便 FormIt 可以找到這些檔案。
