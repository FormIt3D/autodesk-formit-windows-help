---
描述：>- 從設計程序開始，透過評估元素的效能來啟動 BIM 工作流程。
---

# 日光和能源分析

\![](<../.gitbook/assets/20220317 Solar Analysis.png>)

## FormIt 中的能源分析

在設計程序早期分析建築模型的能源效率。

[檢視您的 Insight 專案](https://gbs.autodesk.com/OneEnergy/Insight)

## 使用 Insight 進行能源分析

透過[工程建設軟體集](https://www.autodesk.com/collections/architecture-engineering-construction/overview)取得 **FormIt Pro** 固定期限的使用授權，您就可以使用 **Insight** 存取能源分析：

* 使用 Green Building Studio 的分析引擎來分析早期設計模型
* 連線至分析結果的管控面板視圖，以比較設計的選項
* 調整「能源分析」係數工具集，例如「窗對牆比率」、「建築方位」等等
* 以每單位面積的底線成本計算的單一數字來總結建築的能源影響
* 儲存您的能源分析結果，以供客戶和其他專案關係人日後檢閱

## FormIt + Insight 的新增功能 <a href="#insight-what-s-new" id="insight-what-s-new"></a>

### **改進 Insight 可靠性** <a href="#improvements-to-insight-reliability" id="improvements-to-insight-reliability"></a>

* [FormIt 2021](https://formit.autodesk.com/blog/post/introducing-formit-2021) 現在會在啟動 Insight 執行之前，檢查您的模型是否有常見的模型問題，並修正常見的 Insight 故障，提供更可靠的體驗。
* FormIt 2021 也通常會改善 FormIt + Insight 連接的可靠性，解決許多已知故障並提高執行成功率。

## 入門 <a href="#insight-getting-started" id="insight-getting-started"></a>

### **如何運作** <a href="#how-it-works" id="how-it-works"></a>

* Insight 能源分析會上傳您的 FormIt 模型資料，在雲端執行數百個分析，以決定各種能源分數
* 能源分析使用 Revit 分析您的模型，因此，就像將 FormIt 資料傳送至 Revit 時一樣，您必須[確保您的 FormIt 模型無縫且流形](https://formit.autodesk.com/blog/post/repairing-solid-models)

### **準備 FormIt 模型** <a href="#preparing-your-formit-model" id="preparing-your-formit-model"></a>

* Insight 將使用 FormIt 草圖中任何可見的幾何圖形
  * 確保您要分析的建築殼體是唯一可見的幾何圖形
  * 將支援幾何圖形 (例如點景、家具和敷地元素) 放在單獨的[圖層](../tool-library/layers.md)上，並關閉圖層
* Insight 搭配簡單、實體的建築模型時運作得最好
  * 確保建築量體是[實體且無縫](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * 如果您的建築設計已有門窗的開口，最好針對能源分析特別建立一個沒有開口的新量體，並使用「圖層」隱藏更詳細的版本
* 簡單的建築量體必須套用[樓層](../tool-library/levels-and-area.md)
* FormIt 模型必須設定[位置](../tool-library/setting-location.md)

![](../.gitbook/assets/insight.png)

### **開始能源分析** <a href="#starting-energy-analysis" id="starting-energy-analysis"></a>

* 在工具列中尋找「能源分析」按鈕

![](../.gitbook/assets/generate\_insight.png)

* 按一下「產生見解」啟動程序
* 這會上傳可見的模型資料，並在雲端執行數百個模擬
* 完成後，螢幕頂部會出現一則訊息，功能表將更新以指出新的見解已準備好進行檢視
  * 按一下「檢視見解」，以在網頁瀏覽器中檢視分析
  * 您也可以在 [Autodesk Insight](https://gbs.autodesk.com/OneEnergy/Insight) 找到您所有的見解。

## 疑難排解 <a href="#insight-troubleshooting" id="insight-troubleshooting"></a>

### **一般錯誤** <a href="#common-errors" id="common-errors"></a>

* 「無法建立 Insight 專案。請稍後再試一次。」
  * 登入 [Green Building Studio 管控面板](https://gbs.autodesk.com/GBS/Project)，然後重新啟動 FormIt
    * 如果您無法登入，或者您看到「存取遭拒」頁面，可能需要[購買 Green Building Studio 固定期限的使用授權](https://knowledge.autodesk.com/search-result/caas/CloudHelp/cloudhelp/ENU/BPA-Help/files/GUID-7FCFF904-F943-4020-BF7F-53AA7148673D-htm.html)
  * 確認您的模型是[實體且無縫](https://formit.autodesk.com/blog/post/repairing-solid-models)
  * 在 [Autodesk 健全狀況管控面板](https://health.autodesk.com/)檢查 FormIt 服務是否有任何問題
* 若要查看 Green Building Studio 是否成功執行此專案的能源分析，請查看 [Green Building Studio 管控面板](https://gbs.autodesk.com/GBS/Project)
  * 您最新的專案會顯示在清單的頂端，並顯示 248 次執行
  * 如果顯示 0 次執行，請[在 FormIt 論壇告訴我們](https://forums.autodesk.com/t5/formit-forum/bd-p/142)，我們可以協助進一步疑難排解

### **詳細記錄** <a href="#detailed-logs" id="detailed-logs"></a>

* FormIt 網頁版在能源分析失敗時提供其他詳細資料：
  * 移至 [FormIt 網頁版](https://formit.autodesk.com/app)
  * 開啟能源分析有問題的模型
  * 執行能源分析
  * 開啟開發工具 (在 Google Chrome 或 Firefox 中按一下 F12)
  * 查看「Console」頁籤
  * 複製或螢幕擷取任何錯誤，並[在 FormIt 論壇回報這些錯誤](https://forums.autodesk.com/t5/formit-forum/bd-p/142)

## 日光分析

透過[工程建設軟體集](https://www.autodesk.com/collections/architecture-engineering-construction/overview)取得 **FormIt Pro** 固定期限的使用授權，您就可以看見太陽對建築的影響：

* 指定要分析日光影響的相關面
* 在應用程式圖元區內以幾秒的時間視覺化結果
* 將滑鼠懸停在輸入點上，可查看日光影響的特定計算值
* 選擇每月進行釉面玻璃研究，或每年進行太陽能板可行性研究來檢視結果

進一步了解 FormIt Pro 中的[日光分析](../tool-library/solar-analysis.md)。
