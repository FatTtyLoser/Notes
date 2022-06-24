# McAfee 部屬失敗紀錄
###### tags: `McAfee`

### 安裝失敗

- 重新啟動排程中

2022/5/6 上午 10:05:47	已開始: 已將立即執行工作「McAfee Agent > 產品部署」傳送至「JEFFERY-PC」
2022/5/6 上午 10:05:50	收到立即執行工作 McAfee Agent > 產品部署。
2022/5/6 上午 10:05:55	已啟動立即執行工作 。
2022/5/6 上午 10:06:42	立即執行工作 McAfee Agent > 產品部署 失敗。
詳細資料: 
```
Product "ENDP_GS_1070" installation failed, reason "Update/deployment failed because reboot pending".
Product "ENDP_GS_1070" installation failed, reason "Unknown error".
Product "ENDP_GS_1070" installation failed, reason "Update/deployment failed because reboot pending".
Product "ENDP_AM_1070" installation failed, reason "Unknown error".。
```

表示電腦有未知的系統程序正在等待重新啟動，像是 Windows 更新排程等等。

###  ePO 無法正常連線

- ePO 無法連到資料庫(未知錯誤)

由於 server 端從本機，創建網域後加入網域，導致連線到資料庫失敗，需要進入到`https://jeffery-server:8443/core/config`進行測試與更改設定，`jeffery-server`可以更改成 IP 位置以便進行更精確地連線，以免因為網域不同而找不到電腦。