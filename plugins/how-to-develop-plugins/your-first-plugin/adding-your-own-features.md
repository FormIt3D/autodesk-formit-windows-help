# 独自の機能を追加する

### HTML、JavaScript、CSS パネル内

Plugin Playground のサンプル プラグインで[Edit]をクリックすると、HTML、JavaScript (JS)、および CSS のパネルが表示されます。HTML パネル(左)では、プラグインのユーザ インタフェースを修正できます。JS パネル(中央)では、JavaScript による FormIt プラグインの API を使用して FormIt に意図を伝える関数を作成できます。最後に、CSS パネル(右)で HTML のスタイルを決定します。

![](<../../../.gitbook/assets/image (27).png>)

### 円柱を作成するための関数を追加する

このプラグインに、円柱を作成する機能を追加します。

まず、HTML パネルで入力フィールドと UI ボタンを構成します。次のコードをコピーして、23 行目と _\<!-- Do not remove below scripts unless you know what you're doing- - >_ の間に貼り付けます。

これにより、プラグインに基本的な UI 要素が追加されます。

```
<p>Cylinder: Create a cylinder at the origin.</p>
<div>
    <input id="Radius" type=number value=2 />
    <label>Radius</label>
</div>

<div>
    <input id="CHeight" type=number value =0.5 />
    <label>Height</label>
</div>


<input id="CreateCylinderBtn" type=button value="Create Cylinder" />

```

![](<../../../.gitbook/assets/image (86).png>)

次に、JS パネルで 2 つの関数を追加します。次のコードをコピーして、ファイルの最後(16 行目の後)に貼り付けます。

これにより、FormIt のワークスペースに円柱が作成されます。

```
// Create cylinder
const createCylinder = async (r,h) =>
{
    const posCenter = await WSM.Geom.Point3d(0,0,0);

    const histID = await FormIt.GroupEdit.GetEditingHistoryID();
    console.log(histID,posCenter,r,h);

    const cyl = await WSM.APICreateCylinder(histID,posCenter,r,h);
}


// Execute function when 'create cylinder' button is clicked
document.getElementById("CreateCylinderBtn").addEventListener("click", ()=>
{
    console.log('create cylinder clicked')

    const r = Number(document.getElementById("Radius").value);
    const h = Number(document.getElementById("CHeight").value);

    createCylinder(r,h);

});
```

![](<../../../.gitbook/assets/image (82).png>)

### 実行してプレビューする

結果を確認する準備ができたら、[Play]ボタン ![](<../../../.gitbook/assets/image (81).png>) を再度クリックして、同じパネルでプラグインが更新されることを確認します。

![](<../../../.gitbook/assets/image (14).png>)

### FormIt プラグインの API

FormIt プラグインの API に関する詳細なドキュメントについては、「[便利なリンク](../useful-links.md)」セクションを参照してください。
