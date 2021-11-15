# .tran 指令
當需要繪製電壓對時間或是電流對時間這類 **時域** 波形圖時，會使用 .tran 指令。

> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/tran-plot.png)

> ![]()
最簡短的設置僅需要設定「stop time」即可，考慮到太多週期的訊號會導致難以閱讀，會設置輸入訊號的三到四個週期當作觀測時間長度。
>>>>>>> Stashed changes

範例（觀察 DSB-SC AM 訊號）
最簡短的設置僅需要設定「stop time」即可，一般會取適當長的時間讓波形不會擠滿整個畫面而無法觀看。

範例（觀察 DSB-LC AM 訊號）
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/tran-stop.png)

# AC 訊號源

如果需要使用交流電壓源（或交直流混合電壓源），以下示範各種波形最簡易的設定參數
## sine
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/volt-source-sine.png)
## pulse 之一：梯形波
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/volt-source-trapezoid.png)
## pulse 之二：鋸齒波
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/volt-source-sawtooth.png)
## pulse 之三：方波
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/volt-source-square.png)
## pulse 之四：脈衝
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/volt-source-pulse.png)

### 訊號延遲開始
如果想要讓訊號在 t=0 之後才開始，可以設置 Tdelay 參數，範例如下：
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/waveform-delay.png)
## 非週期訊號
很多時候，會需要一組訊號，它只會在某個時段出現，這個時候會需要使用 Ncycle 參數來設定出現次數。
### 範例（開關訊號）
開關訊號通常都會有一個 off 狀態，然後隨機在某時產生 on 狀態，這個時候可以用 Ncycle 指定訊號只產生一次。
下面這個開關訊號，off 狀態輸出 5V，on 狀態輸出 0V，在 3msec 的時刻，開關切換至 on，並且只打開一次。可以用下面的設定產生模擬開關的波形。
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/waveform-switch-on.png)

## AC 訊號源內阻
考慮到訊號源的寄生效應時，可以在設定 AC source 時，一併設定寄生參數。
### 範例（喇叭電路） 
以下示範喇叭的負載效應，如果不設定 AC source 的輸出阻抗時，將無法將喇叭的負載效應反應在波形上。（即喇叭分壓遠小於函數產生器設定值的現象）
設定過程
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/internal-impedance.gif)
模擬結果
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/speaker-voltage.png)

# 波形圖上的操作
## 更改曲線粗細
## 縮放波形
## 呼叫游標
## 標示座標

如果需要使用交流電壓源（或交直流混合電壓源）在擺放電壓源之後，右鍵選單選擇「Advanced」

