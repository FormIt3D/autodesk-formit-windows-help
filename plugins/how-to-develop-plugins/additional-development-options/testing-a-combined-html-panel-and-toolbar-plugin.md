# HTML パネルとツールバーを組み合わせたプラグインをテストする

FormIt for Windows の組み込みの[スクリプト エディタ](../advanced-development/setting-up-formit-for-development.md)を使用して、進行中のプラグインを簡単にテストできます。

テスト時には `FormIt.LoadPlugin("URL");` を使用することをお勧めします。これにより、このセッションのために一時的にプラグインがロードされます(FormIt を再起動するとプラグインはロード解除されます)。&#x20;

テストが完了した後に `FormIt.InstallPlugin("URL");` を使用すると、他のセッションでもプラグインを保持できます。

**FormIt for Windows v17 以降**

****

### **ツールバーのプラグイン**

プラグインを FormIt にロードし、最新の UI を表示して最新の機能をテストします。

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

変更を加えてから、上記のコマンドを使用してプラグインを再びロードします。

テスト時に、同じプラグインの多数のインスタンスが現在のセッションにロードされる可能性があります。インスタンスごとに独自の UI があります。

最新の UI インスタンスを使用して、最新の変更をテストするようにしてください。



### **HTML パネルのプラグイン**

プラグインを FormIt にロードし、最新の UI を表示して最新の機能をテストします。

* `FormIt.LoadPlugin("http://localhost:8080/YourPluginName");`

変更を加えてから、パネルを右クリックして[ハード再ロード]を選択すると、パネルが最新の HTML、CSS、スクリプトとともに再ロードされます。

****

### **Plugin Manager を使用してプラグインをプレビューする**

プラグインをロードしたら、このガイドの[前の章](../advanced-development/previewing-a-plugin-in-the-plugin-manager.md)を参照してください。

****

### **.JSON ファイルの Web キャッシュを強制的にクリアする**

プラグインまたはリポジトリの manifest.json ファイル内のタイトルや説明を変更した場合は、FormIt for Windows でキャッシュを強制的にクリアし、次回 Plugin Manager を再ロードするときにこれらの変更が反映されるようにする必要があります。

FormIt for Windows では、Web キャッシュが下記の場所に保存されます。AppData フォルダを表示するには、Windows エクスプローラで隠れた項目を表示するように設定する必要があります。

* C:\Users\user\AppData\Local\Autodesk\FormIt 360\QtWebEngine\Default

Web キャッシュを削除するには、上記の「Default」フォルダを削除します。その後 Plugin Manager を再ロードすると、更新されたタイトルと説明が表示されます。
