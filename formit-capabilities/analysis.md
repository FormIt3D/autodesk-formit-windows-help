---
描述：>- 
通过从设计流程一开始就评估图元的性能，来启动 BIM 工作流。
---

# 日光 + 能量分析

![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## FormIt 中的能量分析

在设计流程早期，分析建筑模型的能效。

[查看 Insight 项目](https://gbs.autodesk.com/OneEnergy/Insight)

## 使用 Insight 进行能量分析

通过[工程建设软件集](https://www.autodesk.com/collections/architecture-engineering-construction/overview)订购 **FormIt Pro** 固定期限的使用许可后，您有权使用 **Insight** 进行能量分析：

* 使用 Green Building Studio 的分析引擎，分析早期阶段设计模型
* 连接到分析结果的面板视图，以比较设计的选项
* 调整能量分析系数控件，例如窗墙比、建筑朝向等
* 使用计算为单位区域底线成本的单一数字，汇总您建筑物的能量影响
* 保存能量分析结果，以供客户和其他相关方将来查看

## FormIt + Insight 的新特性<a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **Insight 可靠性改进**<a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* 现在，[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) 会在启动 Insight 运行之前检查模型中是否存在常见模型问题，并会修复常见 Insight 故障以实现更可靠的体验。
* 通常，FormIt 2021 还会提高 FormIt + Insight 连接的可靠性，从而解决许多已知故障并提高运行成功率。

## 快速入门<a href="#insight-getting-started" id="insight-getting-started"></a>

### **工作方式**<a href="#how-it-works" id="how-it-works"></a>

* Insight 能量分析会上传 FormIt 模型数据，并在云中运行数百个分析以确定各种能量分数
* 能量分析会使用 Revit 分析模型，因此就像将 FormIt 数据发送到 Revit 时一样，您需要[确保 FormIt 模型无间隙且流形一致](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **准备 FormIt 模型**<a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight 将使用 FormIt 草图中任何可见的几何图形
  * 确保要分析的建筑外壳是唯一可见的几何图形
  * 将环境、家具和场地图元等支持几何图形放置在单独的[图层](../tool-library/layers.md)上，然后关闭该图层
* Insight 最适用于简单的实体建筑模型
  * 确保建筑体量是[实体且无间隙](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * 如果建筑设计中已经有窗和门的洞口，则最好专为能量分析创建一个没有洞口的新体量，然后使用“图层”隐藏更详细的版本
* 简单建筑体量需要应用[标高](../tool-library/levels-and-area.md)
* FormIt 模型需要设置[位置](../tool-library/setting-location.md)

![](../.gitbook/assets/insight.png)

### **启动能量分析**<a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* 在工具栏中查找“能量分析”按钮

![](../.gitbook/assets/generate\_insight.png)

* 单击“生成见解”以开始该过程
* 这将上传可见模型数据，并会在云中运行数百个模拟
* 完成后，屏幕顶部将显示一条消息，菜单会更新以指示新见解可供查看
  * 单击“查看见解”以在 Web 浏览器中查看分析
  * 还可以在 [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight) 中找到所有见解。

## 疑难解答<a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **常见错误**<a href="#common-errors" id="common-errors"></a>

* “Insight 项目无法创建。请稍后重试。”
  * 登录到 [Green Building Studio 面板](https://gbs.autodesk.com/GBS/Project)，然后重新启动 FormIt
    * 如果您无法登录或者看到“访问被拒绝”页面，则可能需要[订购 Green Building Studio 的固定期限的使用许可](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
  * 检查模型是否是[实体且无间隙](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * 在 [Autodesk 运行状况面板](https://health.autodesk.com/)上检查 FormIt 服务是否存在任何问题
* 要查看 Green Building Studio 是否已成功执行此项目的能量分析运行，请查看 [Green Building Studio 面板](https://gbs.autodesk.com/GBS/Project)
  * 最新项目应显示在列表顶部，并应显示 248 个运行
  * 如果显示 0 个运行，请在 [FormIt 论坛上告知我们](https://forums.autodesk.com/t5/formit-forum/bd-p/142)，我们可以进一步帮助您解决问题

### **详细日志**<a href="#detailed-logs" id="detailed-logs"></a>

* FormIt Web 会在能量分析失败时提供其他详细信息：
  * 转到 [FormIt Web](https://formit.autodesk.com/app)
  * 打开存在能量分析问题的模型
  * 运行能量分析
  * 打开开发人员工具（在 Google Chrome 或 Firefox 中点击 F12 键）
  * 查看“控制台”选项卡
  * 复制任何错误或为其创建屏幕截图，然后[在 FormIt 论坛上报告它们](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## 日光分析

通过[工程建设软件集](https://www.autodesk.com/collections/architecture-engineering-construction/overview)订购 **FormIt Pro** 固定期限的使用许可，可以直观地了解太阳对建筑的影响：

* 指定要就日光影响进行分析的相关面
* 在应用程序画布内以数秒时间可视化结果
* 将鼠标光标悬停在输入点上，以查看特定的日光影响计算值
* 选择以月度玻璃制品研究，或年度太阳能电池板可行性研究形式查看结果

详细了解 FormIt Pro 中的[日光分析](../tool-library/solar-analysis.md)。
