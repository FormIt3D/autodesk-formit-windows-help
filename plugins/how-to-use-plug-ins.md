# プラグインの使用方法

![](<../.gitbook/assets/g3 (1).gif>)

## Plugin Manager

FormIt Plugin Manager では、1 つの場所でプラグインの検索と管理を行うことができます。

FormIt がインターネットにアクセスできる限り、Plugin Manager は FormIt の起動時に自動的にロードされます。

アプリケーションの右側にあるプラグのアイコン ![](https://formit3d.github.io/FormItExamplePlugins/docs/images/PluginManagerTab.PNG) をクリックしてアクセスします。

![](../.gitbook/assets/c1.PNG)

## プラグインのカテゴリ

Plugin Manager では、プラグインがカテゴリ別に分類されているため、関心の高いプラグインを簡単に見つけることができます。

![](../.gitbook/assets/d16.png)

**Installed** プラグイン: ユーザによって既にインストールされているプラグイン。&#x20;

**Recommended** プラグイン: FormIt の主要機能を拡張し、新しいワークフローを実現するために FormIt チームが推奨するプラグイン。コミュニティで開発されたプラグインは、FormIt チームによって承認された後に、ここに表示されます。\
GitHub のタグ: _formit-plugin-recommended_

**Public**プラグイン: コミュニティによってビルドされたプラグイン。このカテゴリのプラグインは、FormIt チームによる確認や承認がまだ行われていません。\
GitHub のタグ: _formit-plugin_

**For Developers** プラグイン: 新しい FormIt プラグインを作成できるように、コミュニティによってビルドされたプラグイン。\
GitHub のタグ: _formit-plugin-developers_

## プライベート プラグイン(ローカル プラグイン)を追加する

[独自のプラグインを開発する](how-to-develop-plugins/)場合は、パネル下部のフィールドにプライベート URL を入力して、[+]ボタンをクリックします。

![](../.gitbook/assets/d4.PNG)

プライベート プラグイン(ローカル プラグイン)の追加に関する詳細については、次の章を参照してください: [Plugin Manager でプラグインをプレビューする](how-to-develop-plugins/advanced-development/previewing-a-plugin-in-the-plugin-manager.md)

## Plugin Manager をリセットする

Plugin Manager は、インストールされたリポジトリとプラグインを保存するために、Windows のレジストリ キーを使用します。 Plugin Manager を既定にリセットする必要がある場合は、次のレジストリ キーを削除します。

`Computer\HKEY_CURRENT_USER\Software\Autodesk\FormIt 360\Plugins`

⚠️ 注: これにより、ユーザが追加したすべてのリポジトリとプラグインがアンインストールされ、Plugin Manager がリセットされて内蔵リポジトリとプラグインのみが含まれるようになります。

## プラグインをインストールする

[Plugin Manager](how-to-use-plug-ins.md#plugin-manager) には多数のプラグインが含まれ、さまざまなカテゴリに分類されています。各プラグインには、名前、説明、GitHub リンク、およびインストールの切り替えスイッチがあります。&#x20;

![](../.gitbook/assets/d5.PNG)

プラグインをインストールするには、プラグイン名の横の切り替えスイッチをオンにします。&#x20;

![](../.gitbook/assets/d6.png)

選択したプラグインのアイコンが右側のパネルに表示されます。プラグインの UI を表示するには、このアイコンをクリックします。

![](../.gitbook/assets/d7.PNG)

## プラグインを使用する

各プラグインには、その開発者が定義した固有の UI があります。プラグインには、通常、使用方法に関する一連の指示、一連のパラメータ(テキスト ボックス、スライダ、チェックボックスなど)、およびプラグインを実行するための 1 つまたは複数のボタンがあります。

たとえば、Plugin Manager でシンプルな例として「Fillet 2D Corners」を使用します。最初に、Plugin Manager の Recommended セクションからこのプラグインをロードします。次に、開発者の指示に従ってフィレット半径を設定し、フィレットする面のグループを選択して Fillet Corners ボタンをクリックします。

![](../.gitbook/assets/g4.gif)

##

