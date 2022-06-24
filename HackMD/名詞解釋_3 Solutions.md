# 名詞解釋_3 Solutions
###### tags: `Training` `Solutions Architect`

### ### 解決方案架構師 Training Step_3

1.	Anti-malware
    「Malware」(惡意程式) 是 malicious software (惡意軟體) 的縮寫，這個字指的是病毒、間諜軟體、蠕蟲等。 惡意程式的設計目的是破壞獨立的電腦或已連接網路的個人電腦。 當使用惡意程式這個術語時，即指用來破壞電腦的程式，可能是病毒、蠕蟲或特洛伊木馬程式。
    Anti 反對，Anti-malware 反惡意程式。
    Malwarebytes Anti-Malware (簡稱MBAM) 是一款在 Microsoft Windows 作業系統上執行，可偵測並移除惡意軟體、勒索軟體、漏洞利用的應用程式。它是由malwarebytes公司於2008年1月釋出初版。它有免費版和付費版。前者需手動執行掃描，可偵測並移除惡意軟體；後者比起前者多了排程掃描、即時防護、快閃記憶體掃描等功能。自第1.75版起，MBAM新增掃描壓縮檔內檔案的能力。
    密碼製造機 cres 無用程式 PUP
    sql injection 資料庫注射 attack
2.	Ransomware
    勒索軟體，又稱勒索病毒，是一種特殊的惡意軟體，又被人歸類為「阻斷存取式攻擊」（denial-of-access attack）。
    AV(Anti-Virus)
3.	Advanced Threat Protection (ATP)
    APT(持續威脅)，高級威脅防護
4.	Endpoint Detection and Response (EDR)
    端點檢測和響應(EDR)，也稱為端點威脅檢測和響應( ETDR )，是一種網絡安全技術，可以持續監控“端點”（例如手機、筆記本電腦、物聯網設備）以減輕惡意網絡威脅
5.	Data Loss Prevention (DLP)
    資料外洩防護，
    主要功能：
    防止機密資料從內部流出。
    使用者將電腦攜出內部的離線狀態下，仍然不能將硬碟裡的機密資料傳送出去。
    應用技術：
    格式比對：限制特定的檔案格式傳送。
    關鍵字過濾：限制自定關鍵字及特殊關鍵字(如卡號)的內容傳送。
    特徵辨識：採用指紋（Fingerprint）或標記（Tag）的特徵辨識技術加以識別的檢查程序。
    DLP架構
    網路型（Network-based）
    採用鏡射（Mirror）的架構部署於內部的骨幹網路，過濾封包當中是否帶有機密資料。
    需以G/W即時封鎖目前傳送中的機密資料。
    主機型DLP （Host-based）
    主機型DLP的防護對象以Windows平臺個人端電腦為主，需安裝代理程式。
    這麼做的好處在於可以透過代理程式，直接從個人端攔截資料的傳送，不需要整合其他產品。
    具備較深層的控管能力，像是複製、貼上、列印，及螢幕截圖等動作。
6.	Disk encryption
    磁碟加密（英語：Disk encryption）是一種通過將資訊轉換為無法辨識的編碼來保護資訊的技術，這些編碼無法被未經授權的人輕易破譯，最終防止未經授權存取資料儲存。磁碟加密使用磁碟加密軟體或硬體來加密磁碟或磁碟卷上的每一位資料。
    術語全磁碟加密（英語：full disk encryption，FDE）表示磁碟上的所有內容都已加密，但主開機紀錄（MBR）或類似區域是未加密的。一些基於硬體的全磁碟加密可以真正加密整個啟動磁碟，包括MBR。不過基於硬體的磁碟加密也出現過金鑰可提取等安全問題。
7.	BitLocker
    Windows 內建的全磁碟加密功能。
8.	Sandbox
    沙盒，一種將程式隔離一個環境作為測試、實驗用的安全機制，對環境嚴格進行控制使用的資源像是記憶體與容量，網路與對實體裝置的控制權限等等，是虛擬化的，建立可以隨時被收回而不影響到作業系統的。
    zero days
9.	Firewall
    防火牆
10.	Vulnerability
    安全漏洞指的是系統因設計、實作、操作或內部控制導致的脆弱環節，足以被攻擊者利用，進而危害系統的完整性、可用性與機密性。
    CVE
11.	Intrusion Detection System (IDS)
    - 入侵**檢測**系統
        通常架設在防火牆與內部網路之間，除了偵測並蒐集所有惡意程式的 log 紀錄，透過演算法根據過往的病毒與攻擊方式來判斷惡意程式並阻擋。IDS 也有可能在 DMS 與內部網路之間
        事件產生器，從計算環境中獲得事件，並向系統的其他部分提供此事件；
        事件剖析器，分析資料；
        回應單元，發出警報或採取主動反應措施；
        事件資料庫，存放各種資料。
