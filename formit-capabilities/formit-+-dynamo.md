---
说明：FormIt 中的计算设计
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt for Windows 内置有 Dynamo，可用于实现令人难以置信的计算设计工作流。

## FormIt + Dynamo 的新特性

### **数据图形、发送标高到 Excel 和镶嵌面控制**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) 支持在[不使用 SendToFormIt 节点](formit-+-dynamo.md#graph-types)的情况下运行 Dynamo 图形、添加了[发送 FormIt 标高到 Excel](formit-+-dynamo.md#send-formit-levels-to-excel) 的功能并添加了[通过新的 FormItGroupOptions 节点对曲线和曲面镶嵌面](../tool-library/curve-+-surface-faceting.md)的控制。

### **尺寸标注输入和早期 JS API 访问**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) 添加了使用[熟悉的 FormIt 尺寸标注作为输入](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes)的功能、引入了[对象级别选项](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes)并提供了 [JavaScript API 访问](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes)的早期预览。在[此处](https://formit.autodesk.com/page/download)获取。

### **多个 SendToFormIt 节点**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) 添加了使用[多个 SendToFormIt 节点和嵌套 Dynamo 图形](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)的功能。

### **SelectFromFormIt 节点**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) 添加了 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点，并支持始终连接的任务、多实例编辑等。

## 快速入门

了解界面并将 Dynamo 目录链接到 FormIt。

### **首次设置**

首次使用 FormIt + Dynamo？可能需要先[配置系统](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes)，才能在 Dynamo 中查看三维画布。

### **Dynamo 面板**

Dynamo 面板可用于启动 Dynamo、放置 Dynamo 组和编辑 Dynamo 图形：

![Dynamo 面板](<../.gitbook/assets/dynamo_dynamopanel (1).png>)

### **添加和管理本地 Dynamo 目录**

* Dynamo 面板的工作方式与[“内容库”](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library)类似，允许您链接和管理包含 Dynamo 文件的本地目录。
* 单击 Dynamo 面板中的“链接目录”按钮，然后在“首选项”对话框中再次单击 (+)，以选择要链接到 FormIt 的目录：<img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* 使用下拉列表在链接的目录之间切换：

![](../.gitbook/assets/dynamo\_dropdown.png)

* 只能通过 Dynamo 面板查看 .dyn 文件和子文件夹。
* 使用过滤栏过滤出 Dynamo 文件和子文件夹，以便可以轻松查找所需内容：

![](../.gitbook/assets/dynamo\_filter.png)

## 不同的 Dynamo 使用方法

在 Dynamo 中制作和编辑图形，或在 FormIt 中调整参数，而无需查看图形。或同时执行两者！

### **图形类型**

FormIt 支持三种类型的 Dynamo 图形：

* 数据图形：数据图形没有 _SendToFormIt_ 节点，并可用于通过 FormIt 创建曲面或传递数据。例如，可以使用数据图形将数据发送到 Excel，或计算非几何数据并将其显示在“Watch”节点中。
* 几何图形：这些图形会立即生成几何图形，需要将其放置到画布中才能查看其参数。单击缩略图后，几何图形会显示在光标上，以便放置到三维场景中。该图形要求在图形末尾至少有一个 _SendToFormIt_ 节点用于接收几何图形。
* 选择图形：这些图形要求先进行 FormIt 选择，然后再运行。您将在 FormIt 的左上角看到提示，以指示需要选择的内容。提供选择后，图形将运行并生成与选择相关的几何图形。该图形要求在图形末尾至少有一个 _SendToFormIt_ 节点用于接收几何图形。

![](../.gitbook/assets/dynamo-graph-types.png)

### **几何图形：将 Dynamo 组放置到 FormIt 中**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* 在 Dynamo 面板中，单击要运行的 Dynamo 图形的缩略图。
  * 可以使用内置样例，也可以[链接您自己的 Dynamo 文件库](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)。
* 将几何图形放置到 FormIt 中会将 Dynamo 图形的副本嵌入到 FormIt 文件中。
  * 要生成几何图形，需要将 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点附加到图形中的输出几何图形节点。
