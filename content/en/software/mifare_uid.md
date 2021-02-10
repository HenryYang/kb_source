---
title: "Tricky for Mifare Classic / Mifare Classic 的冷知識"
date: "2020-10-27"
---

##### Tools

* [MIFARE Classic Tool](https://play.google.com/store/apps/details?id=de.syss.MifareClassicTool) - 用來讀取與編輯 Mifare Classic 卡
* [NFC TagInfo](https://play.google.com/store/apps/details?id=at.mroland.android.apps.nfctaginfo) - 用來識別 RFID 卡片的類型與 UID 相關資訊
* [Mifare Calculator](https://play.google.com/store/apps/details?id=cc.yuyeye.mcalc) - Mifare 卡較驗碼的計算

##### Servies

* [XOR Calculator](https://toolslick.com/math/bitwise/xor-calculator)
* [Mifare Classic UID BCC Calculator](https://nric.biz/mifare-bcc-calculator.html)


##### Notes

* Sector0 Block0 前 4 Byte 放置了該張卡的 UID，第 5 Byte 是校驗碼，為前 4 個 Byte XOR 的結果
* 假設 UID 為 DDCCBBAA 那這時候要解讀回 10 進位就是變成 (AABBCCDD)hex = 2864434397 (如果長度不足十位則前面補 0 )


[參考資料](https://notes.andywu.tw/2018/%E8%A4%87%E8%A3%BD%E4%B8%80%E5%BC%B5%E5%AE%BF%E8%88%8D%E9%96%80%E7%A6%81%E5%8D%A1%E4%BA%8C-mifare-one-%E5%84%B2%E5%AD%98%E7%B5%90%E6%A7%8B/)

