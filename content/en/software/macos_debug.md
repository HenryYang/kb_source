---
title: "MacOS Debug / MacOS 除錯設定"
date: "2020-07-07"
---

##### 常見 Mac 開機時除錯快捷鍵

* 預設在 Windows 鍵盤上
    * Option 就是 Alt
    * Command（⌘） 就是 ⊞ WinKey
* 執行 Mac 上的「Apple 診斷」
    * 關機時按下電源鍵，且立即按住鍵盤上的 D 鍵，按住直到出現「選擇語言的畫面」為止。
* 重新安裝 macOS 
    * 關機且插上網路線時按下電源鍵，且立即按住鍵盤上的 Command（⌘）與 R 兩個鍵。
* 手動選擇開機磁碟
    * 關機時按下電源鍵，且立即按住鍵盤上的 Option 鍵，按住直到出現「選擇硬碟的畫面」為止。
* 進入安全模式
    * 關機時按下電源鍵，且立即按住鍵盤上的 Shift 鍵，按住直到出現「登入畫面」為止。
* 驗證是否在安全模式
    * 點選 左上方的蘋果圖案 -> 關於這台 Mac -> 系統報告 -> 軟體，然後檢查「開機模式」。
    * 為「安全」表示在安全模式，為「正常」則是正常開機。
* 以目標磁碟模式啟動( 把 Mac 當成 Thunderbolt 外接硬碟用 ) 
    * 關機時按下電源鍵，且立即按住鍵盤上的 T 鍵，按住直到出現『 Thunderbolt 的畫面』為止。
* 進入 Single-User 模式
    * 關機時按下電源鍵，且立即按住鍵盤上的 S 鍵，持續按住直到出現登入畫面為止。
    * 僅支援到 High Sierra (10.13) 版本，目前最新的 Mojave (10.14) 不支援。
* 重置 Mac 上的 NVRAM 或 PRAM (通常用於電腦操作有非預期的反應但又不像整台壞掉)
    * 關機時按下電源鍵，且立即按住 Option、Command、P 和 R 不放。
    * 放手時機為「按住超過 30 秒」或是「螢幕閃爍超過三次」或是「電腦發出開機聲超過三次」。
* 重置 Mac 上的系統管理控制器（SMC）(通常用於外接各種設備異常時或是異常燙、異常耗電這種非直觀的異常)
    * 請直接參考[官方最新版文件](https://support.apple.com/zh-tw/HT201295)，因為每款機型操作方式都不同。

</br>

##### 實用經驗

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
    * 這時候把『啟系統偏好設定』整個關掉再打開就會可以進入 使用者群組 了。當進去後請記得給該網域帳戶 Mobile Account 的權限。


</br>

* 檢查自己目前安裝的 macOS 軟體是不是 intel only
    * https://github.com/DigiDNA/Silicon


</br>

* 在 macOS 上重建損壞的分割區 （請看 Method 2）
    * https://www.macgasm.net/data-recovery/mac-partition-recovery/