* SendToFormIt 节点中的几何图形将在光标上可用于放置。
  * 如果图形中有 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点标记为“是输入”，则 FormIt 会先要求进行选择（每个选择节点按垂直顺序排序），然后在正确的位置生成与选择相关的几何图形。
* 现在，原始 Dynamo 文件的副本会嵌入到 FormIt 组中，并独立于源图形。
* 放置后，“特性”面板会自动切换以显示可用参数。

### **几何图形：修改参数**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* 放置 Dynamo 组后，选择它并切换到“特性”面板，或者只需双击组以自动切换到“特性”。
  * 在 Dynamo 中，标记为“是输入”的任何输入节点都会在此处列出。
  * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 输入节点会显示为顶部的按钮，并可用于更新用于驱动图形的选择。
  * FormIt 支持以下输入节点：Number Slider、Integer Slider、Boolean Toggle 和 Number/String 字段。
* 在 FormIt 中对输入进行更改，然后单击“运行”。“运行”按钮将变为蓝色，以指示参数已修改并需要运行图形。
  * Dynamo 将在后台运行以处理更改，然后在 FormIt 中返回更新后的几何图形。
  * 在 FormIt 2022 及更高版本中，首次从“特性”面板运行时会启动专用的 Dynamo 实例，从而使后续编辑速度更快。
  * 可以在 Dynamo 运行的情况下继续使用 FormIt。
* 请注意，当 Dynamo 图形运行时，每个 SendToFormIt 组内的所有几何图形都会被删除并替换。

### 数据图形：发送 FormIt 标高到 Excel

在 FormIt 2023 及更高版本中，可以使用 Dynamo 将 FormIt 标高发送到 Excel：

* 在[此处](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn)下载样例 Dynamo 图形。
* 将 Dynamo 选项板指向保存 Dynamo 图形的本地目录。
* 在缩略图上单击鼠标右键，然后单击 _“编辑嵌入的图形”_。
* 在某处创建一个空的 Excel 电子表格。
* 编辑“电子表格位置”字段，以使用 Excel 电子表格的路径。
* 编辑所需的任何其他字段，例如“图纸名称”。
* 关闭 Dynamo 并保存图形。

现在，只需在选项板中单击示例文件，然后它将在 FormIt 中运行，而无需生成几何图形。

您将看到 Dynamo 输入出现在 Dynamo 选项板中，并且会看到 Excel 打开以显示图形中的结果。

在对模型进行更改时，可以再次单击图形缩略图或 _“运行”_ 按钮，以使用最新版本 FormIt 草图中的标高数据更新电子表格。

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### 启动新的 Dynamo 窗口

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* 在 FormIt 2021 及更高版本中，单击 Dynamo 面板中的“启动 Dynamo”按钮会自动启动与 FormIt 连接的任务。
  * 这将在 Dynamo 中打开图形模板，并会在 FormIt 中自动生成模板几何图形。
  * 生成的几何图形会显示在新组中，位于当前组编辑上下文的原点处。最好位于所需的组上下文中，然后再启动 Dynamo。
  * 该模板包含 FormIt 节点和一些示例几何图形。调整滑块时会调整立方体在两个应用程序中的大小。
  * 在此处，可以打开不同的 Dynamo 图形，也可以使用模板中的这些基本构件构建新图形并使用 Dynamo 中的“另存为”保存到新位置。

### **编辑嵌入 + 源图形**

可以采用两种不同的方式编辑现有 Dynamo 图形：编辑已放置在 FormIt 中嵌入的图形，或编辑保存在计算机上的源图形。

### **嵌入的图形**

将 Dynamo 对象放置到 FormIt 中后，其基础图形会被复制并嵌入到当前 FormIt 文件中。在 Dynamo 中，通过 **“编辑嵌入的图形”** 按钮进行编辑。

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* 选择“Dynamo 组”并切换到“特性”面板，或者只需双击组即可自动切换到“特性”。
* 单击 **“编辑嵌入的图形”** 按钮。
* 在 Dynamo 中，您会注意到顶部的文件名现在包含“(FormIt)”，这意味着您正在编辑嵌入在此 FormIt 文件中的图形，而不是修改源图形。
* 确保一个或多个 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点已连接到要发送到 FormIt 的几何图形。
* 当调整图形时，FormIt 会实时显示对几何图形的更新。
* 如果未在 Dynamo 中保存更改，则 FormIt 会回滚到上次保存的 Dynamo 图形版本。
* 请注意，当 Dynamo 图形运行时，每个 SendToFormIt 组内的所有几何图形都会被删除并替换。

