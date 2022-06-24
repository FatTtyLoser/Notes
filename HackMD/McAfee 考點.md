# McAfee 考點
###### tags: `McAfee`

### 三服務

1. Select Start > Programs > Administrative Tools > Services.
2. Identify the services installed on the server and started. Pay special attention to these services:
    a. ePO Application Server Service(Tomcat)：負責顯示控制台及運行延伸模組，以及其他背景功能。
    Location:`...\<epoinstallationdirectory>\server\logs\`
    b. ePO Event Parser Service：從客戶端環境上傳到 ePO Server 事件分析並儲存到 SQL。
    Location:`...\<epoinstallationdirectory>\db\logs\`
    C. ePO Server Service(Apache)：處理及接收所有代理程式與伺服器間的通訊。
    Location:`...\<epoinstallationdirectory>\db\logs\`

#### ePO 所有服務

- ePO Application Server Service (Tomcat)
- ePO Event Parser Service
- ePO Server Service (Apache)
- Product Improvement Program Service (optional)
- SQL Server
- SQL Server Browser

#### ePO Ports

![ePO Ports](https://i.imgur.com/WDMaW2b.jpg)


關於 Agent Handlers(AH) Important Notes

- Agent Handlers(AH) are NOT a solution to low bandwidth.
    代理處理程式，不是一個解決低帶寬的方案。
- An additional Agent Handler with low bandwidth to the SQL server has WORSE performance than just having agents connect to the ePO server.
    與 SQL 服務器連接的帶寬較低的附加代理處理程序的性能比僅讓代理連接到 ePO 服務器的性能更差。
- A single Agent Handler with a poor connection to SQL will have a massive performance impact on the whole ePO infrastructure, not just the clients it is handling.
    與 SQL 連接不佳的單個代理處理程序將對整個 ePO 基礎架構產生巨大的性能影響，而不僅僅是它正在處理的客戶端。
    - When one AH is interacting with the database, the other AHs are locked out. The AH with the poor connection locks the database for large amounts of time, preventing the other AHs from working.
        當一個 AH 與數據庫交互時，其他 AH 被鎖定。連接不佳的 AH 會長時間鎖定數據庫，從而阻止其他 AH 工作。
- Agent Handlers MUST have a high-speed connection to the SQL server and a stable connection to the SQL server database.
    代理處理程序**必須**與 SQL 高速連接並穩定的連接。
- If the database serving the ePO server is under heavy load, adding Agent Handlers will not help.
    如果 ePO 伺服器的工作負載過重，增加 AH 毫無幫助。
- You may need to upgrade your SQL server hardware to take advantage of multiple Agent Handlers.
    可能需要提高 SQL server 硬體以利用多個代理處理程式。
- Agent Handlers should be co-located with the SQL server and never installed in “remote” locations.
    代理處理程式必須與 SQL server 同一個位置，並且永遠不要安裝在遠程位置。
    
    
    
[How to change the ePO agent-to-server communication secure port](https://kc.mcafee.com/corporate/index?page=content&id=KB72936&actp=null&viewlocale=en_US&showDraft=false&platinum_status=false&locale=en_US)


- System-based rules:
    Assigned to managed systems
    Assigned priority, which can be changed
    Cannot include user-based criteria

- User-based rules:
    Assigned to groups, organizational units, or user names
    Can include system-based criteria
    Enforced when users log into the network
原則分配規則可以指定優先級

user management

Overview

A permission set is a group of permissions, divided in sections, that grants a set of rights and access to a user. The following default permission sets are included with ePO, for immediate assignment or for use as a template for customization:

以下是除了管理員之外的身分組，身分組中檢閱者的權限不必被權限集的群組所指派是因為檢閱者只有檢閱功能，也只能檢閱已經決定好的工作、分配好的可視範圍，因此沒有進一步檢視設備或群組的設定，而其他兩者是基於群組的權限來創設，因此無論是檢視群組與群組裝置的內容，都需要按照一定的原則身份才能檢視。

- Executive Reviewer: Provides view permissions to dashboards, events, contacts, and can view information that relates to the entire System Tree
    - 執行檢閱者：提供對儀表板、事件、聯繫人的查看權限，並可查看與整個系統樹相關的信息
- Global Reviewer: Provides view access globally across functionality, products, and the System Tree, except for extensions, multi-server roll-up data, registered servers, and software
    - 全域檢閱者：提供跨功能、產品和系統樹的全局視圖訪問，擴展、多服務器匯總數據、註冊服務器和軟件除外
- Group Admin: Provides view and change permissions across ePO features. Users, who are assigned this permission set, each need at least one more permission set that grants access to needed products and groups of the System Tree.
    - 群組管理員：提供跨 ePO 功能的查看和更改權限。 被分配了這個權限集的用戶，每個人都需要至少一個權限集來授予對系統樹的所需產品和組的訪問權限。
- Group Reviewer: Provides view permissions across ePO features. Users, who are assigned this permission set, each need at least one more permission set that grants access to needed products and groups of the System Tree.
    - 群組檢閱者：提供跨 ePO 功能的查看權限。 被分配了這個權限集的用戶，每個人都需要至少一個權限集來授予對系統樹的所需產品和組的訪問權限。!
    - [4身分組管理](https://i.imgur.com/4OMRTCq.png)
