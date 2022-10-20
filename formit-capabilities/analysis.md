---
description: >- 
  BIM ワークフローでは、最初に、設計プロセスの初期段階から各種要素のパフォーマンスを評価します。
---

# 日照解析とエネルギー解析

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## FormIt でのエネルギー解析

設計プロセスの初期段階で、建築モデルのエネルギー効率を解析します。

[Insight プロジェクトを表示する](https://gbs.autodesk.com/OneEnergy/Insight)

## Insight を使用したエネルギー解析

[AEC コレクション](https://www.autodesk.com/collections/architecture-engineering-construction/overview)を通じて **FormIt Pro Subscription** を購入している場合は、**Insight** を使用してエネルギー解析を実行することができます。

* Green Building Studio の解析エンジンを使用して、早期段階の設計モデルを解析できます。
* 解析結果のダッシュボード ビューに接続して、設計の選択肢を比較します。
* 「窓対壁比」や「建物の向き」など、エネルギー解析の各種要因のウィジェットを調整できます。
* 面積あたりの最終的なコストが 1 つの数値として表示され、建物に対するエネルギーの影響が一目でわかります。
* クライアントをはじめとする各関係者による将来的なレビューのために、エネルギー解析の結果を保存することができます。

## FormIt + Insight の新機能 <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Insight の信頼性の向上** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) では、Insight の実行を開始する前にモデルの一般的な問題がチェックされ、Insight の一般的なエラーが修正されるようになりました。より信頼性の高いエクスペリエンスを提供します。
* また、FormIt 2021 では、FormIt + Insight 接続の信頼性が全般的に向上し、多くの既知のエラーが解決され、実行成功率が改善されました。

## スタートアップ <a href="#insight-getting-started" id="insight-getting-started"></a>

### **動作** <a href="#how-it-works" id="how-it-works"></a>

* Insight エネルギー解析では、FormIt モデル データをアップロードし、クラウドで数百回の解析を実行して、さまざまなエネルギー スコアを決定します。
* エネルギー解析では Revit を使用してモデルを解析するため、FormIt データを Revit に送信する場合と同様に、[FormIt モデルが密閉状態で多様体であることを確認する](https://formit.autodesk.com/blog/post/repairing-solid-models)必要があります。

### **FormIt モデルを準備する** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight は FormIt スケッチ内の表示ジオメトリを使用します。
  * 解析する建物シェルのみが表示ジオメトリであることを確認します。
  * 点景、家具、外構要素などの支持ジオメトリを別の[レイヤ](../tool-library/layers.md)に配置し、レイヤを非表示にします。
* Insight は、シンプルでソリッドな建築モデルを使用する場合に最適です。
  * 建物のマスが[ソリッドで隙間がない](https://formit.autodesk.com/blog/post/repairing-solid-models)ようにします。
  * 建物の設計に窓やドアの開口部が既に存在する場合は、エネルギー解析専用の開口部を持たない新しいマスを作成し、レイヤを使用して、より詳細なバージョンを非表示にすることをお勧めします。
* 単純な建物マスには、[レベル](../tool-library/levels-and-area.md)を適用する必要があります。
* FormIt モデルには、[場所](../tool-library/setting-location.md)を設定する必要があります。

![](../.gitbook/assets/insight.png)

### **エネルギー解析を開始する** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* ツールバーで[エネルギー解析]ボタンを探します。

![](../.gitbook/assets/generate\_insight.png)

* [Insight を作成]をクリックしてプロセスを開始します。
* これにより、表示されているモデル データがアップロードされ、クラウドで数百回のシミュレーションが実行されます。
* 完了すると、画面の上部にメッセージが表示され、メニューが更新されて新しい Insight が表示できる状態になったことがわかります。
  * Web ブラウザで解析を表示するには、[Insight を表示]をクリックします。
  * [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight) ですべての Insight を確認することもできます。

## トラブルシューティング<a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **一般的なエラー** <a href="#common-errors" id="common-errors"></a>

* 「Insight プロジェクトを作成できませんでした。後でもう一度試してください」
  * [Green Building Studio ダッシュボード](https://gbs.autodesk.com/GBS/Project)にログインし、FormIt を再起動します。
    * ログインできない場合、または「アクセスが拒否されました」ページが表示される場合は、[Green Building Studio のサブスクリプションを購入する](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)必要があります。
  * モデルが[ソリッドで隙間がない](https://formit.autodesk.com/blog/post/repairing-solid-models)ことを確認します。
  * [Autodesk Health Dashboard](https://health.autodesk.com/) で FormIt サービスに関する問題を確認します。
* Green Building Studio でこのプロジェクトのエネルギー解析が正常に実行されたかどうかを確認するには、[Green Building Studio ダッシュボード](https://gbs.autodesk.com/GBS/Project)を参照してください。
  * 最新のプロジェクトがリストの一番上に表示され、実行回数に 248 回と表示されます。
  * 実行回数が 0 回と表示される場合は、[FormIt フォーラムでお知らせください](https://forums.autodesk.com/t5/formit-forum/bd-p/142)。トラブルシューティングのお手伝いをいたします。

### **詳細なログ** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt Web では、エネルギー解析が失敗した場合に追加の詳細を提供します。
  * [FormIt Web](https://formit.autodesk.com/app) に移動します。
  * エネルギー解析に問題があるモデルを開きます。
  * エネルギー解析を実行します。
  * デベロッパー ツールを開きます(Google Chrome または Firefox では[F12]キーを押す)。
  * [コンソール]タブを開きます。
  * エラーをコピーまたはスクリーンショットして、[FormIt フォーラムで報告](https://forums.autodesk.com/t5/formit-forum/bd-p/142)します。

## 日照解析

[AEC コレクション](https://www.autodesk.com/collections/architecture-engineering-construction/overview)を通じて **FormIt 360 Pro Subscription** を購入している場合は、建物に対する日照の影響を視覚的に確認することができます。

* 日照の影響を解析する面を指定します。
* わずか数秒で、解析結果をアプリケーション キャンバス内で可視化できます。
* 入力点にカーソルを合わせることにより、日照の影響の特定の計算値を確認できます。
* 解析結果を、ガラスに関する月次調査結果として表示したり、ソーラー パネルの実現可能性に関する年次調査結果として表示することもできます。

詳細については、FormIt Pro の[日照解析](../tool-library/solar-analysis.md)のドキュメントを参照してください。
