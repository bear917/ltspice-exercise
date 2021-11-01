# SPICE 語言
[SPICE; Simulation Program with Integrated Circuit Emphasis](https://en.wikipedia.org/wiki/SPICE)是用來描述電路並可用作模擬的一種程式語言。 LTspcie是一種利用圖形界面編輯的 SPICE 的應用程式，在製作 schematic 電路藍圖時，同時也會產生相對應的 netlist 檔案，檔案內容就是用 SPICE 語法表示電路連接關係與模擬所需設定。同學在使用這類應用程式時，仍須對於 SPICE 語法具有一定程度認識。

schematic 與 netlist 實際範例
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/schematic-and-netlist.png)

# .op 指令
我們經常關注電路中各元件的電壓與電流大小，這個時候可以使用 .op 指令配合 .op label 去觀察有興趣的節點，不管是電壓或是電流，皆可以標示出來。

請注意：欲使用 .op label 時，必須進行至少一次的 simulate，讓電腦存有第一次的計算結果才能標示。
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/sim-op.png)

以下範例為，電路尚未模擬時，未存在計算結果，.op data label 無法選擇的狀態
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/no-op-data.png)

執行一次模擬後，呼叫 .op data label 的範例
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/add-op-label.gif)

# 註解
註解在模擬電路的過程中，不參與計算。純粹做為標示使用，一般來說，為了增加電路圖的可讀性，會進行適當的標示。
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/Text.png)
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/edit-text.png)
# net name
系統預設的節點名稱為 nxxx，例 n001、n002、…，自動編號的節點名稱並不好理解其意義，同時也不方便在圖面上尋找其位置。所以會使用「Label net」 來自訂節點名稱。
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/Label-Net.png)
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/edit-label.png)

電路圖上標示相同節點名稱的，都是同一節點，即使圖上沒有使用 wire 連接，常見於電源連接的表示。
下面兩張電路圖雖然圖面上看起來不一樣，但是電路組態是一模一樣的（兩張電路圖的 netlist 完全相同）
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/connect-seperately.png)
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/connect-together.png)

# LTspice 使用的數字表示法
常用表示法
- aeb; $3 \times 10$
- f; 1e-15
- p; 1e-12
- n; 1e-9
- u; 1e-6

## .op 實際範例
請同學參考 ckt-2-1.asc、ckt-2-2.asc 檔案。並請嘗試從頭到尾重現一模一樣的電路並模擬。

參考結果
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/result.png)