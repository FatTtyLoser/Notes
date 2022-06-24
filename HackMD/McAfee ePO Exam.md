# McAfee ePO Exam
###### tags: `McAfee`

### 題目

1. Which option reduces the bandwidth required by ePo to distribute(分發) updates to clients?
    - Reconfigure Bandwidth utilization in Server Settings
    - Relay Server communication
    - Compress the update files in the repository
    - :heavy_check_mark:Configure a super-agent hierarchy(階層)

2. What service must be running and fully operational while regenerating(再生) the Apache SSL Certificate as part of the manual disaster recovery procedure?
    - ramework service
    - Event parser service
    - Application server service
    - :question:Apache Service

3. How many Snapshots are retained when running the Disaster Recovery Snapshot Server Task?
    - 4
    - 10
    - :heavy_check_mark:0
    - Number is configurable in the task.

4. Which of the following is exclusively performed by a Global Administrator?
    - :heavy_check_mark:Create,edit or delete source and fallback repositories
    - Create,export or delete policies in the policy catalog
    - Create,duplicate or assign tasks in the client task catalog
    - Create,export or delete dashboards from Reporting Dashboards

5. What are the connectors for which System tree synchronization can be configured?
    - Open LDAP
    - eDirectory
    - :heavy_check_mark:Active Directory
    - Novell

6. Which of the following creates database performance problems and can be solved by regular database maintenance?
    - Table corruption
    - Transaction log file management
    - Auto-shrink is not enabled
    - :heavy_check_mark:Index fragmentation

7. Where in the ePo console would an administrator go to add a new location for a master repository pull task to pull from?
    - Server settings Source Repositories
    - :heavy_check_mark:Server settings Source Sites
    - Master Repository Edit
    - You cannot change where the repository pull task pulls from

8. How could an Administrator Schedule a purge of the Audit Log?
    - Policy Catalog
    - :heavy_check_mark:Server Task
    - Client Task
    - Task Scheduler

9. :question:Which supported method ePO allows a user to configure system tree synchronization?
    - Open LDAP
    - eDirectory
    - :question:Active Directory
    - Novell

10. Fill in the blanks: The two methods by whichs by policies are applied to any system inheritance or __________.
    - Time window
    - GPO
    - Locking
    - :heavy_check_mark:Assignment

11. Which of the following Audit Log Details is found in the Audit Log?
    - Server service started
    - Machine has applied policy
    - :heavy_check_mark:User "User Name" has logged out
    - Last Device communication time

12. What is required when using the McAfee Smart Installer to install the McAfee Agent?
    - :heavy_check_mark:Administrator rights
    - User Rights
    - Local console access
    - Windows 2000 or above

13. How can changes to policy ingeritance be prevented?
    - Enable a Policy Assignment Rule
    - Set the master policy in the Policy Catalog
    - :heavy_check_mark:Implement a Permission Set
    - Lock the policy

14. What feature can be used to override the policy assignment in the system tree for an endpoint to provide a different policy?
    - :heavy_check_mark:Policy Assignment Rule
    - Policy Override
    - LDAP Sync
    - Tags

15. What is an example of an aggregating response
    - :heavy_check_mark:A response is triggered if multiple events occur within 1 hour
        - 本題應該是說具有兩個限制以上的綜合響應的例子，在一段時間內、多個事件，則觸發響應。
    - At most, trigger a response every 1 hour
    - At most, trigger this response every 2 days
    - The policy catalog has been duplicated and exported into an xml file

16. Who can approve Policy and Client Task Change Approvals?
    - :question:Only Administrator
        - 能變動批准權限的只有管理員
    - any user in ePO
    - :heavy_check_mark:Administrator and non-admin users with appropriate permission sets
    - There is no option in ePO to approve policy or tasks

17. Which of the following options are available in the System Tree for managing tags?
    - :heavy_check_mark:Clear Tag
    - Delete Tag
    - Edit Tag
    - New Tag

18. Which server task takes user information from LDAP and makes a copy of it in the ePO DB?
    - :heavy_check_mark:Active Directory Sync
    - LDAP Mirroring
    - :question:Ldap Sync
        - 單純用同步？
    - Database Mirroring

19. Which server setting would you edit to enable automatic user creation?
    - [ ] User Policies
    - [ ] User Session
    - [x] :question:Active Directory User Logon
        - 當同步 AD 之後可以自動產生的，只有登入權限的生效。
    - [ ] Active Directory Groups

20. If a user is not able to log in to the ePO console, which log should be referenced to get more information?
    - server_(server name).log
    - [x] orion.log
    - EpoApSvr_(server name).log
    - localhost_access_log.log

