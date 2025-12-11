---
title: "iOS 冷知識與實用網站"
date: "2025-10-01"
---

### 關於 ipa 部分

</br>

##### 舊版 iTunes 12.6.5 下載（還可以載 .ipa 的版本）
* https://support.apple.com/en-us/HT208079

##### 下載舊版的 .ipa 教學
* https://hiy.tw/2021/03/testflight_export_ipa/

##### 網路上找到的共用 Apple ID 服務 （請慎用
* https://pastebin.com/GACW3aC4

</br>

### 關於驗機、設備資訊

</br>

##### 中國知呼的 iPhone 驗機與注意事項
* https://www.zhihu.com/question/279981966/answer/1487316109

##### 中國知呼的 iPad 驗機與注意事項
* https://www.zhihu.com/question/282974354/answer/1453767111

##### 中國知呼的 AirPods 驗機與注意事項
* https://www.zhihu.com/question/279688500

##### 詳細 Apple 產品規格參數
* https://hubweb.cn

##### iOS 設備上直接查詢 UDiD 資訊 (需安裝網站方的描述檔)
* https://showmyudid.com/

##### 查詢設備啟用相關資訊 
* https://applesn.info/devices/  

##### iPhone 機型型號判斷
* `機型型號` 第一英文字代表是類別
    * 新機是 `M` 開頭
    * 官方認證整新品是 `F` 開頭 
    * 維修後換新品是 `N` 開頭
    * 有刻紋是 `P` 開頭
    * Apple Store 的 DEMO 機是 `3` 開頭
* `機型型號` 最尾在 `/` 前面的一或兩碼英文表示屬於哪邊所販售的
    * 台灣是 `TA`
    * 香港是 `ZP`
    * 日本是 `J`
    * 美國是 `LL`
    * 中國是 `CH`


</br>


### 工具類

</br>


##### 電腦批次下載 iCloud Photo 工具
* https://github.com/icloud-photos-downloader/icloud_photos_downloader

##### iDevice 各平台的 Beta 版描述檔
* https://betahub.cn/

##### 各版本的 ipsw 下載
* https://ipsw.me/


</br>

### 實用指令

</br>

##### 快速切換 App Store 顯示國家
* [美國](https://itunes.apple.com/WebObjects/MZStore.woa/wa/resetAndRedirect?dsf=143441&mt=8&url=/WebObjects/MZStore.woa/wa/viewSoftware?cc=us)
* [日本](https://itunes.apple.com/WebObjects/MZStore.woa/wa/resetAndRedirect?dsf=143462&mt=8&url=/WebObjects/MZStore.woa/wa/viewSoftware?cc=jp)
* [台灣](https://itunes.apple.com/WebObjects/MZStore.woa/wa/resetAndRedirect?dsf=143470&mt=8&url=/WebObjects/MZStore.woa/wa/viewSoftware?cc=tw)

[參考資料](http://switchr.imagility.io)、[參考資料](https://as.dogged.cn/)


##### 查詢 iPhone 手機訊號
```shell
# 先關閉 WiFi 後打開電話撥打下面號碼。
＊3001＃12345＃＊
```
[參考資料](https://mrmad.com.tw/iphone-ftm-dashboard)


##### 停用 Finder 提示通知的 iOS Update
```shell
# 雖然 10.15 後沒有 iTunes 但還是用這服務來看設定值 （要重開機）
defaults write com.apple.itunes disableCheckForDeviceUpdates -bool YES
```


</br>



### 冷知識

</br>

##### Apple ID 註冊國家注意事項

* 在中國大陸，新 Apple ID 必須為另一組（+86）行動電話號碼。 在印度，新 Apple ID 必須為另一組（+91）行動電話號碼。
    * 這意味一旦 Apple ID 帳戶歸屬到中國或是印度，裡面的手機號碼就只能綁定該國的手機號碼

[參考資料](https://support.apple.com/zh-tw/HT207944)

