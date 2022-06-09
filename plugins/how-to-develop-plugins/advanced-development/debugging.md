# デバッグ

FormIt プラグインのデバッグに必要な操作方法は、デバッグするエンジンによって異なります。(エンジンの詳細については、[前のセクション](client-side-vs-web-side-engines.md)を参照してください)

### **クライアント側(FormIt)のデバッグ**

ツールバーベースおよびパネルベースの両方のプラグインに適用する FormIt 側のコードでデバッグするには、コードに行を追加して、デスクトップ アプリケーションの組み込み JS デバッガを開きます。

`debugger`

![](../../../.gitbook/assets/debugger.gif)

### **Web 側(HTML)のデバッグ**

パネルは基本的にスタイル設定とスクリプトを持つ HTML の Web サイトであるため、パネルベースの FormIt プラグインには HTML ベースの UI デバッグが用意されています。

パネルに組み込まれ、スクリプトとスタイル設定があるプラグインの HTML 側コードをデバッグするには、次のように操作します。

* **FormIt for Windows 2021.1 以降**
   * プラグインの HTML ページを右クリックして[Debug]をクリックし、アプリケーションの組み込み HTML デバッガを表示します。

![](../../../.gitbook/assets/debugpanelplugin.gif)

* **FormIt for Web**
   * ブラウザの HTML デバッガを表示するには、ショートカットの[F12]または[Ctrl]+[Shift]+[I]を使用します。

![](../../../.gitbook/assets/debugonweb.gif)

