# HTML パネルのプラグインを作成する

![](<../../../.gitbook/assets/PANEL BASED PLUGIN.gif>)

HTML ページを表示するパネルベースのプラグインには、次の構造を持つ _manifest.json_ ファイルがあります。

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

[一般的な JSON プロパティ](../advanced-development/general-plugin-setup-in-the-manifest.md)に加えて、パネルベースのプラグインには、次の特殊な JSON プロパティが含まれています。

* 「Panel」は、このプラグインがパネルであること、およびパネルにロードする必要がある HTML ファイルの場所へのリンクを、FormIt に伝えます。
* HTML ファイルのヘッダには、適切な JavaScript ファイルおよびスタイル設定用の CSS ファイルへのリンクが必要です。
* HTML ファイルは、ブラウザの場合と同様に、FormIt パネルでレンダリングされます。
* [FormIt3D Organization](https://github.com/FormIt3D/) には、HTML インタフェースの例が数多く用意されています。
* 「PanelIcon」は、アプリケーションの右側のタブに表示されるこのプラグインのアイコンを定義します。未定義の場合は、FormIt によってプラグイン名の頭文字を使用したアイコンが自動で作成されます。

HTML、CSS、および JavaScript ファイルを設定したら、[ロードまたはインストール](../advanced-development/setting-up-formit-for-development.md#load-vs.-install)して、HTML パネルのプラグインのテストを開始できます。
