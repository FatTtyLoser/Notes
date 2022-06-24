# AWS 入門
###### tags: `Amazon Web Services` 

[TOC]

### AWS

亞馬遜網路服務（英語：Amazon Web Services，縮寫為AWS），是由亞馬遜公司的子公司(Amazon Web Services, Inc.)所建立之雲端運算平台，向個人、企業和政府提供一系列包括資訊科技基礎架構和應用的服務，如儲存、資料庫、計算、機器學習等等。

### 創建帳戶

創建帳戶後，此帳戶為根帳號(root)具有最大權限，因此應該創建一個 [IAM](https://aws.amazon.com/tw/iam/faqs/) 帳號(Identity and Access Management)，透過根帳號設定工作群組來制定IAM帳號的權限進行管理，避免造成不可預期的操作失誤。

### 虛擬伺服器

AWS 提供許多雲端服務，其中功能包含最廣泛的就是虛擬伺服器 EC2，透過虛擬伺服器 LinuxServer 並可以使用 AWS 提供的工具進行資料儲存、機器學習等等。

### 建立 EC2

透過 AWS 網頁設定虛擬機的作業系統、服務方案與個人化的標籤與認證方式、服務方案，選擇的連線方式與密鑰關乎連線的權限與方式，本機使用個人 IP 作為權限限制，並創建新的金鑰、下載並保存後，透過 Tera term 連線到公開 IPv4 地址:**18.181.78.96**，即可成功連線。
透過 Tera term 連線是使用 Linux 提供的 SSH(Secure Shell) 的連線方式來確保傳輸安全性，因此需要使用我們在建立伺服器時新增的金鑰進行遠端連線。還有不同的傳輸方式可以使用。

![建立新連線](https://i.imgur.com/uuAEloW.jpg)

* 建立新連線
  1. Host 填入 EC2 IPv4 的位址
  2. 2.TCP port 號預設 22
  3. 服務選擇 SSH 連線方式

![SSH 認證](https://i.imgur.com/dj22Ew8.jpg)

* SSH 認證
  1. 用戶名 ec2-user 是 Amazon Linux 2 啟動時建立的使用者
  2. 選擇 RSA 密鑰登錄，使用我們預先下載的密鑰(.pem)檔案

![連線成功](https://i.imgur.com/7LzOIIA.jpg)
:arrow_up:連線成功！

#### 不同的傳輸方式

Session Manager(工作階段管理)是 AWS Systems Manager 的服務之一，預設定對 EC2 上 Systems Manager 的存取權限時必須使用 IAM 角色。
從 Systems Manager 右側可見節點管理的工作群組，可以從機群管理員中查看目前啟動中可用的虛擬機，而從工作階段管理員可見可執行工作的執行個體，選擇後點選開始工作階段之後，就可以成功連線到虛擬機上了，相較於傳統 SSH 的連線方式便捷許多。
因此如果之後不使用 SSH 時，可以在 EC2 儀表板中的安全群組編輯傳入規則刪除，如此不能透過 SSH 做遠端連線了。

### 映像檔

Amazon Machine Image (AMI)，當我們選擇所需要的服務來建立一個客製化的執行個體時，像是我們可以將自己選擇的指定格式與服務的 EC2 伺服器進行打包，形成一個 Image 讓我們下次需要重新啟動時可以快速建立，而且要幾個就有幾個。

### 執行指令

#### sudo -u [使用者名稱(user name)]

當我們使用 SSH 或是 session manager 連線時，使用的身分是 AWS EC2 建立時預設建立的使用者(ec2-user 或 ssm-user)，因此我們透過使用者操作時，並沒有全部的權限，擁有的權限看我們如何透過 root 設定，此時如果我們有需要 root 權限的操作時，可以使用 **sudo** 指令來做單指令的權限突破。

```
sudo -u ec2-user cat /var/log/recure
= cat /var/log/recure

sudo cat /var/log/recure
= sudo -u root cat /var/log/recure
```

#### sudoers 檔

而並不是每個使用者都可以使用 sudo 指令，我們可以透過 sudoers 檔案來查找特定使用者是否在 sudoers 類別裡面。

```
sudo cat /etc/sudoers
# wheel ALL=(ALL) ALL

sudo cat /etc/group | grep wheel
# wheel:x:10:ec2-user
```

### EC2 的套件管理

在 EC2 上有幾種方式可以管理套件，由於本身是 Linux kernel(核心)因此在 Linux 使用的指令，在 EC2 同樣可以，但由於經過 AWS 的編寫管理，有部分的套件為了更好地融入 AWS 提供的服務，所以有更好的管理套件可以使用。

#### yum

使用 yum 來安裝套件 `sudo yum install http` 系統會自動聯網並找到套件的安裝模組並進行安裝，安裝後系統會先顯示依存項目的下載大小、安裝大小供你確認，確認後並同意安裝，安裝結束後會一併顯示 Installed((已安裝套件一覽清單)、Dependency Installed(已安裝的依存項目清單)、Complete!(表示已成功安裝)，可以在安裝指令加上 `-y` 省去確認的步驟。

* 常用指令
    安裝套件 `yum install -y 套件名稱`
    更新套件 `yum update 套件名稱`
    移除套件 `yum remove 套件名稱` `yum erase 套件名稱`
    列出所有已安裝套件 `yum list`
    查詢特定已安裝套件 `yum list | grep '套件名稱'`
    查詢命令被什麼套件安裝 `yum provides "/*/套件名稱"`

#### rpm

由於 rpm 安裝套件時需要自行將套件的依存項目準備好，在安裝指令也要寫上包含版本的套件全名，可能會東漏西漏的無法正常安裝套件，所以比較常用 yum 來安裝比較方便，而 rpm 也可以用來管理安裝套件。
rpm 模組格式舉例說明： `httpd-2.4.x-1.i686.x86_64.rpm`
`httpd` 是套件名稱，`2.4.x`是版本資訊，`1.i686`是釋出版本號，`x86_64`是執行平台若是`noarch`則代表無平台限制。

* 安裝 / 升級模式
    `-i`: 安裝套件
    `-U`: 升級套件(若無，則進行安裝
    `-F`: 若已安裝此套件，就進行升級
    可以進一步附加併用選項
    `v`: 顯示詳細資訊
    `h`: 以「#」顯示進度
    `--nodeps`: 安裝時忽略依存項目
    舉例： `rpm -ivh RPM套件名稱`
* 查詢模式
    `-q`: 查詢已安裝的套件
    可以進一步附加併用選項
    `a`: 顯示所有已安裝的套件
    `p`: 指定查詢特定套件
    `c`: 僅顯示設定檔
    `i`: 顯示套件資訊
    `--changelog`: 顯示變更日誌紀錄

#### amazon-linux-extras

Amazon Linux 2 (AWS 的 linux kernel 名稱)具有名為 **amazon-linux-extras** 的儲存庫，可提供新版本的套件，由於 Amazon Linux 2 預設裡面的軟體並不會持續更新，所以當我們有需要更新版本的軟體時，若軟體羅列在 amazon-linux-extras 中則可以進行更新安裝。
* `amazon-linux-extras list`: 檢視儲存庫的所有套件
    查找自己所需要的套件有列於此處時，就可以使用`amazon-linux-extras install python3.8`(列表中第一列套件名稱或加上版本) 來安裝在列表上的指定版本。
    
### 使用 S3(Simple Storage Service)

Amazon Simple Storage Service 是 Amazon 提供的物件儲存服務，具有以下幾項特色：資料儲存不受限、具高度耐久性與可用性、支援網路存取。

* 資料儲存不受限
    EC2 是 Linux kernel 的虛擬機，通常虛擬機在建置時預設 8GB 的大小，而 EC2 如果有更大的容量需求則需要擴充它，上限到 16TB，S3 的儲存容量不需要預留，只要須建立名為儲存貯體(Bucket)的資料容器，將資料存入儲存貯體即可，Bucket 沒有容量限制。
* 高度耐久性與可用性
    S3 具有由「可用區域」(Availability Zones)的多個資料中心構成的資料中心群組，儲存於 S3 的資料會自動使用多個可用區域，以確保耐用性。
* 支援網路存取
    可透過 HTTP/HTTPS 協定從世界各地輕鬆存取，存取方法包括使用「管理控制台」的瀏覽器 GUI 工具，CLI (Command-Line Interface，命令列介面)，以及 SDK (Software Development Kit，軟體開發套件)等，是個可編寫程式的儲存服務。
    
#### 使用 AWS CLI(命令列介面)

Amazon Linux 2 預設已經安裝了 AWS CLI 我們可以透過終端機查看版本 `$aws --version` 。

要使用 S3 之前我們需要先為　EC2 執行個體開啟權限，當初我們建立 EC2 時同時建立了一個 IAM 角色並命名為 LinuxRole 把 EC2 服務的權限賦予給角色，因此我們也要將使用 S3 儲存服務的權限加入到 IAM 角色中，才可以開啟服務。相關操作流程：進入 IAM 儀表版、選擇角色、連接政策、搜尋 S3 並新增連接政策。

### 服務相關知識

- [AWS 區域服務](https://aws.amazon.com/tw/about-aws/global-infrastructure/regional-product-services/)
AWS 服務目前具有 26 個區域與每一個區域內有數個可用區域可以提供使用者選擇，而本一個可用區域提供的服務可能有區別，常見的核心服務都有提供，網址可以查詢該區域提供的服務列表。
