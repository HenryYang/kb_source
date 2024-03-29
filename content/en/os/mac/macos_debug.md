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


##### iCloud 同步問題處理

* 解決一直卡在上傳的狀態
```shell
# 停用服務
$ killall bird

# 刪除同步的暫存檔，完成後請重開機
$ cd ~/Library/Application\ Support
$ rm -rf CloudDocs
```

* 解決部分檔案下載不下來（好發在大型檔案）

```shell
# 找尋檔案清單
$ find . -name '.*icloud'

# 強迫下載檔案回來
$ find . -name '.*icloud' | perl -pe 's|(.*)/.(.*).icloud|$1/$2|s' | while read file; do brctl download "$file"; done
```

[參考資料](https://www.facebook.com/htlin.lizard/posts/pfbid025u4jnAcDys9faxKbS2gY6HNaAWnBEww5EMoCMwHGnqtkt2UH45GxzqjG7EshAw7Fl)