### **源图形**

[链接本地目录](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)后，源图形会显示在 Dynamo 面板中。这些图形存储在计算机上，可以在 Dynamo 中通过单击“编辑源图形”按钮进行编辑。

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* 将包含 Dynamo 文件的目录[链接](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)到 Dynamo 面板，然后导航到面板中的该位置。
* 在要编辑的 Dynamo 图形的缩略图上单击鼠标右键（或单击箭头），然后选择 **“编辑源图形”** 按钮。
* Dynamo 将启动并打开请求的图形，然后在 FormIt 中，您会看到图形的最终输出中显示几何图形。
  * 对于使用一个或多个 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点作为输入的图形，在“SelectFromFormIt”节点中填入选择内容后，才可能会看到生成的几何图形。
* 生成的几何图形会显示在新组中，位于当前组编辑上下文的原点处。
  * 最好位于所需的组上下文中，然后再单击“编辑源图形”。
* 完成编辑后，保存并关闭 Dynamo。在 FormIt 中，源图形已复制并嵌入到 FormIt 文件中。
  * 如果需要对 **“源图形”** 进行更多编辑，请删除嵌入的副本并再次执行这些步骤。

### **控制曲线 + 曲面镶嵌面**

*   从 FormIt 2023 开始，可以使用“FormItGroupOptions”节点“SetCurveFacetingCount”和“SetSurfaceFacetingCount”，来控制附着到“SendToFormIt”节点的曲线和曲面的镶嵌面。

    <img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">
