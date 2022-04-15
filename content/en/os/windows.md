---
title: "Windows Essential App & Tips / Windows 常見軟體與小技巧"
date: "2020-07-07"
---

##### 開啟虛擬化 (WSL2 需要)
```shell
bcdedit /set hypervisorlaunchtype auto
```

</br>

##### 關於靜態路由
```shell
# 顯示目前路由表
route print

# 刪除全部路由表
route -f
```

</br>

##### diskpart 來完整清除分割區
```shell
#顯示磁碟清單
list disk

#選擇要處理的磁碟
select disk {NO}

#清除目前處理磁碟的所有分割區
clean
```
</br>

##### 關閉 Microsoft Compatibility Appraiser
```shell
工作排程器 -> 工作排程器程式庫 -> Microsoft -> Windows -> Application Experience 對 Microsoft Compatibility Appraiser 按右鍵選停用
```

</br>

##### 快捷鍵重置 Windows 10 的繪圖驅動程式
```shell
𝚆𝚒𝚗+𝙲𝚝𝚛𝚕+𝚂𝚑𝚒𝚏𝚝+𝙱
```

</br>

##### 當 WSL 的顯示語系異常時
```shell
控制台 -> 時鐘與區域 -> 地區 -> 系統管理 -> 更變系統地區設定，把這選成自己常用的語言
```

</br>


##### 透過 CLI 移除各種預載在 Windows 內的應用程式 
```shell
#顯示安裝軟體的清單
winget list

#移除指定軟體
winget uninstall "軟體名稱"

```

</br>



##### 讓 Windows 11 的右鍵找回原本的選單
```shell
#使用 CMD 即可，不需要管理員權限，修改完要重開
reg add “HKCU\Software\Classes\CLSID\{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}\InprocServer32” /f /ve

```

</br>
