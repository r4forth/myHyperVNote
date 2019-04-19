# Hyper-V Server 2016 使用記錄

## 查詢 Hyper-V Server 2016 授權資訊

```
slmgr.vbs -dlv
```

[圖片]()


## 了解 Hyper-V 主機預設開啟 Port

```
netstat -nao
```

[圖片]()

* TCP 135, 49153, 49155、UDP 5355: svchost.exe Windows Service 的主機處理程序
* TCP 139, 445,5985,47011、UDP 137,138: System NT Kernel 與 System
* TCP 2179: vmms.exe 虛擬機器管理服務
* TCP 49152: wininit.exe Windows 啟動應用程式
* TCP 49154: lsass.exe Local Security Authority Process
* TCP 49156: service.exe 服務與控制站應用程式

## 設定固定IP位址

## 新增本機系統管理員帳號

1. 新增本機管理員
2. 確定新增系統管理員帳號資訊
3. 停用 administrator 帳號

```
net user administrator /ACTIVE:no
net user administrator
```

[圖片]()


## 主機允許 Ping 回應

1. 命令列下，執行 `sconfig`，叫出【伺服器設定】選單。
2. 設定遠端管理(4)/設定伺服器對 Ping 回應(3)

[圖片]()


## 不小心將所有視窗關閉，如何叫出命令列?

1. 實體主機: ctrl + Alt + Delete
2. 虛擬主機: 利用 Hypervisor 軟體送出組合鍵。
3. 遠端桌面操作: ctrl + Alt + END

然後叫出工作管理員，執行 `cmd` ，叫出命令列。
執行 `sconfig` 即可叫出 **伺服器設定** 選單


## 列出 Hyper-V Server 2016 所有支援的功能

進入 powershell

```
Get-WindowsFeature
```

[圖片]()


## 遠端管理使用單機環境

1. Hyper-V Server 新增 LocalAdministrator 管理者帳號
2. 在要遠端管理的主機(例如您的NB)上，新增一些設定
  * 新增 `C:\Windows\System32\drivers\etc\`
3. 允許 Anonymous Logon 遠端存取權限設定
4. 設定 Hyper-V Server 為信任主機
5. 兩邊主機都要設定相同的管理者帳號
6. 使用 Hyper-V Manager 遠端管理工具

## 


