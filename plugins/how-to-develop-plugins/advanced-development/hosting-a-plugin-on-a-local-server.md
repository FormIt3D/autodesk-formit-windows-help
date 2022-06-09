# 在本端伺服器上裝載外掛程式

在 FormIt 中預覽複製的外掛程式之前，您必須將其裝載在本端伺服器上。

### **在 IDE 中檢視終端機**

您可以選擇在 Visual Studio Code 中啟動伺服器，而不是在單獨的終端機視窗中啟動。\*\*\*\* 開啟終端機之前，請確保在 Visual Studio Code 中開啟正確的資料夾。

「檢視」>「終端機」(或快速鍵 Ctrl + \`)

![](<../../../.gitbook/assets/image (11).png>)

### 設定 HTTP 伺服器

運作正常的 HTTP 伺服器是 npm 的[http-server](https://www.npmjs.com/package/http-server)。

首先，您必須下載並安裝 [NodeJS](https://nodejs.org/zh-tw/) (如果尚未安裝)。

如果在以下步驟遇到錯誤，請嘗試重新啟動電腦以完成 NodeJS 安裝。

在指令提示下，輸入以下內容以全域安裝 npm 的 _http-server_ (一次性設定)。

* `npm install http-server -g`

![](<../../../.gitbook/assets/image (47).png>)

### 啟動本端伺服器

設定完成後，在終端機中執行以下指令以啟動 npm http-server：

* `http-server`

![](<../../../.gitbook/assets/image (84).png>)

秘訣 1：如果執行 http-server (全域安裝或本端安裝) 時發生任何問題，直接透過 npx 執行它可能會有幫助：

* `npx http-server`

秘訣 2：如果是 Windows 10/11 使用者，如果您在新電腦上執行指令碼時遇到錯誤，這可能是因為設定已停用。若要解決此問題，請執行下列操作：

* 以系統管理員身分啟動 PowerShell 指令碼
* 輸入：`Set-ExecutionPolicy RemoteSigned`

### 為 FormIt 網頁版進行開發

若要為 FormIt 網頁版進行開發，只需改為執行以下指令：

* `http-server --cors`

![](<../../../.gitbook/assets/image (10).png>)

### 確認您的伺服器

您可以在網頁瀏覽器中導覽至以下地址來確認伺服器：

* http://localhost:8080

您應該會在瀏覽器視窗中看到您的專案資料夾檔案。

\*\*如果您使用的網頁伺服器不是 npm，則預設地址/連接埠可能不同。

![](<../../../.gitbook/assets/image (41).png>)
