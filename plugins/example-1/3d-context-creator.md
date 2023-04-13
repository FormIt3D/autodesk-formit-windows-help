# 3D Context Creator

![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## 概要

3D Context Creator は、FormIt 内に 3D コンテキストの建物を生成するための使いやすいプラグインです。

このプラグインを使用すると、周囲の状況に合わせてプロジェクトの敷地を視覚化し、設計プロセスの初期段階で情報に基づいた意思決定を行うことができます。

このプラグインは、[Open Street Map](https://www.openstreetmap.org/about) からデータを取得して、FormIt ジオメトリに変換できます。このプラグインのソース コードは、[Github](https://github.com/matterlab-co/FormIt-Context-Plugin) で取得可能です。

## 使用方法

プラグインをインストールするには、他のプラグインと同様に、プラグインの切り替えをプラグイン マネージャで有効にします。

![](../../.gitbook/assets/contextcreator3.png)

スイッチをオンにすると、プラグインがアプリケーションの右側に表示され、使用できるようになります。

![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

敷地に場所が設定されていない場合は、**[場所を設定...]** リンクをクリックして場所を設定し、3D コンテキストの生成に使用する境界を定義します。

場所を設定すると、3D Context Creator は現在の場所で更新され、ボタンが有効になります。

![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator は、衛星画像の範囲を使用して 3D コンテキストを生成します。**[3D コンテキストを生成]** をクリックするだけで実行できます。

衛星画像の範囲や建物の複雑さによって、生成には数秒かかることがあります。

3D コンテキスト建物は自動的にグループ インスタンスに配置され、「コンテキスト建物」と呼ばれるレイヤに配置されます。 このレイヤを使用して、コンテキストの表示を切り替えることができます。

![](<../../.gitbook/assets/3D Context Creator_layers.png>)

![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

後で場所を変更したり、衛星画像の範囲を調整する場合は、**[3D コンテキストを生成]** を再度クリックして、建物を再生成することができます。

_コンテキストを再生成すると、建物を含むグループ インスタンスが新しいインスタンスに置き換えられるため、建物に対して行われたすべての変更が失われます。_ これを防ぐには、コンテキスト コンテナをグループ解除してから再度グループ化します。

## **次に例を示します**

次のコンテキストで表現される象徴的な都市を推測してみてください。

![](<../../.gitbook/assets/image (2) (1).png>)

![](<../../.gitbook/assets/image (34).png>)

![](<../../.gitbook/assets/image (13) (1) (1).png>)

![](<../../.gitbook/assets/image (59).png>)