21. Which of the following features require you have a registered LDAP server defined to use them?
    - [X] Active Directory Sync, Policy Assignment Rules, Tags based on users
    - Database Mirroring, LDAP Mirroring, Push Agent Install
    - No features require a registered LDAP server
    - LDAP Sync, Automatic User Creation, User Based Policies

22. How to review the progress from the Sha1 to Sha2 certificate migration within the ePO console?
    - By navigating to the folder Policy Orchestrator\Apache2\conf\ssl.crt a .txt file will be writen there recording the progress
    - [x] Menu> Configuration> Certificate Manager
    或者是 Agent Handler
    - Menu>Reporting> Audit log
    - Menu>Systems> System tree and then adding the collumn "sha1 to sha 2 miration"


23. Which of the following methods can be used to add systems to groups within the system tree?
    - Client task
    - [x] Running an ePO discovery scan
    - Text file
    - Super-agent wake-up call

25. Which of the following helps in configuring Sorting criteria?
    - Operation system
    - [x] Tag
    - Client time zone
    - Policy

25. Which SQL Maintenance tasks should be run as part of a recommended ePO database maintenance plan?
    - Run SQL Trace
    - Shrink Database
    - Check Database Integrity
    - [x] Database Snapshot

26. What is the purpose of different repository branches (Current, Evaluation and Previous) in ePO?
    - The Current branch holds most software, the Evaluation branch is for unlicensed (trial) Software and the Previous branch is for identifying unsupported software
    - [x] The different branches allow the administrator more flexibility in controlling when and how machines apply software installs and updates based on McAfee Agent update policies
    - Files downloaded by the ePO server will be placed automatically into the Evaluation branch - only pre-installed packages exist within 
    - The Current branch The Current branch holds software packages which are used for the ePO server itself - Evaluation and Previous are used for serving files to managed Agents


27. What component needs to be installed in the DMZ to allow external managed systems to receive appropriate policies and tasks?
    - Framework
    - :question:Agent Handler or ePO
    - Super Agent
    - Repository

28. Which line in log-config.xml can be changed to enable Debug logging for orion?
    - :question:Change < priority value="Warn" /> to < priority value="debug" />
    - Change < priority value="debug" /> to < priority value="warn" />
    - ">Change < priority value="warn" /> to < priority value="debug level 1" />
    - ">Change < priority value="debug level 1" /> to < priority value="Warn" />

29. What does locking of assignments prevent?
    - Changes to the policy at the parent
    - Changes to client tasks
    - :question:Changes to inheritance
    - Changes by users

30. What is the format of the normalized data in the Threat Event table?
    - Extensible Configuration Checklist Description Format(XCCDF)
        - XCCDF 是一種 XML。
    - Common Events Format(CEF)
    - Security Content Automation Protocol Format(SCAP)
    - Data Access Layer(DAL)

31. What is the URL to test the connectivity of ePO to database?
    - https://localhost:8443/core/db
    - :question:https://localhost:8443/core/config
        - 只有 /core/config 是正確網址
    - https://localhost:8443/config
    - https://localhost:8443/db

32. Who has access to private queries?
    - :question:The creator
        - 只有建立者可以查看個人的私人查詢，除非將其移入公有群組
    - Gloval Administrators
    - Administrators with the correct permission set
    - Group Administrators

33. What action on ePO console will force a remote host to check in with ePO server?
    - Fetch inventory(提取庫存)
    - :question:Wake up agents
        - 強制喚醒
    - Enforce policies
        - Agent 在預設收集資訊的間隔閒置時無法強制更新 policy 但一旦接受會以 ePO 所發布的 policy 為準。
    - Show source systems

34. Which of the following criteria purges Threat Events?
    - Managed system query
    - Event Age
        - 根據事件日期自動清除
    - Single line chart
    - Multi line chart

35. On what basis are **Criteria-based** tags created on?
    - Task settings
    - System properties
    - Product properties
        - 查找 Tag catalog 中的 tag details 可能是 system properties or product properties
    - Policy settings

36. What is the minimum password Length for an ePO user if Passeord Strength Criteria is enabled?
    - :question:7.0
    - 10.0
    - There is no option in ePO to enable password strength criteria
    - 4.0

37. Which ePO process writes to the orion log?
    - Apache.exe
    - :question:Tomcat7.exe
    - Eventparser.exe
    - orion.exe

38. What does locking assignments, prevent the other ePO users from doing?
    - Modifying a policy
    - :question:Breaking inheritance
    - Modify system tree
    - Add subgroups

39. Why would a managed system appear in the Lost&Found group?
    - No matching criteria were met
    - Matched sorting criteria were met
    - Multiple matching criteria were met
    - :question:Agent has not communicated for a specified amount of time


