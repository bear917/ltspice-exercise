# .tran 指令
當需要繪製電壓對時間或是電流對時間這類 **時域** 波形圖時，會使用 .tran 指令。
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/tran-plot.png)

範例（觀察 DSB-SC AM 訊號）
最簡短的設置僅需要設定「stop time」即可，一般會取適當長的時間讓波形不會擠滿整個畫面而無法觀看。

範例（觀察 DSB-LC AM 訊號）
> ![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture3/tran-stop.png)

# AC 訊號源
如果需要使用交流電壓源（或交直流混合電壓源）