# ローカル サーバにプラグインをホストする

クローンとして作成したプラグインを FormIt でプレビューする前に、ローカル サーバにホストする必要があります。

### **IDE でターミナルを表示する**

別のターミナル ウィンドウではなく、Visual Studio Code 内でサーバを開始するオプションがあります。 **** ターミナルを開く前に、適切なフォルダが Visual Studio Code で開いていることを確認してください。

[表示] > [ターミナル] (またはキーボード ショートカット[Ctrl]+[\`])

\![](<../../../.gitbook/assets/image (11) (1).png>)

### HTTP サーバを設定する

正常に動作する HTTP サーバは、npm の [http-server](https://www.npmjs.com/package/http-server) です。

[NodeJS](https://nodejs.org/en/) がまだインストールされていない場合は、ダウンロードしてインストールする必要があります。

次の手順でエラーが発生した場合は、コンピュータを再起動して NodeJS のインストールを完了してください。

コマンド プロンプトで、次のように入力して npm の _http-server_ をグローバルにインストールします(1 回限りの設定)。

* `npm install http-server -g`

\![](<../../../.gitbook/assets/image (47).png>)

### ローカル サーバを起動する

設定が完了したら、ターミナルで次のコマンドを実行して npm の http-server を起動します。

* `http-server`

\![](<../../../.gitbook/assets/image (84).png>)

ヒント 1: http-server を実行する際に問題が発生した場合は、インストールがグローバルでもローカルでも、npx を使用して直接実行するとうまくいく場合があります。

* `npx http-server`

ヒント 2: Windows 10/11 ユーザが新しいコンピュータでスクリプトを実行するときにエラーが発生した場合は、設定が無効になっていることが原因である可能性があります。そのためには、次のようにします。

* PowerShell スクリプトを管理者として起動します。
* 次のように入力します: `Set-ExecutionPolicy RemoteSigned`

### FormIt Web 用の開発

FormIt Web 用に開発するには、代わりに次のコマンドを実行します。

* `http-server --cors`

\![](<../../../.gitbook/assets/image (10) (1).png>)

### サーバを確認する

Web ブラウザで次のアドレスにナビゲートすると、サーバを確認できます。

* http://localhost:8080

ブラウザのウィンドウにプロジェクト フォルダのファイルが表示されます。

** npm 以外の Web サーバを使用している場合は、既定のアドレス/ポートが異なる可能性があります。

\![](<../../../.gitbook/assets/image (41).png>)
