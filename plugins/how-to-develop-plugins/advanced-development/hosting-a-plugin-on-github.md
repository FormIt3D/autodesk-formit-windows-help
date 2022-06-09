# GitHub にプラグインをホストする

便利なプラグインをビルドし、共有を希望する場合は、GitHub にリポジトリをホストして、他のユーザが [Plugin Manager](../../how-to-use-plug-ins.md#plugin-manager) からプラグインをインストールできるようにすることができます。

### プラグイン プロジェクトをホストする

このプロセスは、前の章で説明した、Plugin Playground で作成した[プラグインをパブリッシュする](../your-first-plugin/publishing-your-project.md)方法と似ています。

GitHub の新しいプラグインのリポジトリ(例: https://github.com/Joe/JoesPlugins)に移動します

上部のメニューで、[Settings] > [Pages]をクリックします。[Source]の下にある[None]ボタンをクリックし、[main branch]を選択します。[Save]をクリックします。

![](<../../../.gitbook/assets/image (74).png>)

### ローカルでプラグイン プロジェクトの更新を続ける

この時点では、ローカルでプラグインの追加、変更、およびテストを続けることができます。パブリッシュの準備が整ったら、GitHub Desktop または別の Git クライアントを使用して GitHub リポジトリに変更をプッシュします。リポジトリとプラグインを使用するユーザは、FormIt の起動時に、常に最新のコードを取得します。

### プロジェクトをパブリッシュする

[Plugin Playground](../your-first-plugin/plugin-playground.md) ではなく、IDE で作成されたプロジェクトの場合は、プラグインのリポジトリに **FormIt-plugin** トピックを追加することで、プラグインをパブリッシュできます。

これにより、[コミュニティのプラグイン](../../example-1/formit-plugin-community.md)のリストでプラグインを見つけてもらうことができます。

プロジェクトのリンク(例: https://github.com/Joe/JoesPlugin)にアクセスして、GitHub 上でリポジトリを表示します。

右上隅にある[Settings]をクリックします。

![](<../../../.gitbook/assets/image (39).png>)

プラグインの説明を追加し、[Topics]フィールドに formit-plugin を追加して、変更を保存します。

![](<../../../.gitbook/assets/image (54).png>)

保存すると、プラグイン プロジェクトが[コミュニティのプラグイン](https://github.com/topics/formit-plugin)のリストに追加されます。

###
