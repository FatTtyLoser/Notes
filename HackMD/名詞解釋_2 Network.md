# 名詞解釋_2 Network
###### tags: `Training` `Solutions Architect`

### 解決方案架構師 Training Step_2

* 專有名詞(網路篇-1)

1.	Open System Interconnection Model (OSI)
    開放系統互連(OSI)是由國際標準組織(International Standard Organization, ISO)所制定的通訊協定體系。
    OSI 7層網路架構、網路架構(network architecture)
    ![網路架構](https://i.imgur.com/Qagz1Ks.png)
2.	Transmission Control Protocol (TCP)
    傳輸控制協定(TCP)根據網路架構中屬於第四層傳輸層，意義在於對網際網路上傳輸資料的方法做出規範，包含 TCP Header 中的 port number、序號、確認編號、標頭長度等等資訊，只要確認這些資訊就可以對資料做正確處理。
3.	User Datagram Protocol (UDP)
    使用者資料協定(UDP)是在PPP(Point-to-point protocol)之內的協定，適用於對可靠性要求不高的應用環境，其 UDP Header 的內容減少(只有 port number)，目的在於減少伺服器的處理負載。
4.	Internet Protocol Address (IP Address)
    IP 位址，每一個要連上網的裝置都需要一個 IP 位址，公共 IP 會透過 ISP 分配並合法授權使用，私人 IP 則是有固定保留的 IP 位址給私人 IP 使用，而當要連外時，仍然需要取得新的公共 IP。
5.	Subnet Mask
    子網路遮罩，代表在一個 Broadcast 裡接收 TCP packet 的 Router(or [LAN switch](https://reurl.cc/n1oZ4l))與其連結的 Media Address Control 裝置(PC...)。
6.	Default Gateway
    預設閘道，代表在架設私人網路所使用的私人IP，通常是指路由器(Router)的地址，對整個 Broadcast domain 的預設 Net_ID，同時也代表連結的 PC 想要連上網路的方向。
7.	Media Access Control Address (MAC Address)
    MAC 媒體存取控制，每一台裝置的 MAC 位址是硬體在製造時已經被設定好的 48 位元資料。
8.	Fully Qualified Domain Name (FQDN)
    完整網域名稱，以`https://www.president.gov.tw/`為例，`www.president.gov.tw/`這些網址的正式名稱就是「完整網域名稱」，FQDN 具有一些限制，像是總長度不可以超過 255 個字母，兩個`.`之間不可超過 63 個字母。
- Domaind Name Server
  通常架設在 AD DC(Active Director Domain Controller)，如果沒有的話會設定代理 DNS 像是 Google DNS(8.8.8.8;8.8.4.4), CHT DNS(168.5.1.1;168.95.192.1)
9.	Hub
    集線器，區域網路(LAN)集線裝置，透過(Layer1)傳輸訊號(電子訊號或是光訊號)。
10.	Switch
    橋接器(Bridge)意即兩個網路要做連線的設備，例如區域網路與廣域網路連接，為 OSI 模式第三層用來決定資料傳遞的路徑設備，最主要是要將資料封包轉為 Data Frame 在第三層稱為 MAC Frame，而處理 MAC Frame 的就是轉接器(Switch)或稱網路轉接器(Network Switch)。
11.	Router
    路由器，用來連接兩個以上網路設備，支援某些協定以便過濾其他的封包，路由器的工作在於確認目標計算機所在的位置並找到數據傳遞的最佳路徑。
12.	Address Resolution Protocol (ARP)
    位址解析協定，是一個通過解析網路層位址來找尋資料鏈路層位址的網路傳輸協定，傳輸層中只在乎 IP packet 中的 IP 位址資訊 MAC 位址等等，只要能夠交付到目的地就好，而 ARP 協定就在處理當一整個 TCP packet 中 IP 位址正確而傳達到整個 Boradcast domain 時，若 MAC 位址不明或缺失時，TCP 封包就會在 Router 暫存，否則無法傳遞到正確裝置的 packet 會占滿整個網路。
13.	VLAN(Virtual Local Area Network)
    虛擬區域網路(VLAN or V-LAN)，建構於(LAN Switch)的網路管理技術，可以透過控制 Switch 有效分派出入區域網的封包到正確的出入埠，對不同實體區域網中的裝置進行邏輯分群(Grouping)管理，可以跨交換器來實現，可以根據網路使用者的位置、作用、部門或根據使用的應用程式、上層協定或者乙太網路連接埠硬體位址來進行劃分。
    一個V-LAN等於一個傳輸層，因此即便是在同一個 Switch 上建立的兩個 VLAN 仍然無法在第三層傳輸資料，需要透過第四層才能夠傳輸，透過 TCP 封包。有 cisco 的設備部分例外。
14.	Trunk
    連線埠匯聚(Trunk)，當我們因為需要降低 Boradcast domain 的  boradcast packets 對 switch 的網路負載，所以建立不只一個 VLAN 時，我們又要透過 Switch and Router 來傳輸到不同的 VLAN 時，可以透過 Trunk 連結其 VLAN 之間，當一設備需要傳輸資料時，Trunk 會在資料上標註(Tag)設備是屬於哪一個 VLAN，因此在另外一個 Trunk 或 Sitch 時，會認得資料的所屬的 VLAN。802.1Q協定具有 native VLAN，所有沒背上 tag 的資料都會先送往 native VLAN。
    只有FastEthernet等級以上才可以做Trunk
15.	Routing
    路由（Routing）是網路封包決定要如何送往外部網路而到達目的地的過程。透過路由協定來處理。有許多不同的路由協定：
    1. 靜態路由(Static Route)
        必須手動輸入，好處是速度快、不需要經過學；缺點是網路拓撲若有任何改變，管理人員必須更新這些資料到路由器設備，除了比較麻煩也必須要有好的維護能力才型，這種方式比較適合幾乎不會有變動的網路拓撲(Topology)。
    2. 動態路由(Dynamic Route)
        動態路由不需要手動輸入，(worry free)一切的工作交給路由器設備之間去協調，互相交換並學習這些資料，網管人員只需要做Routin Protocol的設定即可。
16.	Default route
    預設閘道(Default Gateway)透過靜態路由來設定。而預設路由就是不知道封包要丟到哪裡時，會採用的預設路徑。
    ```
    Router#show ip route  來查看
    ```
17.	Static routing
    靜態路由，一種路由方式，路由項(routing entry)由手動配置，而非動態決定，靜態路由是固定的不會改變，即使網路狀態已經改變或重新被組態。靜態路由是由網管逐項加入路由表。
18.	Loop
    迴圈，若 Switch 之間相互連接導致資料流形成一個迴圈，導致 MAC Table 持續更動，會使得資料錯亂找不到家，造成網路壅塞，Switch 是否有 loop 偵錯功能就代表有無避免造成此情況的意思。
19.	Wide Area Network (WAN)
    廣域網路，架構適用於兩個距離超過二十公里以上之區域網路要做連線所需的方式。
    1. 公共交換電話網路(Public Switched Telephone Network; PSTN)
    2. 租用專線(Leased Line)
    3. 分封交換數位網路
    4. 非對稱數位用戶迴路(ADSL)(DSL技術有很多類，例如：HDSL，IDSL，VDSL等等)
    5. 纜線數據機(Cable Modem)
20.	Local Area Network (LAN)
    區域網路，架構為四公里以內範圍，是網路最基本的連線組織方式。只要兩台以上的電腦連接都可稱為區域網路，而一般商業組織會以防火牆為基準，防火牆內部稱為內部網路。
    拓樸方式可分為星型(Star)、環狀(Ring)、匯流排型(Bus)。星型方式一個設備斷連並不會影響到其他設備。
21.	Demilitarized Zone (DMZ)
    非軍事區，由於防火牆的阻擋是全面的，透過白名單也就是存取控制清單(ACL)的列舉來達到有效控制，而 DMZ 是作為內網與外網的緩衝區域，通常會將一般網頁與對外服務的設備放此處，讓內外網都可以進行連線。
    * 通常會放在防火牆延伸出來一個 DMZ，而 DMZ 所建置的 Mail Sever or Web Server 必須經過 Firewall 過濾之外，同時也對 Server 的 IP 做 NAT 
22.	Network Address Translation (NAT)
    網路位址轉換又稱網路遮掩、IP遮掩，在 IP 封包通過路由器或 Firewall 重寫來源 IP 地址或目的 IP 地址的技術，這種技術被普遍使用在有多台主機或只通過一個公有 IP 位址存取網際網路的私有網路中。
23.	Port Address Translation (PAT)
    端口地址轉換PAT，是對網路地址轉換NAT的擴展，允許內部網路LAN上的多個設備映射到一個單一的公共IP地址。
24.	Bridge Mode
    對應到 Repeater(中繼)模式，Repeater 模式中藉由中繼傳送並放大的訊號與 ISP ATU-R(小烏龜)所發的訊號一樣，而橋接模式中的訊號會改變，可以透過Bridge模式做domain的管理。
25.	High Availability (HA)
    高可用性代表系統無間斷執行其功能的能力，代表系統的可用性程度，是進行系統設計時的準則之一。
    A（可用性），MTBF(平均故障間隔)，MDT(平均修復時間)，在線系統和執行關鍵任務的系統通常要求其可用性要達到5個9標準(99.999%)。
* 專有名詞(網路篇-2)

26.	Simple Mail Transfer Protocol (SMTP) port:25
    簡單郵件傳送協定，可用在傳送和接收電子郵件的資訊，但通常用作傳送電子郵件資訊，會在客戶端(傳送者)與伺服器端(接收方)建立連結後會建立一個合法的SMTP對話。缺點是並沒有對使用者的身分做認證，認證機制並不能篩掉垃圾郵件，所以後來產生了加密的SMTPS。
27.	Post Office Protocol - Version 3 [(POP3)] 110(https://www.techtarget.com/whatis/definition/POP3-Post-Office-Protocol-3)
    郵局協定，[POP與IMAP的差別](https://support.microsoft.com/zh-tw/office/imap-%E5%92%8C-pop-%E6%98%AF%E4%BB%80%E9%BA%BC-ca2c5799-49f9-4079-aefe-ddca85d5b1c9)，在於IMAP是客戶端在與郵件伺服器存取時，並不是下載郵件到本地端，而是與郵件伺服器互動，因此速度較快，而POP則是客戶端在與郵件伺服器互動時，是將所有郵件下載到本地端後，伺服器則進行刪除，之後讀取郵件只能透過其下載的裝置，因此每一次都需要經過下載，會比較慢，而兩者同樣都可以從不同裝置作互動。
* IMAP(Internet Message Access Protocol)互動郵件存取協定
28.	Network Time Protocol (NTP)port:123
    網路時間協定是在資料網路中潛伏時間(Latency)可辨的電腦系統之間通過封包交換進行時鐘同步的網路協定。
29.	Server Message Block (SMB)port:445
    伺服器訊息區塊，是在應用層中協定兩台電腦交換資訊的方式，像是windows電腦，可以透過TCP/IP來交換、傳送資料與執行程式，實際的應用在Hyper-V的遠端服務上。
30.	Lightweight Directory Access Protocol (LDAP)AD
    輕型目錄存取協定，LDAP目錄的條目（entry）由屬性（attribute）的一個聚集組成，並由一個唯一性的名字參照，即專有名稱（distinguished name，DN）。例如，DN能取這樣的值：「ou=people,dc=wikipedia,dc=org」。
    linux open ldap
- RDP(Remote Desktop Protocol)遠端桌面協定 port:3389
31.	Service Set Identifier (SSID)
    服務集（Service set）是無線區域網路中的一個術語，用以描述802.11無線網路的構成單位（一組互相有聯絡的無線裝置），使用服務集識別碼（SSID）作為辨識。可以分為獨立基本服務集（IBSS）、基本服務集（BSS）和擴充服務集（ESS）三類。
    服務集識別碼（英語：Service Set Identifier，SSID）是一個或一組基礎架構模式無線網路的標識，依照標識方式又可細分為兩種：
    基本服務集識別碼（BSSID），表示的是AP的資料鏈路層的MAC位址
    擴充服務集定識別碼（ESSID），一個最長32位元組區分大小寫的字串，表示無線網路的名稱
    多個AP可以擁有同一個ESSID以對客戶提供漫遊能力，但是BSSID必須唯一，因為資料鏈路層的MAC位址是唯一的。
    一個全為1的BSSID表示廣播，一般用於檢查可用無線存取點。
32.	ping (-t …)
    ping 這個指令是一個最常用的網路檢測工具，它可以藉由發送 ICMP ECHO_REQUEST 的封包，檢查自己與特定設備之間的網路是否暢通，並同時測量網路連線的來回通訊延遲時間（round-trip delay time）
    icmp
```
    ping
    -t             Ping 指定的主機，直到停止。
                   若要查看統計資料並繼續，請按 Control-Break;
                   若要停止，請按 Control-C。
    -a             將位址解析為主機名稱。
    -n count       要傳送的回應要求數目。
    -l size        傳送緩衝區大小。
    -f             在封包中設定 Don't Fragment 旗標 (僅 IPv4)。
    -i TTL         存留時間。
    -v TOS         服務類型 (僅 IPv4。此設定已過時，而且對 IP 標頭中的
                   服務類型欄位沒有影響)。
    -r count       記錄路由以供計算躍點 (僅 IPv4)。
    -s count       供計算躍點的時間戳記 (僅 IPv4)。
    -j host-list   鬆散的主機清單的來源路由 (僅 IPv4)。
    -k host-list   嚴格的主機清單來源路由 (僅 IPv4)。
    -w timeout     每個回覆的等候逾時 (單位為毫秒)。
    -R             也使用路由標頭測試反向路由 (僅 IPv6)。
                   根據 RFC 5095，已不再使用此路由標頭。如果使用此標頭，某些
                   系統可能會捨棄回應要求。
    -S srcaddr     要使用的來源位址。
    -c compartment 路由區間識別碼。
    -p             對 Hyper-V 網路虛擬化提供者位址執行 Ping。
    -4             強制使用 IPv4。
    -6             強制使用 IPv6。
```
33.	telnet
    是一個檢測某個埠號是否可訪問。TCP/IP的協議一部分，提供在本地端完成遠端主機工作的能力。MIS的命脈?
    透過遠端命令式操作介面，與Linux的ssh連線相同。([閱讀](https://ithelp.ithome.com.tw/questions/10193550))
34.	netstat
    是Linux查詢網路相關資訊所使用者命令式。
    ```
    netstat -[rn] 用來查詢網路相關資訊
    netstat -[antulpc] 與網路介面有關資訊
    ```
35.	Secure Shell (SSH) port:22, FTP port:20, 21
    安全外殼協定，它可以透過資料封包加密技術，將等待傳輸的封包加密後再傳輸到網路上。通常用於遠端登入。


網路位址（英語：Network address）是電信網路（Telecommunications network）中節點或網路介面的識別碼。網路位址通常被設計為一個跨網路獨一無二的識別碼，但是某些網路系統中，允許本地或相對位址，可以是非獨一的。在一個網路系統中，通常擁有不只一種網路位址。


Leaf Node 每一個沒有子節點的節點都是Leaf Node。
Linked List(連結串列)，一維線性結構，樹(與Graph)則推廣成多維的結構，
node(節點)，用以代表資料(data)、狀態(state)，連結各個node之間的 link 稱為 edge(單雙向)。
Tree 用以描述具有階層結構(hierarcical struture)的問題，具有先後順序。
Binary Tree(二元樹)代表指向 left subtree 與 right subtree
一棵樹只能有一個 root(樹根)，不只一棵樹時稱為 Forest(森林)。
邏輯樹[延伸閱讀](http://alrightchiu.github.io/SecondRound/treeshu-introjian-jie.html)

ARP(Address resolution protocol)位址解析協議，用於透過 IP 來查找 MAC 位址的方法，使得資料可以經由 IP 正確傳達到 Domain 中的 Client
ARP 快取緩衝區(ARP Cache)中建立一個 ARP 表格，用來記錄 IP 位址與實體位址的對應關係。這個 Table 的每一筆資料都會根據自身的存活時間遞減而中消失，以確保資料的真實性。
ARP 可以透過命令提示列來搜尋`arp -a/arp -g` 來查看該 Domain 中的裝置，透過 ARP Cache 建立的 Table 來辨識，而 Table 通常存在兩分鐘，除非經過 command line 查看後會自動延遲時間至多十分鐘後仍會刪除，為了保持資料的真實性，為了將 MAC 位置可能會因為裝置重新連結網路而導致改變等等問題排除。


tracert 追蹤封包傳送的路由跳躍點，上限30個，鍵入指令可以取得功能

route ping nslookup arp常用

proxy 設定，普遍windows browser 都會放在IE瀏覽器的設定中，microsoft內建的設定，目前Proxy server已經很少見，通常被Firewall取代。