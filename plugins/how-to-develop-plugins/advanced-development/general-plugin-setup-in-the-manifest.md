# manifest での一般的なプラグインの設定

FormIt プラグインは、_manifest.json_ ファイルと呼ばれる主要なコア コンポーネントで構成されています。&#x20;

manifest ファイルは [JSON オブジェクト](https://www.json.org/json-ja.html)であり、取得するファイルと作成するプラグインの種類を FormIt のインフラストラクチャに伝えます。

### manifest.json の構造とプロパティ

manifest.json ファイルの構造は次のとおりです。追加のプロパティは、[ツールバーベースのプラグイン](../additional-development-options/creating-a-toolbar-based-plugin.md)か [HTML パネルベースのプラグイン](../additional-development-options/creating-an-html-panel-plugin.md)かによって異なります。

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

一般的なプラグインには、次の JSON プロパティが含まれています。

* 「PluginName」は内部でのプラグインの名前を表し、多くは [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager)
* 「PluginType」はプラグインの種類を表し、[Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) の説明に表示されるため、プラグインのインストール時に探すべきプラグインがわかります。
* 「PluginDescription」は [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) に表示され、プラグインの機能を伝えます。
* 「Scripts」には、プラグインとの関連付けが必要な外部スクリプトが一覧表示されます。これらのスクリプトは、FormIt アプリケーションにロードされ、プラグイン機能が呼び出されたときに実行されます。

![](<../../../.gitbook/assets/image (5).png>)

プラグインの開発を開始するには、プラグイン フォルダ内に manifest.json ファイルを作成します。次に、作成するプラグインがツールバーベースかパネルベースかを決定する必要があります。

![](<../../../.gitbook/assets/image (36).png>)

**注:** 上記の manifest.json ファイル全体で PLUGINLOCATION を必ず使用します。PLUGINLOCATION は大文字と小文字を区別します。FormIt は PLUGINLOCATION をそのプラグインのサーバの場所に置き換えます。
