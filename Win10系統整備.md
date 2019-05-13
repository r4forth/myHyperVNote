# Win10 安裝基礎

# 系統準備

Windows 10 Sysprep 系統準備的步驟

1. 設定 BIOS： 光碟或 USB 開機
2. 入系統後，執行 Windows Update ，更新系統至最新。
3. 更改使用者帳戶控制設定----改為不要通知。
4. 變更 C:\Program Files\WindowsApps 資料夾的擁有者----變更為 administrators 群組
5. 移除內建的 APP(需要重開機執行多次)：

```
Get-AppxPackage | Remove-AppxPackage
Get-AppxPackage -allusers | Remove-AppxPackage
```

6. 使用 Administrator 帳號，並以 Administrator 登入，登入後重新執行上一個步驟(步驟 5)；並刪除不必要的帳號及使用者設定檔。
7. 進行磁碟清理
8. 進行 Sysprep：

```
Sysprep /generalize /shutdown /oobe
```
9. 使用 Dism++ 備份系統


# WinPE 使用教學

# Diskpart 指令整理


# Office365 設定檔組態程式

[官網連結](https://config.office.com/deploymentsettings)
