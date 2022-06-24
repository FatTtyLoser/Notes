# WatchGuard Firewall Lab_2
###### tags: `Training` `Solutions Architect`

### :question: Question

- Lab_2 架構圖
![Lab_2 架構圖1](https://i.imgur.com/YligGhU.png)
![Lab_2 架構圖2](https://i.imgur.com/wBRI2hu.png)


- 任務
  **WAN**
  External_Servers > Interface 0
  IP > 59.120.145.169-59.120.145.174/24
  Default Gateway > 59.120.145.254
  DNS > 168.95.1.1, 8.8.8.8
  External_Servers > Interface 1(PPPoE)
  Username > 76936216@hinet.net
  Password > jzzhaazl
  
  **LAN**
  Internal_Clients > Interface 2
  IP > 192.168.1.254/24
  DHCP > 192.168.1.51 - 192.168.1.99
  IP > 192.168.2.254/24
  DHCP > 192.168.2.10 - 192.168.2.100
  IP > 192.168.3.254/24
  DHCP > 192.168.3.10 - 192.168.3.50
  Internal_Servers > Interface 5
  IP > 192.168.5.254/24
  DHCP > 192.168.5.141 - 192.168.5.150
  
  DNS > 192.168.1.100、192.168.1.102
  
  1. [x] 設定 Internal 能夠到 Internal_Lab；
     Internal_Lab 無法連到 Internal
  2. [x] 設定郵件外傳時，透過 59.120.145.170 出去
  3. [x] 設定網頁伺服器192.168.1.1:80需要能夠對外提供服務，使用59.120.145.170
    當內部 IP(裝置) 要提供服務像是 Web Server 時候，當外部連線到對外 IP 時，要啟用 D
  4. [x] 設定網頁伺服器192.168.1.4:80需要能夠對外提供服務，使用59.120.145.173
  5. [x] 設定外部郵件傳給內部時，先經過郵件閘道器192.168.1.11:25，透過59.120.145.170
  6. [x] 設定外部郵件直接傳到內部郵件伺服器192.168.1.14:110，透過59.120.145.170
  7. [x] 設定外部郵件直接傳到內部郵件伺服器192.168.1.14:25，透過59.120.145.173
  8. [ ] 對外提供報表伺服器192.168.1.201(port:443&80&4115)，透過59.120.145.173
  9. [ ] 設定AP符合內部與來賓使用，來賓(Guest)需要有認證頁面
  10. [ ] 來賓(Guest)不能存取公司內部網段
  11. [ ] 啟用SSL-VPN，建立全公司使用者帳號密碼
  12. [ ] 設定內部能夠Ping到任何地方，也可以透過外部Ping到防火牆
  13. [ ] 設定內部都能正常出外網
  14. [ ] 設定能夠從WAN管理WatchGuard



- XTM510 license key
```
Serial Number: 8013036478DED
License ID: 8013036478DED
Name: 06-20-2022_08:00
Model: M370
Version: 2
Feature: ACCESS_PORTAL@Jan-02-2021
Feature: APP_CONTROL@Jan-02-2021
Feature: APT@Jan-02-2021;+9E66CECA37423B2C71FA805C66E04AB6A3EC8AF2F176A20595FB5730E8B872894957B1BD56D169FBBC8B4D1220EFD44F
Feature: AUTHENTICATED_USER#0
Feature: AV@Jan-02-2021
Feature: BOVPN_TUNNEL#100
Feature: DIMENSION_BASIC@Jan-02-2021
Feature: DIMENSION_COMMAND@Jan-02-2021
Feature: DLP@Jan-02-2021
Feature: DNSWATCH@Jan-02-2021
Feature: FIREWARE_XTM
Feature: FW_RULE#0
Feature: FW_SPEED#0
Feature: FW_USERS#0
Feature: INTELLIGENT_AV@Jan-02-2021
Feature: IPS@Jan-02-2021
Feature: L2TP_USER#150
Feature: LIVESECURITY@Jan-02-2021
Feature: MUVPN_USER#150
Feature: NETWORK_DISCOVERY@Jan-02-2021
Feature: RED@Jan-02-2021
Feature: SESSION#7000000
Feature: SPAMBLOCKER@Jan-02-2021;UC17Q63WEU2Q2UGD54HB
Feature: SSLVPN_USER#150
Feature: TDR@Jan-02-2021;AMER
Feature: VLAN#300
Feature: VPN_SPEED#0
Feature: WATCHMODE
Feature: WEBBLOCKER@Jan-02-2021
Feature: XTM_PRO
Expiration: never
Signature: 302e021500da60c8-25e72b6d6a53e5e6-2ffb1c733c3e4d87-a0021501375d6bea-76757b995a15b48f-0c5f5112aadaac9c
```

SNAT: Source Network Address Translation，是修改網路封包**源** IP 地址的。
DNAT: Destination Network Address Translation，是修改網路封包**目的** IP 地址的。


Enable login limit for each user or group

Allow unlimited concurrent firewall authentication logins from the same account 

Limit concurrent user sessions to 1
when the limit is reached: Allow subsequent login attempts and log off the first seesion.
Reject subsequent login attempts.

為每個用戶或組啟用登錄限制

允許來自同一帳戶的無限並發防火牆身份驗證登錄

將合流用戶會話限制為 1
達到限制時：允許後續登錄嘗試並註銷首次訪問。
拒絕隨後的登錄嘗試。


When you set the DNAT source IP address in a policy, make sure the policy is configured to allow traffic out through only one interface.

if the policy is used to allow hostout traffic to go through BOVPN traffic selector tunnel, the DNAT source IP address must match the tunnel route local address.

If the interface is a BOVPN virtual interface, the DNAT source IP address must be an IP address that the BOVPN remote peer can route to.

If the interface is any other typem the DNAT source IP address must be on the sames subnet as that interface, or must be on the same subnet of the primary or secondary IP address of the Loopback interface.

在策略中設置 DNAT 源 IP 地址時，請確保將策略配置為僅允許流量通過一個接口傳出。

如果該策略用於允許 hostout 流量通過 BOVPN 流量選擇器隧道，則 DNAT 源 IP 地址必須與隧道路由本地地址匹配。

如果接口是 BOVPN 虛擬接口，則 DNAT 源 IP 地址必須是 BOVPN 遠程對等體可以路由到的 IP 地址。

如果接口是任何其他類型，則 DNAT 源 IP 地址必須與該接口位於同一子網中，或者必須與 Loopback 接口的主 IP 地址或輔助 IP 地址位於同一子網上。

policies that were left with empty From or To field. Please correct the following policies. by adding addresses to their empty From or To fields. Allow_Internal to Lab, Deny_Lab to Internal

留有空 From 或 To 字段的策略。 請更正以下政策。 通過將地址添加到其空的 From 或 To 字段。 Allow_Internal 到實驗室，Deny_Lab 到內部

