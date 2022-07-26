---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt for Windows には Dynamo が組み込まれており、非常に優れた計算設計ワークフローを実現します。

## FormIt + Dynamo の新機能

### **データ グラフ、Excel へのレベルの送信、切り子面のコントロール**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) では、[SendToFormIt ノードを使用せずに](formit-+-dynamo.md#graph-types) Dynamo グラフを実行できるようになり、[FormIt レベルを Excel に送信する](formit-+-dynamo.md#send-formit-levels-to-excel)機能が追加され、[新しい FormItGroupOptions ノードを使用してカーブとサーフェス切り子面](../tool-library/curve-+-surface-faceting.md)をコントロールできるようになりました。

### **寸法入力と JS API への早期アクセス**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) では、[使い慣れた FormIt の寸法を入力として使用する機能](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes)が追加され、[オブジェクト レベルのオプション](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes)が導入された他、[JavaScript API アクセス](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes)の早期プレビューが提供されるようになりました。[こちら](https://formit.autodesk.com/page/download)で入手できます。

### **複数の SendToFormIt ノード**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) には、[複数の SendToFormIt ノードとネストされた Dynamo グラフ](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)を使用する機能が追加されています。

### **SelectFromFormIt ノード**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) では、[SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードが追加され、常時接続されているセッション、マルチインスタンス編集などを実行できます。

## スタートアップ

インタフェースについて学習し、Dynamo フォルダを FormIt にリンクします。

### **初期セットアップ**

FormIt + Dynamo を初めて使用する場合は、Dynamo で 3D キャンバスを表示するため、まず初めに[システムを設定する](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes)必要があります。

### **[Dynamo]パネル**

[Dynamo]パネルを使用して、Dynamo の起動、Dynamo グループの配置、Dynamo グラフの編集を行います。

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **ローカルの Dynamo フォルダを追加および管理する**

* [Dynamo]パネルは[コンテンツ ライブラリ](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library)と同様に機能し、Dynamo ファイルを含むローカル フォルダをリンクして管理できます。
* [Dynamo]パネルでフォルダをリンクするボタンをクリックし、[基本設定]ダイアログ ボックスで再度(+)をクリックして、FormIt にリンクするフォルダを選択します。<img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* リンクされたフォルダを切り替えるには、ドロップダウンを使用します。

![](../.gitbook/assets/dynamo\_dropdown.png)

* [Dynamo]パネルでは、.dyn ファイルとサブフォルダのみを表示することができます。
* フィルタ バーを使用すると、Dynamo ファイルやサブフォルダをフィルタして、必要なファイルを簡単に見つけることができます。

![](../.gitbook/assets/dynamo\_filter.png)

## Dynamo のさまざまな利用方法

Dynamo でグラフを作成および編集したり、グラフを表示せずに FormIt でパラメータを変更することができます。また、その両方を同時に行うこともできます。

### **グラフ タイプ**

FormIt は、次の 3 種類の Dynamo グラフをサポートしています。

* データ グラフ: データ グラフには _SendToFormIt_ ノードがないため、FormIt を介してデータを表示したり渡すために使用されます。たとえば、データ グラフを使用して Excel にデータを送信したり、非ジオメトリック データを計算して Watch ノードに表示できます。
* ジオメトリ グラフ: このグラフではジオメトリがすぐに生成されます。パラメータを表示するにはキャンバスに配置する必要があります。サムネイルをクリックすると、3D シーンに配置するジオメトリがカーソル上に表示されます。このグラフには、少なくとも 1 つの _SendToFormIt_ ノードが存在し、グラフの最後でジオメトリを受け取る必要があります。
* 選択グラフ: このグラフでは、実行する前に FormIt で選択を行う必要があります。選択が必要な項目を示すプロンプトが FormIt の左上隅に表示されます。選択を行うとグラフが実行され、選択に対するジオメトリが生成されます。このグラフには、少なくとも 1 つの _SendToFormIt_ ノードが存在し、グラフの最後でジオメトリを受け取る必要があります。

