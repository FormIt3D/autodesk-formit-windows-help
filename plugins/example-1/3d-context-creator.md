# 三维上下文创建器

\![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## 它是什么？

“三维上下文创建器”是一个易于使用的插件，将在 FormIt 中生成三维上下文建筑。

此插件可以帮助您可视化项目场地及其周围环境，并在设计过程的早期阶段做出明智决策。

此插件会从 [Open Street Map](https://www.openstreetmap.org/about) 中检索数据，以帮助将其转换为 FormIt 几何图形。此插件的源代码会在 [Github](https://github.com/matterlab-co/FormIt-Context-Plugin) 上提供。

## 使用方法

要安装它，只需从”插件管理器”打开插件的开关，就像使用任何其他插件一样。

![](../../.gitbook/assets/contextcreator3.png)

打开插件后，该插件应该会显示在应用程序的右侧，并可供使用。

\![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

如果您的场地还没有位置，可以单击 **“设置位置...”** 链接来设置位置，并定义将用于生成三维上下文的边界。

设置好位置后，三维上下文创建器将使用当前位置进行更新，并且该按钮会处于启用状态：

\![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

三维上下文创建器将仅使用卫星图像的范围来生成三维上下文。您只需单击 **“生成三维上下文”**！

根据卫星图像的范围和建筑的复杂性，这可能需要几秒钟的时间才能生成。

三维上下文建筑将自动放置到组实例中，并放置于名为“上下文建筑”的图层上。 可以使用此图层来切换上下文的可见性。

\![](<../../.gitbook/assets/3D Context Creator_layers.png>)

\![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

如果稍后决定更改位置或调整卫星图像的范围，可以再次单击 **“生成三维上下文”** 以重新生成建筑。

_请注意，重新生成上下文会将包含建筑的组实例替换为新实例，因此对建筑所做的任何更改都会丢失。_为了避免出现这种情况，可以解组上下文容器，然后对其重新分组。

## **某些示例**

尝试猜测以下上下文中表示哪些标志性城市：

\![](<../../.gitbook/assets/image (2) (1).png>)

\![](<../../.gitbook/assets/image (34).png>)

\![](<../../.gitbook/assets/image (13) (1) (1).png>)

\![](<../../.gitbook/assets/image (59).png>)
