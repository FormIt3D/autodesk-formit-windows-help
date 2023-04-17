# 正投影和透視相機

FormIt 2023 包括多個正投影和透視相機選項。您可以在浮動的導覽功能表中找到「正投影」、「兩點透視」和「三點透視」按鈕：

![三點透視 (上)、兩點透視 (中) 和正投影 (下) 相機檢視按鈕](../.gitbook/assets/camera-2point-floating-nav-blurred.png)

### 三點透視

* 這是預設的透視相機。在某些相機角度，垂直線會在相機頂端附近收斂。
* 在此模式中設定的相機位置將定義正投影相機的裁剪平面。
* 在此模式中按住 Ctrl 的同時縮放，可讓您以固定速率縮放，而不會隨著相機接近物件而減慢速度。

### 兩點透視

* 此相機類似於三點透視，但可確保垂直線保持垂直。
* 在某些相機角度，幾何圖形看起來可能會變形，讓垂直線永遠保持垂直。
* 在此模式中設定的相機位置將定義正投影相機的裁剪平面。
* 在此模式中按住 Ctrl 的同時縮放，可讓您以固定速率縮放，而不會隨著相機接近物件而減慢速度。
* 兩點透視也是一種工作模式，因此您會發現即使相機改變了，垂直線還是會保持垂直 - 這可能會讓場景在某些相機角度變形

![](../.gitbook/assets/camera-2point-working-mode.gif)

### 正投影

* 正投影模式對於圖表、3D 詳圖和其他非透視圖形非常有用。
* 在兩種透視模式中設定的相機位置定義正投影相機的裁剪平面。如果您看到場景意外被裁剪，請切換成透視模式，拉遠，然後切換回正投影模式。

### 使用模式

相機模式是所有功能都能完整運作的模式，可讓您以任何想要的模式存取導覽和繪圖工具。此功能表可讓您輕鬆切換不同的相機。

![切換三種不同的相機模式：三點透視、兩點透視和正投影。](../.gitbook/assets/perspective-gif.gif)

一旦選取了相機，其他任何相機工具都會配合目前的模式。例如，**將相機與面對齊**會將「正投影相機」與面對齊，進而產生正投影立面視圖。

如果您手動導覽至預先設定的正投影視圖 (例如上視圖或前視圖)，正投影相機將鎖點至該位置，以便更輕鬆地存取這些預先設定的視圖。

![](../.gitbook/assets/orthoorienttoface.gif)

### 軸測

除了導覽工具列中提供的「正投影」和「透視相機」選項外，FormIt 還提供只能從「檢視」功能表中使用的「軸測相機」(僅限 Windows)：

<figure><img src="../.gitbook/assets/AxonometricMenu (2).png" alt=""><figcaption></figcaption></figure>

選取此選項會在軸測視圖中放置相機：

<figure><img src="../.gitbook/assets/Axonometric (2).png" alt=""><figcaption></figcaption></figure>

### 傾斜

FormIt 還提供只能從「檢視」功能表中使用的「傾斜相機」(僅限 Windows)：

<figure><img src="../.gitbook/assets/ObliqueMenu.png" alt=""><figcaption></figcaption></figure>

選取此選項會在傾斜視圖中放置相機：

<figure><img src="../.gitbook/assets/Oblique (2).png" alt=""><figcaption></figcaption></figure>
