# McAfee ePO operational Lab_2
###### tags: `Training` `Solutions Architect`

1.	:OK_hand:還原Client所有原則設定
2.	:OK_hand:這個ePO同時會有很多人進行管理，請您設定Andy與Leo為管理員，能夠登入ePO管理
3.	:OK_hand:請您在伺服器工作中，找到更新主要存放庫之工作，設定只要更新AMCore病毒碼更新與掃描引擎更新(Windows)
4.	:OK_hand:客戶希望更新病毒碼能夠節省頻寬與更快速的更新完成，請您將Client的Agent設定轉換成Super Agent，達成分散式存放庫架構
5.	:OK_hand:客戶想要更快速的查看所需資訊，請您在ePO的系統樹狀目錄中新增選擇欄位，包含McAfee產品版本 & Endpoint Security各個套件版本 & AMCore病毒碼版本 & 掃描引擎版本
6.	:OK_hand:客戶基於稽核要求，需要知道三個月內非作用中的代理程式有哪些，請您於查詢與報告中，新增一個查詢是可以達到這個需求
7.	:OK_hand:客戶希望每周都能針對上一份查詢定時透過郵件收到，請您設定每周一定時發送該查詢給你自己
8.	:OK_hand:客戶想要一目瞭然所有事件的發生與更新狀況，請您在儀表板中設定可以達成該要求之內容
9.	:OK_hand:目前ePO版本有點舊，請您將ePO升級至5.10版本
10.	:OK_hand:ePO升級完成後，請將ePO版本更新至Update12版本

升級packge需要一個路徑，至少兩層，可以放在此處：`C:\Program Files\McAfee\Repository`

### Question:
1. ePO 郵件設定，如果客戶公司有 Mail server 可以透過該公司管理員的 Mail 發送，假如沒有的話呢？
    Ans.郵件轉發的功能仍然需要客戶的 Mail server 開啟 relay 功能，才能進行轉發，因此如果客戶本身條件需求不足則就沒有辦法。
2. 儀表版上面的內容，客戶若無客製需求，有沒有應當預設的查詢報告？example: 7日內威脅摘要之類的。
    Ans.基本上 **ePO 摘要**儀表板，可以最簡單給予客戶更新狀況與偵測歷程即可。
3. 誤刪:
    product improvement program 
    product improvement program content
    product improvement program ePO content
    a.由於上列三者套件，用於幫助 McAfee 進行資料蒐集以最佳化產品為目的，不影響使用的情況下，可以替客戶刪除來整理存放庫，方便查找。
    
Jeffery-Server ePO 登入：[McAfee ePolicy Orchestrator](https://IPAddress:8443/core/orionSplashScreen.do)