40. Which ePO log should be reviewed first when the ePO console fails to load successfully or allow logins?
    - :question:Orion log
    - System log
    - Apache log
    - Server log

41. Which log should be referened if an ePO dahboard does not report results?
    - Apache
    - ePOAPSvr
    - Server
    - :question:Orion

42. Which of the following command line for the cmdagent.exe will check for new policies and enforces them immediately upon receipt?
    - /n
    - /p
    - :question:/c
        - 檢查新原則理論上接收到新原則就會強制執行
    - /e
        - 強制執行原則(locally)

43. Where is the System Tree Sorting enabled in the console?
    - :question:Server Settings
        - server setting 中的 Filter criteria setting
    - Client tasks
    - Sorting Criteria
    - Assigned Policies

44. What would be the vest log to review first if all agents are failing to communicate with a handler?
    - :question:server_.log
    - Orion.log
    - eventparser_.log
    - handler.log

45. Which service for epo listens on port 443 (default) and processes agent-to-server communication requests?
    - McAfee ePolicy Orchestrator Application Server
    - McAfee ePolicy Orchestrator Event Parser
    - McAfee ePolicy Orchestrator Server
    - :question:McAfee ePolicy Orchestrator Handler


46. Which ePO process writes to the server_.log?
    - :question:Apache.exe
    - Tomcat7.exe
    - Eventparser.exe
    - naimsrv.exe

47. What is the purpose of the Audit Log?
    - Maintain and access a record of all Managed Systems
    - Maintain and access a record of all Enforced Policies
    - [x] Maintain and access a record of all ePO User Actions
    - Maintain and access a record of all Threat Events


48. Which of following keys is required for the ePO Server to communicate with existing Agent, while restoring ePO from a backup?
    - Local Master Repository Communication Key
    - Agent Server Secure Communication Key
    - [x] Legacy Agent Server Communication Key
    - McAfee SIA Repository Communication Key

49. Which service for ePO listens on port 8443(default) and hosts the ePO console?
    - [x] McAfee ePolicy Orchestrator Application Server
    - McAfee ePolicy Orchestrator Event Parser
    - McAfee ePolicy Orchestrator Server
    - McAfee ePolicy Orchestrator Console

50. How can the machines be logically grouped, and policies and tasks be assigned?
    - AD Sync
    - [x] System Tree
    - Policy Catalog
    - Sorting Criteria

51. How will the system sort the group if the sorting criteria overlaps two groups?
    - Sorting order
    - [x] Tag
    - AgentGUID
    - MAC

52. Where in the ePO console would an Administrator go to view the Threat Event Log?
    - Server Settings
    - Configuration
    - :question:Reporting
    - Automation

53. Which of the following options are avaliable for Default Dashboards?
    - Modify
    - Delete
    - :question:Duplicate
    - Share

54. Where does the Treat Event Log view and sort through events
    - In the database
    - On the Managed System
    - From the Event Log
    - :question:In the System Tree
        - 點進去個別系統可以查看威脅日誌

55. What are the two types of configurable Product Deployment?
    - Continuous and Fixed
        - 產品部屬的方式，如果選擇群組做發布，只要後來加入群組的系統都會執行同樣的工作，這種方式就是 Continuous，如果只對個別系統(多數)進行部屬，那麼只會影響所選擇的系統。
    - Immediately and Delayed
    - Timed and One Time
    - Software and Scripts

56. What are Agent Handlers used to?
    - Replace distributed repositories
    - :question:Route communication between agents and the database
        - 不是降低頻寬影響，而是減少 ePO server 的負擔。
    - Fix a broken network segment
    - Identify Rogue on the network

57. What would be the best log to review first if no users are able to access the ePO cosole?(沒有用戶，代表整組壞去，所以不是eventparser也不是ePoSr.log會記錄的)
    - eventparser_log
    - server_log
    - console_log
    - :question:Orion_log

58. What is the URL to test the connetivity of ePO to database?
    - https://localhost:8443/core/db
    - :question:https://localhost:8443/core/config
        - 本題題目應該確定有重複，只有這個網址是正確的。
    - https://localhost:8443/config
    - https://localhost:8443/db

59. What third-party method can be used to deploy McAfee Agent?
    - Microsoft downloader
    - [x] Group Policy Objects
    - FTP
    - BootP

60. What happens when a purge task is run against the Audit Log?
    - The records are archived to a configurable location on the ePO for future review
    - The records are archived to the Temp directory for future review
    - The records are deleted permanently according to the Filter configured in the Audit Log
    - [x] The records are deleted permanently according to the configured Actions and Schedule
