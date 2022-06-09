# 外掛程式簡介

![](../.gitbook/assets/gg4.gif)

外掛程式是擴充 FormIt 核心功能的自訂軟體附加程式。外掛程式可以增進、強化和簡化 FormIt 中的 3D 塑型工作流程。&#x20;

外掛程式可用來產生物件、修改既有物件或擷取物件的相關資訊。外掛程式也可以使用豐富的網頁介面來顯示資料，以及直接在應用程式中提供控制和輸入。&#x20;

## 存取外掛程式

只要您連線至網際網路，就可以在 FormIt 的桌面版和網頁版的 [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) 中使用外掛程式。外掛程式由一系列裝載在 GitHub 的檔案和資料夾組成，或在您建置自己的外掛程式時，由本端伺服器上的檔案和資料夾組成。&#x20;

![](../.gitbook/assets/c17.PNG)

### 外掛程式需要網際網路存取

外部的外掛程式 (不在本端裝載的外掛程式) 需要網際網路連線才能初始載入，這表示：

* 如果 FormIt 啟動時未偵測到網際網路連線，則不會載入外部外掛程式。載入後，有些外部外掛程式可以繼續在該工作階段的離線模式下運作，但有些外掛程式可能會中斷，直到連線恢復。&#x20;
* 外部外掛程式在每次執行時會在伺服器上載入最新的程式碼，因此每當作者推送變更時，功能都會更新。外掛程式並非同步載入，這表示外掛程式在 FormIt 介面中的順序可能會隨每個新工作階段而變更。

## 開放源碼

外掛程式是開放原始碼，可讓您免費使用 [Plugin Manager](how-to-use-plug-ins.md#plugin-manager) 中的外掛程式，輕鬆發佈和共用外掛程式，並在 GitHub 尋找其他外掛程式以了解它們的建置方式。&#x20;

如果您是開發人員，想要獲得如何發佈外掛程式的更多資訊，請參閱[在 GitHub 裝載外掛程式](how-to-develop-plugins/advanced-development/hosting-a-plugin-on-github.md)。&#x20;

如果您要製作外掛程式供私人使用，可以使用本端服務來開發和裝載。如需更多資訊，請參閱[使用 IDE。](how-to-develop-plugins/advanced-development/using-an-ide.md)

![](../.gitbook/assets/c18.PNG)



## 與我們聯絡

如果您需要 FormIt 外掛程式的任何協助，請在 [FormIt 論壇](https://forums.autodesk.com/t5/formit-forum/bd-p/142?profile.language=zh-CN)留下訊息。

![](../.gitbook/assets/c19.PNG)

&#x20;

&#x20;
