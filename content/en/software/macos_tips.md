---
title: "MacOS Tips / MacOS 小技巧"
date: "2020-07-07"
---

## 顯示從 Keychain 匯出的 .p12 中的公私鑰

```shell
openssl pkcs12 -info -in INFILE.p12 -nodes
```

[憑證格式相關資訊](https://support.ssl.com/index.php?/Knowledgebase/Article/View/19/0/der-vs-crt-vs-cer-vs-pem-certificates-and-how-to-convert-them)

</br>


## 在 CLI 匯入憑證到 Keychain

```shell
# 解鎖 Keychain
security unlock-keychain -p 電腦的密碼 ~/Library/Keychains/login.keychain-db

# 匯入公私鑰
security import 要匯入的憑證 -k ~/Library/Keychains/login.keychain-db
```

</br>

## 手動安裝 Xcode

```shell
# 去 Apple Developer 網站下載 xip 格式的 Xcode (現在需要登入才能下載)
https://developer.apple.com/download/more/

# 使用 xip 指令直接安裝
xip -x ~/Download/Xcode_12.xip

```

</br>

## 執行 macOS 取消到期通知指令

```shell
sudo defaults write /Library/Preferences/com.apple.loginwindow PasswordExpirationDays 0
```

</br>


## 手動把帳戶加入 Mobile Account 方法

```shell
sudo /System/Library/CoreServices/ManagedClient.app/Contents/Resources/createmobileaccount -P -v -n 使用者帳戶
```

</br>


## 手動更新 FileVault2 的開機解鎖密碼

```shell
sudo diskutil apfs changePassphrase disk1s1 -user $(sudo fdesetup list | grep id -un | awk -F',' '{print $2}')
```