12.	Intrusion Prevention System (IPS)
    入侵**預防**系統，防禦主機，假如駭客有辦法透過偽裝進入到內部網路，並且發送惡意封包欲探索主機位置，IPS 偵測並判定其為惡意封包時就不會回傳封包，讓 hacks 找不到主機位置。
13.	Proxy
    代理伺服器，允許 Client 訪問 Server 時經過這個服務來訪問，Proxy 伺服器同時也是一個暫存網站資料的暫存伺服器，
14.	Wireless
    無線的，Wireless LAN Controllers(WLC)  
15.	Thin Access Point (Thin AP)
    集中式管理設定 AP 裝置，無線連線。
16.	Fat Access Point (Fat AP)
    傳統無線 AP 透過手動設定，多台連接實體網路線。
17.	Microsoft Exchange
    Microsoft 發行的一套群組軟體，可以很好的與 Microsoft Active Directory 結合進行管理，與 outlook 結合可以只開一個 443 port 即可進行所有傳遞服務。
18.	Virtual Desktop Infrastructure (VDI)
    [桌面結構虛擬化](https://satosi0209.wordpress.com/2010/11/22/%E7%B0%A1%E8%BF%B0%E5%BE%AE%E8%BB%9F%E8%99%9B%E6%93%AC%E6%A1%8C%E9%9D%A2%E5%9F%BA%E7%A4%8E%E6%9E%B6%E6%A7%8Bvdi%E9%81%8B%E4%BD%9C%E6%96%B9%E5%BC%8F%E5%8F%8A%E5%AE%89%E8%A3%9D%E6%AD%A5%E9%A9%9F/)
19.	Multi-factor authentication (MFA)
    多重因素認證，結合不同服務或是與其他平台取得信任關係(連線安全)可以透過單一登入。
20.	Infrastructure as a Service (IAAS)
    基礎設施即服務(AWS EC2)
21.	Software as a Service (SAAS)
    軟體即服務(Applications)
22.	Platform as a Service (PAAS)
    平台即服務(Heroku、AWS)
23.	Cloud Access Security Broker (CASB)
    雲端存取資安代理，頻外配置（Out-of-Band）的 API 控制（API Control），以及內嵌配置（Inline）的反向代理（Reverse Proxy）以及前向代理（Forward Porxy）
    延伸閱讀：[什麼是 CASB？一起認識雲端資安代理](https://hennge.com/tw/blog/what-is-casb-cloud-access-security-broker.html)
24.	Syslog
    系統記錄通訊協定 (System Logging Protocol, Syslog) 是讓網路裝置能夠運用標準訊息格式與記錄伺服器通訊的方法。這是為了簡化網路裝置監控作業而設計的協定。在各種具體情況下，裝置都能使用 Syslog 代理程式發出通知訊息。
    由於 syslog 會產生大量的系統訊息，因此需要大型資料庫做儲存，而需要再 syslog 監控其發生況狀的回報可以使用 SIEM 軟體做管理。
    Syslog 的一大優點就是記錄伺服器可以透過記錄檔監控大量的 syslog 事件。路由器、交換器、防火牆以及伺服器都會產生記錄訊息，許多印表機和其他裝置也一樣。
    [syslog server](https://www.whatsupgold.com/tw/blog/what-is-a-syslog-server-and-how-does-it-work)
25.	Security Information and Event Management (SIEM)
    資訊安全管理、資安事件管理(SIEM)，將 syslog 的 log 檔收集之後做正規化轉換，進而進行相關資安事件的分析，輔助 IT 部門或專責的資安部門對企業資安達成早期預警及事後分析。

### Additional materials：

Vulnerability 相關
CVE 

Service Provider: ePolicy Orchestrator (ePO) 2023

建議條件修得

Service Provider: Endpoint Protection 2023


Intranet 

Extranet

Data loss prevention - Endpoing (sophos, McAfee)
                     - Network (McAfee) 手法：關鍵字、正規表示法
Disk Encryption -> Bitlocker (透過演算法規律打亂) McAfee MDE Drive Encryption 

- File Encryption 
    -> 內部(透明加密)透過應用程式 example word 儲存的檔案就需要加密(檔案開不起來)
    -> 外部 example finalcode 檔案加密

Cloud DCP -> CASB

FinalCode Client 1~2 透過金私鑰來取決 Client 是否可以打開檔案(.fcl)，若非指定的私鑰則無法透過 Finalcode軟體打開，打開則遠端自動刪除，並回傳LOG。

(.html)檔案則可以讓他者透過 Browser 唯讀


thin ap fat ap 差別 
Tunnel mode    split tummel
complete tunnel

連上 thin ap 之後透過虛擬通道到 WLC 
檢查流量後才連上網路

MFA 型一 型二 型三 VPN綁手機確認

KIWI Syslog

Siem leef cef log
