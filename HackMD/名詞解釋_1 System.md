# 名詞解釋_1 System
###### tags: `Training` `Solutions Architect`

### 解決方案架構師 Training Step_1

* 專有名詞(系統篇-1)

1.	CIA Triad[(CIA三要素)](https://zh.wikipedia.org/wiki/%E4%BF%A1%E6%81%AF%E5%AE%89%E5%85%A8)
    機密性(Confidentiality) 
    keeping information secret，
    確保資料傳遞與儲存的隱密性，避免未經授權的使用者有意或無意的揭露資料內容。
    資料完整性(Integrity) 
    maintaining the expected state of our information or systems，
    代表確保資料無論是在傳輸或儲存的生命週期中，保有其正確性與一致性。
    可用性(Availability) 
    Ensure that the information or systems are accessible to those with permisions，
    當使用者透過資訊系統進行操作時，資料與服務必須保持可用狀況，並能滿足使用者需求。
    ![CIA Traid](https://i.imgur.com/mPj3ayE.jpg)
    The six basic security concepts，除了 C.I.A 另外衍伸出三個安全性要素分別是：不可否認性(Non-requdiation)、鑑別性(Authntication)、存取權限控制(Accss Control)
從零開始學資安 — 什麼是資訊安全?[延伸閱讀文章](https://medium.com/hannah-lin/%E5%BE%9E%E9%9B%B6%E9%96%8B%E5%A7%8B%E5%AD%B8%E8%B3%87%E5%AE%89-%E4%BB%80%E9%BA%BC%E6%98%AF%E8%B3%87%E8%A8%8A%E5%AE%89%E5%85%A8-75a7a208e8db)
2.	Client
    客戶端，也就是被服務的使用者端。
3.	Server
    以主從式架構(Client-server model)也稱C/S架構，一種網路架構，Client 客戶端與 Server 伺服器端。
4.	Operation System (OS)
    作業系統，像是 Microsoft 開發的 Windows，Linux 開源系統從 kernel 到 shell 皆可以被修改。
5.	Windows (7、8、10、11)
    Microsoft 微軟公司所開發以圖形化使用者介面為主的商業軟體作業系統，windows7 為 2009 年 Microsoft 所開發的新版本，windows 後方的數字從 windows7 開始代表版本代號與更新順序。
6.	Linux (RedHat、Ubuntu、CentOS、SUSE…)
    從 Unix Kernel 而來的作業系統，由於是受到 GUN 通用公眾授權條款(GNU General Public License)限制，開源軟體營利受到限制，因此後續有不同的版本分別由不同的單位開發，像是 RedHat 版本由紅帽公司開發，除了免費版本之外也有付費版本，用以整合紅帽公司其他的 IaaS,PaaS 等等服務。
7.	Mac (Big Sur…)
    macOS 是蘋果公司推出的基於圖形化使用者介面作業系統，為麥金塔(mac)系列電腦的主作業系統。MacOS Big Sur  macOS 的第17版。
8.	Basic Input/Output System (BIOS)
    寫入唯讀記憶體(ROM)晶片的軟體，由於唯讀記憶體的內容無法更改因此 BIOS 與主機板硬體也被稱為韌體，現今由於硬體更新的需求與容量需求，BIOS 現今寫入在唯讀記憶體(EEPROM)以及儲存普通資訊 CMOS(隨機存取記憶體 RAM)以應對更新的需求。
9.	Unified Extensible Firmware Interface (UEFI)
    統一可延伸韌體介面（英語：Unified Extensible Firmware Interface，縮寫UEFI），是一種個人電腦系統規格，用來定義作業系統與系統韌體之間的軟體介面，作為BIOS的替代方案。可延伸韌體介面負責加電自檢（POST）、聯絡作業系統以及提供連接作業系統與硬體的介面。
10.	Master Boot Record 主開機紀錄(MBR)
    （BIOS→MBR→Windows）在啟動Windows時，會從磁區內使用一段代碼來啟動系統，因此如果MBR的啟動資訊損壞，Windows就無法正常啟動。
    使用MBR磁碟分割表格的硬碟在電腦啟動時，會先啟動主機板的BIOS，隨後BIOS載入MBR，再從MBR啟動Windows，這就是MBR格式硬碟啟動的過程。
    主開機紀錄，又叫做主引導磁區，記錄著硬碟本身的相關資訊以及硬碟各個分割區的大小及位置資訊，是資料資訊的重要入口，如果它受到破壞，硬碟上的基本資料結構資訊將會遺失。作業系統是建立在進階格式化的硬碟分割區之上，是和一定的檔案系統相聯絡的，進階格式化又稱邏輯格式化，它是指根據使用者選定的檔案系統（如FAT12、FAT16、FAT32、exFAT、NTFS、EXT2、EXT3等），在磁碟的特定區域寫入特定資料，以達到初始化磁碟或磁碟分割區、清除原磁碟或磁碟分割區中所有檔案的一個操作。進階格式化包括對主開機紀錄中分割區表相應區域的重寫、根據使用者選定的檔案系統，在分割區中劃出一片用於存放檔案分配表、目錄表等用於檔案管理的磁碟空間，以便使用者使用該分割區管理檔案。
    GPT(GUID Partition Table)磁碟分割表<全域唯一標識磁碟分割表格>的縮寫，是逐漸取代 MBR 的新標準，GPT 使用了更加現代的技術取代了老舊的 MBR 磁碟分割表格。
11.	New Technology File System (NTFS)[NTFS概觀](https://docs.microsoft.com/zh-tw/windows-server/storage/file-server/ntfs-overview)
    微軟公司開發的專用檔案系統，提供一組完整的功能，包括安全性描述元、加密、磁碟配額，以及豐富的中繼資料，並且可與叢集共用磁碟區 (CSV) 搭配使用，以提供持續可用的磁碟區，讓您可以從容錯移轉叢集的多個節點同時存取。
    加密檔案系統(EFS)提供對NTFS卷上任意檔案和資料夾的使用者透明的強保護。加密檔案系統需要與EFS服務、Microsoft的加密應用程式介面（CryptoAPI）以及EFS 檔案執行時庫（FSRTL）聯合工作。EFS使用對稱金鑰加密檔案，
12.	File Allocation Table (FAT)
    檔案配置表，是一種由微軟發明並擁有部分專利的檔案系統，理解成為對磁碟寫入資料的一種格式，按照 FAT 寫入的檔案必然有固定的大小格式，因此可以進一步分割與創建資料叢集，承 MRB 邏輯格式化。
13.	Localhost
    localhost 是在電腦網路中用於表示「此電腦」的主機名稱，它被用於通過本地環回網路介面，來存取本機執行的服務，並且將會繞過任何物理網路介面硬體。運用本地環迴機制，便可在主機上運行網路服務，期間不須安裝實體網路介面卡，也無須將該服務開放予主機所在網路。例如，在設定好本地安裝的網站後，可通過`http://localhost`這一網址，來存取本地網站。
    像是從本地端開啟的 Juypter notebook 預設閘道。
`127.0.0.1    localhost`
`::1          localhost`
14.	Safe Mode
    指作業系統的一種特殊偵錯模式，或軟體的一種運行模式。當作業系統進入安全模式時，功能會減少、部分API將無法使用，透過運行最小需求的程式來進行系統偵錯，在安全模式下有可以使用的偵錯工具。而像是瀏覽器上的安全模式，進入安全模式後阻擋瀏覽器載入的外掛。
15.	Domain
    網域名稱、域名、網域，域名可以說是一個 IP 位址的代稱，域名系統(DNS Domain name system)透過域名註冊管理機構(域名註冊局)負責，以`https://www.president.gov.tw/`為例，`.gov`為頂域名(TLD Top-level Domains)，`.tw`為子域名(Subdomain)。
16.	Uniform Resource Locator (URL)
    統一資源定位符、網頁位址，是網際網路上標準的資源位址(Address)，以**「`https://zh.wikipedia.org:443/w/index.php?title=隨機頁面`」爲例，其中：`https`，是協定；`zh.wikipedia.org`，是伺服器；`443`，是伺服器上的網路埠號；`/w/index.php`，是路徑；`?title=Special:隨機頁面`，是詢問。
17.	Universal Naming Convention [(UNC)](https://www.techtarget.com/whatis/definition/Universal-Naming-Convention-UNC)
    通用命名慣例，只用一種通用語法來描述網路資源的位置，格式`\\伺服器名\共享名\路徑\檔名`。
18.	Mail Server
    電子郵件伺服器，自己架設 mail server 可以自訂網域並管理使用者。
19.	Microsoft Active Directory [(AD)](https://docs.microsoft.com/zh-tw/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
    Active Directory(AD)以樹狀的資料結構來組成網路服務的資訊，在簡單的網路環境中（例如小公司），通常網域都只有一個，在中型或大型的網路中，網域可能會有很多個，或是和其他公司或組織的AD相互連結。
    大致理解為，AD 可以透過連結來連結實體的電腦作為一個 IaaS 的單位作為目錄子資料集，透過 AD 管理使用者與紀錄資料，Active Director 依賴 DNS 可以讓 AD 表現出階層化的樹狀結構，以 SRV 紀錄來識別網路控制站，以提供網域處理的服務。
    AD 的操作同時也可以從圖形化介面進行設定。
20.	Domain Controller (DC)
    域名控制器，透過 DC 來管理整個 Domain forest 的域名，一個網域可以不只一台 DC，多台 DC 可以確保某台 DC 癱瘓期間的使用。
    Administrators 此為一個安全屬性的群組，在 AD 環境中，它擁有針對整個樹系中所有網域中的所有物件的完全控制的權限。Adiministrator 此為一個使用者帳戶擁有最高權限的(root)帳戶，Domain Admin 掌管了 DNS 的最高權限。
21.	Domain Administrator
    擁有 Administrators 所有權限的帳戶，AWS 中的根帳戶(root)。
22.	Domain Users
    在網域環境中的使用者帳戶，AWS 中的 IAM 帳戶。
23.	Group Policy Objects (GPO)
    群組原則，除了限制使用者在電腦的操作之外，限制不明使用者從遠端連接到網路共享；阻止存取特定資料夾等等，從 AWS 理解就是根帳戶要將使用者帳戶加入到某個服務的群組，才可以開啟服務的使用權限，GPO 就是特定群組的工作原則。
24.	Domain Name System (DNS)
    域名系統，使用TCP、使用者資料包協定[(UDP)](https://ithelp.ithome.com.tw/articles/10254068)傳輸，是網際網路的一項服務。它作為將域名和IP位址相互對映的一個分散式資料庫，能夠使人更方便地存取網際網路。
25.	Internet Information Server (IIS)
    IIS(Internet Information Server)是微軟伺服器 Windows Server 上，管理各種電腦網路服務的整合介面。IIS 7伺服器通過執行於核心態的組件Http.sys（HTTP 協定堆疊）來接受客戶的http請求。再通過Process（Web Process Activation service，WAS）與WWW Pulishing Service（W3SVC）兩個使用者態的系統服務來查詢、排程對應的應用程式池（Application Pool）開啟W3WP.exe工作者處理程序。
    最新版支援VScode做開啟網頁的功能，可以避免針對javascript的安全性設定而無法開啟。

* 專有名詞(系統篇-2)

26.	Certificate Authority (CA)
    Microsoft AD 具有透過憑證認真的功能，專門 For Domian 做管理使用，使得不容易被偽造身份。
    像是 Google 作為對外為主的服務，其憑證必須要是第三方的證書頒發機構，第三方證書頒發機構，負責驗證實體的身分(webside,email,companies,individual persons)，並透過以下方式將其綁定到加密密鑰電子文件的簽發稱為數字證書，身分驗證，通過充當憑證來驗證其頒發給的實體的身份，加密，用於不安全的網路上進行安全通信，簽署文件的完整性與證書一起，使他們在傳輸過程中不能被第三方更改(HTTPS SSL/TLS)，
27.	Remote Authentication Dial In User Service (RADIUS)
    Radious 的機制，多半伴隨著憑證、與較嚴謹的權限使用，像是綁定的 Domain 的 User 帳號密碼的限制或是 Wireless Controller 的限制。
    遠端使用者撥入驗證服務，由於使用UDP傳輸協定，因此路徑管理與傳輸可靠性需要使用RADIUS的應用程式來實現。應用實例ISP（網際網路服務提供者）行動電話的網路連接服務、無線 LAN、VLAN，Web 上提供收費內容的服務。
28.	Volume Shadow Copy Service (VSS)
    磁碟區陰影複製服務，定時為磁碟區做複製的服務，會在磁碟區新增一個名為Shadow copy的選項，可以為離線使用者提供離線檔案服務，檔案系統亦須視 NTFS 才可以建立與儲存，排成的 Windows 備份或是系統還原點時才會使用到此服務。
        NeuShield 具有建立還原點的方式，也同樣建立個磁碟區陰影複製。
29.	System Volume Information
    此訊息在磁碟中的資料夾，記錄著系統還原工具必須使用到的訊息與還原點，也就是系統備份訊息。
    NeuShield 的歷程檔案也會放在此處。
30.	Hypervisor
    虛擬機器監視器(virtual machine monitor VMM)，是用來建立與執行虛擬機器的軟體、韌體或硬體，像是 vmware workstation 執行、佈建、維護與審核不只一個 VM 以及清除不使用的 VM、即時移轉，在無需停止機器運作的情況下，在不同實體機器之間移動Hypervisor等等。
    透過將 OS 與 Hypervisor 整合在一起的方式，能使得 Hard drive 到 VM 實際使用的資料傳輸速度與資源的分配。
31.	Virtual Machine (VM) 
    虛擬機器，從實體機器電腦或伺服器中執行作業系統與其應用程式，每部虛擬機器無法直接與實體電腦互動，必須借助 VMM 協調，因此 VMM 透過分配實體硬體資源來建置 VM 做資源的有效分配。
    VM 的優勢，資源使用率與ROI(投資報酬率)提高、規模擴充、可攜性、靈活彈性、安全性。使用實例：雲端運算、支援DevOps(Docker...)，測試新的作業系統，調查惡意軟體，執行不相容的軟體、安全瀏覽。
    [IBM Cloud Education](https://www.ibm.com/tw-zh/cloud/learn/virtual-machines)虛擬機器(VM)
32.	Blue Screen of Death (BSOD)
    藍白當機畫面，指在 Windows 作業系統在無法從一個系統錯誤中恢復過來時所顯示的螢幕圖像。
33.	Memory Dump [實例](https://www.allion.com.tw/windows-dump-file-analysis/)
    BSOD 發生時，可以透過記憶體傾印檔(Memory dump)來找尋故障原因，
34.	Windows Batch file (file.bat)
    將 Command Prompt 中輸入的指令集結起來、輸入在文字檔中，用以批次執行(直接操作系統)，稱為批次檔(Batch file)。
35.	Database (SQL)
    資料庫，分為關聯式資料庫 SQL 與非關聯式資料庫 NoSQL，差別在於 NoSQL 允許非特定與半結構式資料做儲存，而關聯式資料庫必須定義所有資料的關聯，而操作 Database 使用的語言是結構化查詢語言(SQL)，並可以透過 DBMS 來進行管理。
    資料庫從最原始的資料索引系統發展至今，資料索引系統的原初概念就是將 key-value 的概念應用在索引目錄中，key 具有唯一性並不能為 null，而遵循 SQL 語法的資料庫具有同樣概念。
36.	SQL Administrator (SA)
    DBA( Database Administrator)資料庫管理員，負責在系統上運行資料庫，執行備份，執行安全策略和保持資料庫的完整性。而 DBA 在資料庫管理層級上也就是 SQL administrator 管理員擁有所有權限。
37.	Secure Copy (SCP)
    Secure copy(SCO) 是基於 Secure Shell(SSH)安全外殼協定，一種加密的網路傳輸協定，可在不安全的網路中為網際服務提供安全的傳輸環境，建立安全隧道做點對點的連線。SSH常用於遠端登入系統。
38.	File Transfer Protocol (FTP)
    檔案傳輸協定，是用於電腦網路在客戶端與伺服器之間進行檔案傳輸的應用層協定。
    印表機相對於本機電腦而言是客戶端，因此可以到印表機官方下載其應用程式透過FTP進行傳輸檔案到客戶端，因此傳輸檔案到印表機後進行列印。FTP服務一般執行在20和21兩個埠。埠20用於在客戶端和伺服器之間傳輸資料流，而埠21用於傳輸控制流，並且是命令通向ftp伺服器的進口。(非安全傳輸協定)
39.	Secure File Transfer Protocol (SFTP)
    安全檔案傳送協定，Secure FTP，根據 FTP 的傳輸基礎做加密，相對於 FTP 加密了傳輸認證資訊與傳輸的資料，故因此傳輸效率低於 FTP。
    `/etc/init.d/sshd start`
    `/etc/init.d/sshd stop`
40.	Network Attached Storage (NAS)
    網路附接儲存，NAS用的是以檔案為單位的通訊協定，例如像是NFS（在UNIX系統上很常見）或是SMB（常用於Windows系統）。
41.	Single sign-on (SSO)
    單一登入、單一遷入，一種對於許多關聯但又各自獨立的軟體系統，提供存取控制的屬性，透過輕型目錄存取協定（LDAP）來實作，伺服器上會將使用者資訊儲存到 LDAP 資料庫中，單一登出同義，降低存取第三方網站的風險。
42.	Windows + R
    執行命令。
43.	Notepad
    記事本。
44.	Command Line (CMD)
    命令行介面，CLT, prompt, console 或是 terminal(終端機)，WIN11 預設 Windows Terminal。
45.	ipconfig (all/release/renew…)
    微軟使用來控制網路連線的工具，`ipconfig /renew` 獲取新IP，
46.	Remote Desktop [(MSTSC)](https://ithelp.ithome.com.tw/questions/10015952)
    遠端桌面
47.	Windows + D
    返回桌面。
48.	Windows + L
    鎖定。
49.	Windows + E
    開啟檔案總管。
50.	Windows + Shift + S
    Microsoft 螢幕擷取工具，功能有長方形剪取、多邊形剪取、視窗剪取、全螢幕剪取。
    
Win + R 執行命令
Win + M 最小化所有窗口
Win + F 檔案搜尋
Win + Tab

ISP(Internet service provider)網際網路連線服務公司，假如只做 DNS 那算是 ISP 嗎？

TCP\IP

LDAP

RAID，Redundant Array of Independent Disks容錯式磁碟陣列

ifconfig 可以查找當前 Boradcast Domain 的所有實體裝置的位置。
```
顯示方式：
eth0 ....
     ....
    interrupt:3 Base address:0x300
eth1 ....
     ....
      ""        Base address:0x2e0
```




---

- NetBIOS(Network Basic Input/Output System)
    
    








`nbtstat -n` 查看此電腦目前所登記的 NetBIOS 名稱(在一個IP底下，名稱不分大小寫)
![查詢裝置 IP 中所註冊的 NetBIOS 名稱](https://i.imgur.com/0h8ybxG.png)
> NetBIOS 電腦名稱最多 15 個字元加上 1 個有特殊用途的第 16 個字元，表示電腦所提供的副物種類。
> 00：代表工作站服務，若此服務啟動的話(預設值)，便可以透過網路來與其他電腦溝通。
> 20：代表伺服器服務，若此服務啟動的話(預設值)，便可以讓其他電腦來與這台電腦溝通。

`nbtstat -n` 查看此 NetBIOS 快取區資料，預設保留 10 分鐘。
![查詢 NetBIOS 快取區資料(預設10分鐘)](https://i.imgur.com/F8Y84ia.png)


~~~ /NetBIOS 相關 port numbers
137/TCP,UDP	 NetBIOS 名稱服務	官方
138/TCP,UDP	 NetBIOS 資料報服務	官方
139/TCP,UDP	 NetBIOS 對談服務	官方
~~~
NetBIOS 與應用程式協作，透過 UDP 訪問 NetBIOS 名稱通過 137 port，Client 端發送的命令透過 139 port，也支援 UDP 138 port 接收 NetBIOS 數據報，數據報服務可以發送和接收數據報和廣播數據報。 

LMHOSTS 檔，可以讓電腦在啟動後將其資料放置到 NetBIOS 快取區，使其作為應用程式透過 NetBIOS 通訊時的資料。

WINS 是以 NetBIOS 作為通訊識別，另外還有 NetBIOS over TCP/IP，是為了讓 NetBIOS 還可以與 TCP/TP 協作。

Workstation Service 工作站服務，影響到 SMB 通訊協定，像是網路上的芳鄰 139(NetBIOS), 445(IP) port
![鳥哥講解 SMB](https://i.imgur.com/ZINT890.png)
額外參考：[微軟 SMB 封包範例](https://docs.microsoft.com/zh-tw/windows/win32/fileio/microsoft-smb-protocol-packet-exchange-scenario)

port 138 範例，透過檔案總管 Search bar 輸入 IP 或是 NetBIOS 可以進行連線。