# McAfee ePO operational Lab_1
###### tags: `Training` `Solutions Architect`

Education support: MBEducation_support@McAfee.com

### windows lab 環境建立

1.	:ok_hand:在Server安裝Microsoft SQL Server(MSSQL) 2016
2.	:ok_hand:在Server安裝McAfee ePolicy Orchestrator(ePO) 5.9.1
3.	:ok_hand:在ePO簽入McAfee Agent與McAfee Endpoint Security(ENS)延伸模組與套件
4.	:ok_hand:在ePO新增樹狀目錄群組，新增Clients & Servers
5.	:ok_hand:產生出代理程式(McAfee Agent)安裝檔案(單機安裝檔與URL安裝檔
6.	:ok_hand:在Client安裝McAfee Agent，並且回報ePO正常
7.	:ok_hand:透過ePO派送ENS安裝工作，對Client立即執行用戶端工作安裝Endpoint Security Threat Prevention
8.	:ok_hand:透過ePO派送ENS安裝工作，對Client設定排程安裝Endpoint Security Firewall & Web Control & Adaptive Threat Protection
9.	:ok_hand:透過ePO派送病毒碼(AMCore)更新工作，對Client設定排程更新AMCore & Engine
10.	:ok_hand:透過ePO派送ENS原則，對Client設定原則並指派，原則包含：移除ENS密碼保護、停用Firewall、停用Web Control

### 補充

病毒碼(AMcore)也稱為 V3 DAT 對應 McAfee Agent 5.7.5 版本，相對於 V2 DAT 對應 McAfee Agent 5.0.6 ，AMCore 是更新版本的反惡意軟件掃描技術。

McAfee ENS Firewall, ENS Threat Preventio, ENS Web Control 對 ENS Platform 有依存性，因此需要先安裝 Platform 才能作為管理與執行系統，而 ENS Adaptive Threat Protection(ATP) 是 Threat Prevention(AM) 的升級版因此需要先安裝 AM 才能安裝進行升級防毒功能。

- 原則指派
    透過原則目錄新增新原則針對需求定義，

威脅、病毒碼更新狀況