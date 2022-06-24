# WatchGuard Firewall Lab_1
###### tags: `Training` `Solutions Architect`

### :question: Question

- Lab_1 架構圖
![Lab_1 架構圖](https://i.imgur.com/ow4Uoq7.png)

- 任務
  **WAN**(Interface 0)
  IP > 59.120.145.172/24
  Default Gateway > 59.120.145.254
  DNS > 168.95.1.1, 8.8.8.8
  
  **LAN**
  Internal_Clients > Interface 1&2
  IP > 172.16.1.254/24
  DHCP > 172.16.1.101 - 172.16.1.110
  
  Internal_Servers > Interface 3&4
  IP > 172.16.2.254/24
  DHCP > 172.16.2.121 - 172.16.2.130
  
  Internal_Lab > Interface 5&6
  IP > 172.16.5.254/24
  DHCP > 172.16.5.141 - 172.16.5.150
  
  DNS > 168.95.1.1, 8.8.8.8
  
  1. 修改 status 與 admin 預設密碼
  2. 設定 Internal_Clients 能夠到 Internal_Lab；
     Internal_Lab 無法連到 Internal_Clients 與 Internal_Servers
  3. 設定 Internal_Clients 能夠存取任何地方
  4. 設定 Internal_Servers 不能存取外部網路
  5. 讓 Clients 能夠取得 172.161.1.X/24 的 IP
    172.161.1.X/24 是指，只要 IP 符合此網段即可，只要 Clients 設定正常則就是落在此網段。
  6. 設定能夠從 WAN 管理 WatchGuard
  7. 設定網頁伺服器 172.16.2.101:80 需要能夠對外提供服務
  8. 啟動 SSL-VPN 建立使用者，登入後取得 172.16.11.X/24 的 IP
  9. 設定 SSL-VPN 使用者只能連到 Internal_Servers

- 要注意的問題
    - 當我們設定 SSL-VPN 只能連到 Servers 時，表示我們 Allow SSL-VPN To Servers 時，同時也應該要 Deny SSL-VPN To Any-ExTernal& Any-Trusted。
    - 修改過 Status&Admin 密碼，記得回復預設。
    - 設定 Web Servers NAT，時如果沒有做 PAT 不用在 NAT 頁面中設定指定 Port 號。



- XTM510 license key
```
Serial Number: 80B00438AEA3A
License ID: 80B00438AEA3A
Name: 05-23-2022_05:53
Model: XTM510
Version: 2
Feature: APP_CONTROL@Aug-14-2014
Feature: APT@Aug-14-2014;+AEE0ED04514E243557103F7370DCBA72F0221CF17079CA4D44580F2763F78D97B33B2EF11080838623181244D9EDEFE5
Feature: AUTH_DOMAIN#5
Feature: AUTHENTICATED_USER#500
Feature: AV@Aug-14-2014
Feature: BOVPN_TUNNEL#75
Feature: DIMENSION_COMMAND@Aug-14-2014
Feature: DLP@Aug-14-2014
Feature: FIREWARE_XTM
Feature: FW_SPEED#1800
Feature: IPS@Aug-14-2014
Feature: LIVESECURITY@Aug-14-2014
Feature: MUVPN_USER#25
Feature: RED@Aug-14-2014
Feature: SESSION#100000
Feature: SPAMBLOCKER@Aug-14-2014;UC17Q63WEU2Q2UGD54HB
Feature: VPN_SPEED#350
Feature: WATCHMODE
Feature: WEBBLOCKER@Aug-14-2014
Feature: XTM_PRO
Expiration: never
Signature: 302d021500bb00f6-6966d4106f8a9209-d23991f94f1578e9-7b0214727ccdb54f-16951373280767cd-d47b3407f19c73
```