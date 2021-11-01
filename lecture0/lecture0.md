# 關於模擬與真實物理現象的差距
在沒有任何前提的假設條件下，模擬結果與真實物理現象可以說是沒有任何關係。因為真實物理現象通常為非線性，難以用簡單數學公式描述。即便是可以用微分方程寫下的物理現象，也因為有限的邊界條件或物理參數，而無法得到一個通解進而預測所有結果。所以使用任何模擬軟體時，務必要知道模擬結果僅能當作參考，其參考價值取決於你可以提供的數學模型、各種物理參數的準確度。以歐姆定律為例，如果總是認為待測物跨壓除以流過的電流為常數，這個結果將無法預測因為熱效應導致待測物產生的電阻變化。再舉另一個例子，我們經常以電阻標示值當作模擬使用的參數，但真實情況常常發生，實際電阻值不等於標示值，在這種情況下進行的模擬，當然會跟實驗結果有差距。
# 實驗課使用的工具軟體
市售電路模擬軟體很多，實驗課採用的是由 [Analog Devices](https://en.wikipedia.org/wiki/Analog_Devices) 提供的合法授權軟體 [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html)
# 官網提供的教育資源
官網除了可以下載安裝檔案以外，還提供電路模擬範例、手冊、元件模型檔等。請有興趣的同學先行研究看看。
![image](https://github.com/bear917/ltspice-exercise/blob/main/lecture0/official-resources.png)

