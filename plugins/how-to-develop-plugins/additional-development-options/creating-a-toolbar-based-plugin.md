# ツールバーベースのプラグインを作成する

![](<../../../.gitbook/assets/Toolbar based plugin.gif>)

### ツールバーベースのプラグインの manifest.json の構造

ツールバーベースのプラグインには、次の構造を持つ _manifest.json_ ファイルがあります。

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

[一般的な JSON プロパティ](../advanced-development/general-plugin-setup-in-the-manifest.md)に加えて、ツールバーベースのプラグインには、次の特殊な JSON プロパティが含まれています。

* 「ToolbarURL」は、このプラグインがツールバーであること、およびツールバーの機能を記述する別の JSON ファイルの場所へのリンクを、FormIt に伝えます。

### JSON でツールバーの形式を設定する

上記のような manifest.json ファイルを作成した後に、toolbar.json ファイルを作成する必要があります。このファイルでは、ツールバーのボタン、ボタンの名前、テキスト、アイコン、および各ボタンに割り当てられる onClick 関数を定義します。ツールバーの JSON ファイルの形式は次のとおりです。

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

toolbar.json ファイルには、次の JSON プロパティが含まれています。

* 「name」はツールバー全体の名前を表し、すべてのボタンを単一のツールバー メニューに関連付けるために内部で使用されます。
* 「buttons」は、ツールバー内に追加される個々のボタンを表します。ツールバーには、任意の数のボタンを含めることができます。
* 「name」はボタンの内部名を定義します。この名前は、ボタンをツールバーおよびボタンの onClick 関数に関連付けるために使用されます。
* 「command」はボタンの機能を定義します。使用できる形式は 2 とおりあります。1 つは JavaScript 関数(manifest.json の「Scripts」フィールドに含まれるスクリプトで定義可能)、もう 1 つは FormIt コマンド(「Draw: Circle」など)です。Messages プラグインを実行すると、FormIt コマンドのリストを取得できます。
* 「iconText」はボタンのツールチップと説明テキストを設定します。アイコンの URL を指定しない場合は、決められた形式でテキストからアイコンが自動生成されます。
* 「iconURL」ではボタンのカスタム アイコンを定義できます。

ボタンがすべて toolbar.json ファイルで定義されると、プラグインを実行する準備が整います。&#x20;

定義する JavaScript 関数が他にもある場合は、manifest.json ファイルと同じフォルダに追加します。FormIt がこのファイルを見つけることができるように、manifest.json ファイルの「Scripts」フィールドにもファイル参照先を追加してください。
