# 添加您自己的功能

### 在 HTML、JavaScript 和 CSS 面板内

在“插件乐园”样例插件中单击“编辑”时，您会看到 HTML、JavaScript (JS) 和 CSS 面板。通过使用 HTML 面板（左侧），可以修改插件的用户界面。通过使用 JS 面板（中间），可以编写可使用 FormIt JS 插件 API 与 FormIt 通信的函数。最后，CSS 面板（右侧）将确定 HTML 的样式。

![](<../../../.gitbook/assets/image (27).png>)

### 添加用于创建圆柱体的函数

我们为这个插件添加一个功能来创建圆柱体。

首先，我们在 HTML 面板中配置输入字段和 UI 按钮。复制以下代码，然后将其粘贴到第 23 行之后和 _\<!-- 除非您知道要执行的操作，否则请勿删除下面的脚本 -- >_ 之前

这会将一些基本 UI 元素添加到插件中。

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

接下来，我们在 JS 面板中添加两个函数。复制以下代码，并将其粘贴到文件末尾（即第 16 行之后）。

这会在 FormIt 工作空间中创建圆柱体。

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

### 运行和预览

当准备好查看结果时，请再次单击“播放”按钮 ![](<../../../.gitbook/assets/image (81).png>)，您将在同一面板中看到对插件的更新。

![](<../../../.gitbook/assets/image (14).png>)

### FormIt 插件 API

有关 FormIt 插件 API 的完整文档，请参见[有用链接](../useful-links.md)部分。
