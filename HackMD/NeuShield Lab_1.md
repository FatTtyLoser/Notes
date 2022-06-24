# NeuShield Lab_1
###### tags: `Training` `Solutions Architect`


### Step.1

要開始做之前，請先跟我說幫您開測試帳號。
您將被指派為管理員，請完成以下設定。
1. :OK_hand:使用管理員帳號，登入啟用NeuShield
2. :OK_hand:首先，確認授權到期日，與具有的 Client 與 Server 授權數量
    ![確認授權到期日](https://i.imgur.com/YHPTWqY.jpg)
    *確認授權到期日*
    ![確認具有的Clients&Servers數量](https://i.imgur.com/WBvxPoP.jpg)
    *確認具有的Clients&Servers數量*
3. :OK_hand:為了達到群組管理，分別建立 Clients 與 Servers 兩群組
    ![建立Clients&Servers群組管理](https://i.imgur.com/dKQRQU3.jpg)
    *建立Clients&Servers群組管理*
4. :OK_hand:在 Clients 與 Servers 群組，分別建立NeuShield Data Sentinel(NDS)安裝檔案
    承3.直接根據建立好的群組點選Installer即可建立安裝檔並下載。
5. :OK_hand:將上述所產生的檔案，分別安裝於 Client 與 Server 兩系統
    將檔案傳到User設備進行安裝。
6. :OK_hand:在 Client 中，手動於桌面建立 Data 資料夾並放入檔案，再設定保護
    ![群組設定](https://i.imgur.com/KWghrlW.jpg)
    *個別群組NDS設定與群組成員NDS操作權限*
7. :OK_hand:在 Server 中，手動於桌面建立 File 資料夾並放入檔案，同時在管理介面設定保護
    ![修改群組原則](https://i.imgur.com/d2yvy4X.jpg)
    修改群組原則，對NDS設定做客製化資料夾路徑進行保護。
8. :OK_hand:在管理介面中，調整 Clients 群組原則設定，調整為強制啟用 Boot Sector Protection & Anti-Wiper Protection，並設定移除密碼與不讓使用者手動還原檔案
    承7.對Clients群組原則設定頁面可以找到所有設定。
9. :OK_hand:在管理介面中，調整 Servers 群組原則設定，調整為關閉 Data Engrams、並將提交周期延長至48小時
10. :OK_hand:同時有多個管理員要登入，請建立一個帳號Andy(andy@pronet-info.com.tw)
    ![在帳號活動內新增一名Admin](https://i.imgur.com/S6sVGz9.jpg)
    在帳號活動內新增一名Admin
