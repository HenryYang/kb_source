---
title: "macOS CLI / macOS 指令"
date: "2020-07-07"
---

##### 顯示從 Keychain 匯出的 .p12 中的公私鑰

```shell
openssl pkcs12 -info -in INFILE.p12 -nodes
```

[憑證格式相關資訊](https://support.ssl.com/index.php?/Knowledgebase/Article/View/19/0/der-vs-crt-vs-cer-vs-pem-certificates-and-how-to-convert-them)

</br>


##### 在 CLI 匯入憑證到 Keychain

```shell
# 解鎖 Keychain
security unlock-keychain -p 電腦的密碼 ~/Library/Keychains/login.keychain-db

# 匯入公私鑰
security import 要匯入的憑證 -k ~/Library/Keychains/login.keychain-db
```

</br>

##### 手動安裝 Xcode

```shell
# 去 Apple Developer 網站下載 xip 格式的 Xcode (現在需要登入才能下載)
https://developer.apple.com/download/more/

# 使用 xip 指令直接安裝
xip -x ~/Download/Xcode_12.xip

```

</br>

##### 執行 macOS 取消到期通知指令

```shell
sudo defaults write /Library/Preferences/com.apple.loginwindow PasswordExpirationDays 0
```

</br>


##### 手動把帳戶加入 Mobile Account 方法

```shell
sudo /System/Library/CoreServices/ManagedClient.app/Contents/Resources/createmobileaccount -P -v -n 使用者帳戶
```

</br>


##### 手動更新 FileVault2 的開機解鎖密碼

```shell
sudo diskutil apfs changePassphrase disk1s1 -user $(sudo fdesetup list | grep id -un | awk -F',' '{print $2}')
```

</br>

##### macOS Network Location 設定檔存放位置
```shell
/Library/Preferences/SystemConfiguration/preferences.plist
```

</br>


##### 讓 Terminal 的 sudo 可以使用 Touch ID 驗證
```shell
#在 /etc/pam.d/sudo 裡面加上下面這一行
auth sufficient pam_tid.so
```

</br>

##### 重起 Touch Bar 的服務
```shell
sudo pkill TouchBarServer
sudo killall "ControlStrip"
```

</br>


##### 允許 macOS 安裝任何來源軟體（危險，風險自負）
```shell
sudo spctl --master-disable
```

</br>



##### 擴充（找回）未使用的硬碟空間

```shell
# 查看目前要擴充的磁碟代號
sudo diskutil list

# 先修復目標擴充的磁碟這邊以 disk0 為例
sudo diskutil repairDisk disk0

# 將 disk0s2 擴充成為 200GB 硬碟
sudo diskutil resizeVolume disk0s2 200G

# 如果是 AFPS 格式磁碟請改成下面指令
sudo diskutil apfs resizeContainer disk0s2 200G


```

</br>



##### 在根目錄建立超連結到其他路徑上

```shell
# 請參考 https://derflounder.wordpress.com/2020/01/18/creating-root-level-directories-and-symbolic-links-on-macos-catalina/
sudo nano /etc/synthetic.conf
# 然後該檔案請依照下面方式編輯，中間是 tab 不能是空白
# bar 那邊是預期的資料夾名稱，而 tab 後面則是路徑，記得第一個 / 不需要加
bar     System/Volumes/Data/bar
```
</br>

#####  製作 macOS Monterey 安裝隨身碟
```shell
sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/<隨身碟名稱>
```

[各版本指令與下載連結](https://support.apple.com/zh-tw/HT201372)


</br>

#####  解決 Mac AppStore 下載轉圈圈不停問題
```shell
kill -9 $(ps -A | grep appstoreagent | awk '{print $1}' | head -1)
```

</br>

#####  掛載 Ext4 磁碟
```shell
# 需要安裝軟體
brew install --cask osxfuse
brew install ext4fuse

# 查詢要掛載的磁碟所在分割區
diskutil list

# 掛載磁碟，以 disk3s1 為例，掛載到家目錄的 MY_DISK
sudo ext4fuse /dev/disk3s1 ~/MY_DISK -o allow_other
```

</br>

#####  解決 homebrew 找不到 Formulae 問題
```shell
rm -rf /usr/local/Homebrew/Library/Taps/homebrew/homebrew-core; brew update
```