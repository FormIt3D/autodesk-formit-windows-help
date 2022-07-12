# 開発のために FormIt を設定する

FormIt デスクトップ アプリケーションでプラグインをテストおよびビルドするには、FormIt for Windows v17.0 以降が必要です。

### **スクリプト エディタとスクリプトの出力を表示する**

FormIt の上部メニューの **[ウィンドウ]** に移動し、**[スクリプト エディタ]** ボックスと **[スクリプトの出力]** ボックスをオンにします。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/EnableDevelopmentWindows.PNG)

[スクリプト エディタ]パネルと[スクリプトの出力]パネルが FormIt ウィンドウの下部に表示されます。

下部にあるボタンを使用して、[スクリプト エディタ]と[スクリプトの出力]を切り替えます。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditorDefaultState.PNG)

両方のパネルを並べて配置することもできます。右上隅にある「x」の横のボタンをクリックして、いずれかのパネルをアタッチ解除し、パネルをドラッグして横に並ぶように移動します。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/ScriptEditor+ScriptOutputConfiguration.gif)

### **スクリプト エディタ**

スクリプト エディタは、コードを記述およびテストできる簡単な開発環境を提供します。

スクリプト エディタに書き込まれたコードは、FormIt.exe ファイルと同じフォルダ内の scratch.js ファイルに格納されます。

上部には 2 つのボタンがあります。

**実行** ![](<../../../.gitbook/assets/image (8).png>): ウィンドウに書き込まれているすべてのコードを実行します。

**選択項目を実行** ![](<../../../.gitbook/assets/image (52).png>): 選択してハイライト表示されたコード行のみを実行します。

### **スクリプトの出力**

[スクリプトの出力]ウィンドウには、プラグインからコンソールに出力されたメッセージが表示されます。

[スクリプト エディタ]で `console.clear();` を実行すると、出力をクリアできます。

## サンプル プラグインを使用する

[リポジトリのクローンを作成](cloning-a-sample-plugin.md)し、[Web サーバを設定](hosting-a-plugin-on-a-local-server.md)したため、ローカル プラグインを FormIt に表示できる状態になっています。

プラグインはすべてロードまたはインストールが可能ですが、この演習では、パネルベースのプラグインとツールバーベースのプラグインの両方をインストールします。npm の http-server がポート 8080 で実行中で、例として使用する両方のリポジトリをホストしていることを前提としています。

### **ロードとインストールの違い**

`FormIt.LoadPlugin();` でプラグインをロードすると、現在のセッションのみで使用できます。プラグインは、アプリケーションを閉じて再起動すると、自動的にロード解除されます。

これは、現在のセッションのみでテストするためにプラグインを一時的に表示する場合に便利なオプションです。

`FormIt.InstallPlugin();` では、レジストリ キーを使用してプラグインが保持されます。これは、さまざまなセッションで頻繁に使用するプラグインに適しています。

Windows では、プラグインを保持するために次のレジストリ キーが使用されます。

* プラグイン: Computer\HKEY\_CURRENT\_USER\Software\Autodesk\FormIt 360\Plugins\InstalledPlugins

`FormIt.UninstallPlugin();` を使用してアンインストールします。

次の例では、特に指定がない限り、演習で作成したプラグインを保持するかどうかによって、__インストールと__ロードのどちらを使用してもかまいません。

### **ツールバー プラグインのサンプル: Flip Along**

スクリプト エディタで、次を実行します。

ローカル サーバを実行する場合

* `FormIt.LoadPlugin("http://localhost:8080/FlipAlong");`

[FormIt の GitHub にあるリポジトリ](https://github.com/FormIt3D/)からロードする場合(インターネット接続が必要)

* `FormIt.LoadPlugin("https://formit3d.github.io/FlipAlong");`

アプリケーション ウィンドウの上部に、[Flip Along]ツールバーが表示されます。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/FlipAlongToolbar.PNG)

### **HTML パネル プラグインのサンプル: Properties Plus**

スクリプト エディタで、次を実行します。

ローカル サーバを実行する場合

* `FormIt.LoadPlugin("http://localhost:8080/PropertiesPlus");`

[FormIt の GitHub にあるリポジトリ](https://github.com/FormIt3D/)からロードする場合(インターネット接続が必要)

`FormIt.LoadPlugin("https://formit3d.github.io/PropertiesPlus");`

アプリケーション ウィンドウの右側に[Properties Plus]パネルが表示されます。

![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PropertiesPlusPanel.png)

### **モーダル ダイアログおよびモードレス ダイアログのプラグインのサンプル**

ダイアログのプラグインは他のものとは異なり、ロードのみが可能で、インストールはできません。

スクリプト エディタで、次を実行します。

ローカル サーバを実行する場合

* モーダル: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModalDialog");`
* モードレス: `FormIt.LoadPlugin("http://localhost:8080/FormItExamplePlugins/ModelessDialog");`

[FormIt の GitHub にあるリポジトリ](https://github.com/FormIt3D/)からロードする場合(インターネット接続が必要)

* モーダル: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModalDialog");`
* モードレス: `FormIt.LoadPlugin("https://formit3d.github.io/FormItExamplePlugins/ModelessDialog");`

HTML パネルの例の[Hello Block!]パネルが、モーダル ダイアログまたはモードレス ダイアログとして画面上に表示されます。
