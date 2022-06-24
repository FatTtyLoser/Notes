# 名詞解釋_4 Troubleshooting
###### tags: `Training` `Solutions Architect`

### ### 解決方案架構師 Training Step_4

1.	TeamViewer
    遠端桌面服務，免費版有限定個人使用，流量異常可能導致被判斷為商用而禁止免費版，封鎖方式是透過 MAC 地址，解鎖只能更換網卡或是申訴成功。
2.	AnyDesk
    遠端桌面服務，除了TV的另外一個選項。遠端桌面服務透過應用程式產生一組UID，兩台電腦輸入對方的UID即可成功連線、設定信任設備或是掛載選項等等，就算重開機還可以自動連線。
    Aweray 香港軟體公司產品，同是遠端桌面服務，推行手機遠端到PC玩遊戲的方式。
3.	[Putty](https://www.putty.org/)
    putty.exe是一個可在windows平台上ssh連線的一套免費軟體，相容於Windows 95、98、ME、NT、2000 and XP，使用putty的ssh連線功能，可以避免因telnet明碼傳輸所造成的安全問題。
    連接 switch 的 console Port 連接到實體網路設備
    Windows內建的OpenSSH。SCP (傳輸檔案) SSH(LINUX) 遠程連到 LINUX 做管理
    console1 console2
    [bitvise](https://www.bitvise.com/download-area) SSH Clent&Server
4.	Wireshark
    收取網路流量，觀察流經自己電腦上特定網卡的封包，觀察是否有異常的行為出現，像是有些惡意程式會在電腦背景執行或是向外連線取得指令、偷傳資料等等。使用教學：[參考資料](https://www.cnblogs.com/linyfeng/p/9496126.html)
5.	Microsoft Process Monitor
    進程監視器，用於監控Microsoft所有檔案與登錄檔，任何刪除更改等事項都會被記錄。
6.	Windows Temp
    Temp(Temporary files)，Tmp, Temp是Windows的暫存檔案，在瀏覽網頁、執行應用程式時所產生的暫存檔案，
7.	Services.msc
    用於控制系統服務，啟動、中止、設定Windows的服務。
8.	Windows Event Viewer
    事件檢視器(Win+R v)開啟，可以看見Windows執行的所有事件包含警訊與錯誤訊息，可以在裡面找到關於錯誤訊息的xml用以查詢原因。
9.	tracert
    透過封包回傳可以追蹤途經的路由，上限30個。
10.	nslookup
    透過nslookup可以解析DNS紀錄將主機名稱轉譯成IP位址，`nslookup www.google.com`可以查詢google的IP位址。
11.	[VirusTotal](https://www.virustotal.com/gui/home/upload)
    可以測試各式檔案是否為病毒的網站，只要將檔案上傳到VirusTotal就可以以病毒特徵檔資料庫去比對檔案的內容。可以透過email上傳128MB以下的檔案，缺點是無法對電腦做健全的掃瞄。
12.	EICAR
    標準反病毒測試檔案，歐洲反電腦病毒協會(EICAR)與電腦病毒研究組織(CARO)研製的檔案，用以測試防毒軟體的回應程度，
    EICAR的測試字元為`X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*`    [測試檔案下載](https://secure.eicar.org/eicar.com.txt)
病毒測試碼
```
X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*
```
### 補充

FTP(22)
SFTP(安全檔案傳輸協定)(22)
Telnet(23)

trunk 除了應用在VLAN之間的通訊，在Core Switch到PoE(power of ehernet)Switch之間，使用trunk確保無線網路的頻寬。

168.95.1.1 CHT 的 DNS 位置

splunk siem

- CONF 檔案格式為 Text 分類為設定檔，分為
    1. 支援 macOS, Linux 的 Unix Configuration File 檔案
    2. 支援 Windows, macOS, Linux 的 Generic Configuration File 檔案