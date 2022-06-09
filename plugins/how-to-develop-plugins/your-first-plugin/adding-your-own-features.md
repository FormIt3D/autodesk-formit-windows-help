# 加入您自己的功能

### 在 HTML、JavaScript 和 CSS 面板中

在 Plugin Playground 範例外掛程式中按一下「編輯」時，您會看到「HTML」、「JavaScript (JS)」和「CSS」面板。「HTML」面板 (左) 可讓您修改外掛程式的使用者介面。「JS」面板 (中) 可讓您編寫函式，這些函式可使用 FormIt JS 外掛程式 API 與 FormIt 溝通。最後，「CSS」面板 (右) 將決定 HTML 的樣式。

![](<../../../.gitbook/assets/image (27).png>)

### 新增函式以建立圓柱

我們在此外掛程式新增一個功能來建立圓柱。

首先，在「HTML」面板中規劃輸入欄位和使用者介面按鈕。複製下列程式碼，並貼到第 23 行後面和 _\<!-- Do not remove below scripts unless you know what you're doing- - >_ 前面

這會將一些基本的使用者介面元素加入外掛程式。

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

接下來，我們在「JS」面板中新增兩個函式。複製下列程式碼，並貼到檔案的結尾 (第 16 行後面)。

這會在 FormIt 工作區中建立一個圓柱。

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

### 執行和預覽

當您準備好查看結果時，請再按一下「播放」按鈕 ![](<../../../.gitbook/assets/image (81).png>)，您會在同一個面板中看到外掛程式的更新。

![](<../../../.gitbook/assets/image (14).png>)

### FormIt 外掛程式 API

如需 FormIt 外掛程式 API 的完整文件，請參閱[有用的連結](../useful-links.md)一節。
