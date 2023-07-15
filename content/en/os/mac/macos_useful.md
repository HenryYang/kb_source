---
title: "MacOS 實用技巧"
date: "2023-07-15"
---


##### 實用經驗


* 超有料的 macOS 使用者部落格 
    * https://mrmacintosh.com/

* 實用 macOS 軟體清單
    * https://github.com/HenryYang/macOS-essential

</br>

* 手動下載 macOS 更新方式
    * https://support.apple.com/downloads/macos
    * 遇到要重新安裝更新、更新韌體、下載離線更新包都可以在這找到各種 masOS 的更新。

</br>

* 個人推薦的系統清理工具 - [OnyX](https://www.titanium-software.fr/en/onyx.html)
    * 用於把系統各種快取與設定清除並且驗證系統檔案的工具。它清除完後第一次重開因為系統會重新建立一些快取所以前一小時電腦會很慢是正常狀況。

</br>

* 處理鬼打牆的 Mac 設備通則
    * 重開機 -> 「磁碟工具程式」修復磁碟 -> 重置 Mac 上的 NVRAM 或 PRAM ->  重置 Mac 上的系統管理控制器（SMC）-> 執行 OnyX


</br>


* 登入電腦版的 iCloud App 跳出 this is valid account but not icloud account 錯誤
    * 這代表這組 Apple ID 是透過網頁註冊出來的。所以沒有 iCloud 帳戶的功能。
    * 解法就是拿一台最新版的 iOS 設備，登入後照流程走就會開通 iCloud 功能，之後再登入電腦版就會正常了
    * P.S. 確認的方式就是登入 https://www.icloud.com/ 然後看看這帳戶有沒有 Find My friends 來判定。


</br>


* 無法開啟系統偏好設定內的使用者群組處置方法
    * 這會發生於為網域帳戶且沒有 Mobile Account 與管理權權限時，解法就是在該網域帳戶下打開終端機用 `su` 指令切換成本機的任意帳戶。
    * 這時候把『啟系統偏好設定』整個關掉再打開就會可以進入 使用者群組 了。當進去後請記得給該網域帳戶 Mobile Account 的權限。


</br>

* 檢查自己目前安裝的 macOS 軟體是不是 intel only
    * https://github.com/DigiDNA/Silicon


</br>

* 在 macOS 上重建損壞的分割區 （請看 Method 2）
    * https://www.macgasm.net/data-recovery/mac-partition-recovery/


</br>

* 在 Apple Silicon 的 macOS 上使用 Android USB Tethering 分享網路
    * https://vocus.cc/article/616bb7d1fd897800012129f0


</br>

* Apple Silicon 平台的 macOS 重灌教學
    * https://www.techtimes.com/articles/254409/20201123

</br>

* macOS 詳細透過 CLI 設定電源管理方法
    * https://www.rawinfopages.com/mac/how-to-customise-power-settings-terminal-mac

</br>


* 舊版 macOS 系統 App Store 下載連結
    * [macOS 13.0 Ventura](https://apps.apple.com/tw/app/macos-ventura/id1638787999)
    * [macOS 12.0 Monterey](https://apps.apple.com/tw/app/macos-monterey/id1576738294)
    * [macOS 11.0 Big Sur](https://apps.apple.com/tw/app/macos-big-sur/id1526878132)
    * [macOS 10.15 Catalina](https://apps.apple.com/tw/app/macos-catalina/id1466841314)
    * [macOS 10.14 Mojave](https://apps.apple.com/tw/app/macos-mojave/id1398502828)
    * [macOS 10.13 High Sierra](https://apps.apple.com/tw/app/macos-high-sierra/id1246284741)
    * [macOS 10.12 Sierra](https://apps.apple.com/tw/app/sierra/id1127487414)

</br>


* M1 系列 macOS 可模擬的遊戲列表清單
    * https://www.applegamingwiki.com/wiki/M1_CrossOver_Windows_compatible_games_list

</br>


* 打包 iCloud 上的各式資料 (包含照片、雲端檔案和郵件)
    * https://privacy.apple.com/

</br>


* 網路上找到的 Macbook SSD 各年份款式

![](https://i.imgur.com/TQWmt1q.jpg)

</br>