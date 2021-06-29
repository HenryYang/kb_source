---
title: "iOS Tips / iOS 小技巧"
date: "2020-07-07"
---

#### 隨機化 iOS 14 的 Mac Address
* [https://support.apple.com/zh-tw/HT211227](https://support.apple.com/zh-tw/HT211227)

</br>

#### 舊版 iTunes 12.6.5 下載（還可以載 .ipa 的版本）
* https://support.apple.com/en-us/HT208079

</br>

#### iOS App 版本號對應 ID 查詢
* https://tools.lancely.tech/apple/app-search


</br>

#### 停用 Finder 提示通知的 iOS Update
```shell
# 雖然 10.15 後沒有 iTunes 但還是用這服務來看設定值 （要重開機）
defaults write com.apple.itunes disableCheckForDeviceUpdates -bool YES
```