# 把參數也當作變數的模擬：DC sweep 功能與 .step param 語法
如果想要改變模擬過程中的參數（譬如：電阻值、電容值、電感值、電晶體偏壓等），產生類似特性曲線的圖形（橫軸不是時間軸）就必須善用 DC sweep 或是 .param 的 SPICE 語法。

## 範例1：理想電阻其跨壓與通過電流關係
+ **DC sweep 的 source，在原始參數必須為一個任意數值**
+ **忘記設定原始參數，模擬時會報錯**

### 範例（忘記設定 I1 電流源的直流值，保留預設符號 I）
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/missing-value.png)

假設待測電阻為 1k Ohm，欲觀察其電壓對電流的關係，可採用下面指令（模擬運算必須給定起點、終點條件，電腦並不存在無限延伸的概念。此外，計算次數也須給定，也就是設定條件增幅 Increment）
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/ohms-law.png)

在輸出結果圖上指定測量 R1 對地電壓（即 R1 的跨壓），因為是理想電阻所以滿足歐姆定律，跨壓與通過電流成正比。
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/dot-dc-meaning(one-source).png)

## 如果有多組直流訊號源要改變，LTspice 最多可提供三組 source（未使用可留空白）多組 source 執行先後順序，可以用程式語言的 for 迴圈稍微說明。

### 執行順序概念說明（並非真實程式）
```C
for (3rd source) {
	// Do task3
	for (2nd source) {
		// Do task2
		for (1st source) {
		// Do task1
		}
	}
}
```
### 範例2：電路中的可變電阻
考慮下圖分壓電路，假設 R1 從 1K Ohm 增加到 10k Ohm（每次漸增 1K Ohm）。
電路圖
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/voltage-divider.png)

如果想觀測節點 out 的電壓變化，可以進行下面操作:
1. 將想設置為可變的參數設置為 {X}
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/set-x.png)

1. 增加 .step 指令並使用 param 語法
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/set-step-param.png)

1. 如果使用繪圖方式觀看結果，記得標示不同條件對應的波形
** view -> step legend 功能僅出現在觀察單一節點。波形圖如果有二個以上節點，該功能無法啟用。**
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/step-legend.gif)

結果圖
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture4/result.png)