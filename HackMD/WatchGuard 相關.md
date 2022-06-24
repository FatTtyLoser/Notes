# WatchGuard 相關
###### tags: `Firewall`

### 過保型號重置回原廠設定並升級韌體

1. 首先進入到 [Recover mode](https://www.watchguard.com/help/docs/help-center/en-US/Content/en-US/Fireware/other/QSW_recovery_mode_wsm.html) 官網可以查詢細節

2. [WSM Watch guard system manager](https://www.watchguard.com/help/docs/help-center/en-US/Content/en-US/Fireware/installation/install_wsm_wsm.html)
    離線管理、設定 Firewall 的管理程式，預先到官網下載，另外一種方式是透過網頁進行設定，連網時設定速度相對慢。

3. Discovery 回復原廠設定的幾個步驟
    a. firmware update(2022/05/18:ver.12.8)
        到官網下載對應型號中最新的韌體版本
    b. feature key
        透過 Partner Portal 查詢已註冊(本公司出售過的產品型號)，找到相對應的機型與名稱，下載 feature key 備用。
    c. config.file
        由於回歸要回歸原廠設定，因此要預先把設定檔匯出，如果更換設備則先在舊設備中匯出。
    

4. WatchGuard 對出廠機器的預設密碼，用於新設定與新匯入設定時
    - 唯讀 **readonly**
    - 讀寫 **readwirte**
    延伸問題：為什麼在欲更換下來的舊機所設定的兩組密碼，再匯入新機型的時候並不需要使用設定過的密碼？
    
    
Any 跟 TCP/UDP 有 Port Numbers 差異

退貨授權(Return merchandise authorization，簡稱RMA)
![使用 Putty SSH 連線到 FW 後台](https://i.imgur.com/yosjmKJ.png)
透過 Putty 連線到後台鍵入檢查 hardware 系統的指令，diagnose hardware system。
![正常狀態下的顯示內容](https://i.imgur.com/GvpL4Kq.png)
![有問題下的顯示內容](https://i.imgur.com/ppBTLAN.png)


Port Scan 防護，通常直接 Blocked prots 1&65535。

Server Load Balance 伺服器負載均衡，當有兩台對外伺服器需要走同一個 IP 時使用負載均衡，並且要設定 Enable Sticky Connection 避免同一個 Source IP 短時間重新連線時，需要重新輸入密碼。
跟 NAT 的設定雷同，因為都必須將一個對外 IP 做轉址。

policies that were left with empty From or To field. Please correct the following policies. by adding addresses to their empty From or To fields. Allow_Internal to Lab, Deny_Lab to Internal




