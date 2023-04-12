# 3D Context Creator

\![](<../../.gitbook/assets/3D Context Creator_new.gif>)

## 這是什麼？

3D Context Creator 是一個容易使用的外掛程式，可在 FormIt 中產生 3D 環境的建築。

此外掛程式可協助您視覺化專案敷地及其周圍環境，並在設計過程的早期階段做出明智決策。

此外掛程式會從 [Open Street Map](https://www.openstreetmap.org/about) 擷取資料，以協助將其轉換為 FormIt 幾何圖形。此外掛程式的原始程式碼位於 [Github](https://github.com/matterlab-co/FormIt-Context-Plugin)。

## 如何使用

若要安裝，只需從 Plugin Manager 切換外掛程式的開關即可啟用，就像使用其他任何外掛程式一樣。

![](../../.gitbook/assets/contextcreator3.png)

開啟後，外掛程式應該會顯示在應用程式的右側，並準備好供您使用。

\![](<../../.gitbook/assets/3D Context Creator new_no location (1).png>)

如果您的敷地還沒有位置，您可以按一下 **「Set Location...」** 連結來設定位置，並定義將用來產生 3D 環境的邊界。

設定好位置後，3D Context Creator 將使用目前位置更新，且按鈕將啟用：

\![](<../../.gitbook/assets/3D Context Creator new_with location.png>)

3D Context Creator 只會單純使用衛星影像的範圍來產生 3D 環境。您只需按一下 **「Generate 3D Context」**!

根據衛星影像的範圍和建築的複雜性，這可能需要幾秒鐘的時間才能產生。

3D 環境的建築會自動放置到群組實體中，並放置在名為「Context Buildings」的圖層上。 您可以使用此圖層切換環境的可見性。

\![](<../../.gitbook/assets/3D Context Creator_layers.png>)

\![](<../../.gitbook/assets/3D Context Creator_NYC.png>)

如果您稍後決定變更位置或調整衛星影像的範圍，可以再按一下 **「Generate 3D Context」** 重新產生建築。

_請注意，重新產生環境將以新的群組實體取代包含建築的群組實體，因此對建築所做的任何變更都將遺失。_若要避免發生這個狀況，您可以解除環境容器的群組，然後重新群組。

## **一些範例**

請試著猜猜看下列環境描繪的是哪些代表性城市：

\![](<../../.gitbook/assets/image (2) (1).png>)

\![](<../../.gitbook/assets/image (34).png>)

\![](<../../.gitbook/assets/image (13) (1) (1).png>)

\![](<../../.gitbook/assets/image (59).png>)