* 这些节点会覆盖全局曲线和曲面镶嵌面设置，这些设置是在“编辑”->“首选项”->“单位+精度”下定义的。
* 如果 Dynamo 图形需要使用特定镶嵌面值生成弯曲对象，这将非常有用，从而无需更改当前任务中运行的每个 Dynamo 图形的全局设置。

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* 还可以在“编辑”->“首选项”->“单位+精度”中全局设置镶嵌面设置
* 在“首选项”中调整镶嵌面质量后，请重新运行图形以使用新的全局镶嵌面设置。

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[了解有关 FormIt 中曲线和曲面镶嵌面设置的详细信息。](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## 将 FormIt 组与 Dynamo 结合使用

利用强大的 FormIt 组来实现更好的 Dynamo 几何图形组织和令人难以置信的工作流。

### **组和 SelectFromFormIt 节点**

* 为 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点选择几何图形时，改为将几何图形存储在 FormIt 组中并选择该组会很有用。
  * 这样一来，可以灵活地更改选定 FormIt 组的内容，然后只需重新运行参照该组的图形即可查看更新后的结果。
* 如果选择未分组的几何图形，则对该几何图形更改可能会导致 FormIt 要求您在下次运行图形时重新选择该几何图形。

### **在组中生成几何图形**

* 在 FormIt 中运行 Dynamo 图形时，其几何结果会包含在 FormIt 组中。
* 图形中的每个 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点都会创建一个子组，以包含来自节点输入端口的几何图形。
* 在 FormIt 中生成 Dynamo 对象后，整个图形及其参数会作为副本嵌入到 FormIt 文件中。
* 当图形运行时，每个子组内的几何图形会被删除并重新生成。
  * 在子组内修改几何图形或绘制曲面时要小心，因为这些更改会在 Dynamo 图形下次运行时丢失。
  * 但是，如果使用 FormIt 材质绘制子组（而非其内的几何图形），则这些材质会在运行之间保留。请参见下文。

### **使用组和材质**

* 使用多个 **SendToFormIt** 节点时，可以按材质组织节点，以便可以使用不同的材质绘制不同的 FormIt 子组。
* 在本示例中，整个建筑是基于 FormIt 中的简单平面生成的。每个需要唯一材质的建筑构件都有其自己的 **SendToFormIt** 节点：

![](<../.gitbook/assets/dynamo_sendtoformit (1).png>)

* 在将材质应用于每个子组后，材质会在 Dynamo 运行之间保留：

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **嵌套 Dynamo 组**

* 可以使用 **SelectFromFormIt** 节点从一个 Dynamo 图形中选择子组结果，以驱动另一个图形的结果。
* 基于上述示例，建筑生成器图形的玻璃制品输出会用作内置“店面幕墙”样例的选择几何图形：

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* 当建筑形状更改时，只需选择竖梃系统组，然后在“特性”面板中单击“运行”。
  * 尽管玻璃制品组的内容已更改，但组本身未更改，因此在重新运行图形时无需重新选择玻璃制品。
* FormIt 2022 及更高版本中提供上述模型，位置为 **“Dynamo 样例”** 的 **“建筑体量”** 子文件夹中的“屋顶平面建筑”。
* 可以将 Dynamo 与 FormIt 的丰富功能结合使用，以在强大的概念建模器的丰富上下文中创建和调整完全参数化的设计（使用材质和嵌套逻辑完成）：

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **标准 FormIt 组行为仍适用**

* 除了上述内容之外，FormIt 中的 Dynamo 组还会按照与其他组相同的规则运行：
  * 从 Dynamo 面板放置新的 Dynamo 对象会创建一个唯一组，并且不会影响已放置在草图中的同一对象的任何实例。
  * 复制和粘贴 Dynamo 组会使它们保持相同。对一个副本的 Dynamo 图形所做的任何更改也会更新其相同实例中的几何图形，除非使它们唯一。
  * 可以使用快捷方式 MU 或通过上下文菜单使 Dynamo 组唯一：

![](<../.gitbook/assets/dynamo_makeunique (1).png>)

## 基本 FormIt 节点

在 FormIt 和 Dynamo 之间发送数据的最强大节点。

### **SendToFormIt 节点**

* 要在 FormIt 中生成 Dynamo 对象，请将所需的几何节点输出附着到至少一个“SendToFormIt”节点的 _“几何图形”_ 输入：

![](<../.gitbook/assets/dynamo_sendtoformitnode (1).png>)

* “FormItGroupOptions”是 FormIt 2022 中的新（可选）端口，将在下面的 **“FormItGroupOptions 节点”** 部分中进行详细介绍。
* 在 FormIt 2021.3 及更高版本中，可以使用多个“SendToFormIt”节点将 Dynamo 结果组织为整齐的 FormIt 组和子组。
* [了解 Dynamo 如何与 FormIt 组结合使用](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)。

![](<../.gitbook/assets/dynamo_sendtoformitnodes (1).png>)

* “SendToFormIt”节点遵循“是输出”标志，该标志默认处于选中状态。可以在节点上单击鼠标右键以确认：

![](<../.gitbook/assets/dynamo_isoutput (1).png>)

* 如果选中该选项，则附着到此“SendToFormIt”节点的几何图形会显示在 FormIt 中的子组内。
* 如果取消选中该选项，则不会将任何几何图形发送到 FormIt，并会删除相应的子组（如果有）。

### **SelectFromFormIt 节点**

* 在 FormIt 2021 及更高版本中，可以从 FormIt 中选择几何图形以用作 Dynamo 图形中的输入：

![](<../.gitbook/assets/dynamo_selectfromformitnode (1).png>)

* “SelectFromFormIt”节点的名称将用于 FormIt 中的提示，因此您应按照描述应选择的 FormIt 几何图形类型的方式对其进行命名：

![](<../.gitbook/assets/dynamo_selectobjectstoarraynode (1).png>)

* 在 Dynamo 图形编辑器或“特性”面板中单击“从 FormIt 选择”按钮时，FormIt 会启动选择向导模式以引导您完成选择几何图形：

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* “SelectFromFormIt”节点会遵循“是输入”标志，该标志默认处于选中状态。需要选中此选项，才能使选择在 FormIt 中可用。在节点上单击鼠标右键以确认。

![](<../.gitbook/assets/dynamo_isinput (1).png>)

* 当“是输入”处于选中状态时：
  * 图形的 Dynamo 面板缩略图会指示需要选择：

![](../.gitbook/assets/dynamo\_patharray.png)

* 运行图形时，FormIt 选择向导会引导您完成每个“SelectFromFormIt”节点的设置选择，从图形顶部开始。
* 在首次生成后，您会在“FormIt 特性”面板中看到每个“SelectFromFormIt”节点的按钮。

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* 单击这些按钮会启动选择向导，以便可以更改用于生成最终几何图形的选择。重新选择后，图形会自动重新运行。

### **提示、技巧和注释**

* 命名“SelectFromFormIt”节点以指示所需的几何图形类型。例如，“Select Site Boundary (Edges)”（“选择场地边界(边)”）
  * 可以选择任何类型的 FormIt 几何图形，但通常最好将选择内容包含到 FormIt 组中，然后[选择该组而不是原始几何图形](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)。
* 如果需要移动基于选择的 Dynamo 图形结果，最好先移动选择几何图形，然后重新运行该图形，这将拾取更新后的选择几何图形并相应地重新定位它本身。
  * 还可以对 Dynamo 结果**和**选择进行分组，然后移动包含的组。
* 如果将 FormIt 几何图形发送到 Dynamo，则任何属性、材质或嵌套组都会在将几何图形返回到 FormIt 时丢失。
* 如果在 Dynamo 中编辑基于选择的图形，而 FormIt 中选定的几何图形发生更改，则需要通过单击“SelectFromFormIt”节点上的“从 FormIt 选择”来重新选择该几何图形。
* 在 FormIt 中选择时，将应用活动的[“选择过滤器”](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering)。例如，如果要选择 FormIt 顶点，则需要在“选择过滤器”中启用该选项。

![](../.gitbook/assets/dynamo\_filterselection.png)

## 其他输入节点

一系列输入选项，可用于在 FormIt 中轻松自定义 Dynamo 图形。

### **FormItLengthString 节点**

在 FormIt 2022.1.0 或更高版本中，可以使用 **FormItLengthString** 节点来以任何受支持的 FormIt 单位类型（英尺-英寸、英寸、米、厘米、毫米）指定尺寸标注，而不管 FormIt 在活动草图中的单位设置为何。

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

与其他支持的输入节点一样，_FormItLengthString_ 会在标记为“是输入”时显示在“FormIt 特性”选项板中；在重命名该节点后，其新名称会显示在 FormIt 中：

![](../.gitbook/assets/dynamo\_propertiespalette.png)

_FormItLengthString_ 节点的每个实例都可用于任何单位类型，因此单个 Dynamo 图形可以混合使用单位，如上所示。

### **从原始数字切换到 FormItLengthString**

在 FormIt 2022.1.1 及更高版本中，在 Dynamo 中编辑图形时，将图形切换为使用“FormItLengthString”节点（通过将第一个节点放置在图形中）或将图形切换为仅使用原始数字（通过删除最后一个“FormItLengthString”）会更改某些行为：

* 在编辑图形的情况下使用 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点时，如上所述在原始数字和 _FormItLengthString_ 节点之间切换时需要为每个 _SelectFromFormItNode_ 重新选择几何图形，以便在 FormIt 中继续正确缩放结果。
* 在图形中放置第一个“FormItLengthString”节点后，图形中要用作尺寸标注的所有数字（包括原始数字输入）会参照单位“米”（Dynamo 的后台原生单位）。
  * [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 节点会考虑更改，并确保在 FormIt 中生成的几何图形会保持正确大小。
  * 反之，从图形中删除所有“FormItLengthString”节点会切换原始数字以参照 FormIt 的单位设置（旧行为）。
* _FormItLengthString_ 节点的数值输出也以“米”为单位，但这不会更改 FormIt 中几何结果的大小：

![](<../.gitbook/assets/dynamo_outputinmeters (1).png>)

### **其他支持的输入节点**

标准 Dynamo 输入节点在 Dynamo 中标记为“是输入”后，它们会显示在 FormIt 的“特性”面板中：

* Number Slider
* Integer Slider
* Number
* String
* Boolean Toggle

可以重命名输入节点（为清楚起见建议重命名），其新名称会显示在 FormIt 中：

![](<../.gitbook/assets/dynamo_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## 其他输出节点

用于从 Dynamo 到 FormIt 显示非几何结果的不同方法。

### **Watch 节点**

在 FormIt 2022 及更高版本中，标记为“是输出”的“Watch”节点会显示在“特性”面板的“Watch 节点输出”部分：

![](<../.gitbook/assets/dynamo_watchnodes (1).png>)

### **显示 FormIt 通知**

在 FormIt 2022.1 或更高版本中，可以使用 **UI.ShowNotification** 节点显示 Dynamo 图形中的 FormIt 端通知：

![](../.gitbook/assets/dynamo\_notifications.png)

### **记录到 FormIt 控制台**

在 FormIt 2022.1 或更高版本中，可以使用 **FormIt.ConsoleLog** 节点将其他数据直接记录到 FormIt 应用程序控制台（“脚本输出”窗口）：

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt 选项节点

控制数据发送到 FormIt 的方式（单个几何图形级别或包含组级别）。

### **FormItGeometryOptions**

在 FormIt 2022.1 及更高版本中，可以自定义如何使用 **FormItGeometryOptions** 节点将各个 Dynamo 几何图形发送到 FormIt。

* 为生成的 Dynamo 组内的各个几何图形指定图层。
* 为生成的 Dynamo 组内的各个几何图形指定字符串属性。

_FormItGeometryOptions_ 节点可以在 _SendToFormIt_ 节点的上游使用：

![](<../.gitbook/assets/dynamo_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

在 FormIt 2022 及更高版本中，可以自定义如何使用 **FormItGroupOptions** 节点在 FormIt 中生成 _SendToFormIt_ 节点中的 Dynamo 组。

* 指定“SendToFormIt”节点将几何图形作为网格还是对象发送到 FormIt。
* 为 SendToFormIt 节点创建的组指定图层。
* 为 SendToFormIt 节点创建的组指定字符串属性。

通过将“FormItGroupOptions”节点以菊花链方式链接在一起，可以按任意顺序使用这些节点的任意组合：

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript API 节点

FormIt 2022.1 及更高版本允许从 Dynamo 通过两个新节点访问 JavaScript API 和自定义函数：

### **CallJSAPI**

**CallJSAPI** 节点允许直接从 Dynamo 调用 FormIt JavaScript API。

![](<../.gitbook/assets/dynamo_calljsapi (1).png>)

有关函数名称和参数，请查看 JavaScript 文档，该文档分为两个部分： [FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) 和 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html)（建模内核）。

**CallPluginJS**

反之，**CallPluginJS** 节点允许调用已加载的插件或从“脚本编辑器”窗口执行的脚本片段中的自定义函数。

![](<../.gitbook/assets/dynamo_callpluginjs (1).png>)

## 重要说明

### **系统要求**

* 要在 FormIt 中使用 Dynamo，您需要有 [FormIt for Windows](https://formit.autodesk.com/page/download) v17.0 或更高版本。
  * FormIt + Dynamo 集成会定期收到新功能和修复，因此始终最好下载可用的最新更新。
* 您还需要 Windows 10。出于技术原因，不再支持较旧版本的 Windows。

**疑难解答**

* 如果您的系统有 [NVIDIA 或 AMD 显卡](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/)或多个显卡，则可能需要设置 FormIt 和 Dynamo 才能使用高性能 GPU：
  * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
  * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
  * 如果您有 NVIDIA 显卡，请[确保已安装 NVIDIA 控制面板](https://whatsabyte.com/blog/find-nvidia-control-panel/)
  * 使用 [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) 或 [AMD](https://www.amd.com/en/support/kb/faq/dh-017) 控制面板，将以下应用程序设置为使用独立显卡：
* 如果您使用的是非英语区域设置，则可能需要将 Windows 10 区域设置设定为“英语”，以避免某些 Dynamo 节点出现问题：
  * 在“开始”中搜索“语言”，然后选择“语言设置”
  * 在“语言”对话框的右上角，单击“管理语言设置”
  * 单击“更改系统区域设置...”按钮
  * 选择“英语(美国)”
* 如果在处理小型几何图形或数字时遇到无法在 FormIt 中生成结果的图形，请尝试将 Dynamo 缩放设置更改为“小”：
  * Dynamo 菜单 >“首选项”>“常规”>“几何图形缩放”>“小”

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **获取支持**

需要 FormIt + Dynamo 的帮助？[在论坛上告知我们](https://forums.autodesk.com/t5/formit-forum/bd-p/142)。
