# 版本管理

在開發和更新外掛程式時，您可能需要在某個時刻管理程式碼的版本。

例如，FormIt 的 API 可能會隨著不同版本而變更，而且，雖然您希望新版本的外掛程式使用新的 FormIt 或 WSM API，但您也希望外掛程式在舊版用戶端中持續保持運作。

從 FormIt **v18.0** 開始，您可以透過三個簡單步驟來實行外掛程式的版本管理：

* 將 _versions.json_ 檔案加入外掛程式目錄的根目錄
* 在 _versions.json_ 中指定每個相容的 FormIt 版本，以及包含這些外掛程式檔案的目錄
* 使用在 FormIt 的「資訊」>「關於」下找到的 FormIt 內部版本號碼 (也就是「建置號碼」)。



### 如何組織外掛程式的版本管理

組織外掛程式檔案和目錄以便與 _versions.json_ 相符

您的 _versions.json_ 應該類似下面：

```
        [
            {
                "version":{
                    "major":18,
                    "minor":0
                },
                "path":"v18_0"
            },
            {
                "version":{
                    "major":19,
                    "minor":1
                },
                "path":"v19_0"
            }
        ]

```

上述路徑 _v18\_0_ 和 _v19\_0_ 必須是目錄/儲存庫根目錄中的有效子路徑。

![](../../../.gitbook/assets/i1.png)

![](../../../.gitbook/assets/i2.png)

![](../../../.gitbook/assets/i3.png)

處理此問題的一個好方法是將您的外掛程式碼移至子目錄。使用上述 _versions.json_，目錄結構將類似下面：

* **versions.json** (檔案)
* **v18\_0** (目錄)

   * **manifest.json** (檔案)
   * **plugin.html** (檔案)
   * **plugin.js** (檔案)


* **v19\_0** (目錄)
   * **manifest.json** (檔案)
   * **plugin.html** (檔案)
   * **plugin.js** (檔案)

version 的可選性質為「exactVersion」和「lastVersion」。「exactVersion」表示版本必須與 FormIt 的版本完全相符。「lastVersion」表示允許在 FormIt 中執行的上一個版本。\


```
[
    {
      "version":{
        "major":18,
        "minor":0,
        "exactVersion":true
        },
        "path":"v18_0"
    },
    {
        "version":{
            "major":19,
            "minor":1,
            "lastVersion":true
       },
        "path":"v19_0"
    }
 ]
```

也可以對路徑使用 git 分支/標籤/提交。

如果您使用 FormIt 的預先發行版或 Beta 版，並且想測試只能與預先發行版搭配使用的外掛程式所做的變更：

* 請遵循上述步驟，但使用檔名 _versions\_prerelease.json_
* 如果您將 _versions\_prerelease_ 提交到您的儲存庫，最好在發行該 FormIt 預先發行版時將其移除
   * 否則，未來的 FormIt 預先發行版可能會從報廢或用於舊版的位置載入外掛程式
