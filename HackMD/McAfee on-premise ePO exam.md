# McAfee on-premise ePO exam
###### tags: `McAfee`
[TOC]

## Chap.Troubleshooting Basics
### Troubleshooting using Log Files

:::info 重點筆記說明
- 事件類型描述
```
    Log檔類型名稱_<名詞變數>.副檔名
    名詞變數指得是個別的名稱 example.<SERVER>=JEFFERY-PC
```
- 可以透過微軟服務管理工具，終止與啟用服務來觸發事件，產生相對應 Log 以檢證以下內容。
:::

#### Common issues

常見問題羅列，參考下列 Log 檔與其路徑。

- Agent: in general; client communication tasks
```
    Masvc_<SYSTEM>.LOG
    Macompatsvc_<SYSTEM>.LOG
```
參考預設路徑：`C:\ProgramData\McAfee\Agent\logs`
- Agent: installation; uninstallation
```
    FRMINST_<SYSTEM>.LOG
    MFEagent.msi.<DATE-TIME>.LOG
```
參考預設路徑：`C:\Windows\Temp\McAfeeLogs`
- Agent: push
```
    server_<SERVERNAME>.LOG
```
- Agent: updating client, managed products
```
    MCSCRIPT.LOG -- (for managed tasks)
    UPDATERUI_<SYSTEM>.LOG -- (for local tasks)
```
參考預設路徑：`C:\ProgramData\McAfee\Agent\logs`
- Agent: wake-up
```
    SERVER_<SERVERNAME>.LOG
```
- Agent-server communication
```
    SERVER_<SYSTEM>.LOG, SERVER_BACKUP.LOG
    Masvc_<SYSTEM>.LOG
```
- Client task: communication
```
    Agent_<SYSTEM>.LOG
    Agent_<SYSTEM>_BACKUP.LOG
```
- Client task: scripts
```
    MCSCRIPT.LOG
```
- Distributed Repositories
```
    REPLICATION.LOG
    ePOAPSVR_<SERVERNAME>.LOG
    ORION.LOG
```
- Error: Apache web server
```
    ERRORLOG.<CURRENT_DATETIME>
```
- Error: Tomcat servlet container
```
    STDERR.LOG, JAKARTA_SERVICE_<DATE>,
    LOCALHOST_ACCESS_LOG.<DATE>, ORION.LOG
```
- Error: Events, event update
```
    EVENTPARSER_<SERVERNAME>.LOG, 
    EVENTPARSER_<SERVERNAME>_BACKUP.LOG
```
- Installation: ePO calls to background, foundation, or other platforms and technologies
```
    CORE-INSTALL.LOG, CORE-UPGRADE.LOG, CORE-RESTORE.LOG
    ePO-INSTALL.LOG, 
```
- Installation: ePolicy Orchestrator custom actions
```
    ePO5XXCOMMONSETUP.LOG
```
- Installation: ePolicy Orchestrator
```
    ePO5XX-INSTALL-MSI.LOG
```
- Migration: from earlier version
```
    MIGRATION.LOG
    ePO5XX-INSTALL-MSI.LOG
```
- Notifications
```
    ORION.LOG
```
- Policies
```
    SERVER.LOG
    Masvc_<SYSTEM>.LOG 
```
- Policy Update
```
    Macompastsvc_<SYSTEM>.LOG
```
- Product Property Update
```
    SERVER.LOG
```
- Pull
```
    ePOAPSVR_<SERVERNAME).LOG
    ORION.LOG
```
- Push Agent
```
    SERVER.LOG
```
- Replicate
```
    ePOAPSVR_<SERVERNAME>.LOG
    ORION.LOG
    REPLICATION.LOG
```
- Script: engine; messages
```
    MCSCRIPT.LOG
```
- Server: in general
```
    SERVER.LOG
    SERVER_BACKUP.LOG
```
- Server: installation
```
    ePO5XXCOMONSETUP.LOG
    ePO5XX-INSTALL-MSI.LOG
```
- Updating
```
    UPDATERUI_<SYSTEM>.LOG
    <AgentGUID>-<TIMESTAMP>.XML (if registry value has been set)
    Mcscript.LOG
    Masvc_<SYSTEM>.LOG (shows when task invoked)
```
- Upgrading: from earlier version
```
    MIGRATION.LOG
    ePO5XX-INSTALL-MSI.LOG
```
- User Interface / Console HKLM\SOFTWARE\Network Associates\ePolicy Orchestrator -> (issues arising after changes to...)
```
    ORION.LOG
```

### Agent Log Files Overview

