# McAfee 筆記
###### tags: `McAfee`

- AMCore 更新時間設定 
    McAfee Labs 會在每天晚上 7 點 (GMT/UTC)/台灣凌晨 3 點 (UTC+8) 前發佈 AMCore 內容套件。若確認有新的威脅，便可能會提前發佈每日的 AMCore 內容檔案，有時可能會延遲發佈。
    因此設定用戶端工作的時間可以設置二至三個時段，在凌晨 5 點 Server 不關機時可以即時更新，或者早上 9 點確保上班時間內更新，以及中午時段的時間可以確保更新延遲發佈或是稍晚接受更新。

- Client 完整掃描參考
![Client 完整掃描參考](https://i.imgur.com/lgTN60G.png)

- 存取保護的規則參考
![存取保護原則1](https://i.imgur.com/TzZsqwF.png)
![存取保護原則2](https://i.imgur.com/XAl9frg.png)
![存取保護原則3](https://i.imgur.com/8w8MyeM.png)

- Advanced Threat Defense
    可偵測零時差惡意軟體，並結合防毒特徵碼、信用評價和即時模擬防禦。
    阻絕規則中可以針對指定行為進行判定，可選擇封鎖、報告或同時選取，同時也可以設定指定排除的應用程式，代表可以執行。
CSDN 文章參考：[查看檔案 MD5, SHA-1 方法(Linux,Windows)](https://blog.csdn.net/nuanhua209/article/details/78403246)

- ENS Web controll - block browser
Browser 支援項目

封鎖使用下列不支援的瀏覽器:

Opera
Safari for Windows
Netscape
Maxthon
Flock
Avant Browser
Deepnet Explorer
PhaseOut

封鎖使用下列支援的瀏覽器:

Internet Explorer
Firefox
Chrome
Edge
Chromium Edge