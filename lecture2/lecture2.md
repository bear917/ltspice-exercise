# SPICE 語言
[SPICE; Simulation Program with Integrated Circuit Emphasis](https://en.wikipedia.org/wiki/SPICE)是用來描述電路並可用作模擬的一種程式語言。 LTspcie是一種利用圖形界面編輯的 SPICE 的應用程式，在製作 schematic 電路藍圖時，同時也會產生相對應的 netlist 檔案，檔案內容就是用 SPICE 語法表示電路連接關係與模擬所需設定。同學在使用這類應用程式時，仍須對於 SPICE 語法具有一定程度認識。

## schematic 與 netlist 實際範例
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/schematic-and-netlist.png)

## model 內容範例（以 NE555 為例）
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/inside-model-file.png)

# .asc 檔案預設儲存位置
很多時候同學會找不到已經儲存的檔案放在哪裡，原因就是因為當你按下 save 時，檔案會直接存在預設資料夾中，LTspice 不會主動問你要存放的位置。因此有兩個方法可以解決這個問題。
## 解法一：另存新檔（推薦）
在 File 選擇 save as 另存新檔，可以自己選擇要存放的位置。存過一次之後，LTspice 會記住目前這個檔案存放的地方，而不會使用預設位置。直到下一次開新檔案後，才會再使用預設位置。
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/save-as.png)
## 解法二：改變預設位置（不推薦，僅供進階使用者）
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/default-directory.png)

# .op 指令
我們經常關注電路中各元件的電壓與電流大小，這個時候可以使用 .op 指令配合 .op label 去觀察有興趣的節點，不管是電壓或是電流，皆可以標示出來。

請注意：欲使用 .op label 時，必須進行至少一次的 simulate，讓電腦存有第一次的計算結果才能標示。
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/sim-op.png)

## 以下範例為，電路尚未模擬時，未存在計算結果，.op data label 無法選擇的狀態
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/no-op-data.png)

## 執行一次模擬後，呼叫 .op data label 的範例
>![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/add-op-label.gif)

# 電壓判讀
因為 SPICE 定義的電壓大小一定是 **對地電壓**，因此每張電路圖都必須標示 GND 位置，否則模擬器在無法得知 GND 位置的情況下，無法開始計算。
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/GND.png)

警告視窗如下：
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/no-gnd.png)
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
常用表示法 [參考資料](https://en.wikipedia.org/wiki/LTspice#Number_conventions)
- AeB; A x 10<sup>B</sup>
- G; 1e9
- *MEG*; 1e6
- k, K; 1e3
- m, M; 1e-3
- u; 1e-6
- n; 1e-9
- p; 1e-12
- f; 1e-15

## .op 實際範例
請同學參考 [ckt-2-1](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/ckt-2-1.zip)、[ckt-2-2](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/ckt-2-2.zip) 檔案。並請嘗試從頭到尾重現一模一樣的電路並模擬。

<<<<<<< Updated upstream
## 參考結果
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/result.png)
=======
參考結果
>![iamge](https://github.com/bear917/ltspice-exercise/blob/main/lecture2/result.png)
>>>>>>> Stashed changes