There are four common types of issues seen when troubleshooting various agent **issues & failures**:
當各種 Agent 的問題與故障中 Troubleshooing 最常碰到的四種問題類型：
![four types and log file](https://i.imgur.com/kZutRXX.png)

### Agent Troubleshooting Log Files

- Agent Installation(代理程式安裝)
    1. 所需文件日誌：`MfeAgent.MSI<DATE>.log`,`MFEagent.msi.2022.05.19.13.50.00.log`
        預設路徑：`%temp%\McAfeeLogs`
        文件描述：包含有關 Agent MSI 部署安裝檔安裝過程的細節。
        閱讀方法：從上而下搜尋字串`Value 2`or`Value 3`
    2. 所需文件日誌：`FrmInst_<SystemName>.log`
        預設路徑：`%temp%\McAfeeLogs`
        文件描述：在使用 **FrmInst.exe** (較完整)安裝檔安裝 Agent 時自動生成，包含內容有
        1. 資訊性消息
        2. 進度消息
        3. 安裝失敗消息
        閱讀方法：滾動到日誌底部查找關於`Fail`or`Error`的任何資訊。
- Agent-to-Server Communication(代理程式與伺服器通訊)
    1. 所需文件日誌：`Masvc_<SystemName>.log`
        預設路徑：`ProgramData\McAfee\Agent\log`
        文件描述：當伺服器向客戶端系統部署代理程式時在客戶端上生成，內容包含：
        1. 代理程式到伺服器的通訊
        2. 原則執行
        3. 其他代理任務
        閱讀方法：從底部開始向上蒐尋短語`Agent started performing ASCI`，並按照日誌往下查找任何錯誤資訊。
- Policy Enforcement(原則執行) \ Policy Updating(原則更新)
    1. 所需文件日誌：`Masvc_<SystemName>.log`
        預設路徑：`ProgramData\McAfee\Agent\log`
        文件描述：當伺服器向客戶端系統部署代理程式時在客戶端上生成，內容包含：
        1. 代理程式到伺服器的通訊
        2. 原則執行
        3. 其他代理任務
        閱讀方法：從底部開始向上蒐尋短語`Agent started performing ASCI`，並按照日誌往下查找任何錯誤資訊。
    2. 所需文件日誌：`Macompatsvc_<systemname>.log`
        預設路徑：`ProgramData\McAfee\Agent\log`
        文件描述：本地系統的主日誌，內容包含：
        1. 原則更新
        2. 原則執行
        3. 工作資訊
        閱讀方法：滾動到底部往上查找有關原則與工作執行的資訊，搜索`Task`,`Policy`,`Enforcement`資訊

:::info
Agent troubleshooting summary
透過以上可以發現，只要是安裝問題，Log 會產生在 %temp%，如果是其他任何工作與原則指派，會在ProgramData\McAfee\Agent\logs之中。
:::


### Installer Log Files Overview

下一部分的故障排除有關 ePO 安裝所碰到的問題。
ePO Installations and Upgrades
Agent Handler Installations and Upgrades
![](https://i.imgur.com/U4EFAeJ.png)

Notes:

- While the installer is running, the `<InstallLogs>` location is: `%temp%\McAfeeLogs`.
- Once the installer has completed (whether successfully or not), the logs are copied to:`C:\ProgramData\McAfee\ePolicy Orchestrator\InstallLogs`
- In a default Windows installation, C:\ProgramData is a hidden folder.

安裝時的Log會在`temp`資料夾，當安裝結束時Log會複製到`C:\ProgramData\McAfee\ePolicy Orchestrator\InstallLogs`，預設狀態下`C:\ProgramData`是隱藏資料夾。

### Troubleshooting Installation / Upgrade Issues

對於安裝程序的問題，需要包含整個 McAfeeLogs 文件夾的 MER 或 Zip，使用 MERTool 找到安裝失敗或故障之後安裝程式會將 Logs 複製到`%temp%\McAfeeLogs`文件夾中，才可以透過 MERTool 找到。確認錯誤時間後，找到 orion.log 並對其進行檢查收集其他故障訊息。

- Log Level 8 debug logging settings [(KB56207)](https://kc.mcafee.com/corporate/index?page=content&id=KB56207) are applicable to the Server.log, ePOApSvr.log, and Eventparser.log files.
- See [KB52369](https://kc.mcafee.com/corporate/index?page=content&id=KB52369) for details on enabling debug logging for the Orion.log.

### ePO 5.x Installer Log Files & Locations

[ 暫略 ]



### Installation / Upgrade Troubleshooting Log Files

有關安裝與升級的所有 Troubleshooting Log Files

1. 所需文件日誌：`EPO5xx-Install-MSI.log`
    預設路徑：`%temp%\McAfeeLogs`
    文件描述：ePO 主要的安裝日誌，包含安裝細節資訊，安裝進度與失敗資訊。
    閱讀方法：從上而下搜尋字串`Value 2`or`Value 3`，若找不到錯誤的值，表示沒有記錄到錯誤資訊。
    
2. 所需文件日誌：`epo-install.log`
    預設路徑：`%temp%\McAfeeLogs\ePO5xx-Troubleshoot\MercuryFramework`
    文件描述：當 ePO 安裝檔呼叫 ePO ANT installer 時建立的 Log，ANT 使用正確的路徑與埠號更新與複製 Apache.conf 文件。
    閱讀方法：
    1. 搜尋"BUILD SUCCESSFUL"到結束，這個過程很少失敗。
    2. 搜尋任何"error"or"faild"，出現錯誤資訊時應會告知失敗原因。

3. 所需文件日誌：`epoST.err`
    預設路徑：`<InstallLogs>\EPO5xx-Troubleshoot\OutputFiles`
    文件描述：安裝或升級大量 ePO extensions 的 ext.exe 執行指令錯誤。
    閱讀方法：如果此檔案存在代表肯定出錯了，因此這個檔案可以是升級 ePO 檢驗錯誤的第一步，而這個錯誤發生代表需要更改 extensions。這個問題很常發生，最簡單的方法就是刪除延伸模組，待 ePO 升級完再進行簽入。

4. 所需文件日誌：`Core-install.log	`
    預設路徑：`%temp%\McAfeeLogs\ePO5xx-Troubleshoot\MFS`
    文件描述：當 ePO 安裝程式呼叫 MFS ANT installer 時建立 Log，提供的資訊包含
    
    1. 創建伺服器的資料庫表
    2. 安裝的伺服器組件

    若此檔案已經刪除，代表已經安裝成功。
    閱讀方法：'BUILD SUCCESFUL'& 'BUILD FAILED'
    
5. 所需文件日誌：`Core-upgrade.log`(UPGRADE only)
    預設路徑：同上
    文件描述：同上，資訊2.為升級的伺服器組件
    閱讀方法：'BUILD SUCCESFUL'& 'BUILD FAILED'
    
6. 所需文件日誌：`<ExtensionFileName>.err`
    預設路徑：`%temp%\McAfeeLogs\EPO5xx-Troubleshoot\OutputFiles`
    文件描述：在簽入套件時 ext.migrate 遠程執行命令的文件
    閱讀方法：成功時刪除
    
7. 所需文件日誌：`EPO5xx-CommonSetup.log`
    預設路徑：`%temp%\McAfeeLogs`
    文件描述：包含 ePO 安裝時的詳細資訊
    1.  自定義操作日誌
    2.  SQL, DTS(微軟數據轉換服務)與服務相關調用
    3.  註冊與註銷 DLL
    4.  重新啟動時選擇刪除的文件和文件夾
    閱讀方法：從底部往上搜尋"error"or"failed"的第一個實例
    
8. 所需文件日誌：`<ExtensionFileName>.cmd`
    預設路徑：`%temp%\McAfeeLogs\ePO5xx-Troubleshoot\OutputFiles`
    文件描述：由 ePO 安裝程式建立。包含檢查延伸模組的指令，發送到遠程客戶端。文件內容包含作為安裝一部份運行的http指令，可以再安裝或升級之外手動執行。
    閱讀方法：成功時刪除
    

### Server Log Files Overview

- 伺服器工作(軟體目錄、AD同步、金鑰管理)

- 存放庫行為(Pull與複製)、中控台登入(密碼管理)

- 事件解析器(未處理的程序)

- SQL連接(TCP/IP 連接問題)


Server log ![server log](https://i.imgur.com/gOsvW0Y.png)

---

- Log 分布
    1. 安裝目錄中的 server logs
    `C:\Program Files (x86)\McAfee\ePolicy Orchestrator\Server\Logs`
    2. 安裝目錄中的 DB logs
    `C:\Program Files (x86)\McAfee\ePolicy Orchestrator\DB\Logs`
    3. `C:\Users\Jeffery\AppData\Local\Temp\McAfeeLogs`
    4. `C:\ProgramData\McAfee\Agent\logs`
    5. `C:\Windows\Temp\McAfeeLogs`
    

The most inportant log file of server logs is **Orion.log**, and second is **epoApSvr.log**.

Orion.log functions

- TOMCAT
- MF(McAfee Foundation)
- Console(password management)
- Browser(console actions)
- JAVA(services program remoted)

info-level

- Four level to descript information's severity
    1. ERROR
    2. INFO
    3. DEBUG
    4. WARN(最嚴重)

McAfee Foundation Services (MFS) 



##### epoApSvr.log

從 JAVA console 調用 C++ 代碼的日誌，跟本機作業有關的操作
- Repository Pull 存放庫拉取
- Repository Replication 存放庫複寫
- Software Catalog 軟體目錄
- Key Management 金鑰管理
- LDAP 輕型目錄存取協定
- AD 同步

troubleshooting 5/20 OK

