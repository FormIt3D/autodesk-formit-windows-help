---
description: Computational Design in FormIt
---

# FormIt + Dynamo

![](<../.gitbook/assets/20181213 formit + dynamo hero image.png>)

FormIt for Windows 內建 Dynamo，具有令人難以置信的設計工作流程運算能力。

## FormIt + Dynamo 的新增功能

### **資料圖表、將樓層傳送至 Excel，以及刻面控制**

[FormIt 2023](https://formit.autodesk.com/blog/post/introducing-formit-2023/) 可在[不使用 SendToFormIt 節點](formit-+-dynamo.md#graph-types)的情況下執行 Dynamo 圖表，加入[將 FormIt 樓層傳送至 Excel](formit-+-dynamo.md#send-formit-levels-to-excel) 的功能，並[透過新的 FormItGroupOptions 節點加入對曲線和曲面刻面](../tool-library/curve-+-surface-faceting.md)的控制。

### **尺寸輸入和早期 JS API 存取**

[FormIt 2022.1](https://formit.autodesk.com/blog/post/introducing-formit-2022-1) 加入使用[熟悉的 FormIt 尺寸做為輸入](https://formit.autodesk.com/page/formit-dynamo#dynamo-input-nodes)的功能、引入[物件層級選項](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-options-nodes)，並提供 [JavaScript API 存取](https://formit.autodesk.com/page/formit-dynamo#dynamo-js-api-nodes)的早期預覽。請從[這裡](https://formit.autodesk.com/page/download)取得。

### **多個 SendToFormIt 節點**

[FormIt 2021.3](https://formit.autodesk.com/blog/post/introducing-formit-2021-3) 加入使用[多個 SendToFormIt 節點和巢狀 Dynamo 圖表](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)的功能。

### **SelectFromFormIt 節點**

[FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) 加入 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點，並允許永遠連線的工作階段、多例證編輯等等。

## 開始使用

了解介面並將 Dynamo 目錄連結至 FormIt。

### **首次設定**

第一次使用 FormIt + Dynamo？您可能需要先[規劃系統](https://formit.autodesk.com/page/formit-dynamo#dynamo-important-notes)，才能在 Dynamo 中看到 3D 圖元區。

### **Dynamo 面板**

使用 Dynamo 面板啟動 Dynamo、放置 Dynamo 群組，以及編輯 Dynamo 圖表：

![Dynamo panel](<../.gitbook/assets/dynamo\_dynamopanel (1).png>)

### **加入和管理本端 Dynamo 目錄**

* Dynamo 面板的運作方式與[內容資源庫](https://windows.help.formit.autodesk.com/building-the-farnsworth-house/import-export-and-content-library)類似，可讓您連結和管理包含 Dynamo 檔案的本端目錄。
* 按一下 Dynamo 面板中的「連結目錄」按鈕，再按一下「偏好」對話方塊中的「(+)」，以選取要連結至 FormIt 的目錄： <img src="../.gitbook/assets/dynamo_selectdirectory.png" alt="" data-size="line">
* 使用下拉式清單在連結的目錄之間切換：

![](../.gitbook/assets/dynamo\_dropdown.png)

* 您只能透過 Dynamo 面板檢視 .dyn 檔案和子資料夾。
* 使用篩選列篩選出 Dynamo 檔案和子資料夾，以便您可以輕鬆找到所需內容：

![](../.gitbook/assets/dynamo\_filter.png)

## 使用 Dynamo 的不同方式

在 Dynamo 中建立和編輯圖表，或在 FormIt 中調整參數而不用查看圖表。兩者也可以同時進行！

### **圖表類型**

FormIt 支援三種類型的 Dynamo 圖表：

* 資料圖表：資料圖表沒有 _SendToFormIt_ 節點，用來呈現資料或將資料傳入 FormIt。例如，您可以使用資料圖表將資料傳送至 Excel，或計算非幾何資料並顯示在 Watch 節點中。
* 幾何圖形圖表：這些圖表會立即產生幾何圖形，必須放在圖元區中才能看到其參數。按一下縮圖後，幾何圖形將出現在游標上，以便放到 3D 場景中。此圖表至少需要出現一個 _SendToFormIt_ 節點，並在圖表結尾處接收幾何圖形。
* 選取圖表：這些圖表在執行前需要 FormIt 選取項目。您會在 FormIt 的左上角看到提示，指出需要選取的項目。提供選取後，圖表將執行並產生與選取相關的幾何圖形。此圖表至少需要出現一個 _SendToFormIt_ 節點，並在圖表結尾處接收幾何圖形。

![](../.gitbook/assets/dynamo-graph-types.png)

### **幾何圖形圖表：將 Dynamo 群組放到 FormIt 中**

![](../.gitbook/assets/dynamo\_stairsgif.gif)

* 在 Dynamo 面板中，按一下您要執行的 Dynamo 圖表的縮圖。
   * 您可以使用內建範例，或[連結您所屬 Dynamo 檔案的資源庫](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)。
* 將幾何圖形放到 FormIt 中，會將 Dynamo 圖表的複本嵌入 FormIt 檔案。
   * 若要產生幾何圖形，必須將 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點連接到圖表中的輸出幾何圖形節點。
* 來自 SendToFormIt 節點的幾何圖形會出現在游標上供您放置。
   * 當圖表有標記為「是輸入」的 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點時，FormIt 會先要求選取 (每個選取節點以垂直順序)，然後在相對於選取的正確位置產生幾何圖形。
* 原始 Dynamo 檔案的複本現在會嵌入 FormIt 群組中，然後就與來源圖表無關。
* 放置後，「性質」面板會自動切換以顯示可用參數。

### **幾何圖形圖表：修改參數**

![](../.gitbook/assets/dynamo\_stairsgif2\_modifyparameters.gif)

* 放置 Dynamo 群組後，請選取該群組並切換至「性質」面板，或者按兩下群組即可自動切換至「性質」。
   * Dynamo 中標記為「是輸入」的所有輸入節點都會列在這裡。
   * [**SelectFromFormIt**](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 輸入節點將會以按鈕的形式出現在頂端，可用來更新用於驅動圖表的選取。
   * FormIt 支援以下輸入節點：Number Slider、Integer Slider、布林切換和 Number/String 欄位。
* 在 FormIt 中變更輸入，然後按一下「執行」。「執行」按鈕將變為藍色，表示參數已修改，需要執行圖表。
   * Dynamo 將在背景中執行以處理變更，並在 FormIt 中傳回更新的幾何圖形。
   * 在 FormIt 2022 和更高版本中，第一次從「性質」面板執行會建立一個專用的 Dynamo 例證，讓後續的編輯更快速。
   * 您可以在 Dynamo 執行時繼續使用 FormIt。&#x20;
* 請注意，執行 Dynamo 圖表時，每個 SendToFormIt 群組內的所有幾何圖形都會被刪除並取代。

### 資料圖表：將 FormIt 樓層傳送至 Excel

在 FormIt 2023 和更高版本中，您可以使用 Dynamo 將 FormIt 樓層傳送至 Excel：&#x20;

* 點[此](https://formit-help.s3.amazonaws.com/Send+Levels+to+Excel.dyn)下載範例 Dynamo 圖表。
* 將 Dynamo 選項板指向儲存 Dynamo 圖表的本端目錄。
* 在縮圖上按一下右鍵，然後按一下 _「編輯內嵌的圖表」。_
* 在某處建立一個空白 Excel 試算表。
* 編輯「試算表位置」欄位，以使用 Excel 試算表的路徑。
* 編輯您想要的任何其他欄位，例如「工作表名稱」。
* 關閉 Dynamo 並儲存圖表。

現在，您只需按一下選項板中的範例檔案，它就會在 FormIt 中執行，而無需產生幾何圖形。&#x20;

您會看到 Dynamo 輸入顯示在 Dynamo 選項板中，也會看到 Excel 開啟以顯示圖表中的結果。&#x20;

對模型做變更時，您可以再按一下圖表縮圖或按一下_「執行」_按鈕，使用最新版 FormIt 草圖中的樓層資料更新試算表。

![](../.gitbook/assets/dynamo-send-levels-to-excel.gif)

### 啟動新的 Dynamo 視窗

![](../.gitbook/assets/dynamo\_launchwindow.gif)

* 在 FormIt 2021 和更高版本中，按一下 Dynamo 面板中的「啟動 Dynamo」按鈕，將自動啟動一個與 FormIt 連接的工作階段。
   * 這會在 Dynamo 中開啟一個圖表樣板，並在 FormIt 中自動產生樣板幾何圖形。
   * 產生的幾何圖形將顯示在新群組中，位於目前群組編輯環境的原點。最好先前往所需的群組環境，再啟動 Dynamo。&#x20;
   * 樣板包括 FormIt 節點和一些範例幾何圖形。調整滑棒會調整兩種應用程式中立方塊的大小。
   * 從這裡，您可以開啟不同的 Dynamo 圖表，或使用樣板中的這些基本元件建立一些新物件，然後使用 Dynamo 中的「另存新檔」將圖表儲存到新位置。

### **編輯內嵌 + 來源圖表**

您可以透過兩種不同的方式編輯既有的 Dynamo 圖表：編輯已放置在 FormIt 中的「內嵌圖表」，或編輯儲存在電腦上的「來源圖表」。

### **內嵌的圖表**

將 Dynamo 物件放到 FormIt 後，會複製其基礎圖表並嵌入目前的 FormIt 檔案中。透過 **「編輯內嵌的圖表」** 按鈕即可在 Dynamo 中編輯此圖表。

![](../.gitbook/assets/dynamo\_embeddedgraph.png)

![](../.gitbook/assets/dynamo\_editgraphgif.gif)

* 選取 Dynamo 群組，並切換至「性質」面板，或者按兩下群組即可自動切換至「性質」。
* 按一下 **「編輯內嵌的圖表」** 按鈕。
* 在 Dynamo 中，您會發現頂端的檔名現在包含「(FormIt)」，這表示您正在編輯嵌入此 FormIt 檔案中的圖表，而不是修改來源圖表。
* 確保一個或多個 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點已連接到您要傳送至 FormIt 的幾何圖形。
* FormIt 會在您調整圖表時即時顯示幾何圖形的更新。
* 如果您在 Dynamo 中沒有儲存變更，FormIt 將撤回到 Dynamo 圖表上次儲存的版本。
* 請注意，執行 Dynamo 圖表時，每個 SendToFormIt 群組內的所有幾何圖形都會被刪除並取代。

### **來源圖表**

[連結本端目錄](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)後，來源圖表會顯示在 Dynamo 面板中。這些圖表儲存在您的電腦上，在 Dynamo 中按一下「編輯來源圖表」按鈕可以進行編輯。

![](../.gitbook/assets/dynamo\_editsourcegraph.png)

![](../.gitbook/assets/dynamo\_sourcegraphgif.gif)

* 將包含 Dynamo 檔案的[目錄連結](https://formit.autodesk.com/page/formit-dynamo#dynamo-getting-started)到 Dynamo 面板，然後在面板中導覽至該位置。&#x20;
* 在要編輯的 Dynamo 圖表縮圖上按一下右鍵 (或按一下箭頭)，然後選取 **「編輯來源圖表」** 按鈕。
* Dynamo 將在開啟要求圖表的狀態下啟動，在 FormIt 中，您會看到圖表最終輸出的幾何圖形出現。
   * 如果是使用一個或多個 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點做為輸入的圖表，在 SelectFromFormIt 節點填入選取之前，您可能看不到產生的幾何圖形。
* 產生的幾何圖形將顯示在新群組中，位於目前群組編輯環境的原點。
   * 按一下「編輯來源圖表」之前，最好位於所需的群組環境中。
* 完成編輯後，儲存並關閉 Dynamo。在 FormIt 中，來源圖表已複製並嵌入 FormIt 檔案中。
   * 如果您需要對**來源圖表**進行更多編輯，請刪除嵌入的複本，然後再次依照這些步驟。

### **控制曲線 + 曲面刻面**

* 從 FormIt 2023 開始，您可以使用 FormItGroupOptions 節點 SetCurveFacetingCount 和 SetSurfaceFacetingCount，控制連接至 SendToFormIt 節點的曲線和曲面的刻面。

<img src="../.gitbook/assets/dynamo-formitgroupoptions-faceting-nodes.png" alt="" data-size="original">

* 這些節點將取代「編輯」->「偏好」->「單位 + 精確度」下定義的全域曲線和曲面刻面的設定。
* 如果您的 Dynamo 圖表需要使用特定的刻面值產生彎曲物件，這會非常有用，如此能減少為目前工作階段中每個 Dynamo 圖表變更全域設定的需求。

![](../.gitbook/assets/dynamo-formitgroupoptions-faceting.gif)

* 您也可以在「編輯」->「偏好」->「單位 + 精確度」中全域設定刻面設定
* 在「偏好」中調整刻面品質後，請重新執行圖表以使用新的全域刻面設定。

![](../.gitbook/assets/dynamo\_controlcurve.gif)

[進一步了解 FormIt 中的曲線和曲面刻面設定。](https://windows.help.formit.autodesk.com/tool-library/curve-+-surface-faceting)

## 將 FormIt 群組與 Dynamo 搭配使用

利用強大的 FormIt 群組，更完善地組織 Dynamo 幾何圖形和令人驚艷的工作流程。

### **群組和 SelectFromFormIt 節點**

* 為 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點選取幾何圖形時，將幾何圖形儲存在 FormIt 群組中，並改為選取群組會很好用。
   * 這樣可讓您靈活地變更所選 FormIt 群組的內容，然後只需重新執行參考群組的圖表，即可查看更新的結果。
* 如果您選取未群組的幾何圖形，一旦對該幾何圖形做變更，下次執行圖表時，可能會導致 FormIt 要求您重新選取該幾何圖形。

### **在群組中產生幾何圖形**

* 在 FormIt 中執行 Dynamo 圖表時，其幾何結果會包含在 FormIt 群組中。
* 圖表中的每個 [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點都會建立子群組，以包含來自節點輸入埠的幾何圖形。
* 在 FormIt 中產生 Dynamo 物件後，整個圖表及其參數會以複本方式嵌入 FormIt 檔案中。
* 當圖表執行時，將刪除並重新產生每個子群組內的幾何圖形。
   * 修改子群組內的幾何圖形或繪製表面時請小心，因為下次執行 Dynamo 圖表時，這些變更將遺失。
   * 但是，如果您使用 FormIt 材料繪製子群組 (而非其中的幾何圖形)，每次執行都會保留這些材料。請參閱以下內容。

### **使用群組和材料**

* 使用多個 **SendToFormIt** 節點時，您可以依材料組織節點，以便您可以使用不同材料繪製不同的 FormIt 子群組。
* 在此範例中，整個建築是從 FormIt 中的簡單平面產生。每個需要獨特材料的建築元件都會有自己的 **SendToFormIt** 節點：

![](<../.gitbook/assets/dynamo\_sendtoformit (1).png>)

* 將材料套用到每個子群組後，每次 Dynamo 執行都會保留材料：

![](../.gitbook/assets/dynamo\_materialsgif.gif)

### **巢狀 Dynamo 群組**

* 您可以使用 **SelectFromFormIt** 節點從一個 Dynamo 圖表中選取子群組結果，以驅動另一個圖表的結果。&#x20;
* 根據以上的範例，產生建築圖表的釉面玻璃輸出會當作內建 Storefront Curtainwall 範例的選取幾何圖形：

![](../.gitbook/assets/dynamo\_storefront\_curtainwallgif.gif)

* 建築造型變更時，您只需選取竪框系統群組，然後在「性質」面板中按一下「執行」。
   * 雖然釉面玻璃群組的內容改變了，但是群組本身並沒有，因此重新執行圖表時，無需重新選取釉面玻璃。
* FormIt 2022 和更高版本提供上述模型，位於 **Dynamo Samples** 的 **Building Masses** 子資料夾中的「Roof Planes Building」。
* 結合 FormIt 的強大功能，您可以在功能強大、完整具備材料和巢狀邏輯的概念建模工具豐富環境中，使用 Dynamo 建立和調整全參數式設計：

![](../.gitbook/assets/dynamo\_parametricdesigngif.gif)

### **標準的 FormIt 群組行為仍適用**

* 除了上面概述的內容外，FormIt 中 Dynamo 群組的運作規則與其他群組相同：
   * 從 Dynamo 面板放置新的 Dynamo 物件會建立一個單獨群組，不會影響草圖中已放置之相同物件的任何實體。
   * 複製並貼上 Dynamo 群組可使其保持相同。對一個複本的 Dynamo 圖表所做的任何變更，也會更新其相同例證中的幾何圖形，除非它們設為唯一。
   * 您可以使用快速鍵 MU 或透過關聯式功能表將 Dynamo 群組設為唯一：

![](<../.gitbook/assets/dynamo\_makeunique (1).png>)

## 基本 FormIt 節點

在 FormIt 與 Dynamo 之間傳送資料最強大的節點。

### **SendToFormIt 節點**

* 若要在 FormIt 中產生 Dynamo 物件，請將所需的幾何節點輸出連接到至少一個 SendToFormIt 節點的 _geometry_ 輸入：

![](<../.gitbook/assets/dynamo\_sendtoformitnode (1).png>)

* FormItGroupOptions 是 FormIt 2022 中新的 (可選) 埠，詳見下方的 **FormItGroupOptions 節點**一節。
* 在 FormIt 2021.3 和更高版本中，您可以使用多個 SendToFormIt 節點，將 Dynamo 結果組織為整潔的 FormIt 群組和子群組。
* [了解 Dynamo 如何與 FormIt 群組搭配運作](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)。

![](<../.gitbook/assets/dynamo\_sendtoformitnodes (1).png>)

* SendToFormIt 節點遵循「是輸出」旗標，此旗標預設勾選。您可以在節點上按一下右鍵確認：

![](<../.gitbook/assets/dynamo\_isoutput (1).png>)

* 如果勾選，連接至此 SendToFormIt 節點的幾何圖形將出現在 FormIt 中的子群組內。
* 如果不勾選，則不會將任何幾何圖形傳送到 FormIt，也會刪除對應的子群組 (如果有)。

### **SelectFromFormIt 節點**

* FormIt 2021 和更高版本提供從 FormIt 選取幾何圖形以在 Dynamo 圖表中當作輸入的功能：

![](<../.gitbook/assets/dynamo\_selectfromformitnode (1).png>)

* SelectFromFormIt 節點的名稱在 FormIt 中將用作提示，因此您最好以應選取哪種 FormIt 幾何圖形的方式命名：

![](<../.gitbook/assets/dynamo\_selectobjectstoarraynode (1).png>)

* 從 Dynamo 圖表編輯器或「性質」面板按一下「從 FormIt 選取」按鈕時，FormIt 將啟動選取精靈模式，引導您選取幾何圖形：

![](../.gitbook/assets/dynamo\_selectobjectstoarrayUI.png)

* SelectFromFormIt 節點遵循「是輸入」旗標，此旗標預設勾選。必須勾選此選項，在 FormIt 中的選取才有用。在節點上按一下右鍵可確認。

![](<../.gitbook/assets/dynamo\_isinput (1).png>)

* 勾選「是輸入」時：
   * 圖表的 Dynamo 面板縮圖將指出需要選取：

![](../.gitbook/assets/dynamo\_patharray.png)

* 執行圖表時，FormIt 選取精靈將引導您為圖表頂端開始的每個 SelectFromFormIt 節點設定選取。
* 第一次產生後，您會在 FormIt 的「性質」面板中看到每個 SelectFromFormIt 節點的按鈕。

![](../.gitbook/assets/dynamo\_selectarraypath.png)

* 按一下這些按鈕將啟動選取精靈，您就可以變更用於產生最終幾何圖形的選取。重新選取後，圖表將自動重新執行。

### **秘訣、技巧和附註**

* 命名 SelectFromFormIt 節點，指出預期的幾何圖形類型。例如，「選取敷地邊界 (邊緣)」
   * 您可以選取任何類型的 FormIt 幾何圖形，但通常最好將選取內容包含在 FormIt 群組中，並[選取該群組，而非原始幾何圖形](https://formit.autodesk.com/page/formit-dynamo#dynamo-groups)。
* 如果您需要移動選取式 Dynamo 圖表的結果，最好先移動選取幾何圖形，然後重新執行圖表，這會處理更新的選取幾何圖形並適當地自行重新定位。&#x20;
   * 您也可以將 Dynamo 結果**和**選取群組在一起，然後移動包含的群組。
* FormIt 幾何圖形傳送到 Dynamo 後，將幾何圖形傳送回 FormIt 時，任何屬性、材料或巢狀群組都將遺失。
* 如果您在 Dynamo 中編輯以選取式圖表，而選取的幾何圖形在 FormIt 中發生變更，您必須按一下 SelectFromFormIt 節點上的「從 FormIt 選取」按鈕，以重新選取幾何圖形。&#x20;
* 在 FormIt 中選取時，會套用作用中的[選取篩選](https://windows.help.formit.autodesk.com/tool-library/select-edge-face-or-object#selection-filtering)。例如，如果要選取 FormIt 頂點，則必須在「選取篩選」中啟用該頂點。

![](../.gitbook/assets/dynamo\_filterselection.png)

## 其他輸入節點

一系列廣泛的輸入選項，可讓您輕鬆在 FormIt 中自訂 Dynamo 圖表。

### **FormItLengthString 節點**

在 FormIt 2022.1.0 或更高版本中，您可以使用 **FormItLengthString** 節點，以任何支援的 FormIt 單位類型 (英尺-英寸、英寸、公尺、公分、公釐) 指定尺寸，不論作用中草圖中的 FormIt 單位設定為何。

![](../.gitbook/assets/dynamo\_formitlengthstring.png)

與其他支援的輸入節點一樣，_FormItLengthString_ 在標記為「是輸入」時會出現在 FormIt 的「性質」選項板中，更名後，新名稱會出現在 FormIt 中：

![](../.gitbook/assets/dynamo\_propertiespalette.png)

_FormItLengthString_ 節點的每個例證都可以使用任何單位類型，因此單一 Dynamo 圖表可以混合使用單位，如上所示。

### **從原始數字切換成 FormItLengthString**

在 FormIt 2022.1.1 和更高版本中，於 Dynamo 中編輯圖表時，切換圖表為使用 FormItLengthString 節點 (在圖表中放置第一個節點)，或切換圖表為只使用原始數字 (移除最後一個 FormItLengthString)，會變更某些行為：

* 使用 [SelectFromFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點編輯圖表時，如上所示在原始數字與_FormItLengthString_ 節點之間切換，將需要為每個 _SelectFromFormItNode_ 重新選取幾何圖形，結果才會繼續在 FormIt 中正確調整比例。
* 在圖表中放置第一個 FormItLengthString 節點後，圖表中要當作尺寸的所有數字 (包括原始數字輸入) 是指公尺 (其實就是 Dynamo 的原生單位)。
   * [SendToFormIt](https://formit.autodesk.com/page/formit-dynamo#dynamo-formit-nodes) 節點會考慮變更，並確保 FormIt 中產生的幾何圖形保持正確大小。
   * 相反地，從圖表中移除所有 FormItLengthString 節點將切換原始數字，以參考 FormIt 的單位設定 (舊式行為)。
* _FormItLengthString_ 節點的數值輸出也將以公尺為單位，但不會變更 FormIt 中幾何結果的大小：

![](<../.gitbook/assets/dynamo\_outputinmeters (1).png>)

### **其他支援的輸入節點**

標準的 Dynamo 輸入節點在 Dynamo 中標記為「是輸入」時，將顯示在 FormIt 的「性質」面板中：

* Number Slider
* Integer Slider
* Number
* String
* 布林切換

您可以更名輸入節點 (為了清楚表示建議使用)，新名稱將顯示在 FormIt 中：

![](<../.gitbook/assets/dynamo\_cuboidsize (1).png>)

![](../.gitbook/assets/dynamo\_inputs.png)

## 其他輸出節點

從 Dynamo 將非幾何結果顯示到 FormIt 的其他方法。

### **Watch 節點**

標記為「是輸出」的 Watch 節點將顯示在 FormIt 2022 和更高版本之「性質」面板的「Watch 節點輸出」區段中：

![](<../.gitbook/assets/dynamo\_watchnodes (1).png>)

### **顯示 FormIt 通知**

在 FormIt 2022.1 或更高版本中，您可以使用 **UI.ShowNotification** 節點從 Dynamo 圖表顯示 FormIt 端的通知：&#x20;

![](../.gitbook/assets/dynamo\_notifications.png)

### **記錄到 FormIt 主控台**

在 FormIt 2022.1 或更高版本中，您可以使用 **FormIt.ConsoleLog** 節點，將其他資料直接記錄到 FormIt 應用程式主控台 (「腳本輸出」視窗)：

![](../.gitbook/assets/dynamo\_logtoconsole.png)

## FormIt 選項節點

控制是在個別幾何圖形層級或在包含的群組層級，將資料傳送至 FormIt。

### **FormItGeometryOptions**

FormIt 2022.1 和更高版本可讓您使用 **FormItGeometryOptions** 節點自訂個別 Dynamo 幾何圖形如何傳送至 FormIt。

* 為產生的 Dynamo 群組內的個別幾何圖形指定圖層。
* 為產生的 Dynamo 群組內的個別幾何圖形指定字串屬性。

_FormItGeometryOptions_ 節點可以在 _SendToFormIt_ 節點的上游使用：

![](<../.gitbook/assets/dynamo\_formitgeometryoptions (1).png>)

### **FormItGroupOptions**

FormIt 2022 和更高版本可讓您使用 _FormItGroupOptions_ 節點自訂來自 **SendToFormIt** 節點的 Dynamo 群組如何在 FormIt 中產生。

* 指定 SendToFormIt 節點將幾何圖形做為網格還是物件傳送至 FormIt。
* 為 SendToFormIt 節點建立的群組指定圖層。
* 為 SendToFormIt 節點建立的群組指定字串屬性。

您可以透過將 FormItGroupOptions 節點以連鎖鏈結的方式連結在一起，以任意順序使用這些節點的任意組合：

![](../.gitbook/assets/dynamo\_daisychain.png)

## JavaScript API 節點

FormIt 2022.1 和更高版本透過兩個新節點提供從 Dynamo 存取 JavaScript API 和自訂函式的途徑：

### **CallJSAPI**

**CallJSAPI** 節點可讓您直接從 Dynamo 呼叫 FormIt JavaScript API。

![](<../.gitbook/assets/dynamo\_calljsapi (1).png>)

如需函式名稱和參數，請查看我們的 JavaScript 文件，該文件分為兩部分：[FormIt API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_formit.html) 和 [WSM API](https://formit3d.github.io/FormItExamplePlugins/docs/FormItJSAPI/group\_\_mod\_\_jsapi\_\_wsm.html) (塑型核心)。

**CallPluginJS**

相反地，**CallPluginJS** 節點可讓您從載入的外掛程式或從「腳本編輯器」視窗執行的腳本片段呼叫自訂函式。

![](<../.gitbook/assets/dynamo\_callpluginjs (1).png>)

## 重要通知

### **系統需求**

* 若要在 FormIt 中使用 Dynamo，您需要 [FormIt for Windows](https://formit.autodesk.com/page/download) v17.0或更高版本。
   * FormIt 與 Dynamo 整合會定期收到新功能和修正，因此最好在可用時就下載最新更新。
* 您還需要 Windows 10。由於技術原因，不再支援舊版 Windows。

**疑難排解**

* 如果您的系統有 [NVIDIA 或 AMD 顯示卡](https://www.howtogeek.com/414201/how-to-check-what-graphics-card-gpu-is-in-your-pc/)，或多張顯示卡，可能需要將 FormIt 和 Dynamo 設定為使用高效能的 GPU：
   * _C:/Program Files/Autodesk/FormIt/FormIt.exe_
   * _C:/Program Files/Autodesk/FormIt/DynamoSandbox/FormItDynamoSandbox.exe_
   * 如果您有 NVIDIA 卡，[請確保已安裝 NVIDIA Control Panel](https://whatsabyte.com/blog/find-nvidia-control-panel/)
   * 使用 [NVIDIA](https://nvidia.custhelp.com/app/answers/detail/a\_id/2615/\~/how-do-i-customize-optimus-profiles-and-settings%3F) 或 [AMD](https://www.amd.com/en/support/kb/faq/dh-017) 控制台，將下列應用程式設定為使用您的獨立顯示卡：
* 如果您使用非英文的地區設定，可能需要將 Windows 10 的區域設定設為英文，以避免某些 Dynamo 節點發生問題：
   * 從「開始」搜尋「語言」，然後選擇「語言設定」
   * 在「語言」對話方塊的右上方，按一下「管理語言設定」
   * 按一下「變更系統地區設定...」按鈕
   * 選擇「英文 (美國)」
* 如果您在處理小型幾何圖形或數字時發生圖表無法在 FormIt 中產生結果的問題，請嘗試將 Dynamo 比例調整設定變更為「小」：
   * Dynamo 功能表 >「偏好」>「一般」>「調整幾何圖形比例」>「小」

![](../.gitbook/assets/dynamo\_geometryscaling.png)

### **取得支援**

需要 FormIt + Dynamo 的協助？請[在論壇上告訴我們](https://forums.autodesk.com/t5/formit-forum/bd-p/142)。