![](../.gitbook/assets/dynamo-graph-types.png)

### **ジオメトリ グラフ: Dynamo グループを FormIt に配置する**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* [Dynamo]パネルで、実行する Dynamo グラフのサムネイルをクリックします。
   * 組み込みのサンプルを使用したり、独自の Dynamo ファイルの[ライブラリをリンクする](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)ことができます。
* ジオメトリを FormIt に配置すると、Dynamo グラフのコピーが FormIt ファイルに埋め込まれます。
   * ジオメトリを生成するには、[SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードをグラフ内の出力ジオメトリ ノードにアタッチする必要があります。
* SendToFormIt ノードからのジオメトリをカーソル上で配置できるようになります。
   * グラフに「入力」とマークされた [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードがある場合、FormIt はまず選択を要求し(各選択ノードを縦に並べます)、選択に対して正しい位置にジオメトリを生成します。
* 元の Dynamo ファイルのコピーが FormIt グループに組み込まれ、ソース グラフから独立するようになりました。
* 配置時に、[プロパティ]パネルが自動的に切り替わり、使用可能なパラメータが表示されます。

### **ジオメトリ グラフ: パラメータを修正する**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* Dynamo グループを配置した後、その配置した Dynamo グループを選択して[プロパティ]パネルに切り替えるか、グループをダブルクリックして自動的にプロパティに切り替えます。
   * Dynamo で「入力」とマークされた入力ノードがここに一覧表示されます。
   * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) の入力ノードはボタンとして上部に表示され、グラフの動作に使用する選択内容の更新に使用できます。
   * FormIt は次の入力ノードをサポートしています: Number Slider、Integer Slider、Boolean Toggles、Number/String フィールド
* FormIt の入力を変更し、[実行]をクリックします。[実行]ボタンが青に変わります。これはパラメータが変更されたため、グラフを実行する必要があることを示しています。
   * Dynamo はバックグラウンドで実行され、変更を処理して、更新されたジオメトリを FormIt に返します。
   * FormIt 2022 以降では、[プロパティ]パネルからの最初の実行で専用の Dynamo インスタンスを起動するようになり、その後の編集が大幅に高速化されました。
   * Dynamo の実行中に FormIt を引き続き使用することができます。&#x20;
* 各 SendToFormIt グループ内のすべてのジオメトリは、Dynamo グラフの実行時に削除されて置き換えられます。

### データ グラフ: FormIt レベルを Excel に送信する

FormIt 2023 以降では、Dynamo を使用して FormIt レベルを Excel に送信できます。&#x20;

* [サンプルの Dynamo グラフは、こちら](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn)からダウンロード可能です。
* [Dynamo]パレットで、Dynamo グラフが保存されたローカル フォルダを指定します。
* サムネイルを右クリックし、次のボタンをクリックします: _[埋め込まれたグラフを編集]_
* 任意の場所に空の Excel スプレッドシートを作成します。
* スプレッドシートの場所のフィールドを編集し、Excel スプレッドシートのパスを指定します。
* [シート名]など、任意のフィールドを編集します。
* Dynamo を閉じてグラフを保存します。

これで、サンプル ファイルをパレットでクリックするだけで、ジオメトリを生成することなく FormIt 内で実行できるようになります。&#x20;

[Dynamo]パレットに Dynamo の入力が表示され、グラフの結果を表示する Excel が開きます。&#x20;

モデルを変更したら、グラフのサムネイルを再度クリックするか、_[実行]_ ボタンをクリックして、最新バージョンの FormIt スケッチのレベル データでスプレッドシートを更新できます。

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### 新しい Dynamo ウィンドウを起動する

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* FormIt 2021 以降では、[Dynamo]パネルの[Dynamo を起動]ボタンをクリックすると、FormIt との接続セッションが自動的に開始されます。
   * これにより、Dynamo でグラフ テンプレートが開き、FormIt でテンプレー トジオメトリが自動的に生成されます。
   * 結果として得られたジオメトリは、現在のグループ編集コンテキストの原点にある新しいグループに表示されます。Dynamo を起動する前に目的のグループ コンテキストに入っておくことをお勧めします。&#x20;
   * テンプレートには、FormIt ノードと一部のサンプル ジオメトリの両方が含まれています。スライダを調整すると、両方のアプリケーションで立方体のサイズが調整されます。
   * ここから、さまざまな Dynamo グラフを開いたり、テンプレート内のこれらの基本コンポーネントを使用して新しいオブジェクトを作成したり、Dynamo で名前を付けて新しい場所に保存することができます。

### **埋め込まれたグラフとソース グラフを編集する**

既存の Dynamo グラフは、2 つの方法で編集できます。FormIt に配置済みの埋め込まれたグラフを編集する方法と、コンピュータに保存されているソース グラフを編集する方法です。

### **埋め込まれたグラフ**

Dynamo オブジェクトを FormIt に配置すると、その基礎となるグラフがコピーされ、現在の FormIt ファイルに埋め込まれます。Dynamo での編集は、**[埋め込まれたグラフを編集]** ボタンを使用して行います。

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* Dynamo グループを選択して[プロパティ]パネルに切り替えるか、グループをダブルクリックして自動的に[プロパティ]に切り替えます。
* **[埋め込まれたグラフを編集]** ボタンをクリックします。
* Dynamo 上部に表示されるファイル名に「(FormIt)」が含まれていることに注目してください。これは、この FormIt ファイルに埋め込まれているグラフを編集中であり、ソース グラフは変更されないことを意味します。
* 1 つまたは複数の [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードが、FormIt に送信するジオメトリに接続されていることを確認します。
* FormIt では、グラフを調整すると、ジオメトリに対する更新がリアルタイムで表示されます。
* Dynamo で変更を保存しない場合、FormIt は最後に保存されたバージョンの Dynamo グラフにロール バックします。
* 各 SendToFormIt グループ内のすべてのジオメトリは、Dynamo グラフの実行時に削除されて置き換えられます。

### **ソース グラフ**

ソース グラフは、[ローカル フォルダをリンク](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)した後に [Dynamo]パネルに表示されます。これらのグラフはコンピュータに保存され、[ソース グラフを編集]ボタンをクリックすることで Dynamo で編集できます。

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* [Dynamo]パネルに、Dynamo ファイルを含む[フォルダをリンク](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)し、パネル内のその場所までナビゲートします。&#x20;
* 編集する Dynamo グラフのサムネイルを右クリック(または矢印をクリック)して、**[ソース グラフを編集]** ボタンを選択します。
* Dynamo が要求されたグラフを開いて起動します。FormIt ではグラフの最終出力のジオメトリが表示されます。
   * 1 つまたは複数の [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードを入力として使用するグラフの場合、SelectFromFormIt ノードで選択を入力するまで結果のジオメトリが表示されない可能性があります。
* 結果として得られたジオメトリは、現在のグループ編集コンテキストの原点にある新しいグループに表示されます。
   * [ソース グラフを編集]をクリックする前に目的のグループ コンテキストに入っておくことをお勧めします。
* 編集が終了したら、保存して Dynamo を閉じます。FormIt では、ソース グラフがコピーされ、FormIt ファイルに埋め込まれています。
   * **ソース グラフ**をさらに編集する必要がある場合は、埋め込まれたコピーを削除して、次の手順に従います。

### **曲面 + サーフェス切り子面をコントロールする**

*   FormIt 2023 以降では、FormItGroupOptions ノード、SetCurveFacetingCount ノードおよび SetSurfaceFacetingCount ノードを使用して、SendToFormIt ノードにアタッチされた曲面とサーフェス切り子面をコントロールできるようになりました。

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* これらのノードは、曲面およびサーフェス切り子面のグローバル設定をオーバーライドします。これらの設定は、[編集]->[基本設定]->[単位 + 精度]で定義します。
* これは、Dynamo グラフで特定の切り子面の値を使用して曲線オブジェクトを生成する必要がある場合に非常に便利です。これにより、現在のセッションで実行する各 Dynamo グラフのグローバル設定を変更する必要がなくなります。

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* [編集]->[基本設定]->[単位 + 精度]で、切り子面の設定をグローバルに設定することもできます。
* [基本設定]で切り子面の品質を調整したら、グラフを再実行して、新しい切り子面のグローバル設定を使用します。

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[FormIt の曲面とサーフェス切り子面の設定の詳細はこちら](https://windows.help.formit.autodesk.com/v/japanese/tool-library/curve-+-surface-faceting)をご覧ください。

## Dynamo で FormIt グループを使用する

FormIt グループの機能を活用して、Dynamo のジオメトリを効率的に編成し、優れたワークフローを実現します。

### **グループと SelectFromFormIt ノード**

* [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードのジオメトリを選択する場合、代わりにジオメトリを FormIt グループに保存してグループを選択すると便利です。
   * これにより、選択した FormIt グループの内容を柔軟に変更し、そのグループを参照しているグラフを再実行するだけで、更新された結果を確認できます。
* グループ化されていないジオメトリを選択した場合、そのジオメトリを変更すると、次にグラフを実行する際にジオメトリを再選択するよう求められることがあります。

### **グループ内のジオメトリを生成する**

* Dynamo グラフを FormIt で実行すると、そのジオメトリ結果が FormIt グループに含まれます。
* グラフ内の各 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードは、ノード入力ポートからのジオメトリを含むサブグループを作成します。
* FormIt で Dynamo オブジェクトを生成すると、グラフ全体とそのパラメータがコピーとして FormIt ファイルに埋め込まれます。
* グラフを実行すると、各サブグループ内のジオメトリが削除されて再生成されます。
   * サブグループ内のジオメトリまたはサーフェスのペイントを変更する場合は注意が必要です。次に Dynamo グラフを実行するときに変更内容が失われてしまいます。
   * ただし、FormIt マテリアルを使用して内部のジオメトリではなくサブグループをペイントする場合、それらのマテリアルは実行操作間で維持されます。次を参照してください。

### **グループとマテリアルを使用する**

* 複数の **SendToFormIt** ノードを使用する場合、マテリアルごとにノードを整理して、異なるマテリアルを使用して別の FormIt サブグループをペイントすることができます。
* 次の例では、建物全体が FormIt の単純な平面から生成されていますが、建物の各コンポーネントには専用のマテリアルが必要であるため、独自の **SendToFormIt** ノードが用意されています。

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* 各サブグループにマテリアルを適用した後は、Dynamo の実行操作間でマテリアルが維持されます。

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **Dynamo グループをネストする**

* **SelectFromFormIt** ノードを使用して、ある Dynamo グラフからサブグループの結果を選択し、別のグラフの結果を導き出すことができます。&#x20;
* 上の例にある建物生成グラフのガラスの出力が、ビルトインの Storefront Curtainwall サンプルの選択ジオメトリとして使用されています。

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* 建物の形状を変更したら、マリオン システム グループを選択し、[プロパティ]パネルで[実行]をクリックします。
   * ガラス グループの内容は変更されましたが、グループ自体は変更されなかったため、グラフを再実行するときにガラスを再度選択する必要はありません。
* 上のモデルは、FormIt 2022 以降で **Dynamo Samples** の **Building Masses** サブフォルダに「Roof Planes Building」として提供されるようになりました。
* FormIt の豊富な機能と Dynamo を組み合わせて使用すると、マテリアルとネストされたロジックを含む完全なパラメトリック デザインを、強力なコンセプト モデラーのコンテキストで作成および調整できます。

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **標準の FormIt グループの動作が引き続き適用される**

* 上の説明を除き、FormIt の Dynamo グループは、他のグループと同じルールで動作します。
   * [Dynamo]パネルから新しい Dynamo オブジェクトを配置すると、固有のグループが作成されます。スケッチに既に配置されている同じオブジェクトのインスタンスには影響しません。
   * Dynamo グループのコピーと貼り付けを行うと、同じ状態を維持します。コピーの Dynamo グラフに変更を加えると、同じインスタンスのジオメトリも更新されます。ただし、固有である場合は更新されません。
   * Dynamo グループは、ショートカットの MU またはコンテキスト メニューを使用して固有にすることができます。

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## FormIt の基本ノード

FormIt と Dynamo の間でデータを送信する、最も高機能なノードです。

### **SendToFormIt ノード**

* FormIt で Dynamo オブジェクトを生成するには、必要なジオメトリ ノード出力を少なくとも 1 つの SendToFormIt ノードの _geometry_ 入力にアタッチします。

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions は FormIt 2022 の新しい(オプションの)ポートです。下の「**FormItGroupOptions ノード**」セクションで詳しく説明します。
* FormIt 2021.3 以降では、複数の SendToFormIt ノードを使用して Dynamo の結果を整理し、FormIt グループとサブグループにまとめることができます。
* Dynamo と FormIt グループの連携については[こちら](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)をご覧ください。

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* SendToFormIt ノードは、既定でオンになっている「出力」フラグを考慮します。ノードを右クリックして、次の内容を確認できます。

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* オンにすると、この SendToFormIt ノードにアタッチされたジオメトリが FormIt のサブグループ内に表示されます。
* オフにすると、ジオメトリは FormIt に送信されず、対応するサブグループ(存在する場合)は削除されます。

### **SelectFromFormIt ノード**

* FormIt 2021 以降では、FormIt からジオメトリを選択して、Dynamo グラフで入力として使用できます。

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* SelectFromFormIt ノードの名前は FormIt のプロンプトに使用されるため、選択する FormIt ジオメトリのタイプを示すような名前にする必要があります。

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* Dynamo グラフ エディタまたは[プロパティ]パネルで[FormIt から選択]ボタンをクリックすると、選択ウィザード モードが開始され、ジオメトリの選択手順を確認できます。

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* SelectFromFormIt ノードは、「入力」フラグを考慮します。これは、既定でオンになっています。これは、FormIt で選択が機能するよう、オンである必要があります。確認するノードを右クリックします。

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* 「入力」がオンになっている場合:
   * グラフの Dynamo パネルのサムネイルは、選択が必要であることを示しています。

![](../.gitbook/assets/dynamo\_patharray.png)

* グラフを実行する際に、FormIt 選択ウィザードでは、グラフの上部から開始して各 SelectFromFormIt ノードの選択を設定する手順が示されます。
* 最初に生成した後、FormIt [プロパティ]パネルには各 SelectFromFormIt ノードのボタンが表示されます。

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* これらをクリックすると選択ウィザードが起動し、最終的なジオメトリの生成に使用する選択を変更できます。グラフは、再選択後に自動的に再実行されます。

### **ヒント、テクニック、メモ**

* SelectFromFormIt ノードに目的のジオメトリのタイプを示す名前を付けます。たとえば、「Select Site Boundary (Edges)」と入力します。
   * 任意のタイプの FormIt ジオメトリを選択できますが、選択したジオメトリを FormIt グループに含めて[未処理のジオメトリの代わりに選択](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)することをお勧めします。
* 選択ベースの Dynamo グラフの結果を移動する必要がある場合は、まず選択ジオメトリを移動してからグラフを再実行します。この操作により、更新された選択ジオメトリが選択され、適切に位置が変更されます。&#x20;
   * また、Dynamo の結果**および**選択をグループ化して、含まれるグループを移動することもできます。
* FormIt ジオメトリを Dynamo に送信すると、ジオメトリを FormIt に戻したときに、すべての属性、マテリアル、またはネストされたグループが失われます。
* Dynamo で選択ベースのグラフを編集しているときに、FormIt で選択したジオメトリが変更された場合は、SelectFromFormIt ノードの[FormIt から選択]ボタンをクリックして、ジオメトリを再選択する必要があります。&#x20;
* FormIt で選択すると、アクティブな[選択フィルタ](https://windows.help.formit.autodesk.com/v/japanese/tool-library/select-edge-face-or-object#firuta)が適用されます。たとえば、FormIt の頂点を選択する場合は、選択フィルタで有効にする必要があります。

![](../.gitbook/assets/dynamo\_filterselection.png)

## その他の入力ノード

FormIt には Dynamo グラフを簡単にカスタマイズするための入力オプションが豊富にあります。

### **FormItLengthString ノード**

FormIt 2022.1.0 以降では、**FormItLengthString** ノードを使用して、アクティブなスケッチの FormIt の単位設定に関係なく、サポートされている FormIt の単位タイプ(フィート-インチ、インチ、m、cm、mm)で寸法を指定できます。

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

サポートされている他の入力ノードと同様に、_FormItLengthString_ は、「入力」としてマークされている場合には FormIt [プロパティ]パレットに表示され、名前を変更すると、新しい名前が FormIt に表示されます。

![](../.gitbook/assets/dynamo\_propertiespalette.png)

_FormItLengthString_ ノードの各インスタンスは任意の単位タイプで使用できるため、前述のように、単一の Dynamo グラフで単位を組み合わせて使用することができます。

### **生の数値から FormItLengthString への切り替え**

FormIt 2022.1.1 以降では、グラフを FormItLengthString ノードを使用するように切り替える(最初の FormItLengthString ノードをグラフ内に配置する)か、生の数値のみを使用するように切り替える(最後の FormItLengthString を削除する)かで、Dynamo でのグラフ編集中の特定の動作が変化します。

* グラフの編集中に [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードを使用する場合、前述のように生の数値と _FormItLengthString_ ノードの間で切り替えるには、各 _SelectFromFormItNode_ のジオメトリを再選択する必要があります。そうすることで、結果は引き続き FormIt で正しくスケールされます。
* 最初の FormItLengthString ノードをグラフに配置すると、寸法として使用するグラフ内のすべての数値(名前の数値の入力を含む)はメートル(Dynamo 内部のネイティブ単位)を参照します。
   * [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) ノードは変更を考慮し、FormIt で生成されたジオメトリが正しいサイズに維持されるようにします。
   * 逆に、グラフからすべての FormItLengthString ノードを削除すると、FormIt の単位設定が何であっても生の数値を参照するように切り替わります(旧来の動作)。
* _FormItLengthString_ ノードの数値出力もメートル単位になりますが、FormIt のジオメトリ結果のサイズは変更されません。

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **サポートされる他の入力ノード**

Dynamo で「入力」とマークされていると、標準の Dynamo 入力ノードが FormIt の[プロパティ]パネルに表示されます。

* Number Slider
* Integer Slider
* Number
* String
* Boolean Toggle

入力ノードの名前を変更すると(分かりやすくするために推奨します)、新しい名前が FormIt に表示されます。

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## その他の出力ノード

Dynamo から FormIt に非ジオメトリの結果を表示する方法はいくつかあります。

### **Watch ノード**

「出力」とマークされた Watch ノードは、FormIt 2022 以降の[プロパティ]パネルの[WATCH ノード出力]セクションに表示されます。

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **FormIt の通知を表示する**

FormIt 2022.1 以降では、**UI.ShowNotification** ノードを使用して、Dynamo グラフから FormIt 側の通知を表示できます。&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **FormIt コンソールにログを記録する**

FormIt 2022.1 以降では、**FormIt.ConsoleLog** ノードを使用して、追加データのログを FormIt アプリケーション コンソール([スクリプトの出力]ウィンドウ)に直接記録できます。

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt のさまざまな Options ノード

個々のジオメトリ レベルまたは含まれるグループ レベルで FormIt にデータを送信する方法をコントロールします。

### **FormItGeometryOptions**

FormIt 2022.1 以降では、**FormItGeometryOptions** ノードを使用して、個々の Dynamo ジオメトリを FormIt に送信する方法をカスタマイズできます。

* 生成された Dynamo グループ内の個々のジオメトリのレイヤを指定します。
* 生成された Dynamo グループ内の個々のジオメトリに対して、文字列属性を指定します。

_FormItGeometryOptions_ ノードは、_SendToFormIt_ ノードの上流工程で使用できます。

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 以降では、_SendToFormIt_ ノードの Dynamo グループを FormIt で生成する方法を **FormItGroupOptions** ノードを使用してカスタマイズできます。

* SendToFormIt ノードがジオメトリをメッシュとオブジェクトのどちらとして FormIt に送信するかを指定します。
* SendToFormIt ノードによって作成されたグループのレイヤを指定します。
* SendToFormIt ノードによって作成されたグループの文字列属性を指定します。

FormItGroupOptions ノードは、ノードを数珠つなぎにすることによって、任意の組み合わせで順番に使用できます。

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript API ノード

FormIt 2022.1 以降では、2 つの新しいノードを介して Dynamo から JavaScript API およびカスタム関数にアクセスできるようになりました。

### **CallJSAPI**

**CallJSAPI** ノードを使用すると、Dynamo から FormIt JavaScript API を直接呼び出すことができます。

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

関数名とパラメータについては、JavaScript に関するドキュメントを参照してください。このドキュメントは、[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) と [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (モデリング カーネル)の 2 つに分かれています。

**CallPluginJS**

一方、**CallPluginJS** ノードを使用すると、ロード済みのプラグインからカスタム関数を呼び出したり、スクリプト エディタ ウィンドウから実行されたスクリプトのスニペットを呼び出すことができます。

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

## 重要

### **動作環境**

* FormIt で Dynamo を使用するには、[FormIt for Windows](https://formit.autodesk.com/page/download) v17.0 以降が必要です。
   * FormIt と Dynamo の統合では、新機能が追加され、修正が定期的に行われるため、最新の更新プログラムが利用可能な場合はダウンロードすることをお勧めします。
* Windows 10 も必要です。技術的な理由から、古いバージョンの Windows のサポートは終了しました。

**トラブルシューティング**

* [NVIDIA または AMD グラフィックス カード](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/)、もしくは複数のカードを搭載したシステムを使用している場合は、必要に応じて FormIt と Dynamo を設定し、高性能な GPU を使用してください。
   * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
   * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * NVIDIA カードを使用している場合は、[NVIDIA コントロール パネルがインストールされていることを確認](https://whatsabyte.com/blog/find-nvidia-control-panel/)してください。
   * [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) または [AMD](https://www.amd.com/ja/support/kb/faq/dh-017) のコントロール パネルを使用して、独立したグラフィックス カードを使用するように次のアプリケーションを設定します。
* 英語以外のロケールを使用している場合、特定の Dynamo ノードの問題を回避するために、Windows 10 の地域設定を英語に設定する必要がある場合があります。
   * [開始]で「言語」を検索し、「言語設定」を選択します。
   * [言語]ダイアログの右上で、[管理用の言語の設定]をクリックします。
   * [システム ロケールの変更...]ボタンをクリックします。
   * 「英語(米国)」を選択します。
* 小さなジオメトリや数のグラフで FormIt の結果を生成できない場合は、Dynamo のスケーリング設定を[小]に変更してみてください。
   * [Dynamo メニュー] > [基本設定] > [一般] > [ジオメトリのスケーリング] > [小]

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **サポートを依頼する**

FormIt + Dynamo のヘルプが必要な場合は、[フォーラム](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=ja)でお知らせください。
