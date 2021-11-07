---
title: "Android adb Tips / Android adb 相關資訊"
date: "2020-10-27"
---

##### adb 最新版下載位置

* Windows 版本：[https://dl.google.com/android/repository/platform-tools-latest-windows.zip](https://dl.google.com/android/repository/platform-tools-latest-windows.zip)
* Mac 版本：[https://dl.google.com/android/repository/platform-tools-latest-darwin.zip](https://dl.google.com/android/repository/platform-tools-latest-darwin.zip)
* Linux 版本：[https://dl.google.com/android/repository/platform-tools-latest-linux.zip](https://dl.google.com/android/repository/platform-tools-latest-linux.zip)

</br>

##### 常用指令
* [adb 常用命令大全](https://juejin.im/post/6844904030016110606)



##### 透過 adb CLI 來開啟 App 指定畫面

```shell
# 範例 開啟 Google Play 
adb.exe shell am start -n com.android.vending/com.google.android.finsky.activities.MainActivity

# 範例 開啟 My App Share
adb.exe shell am start -n com.yschi.MyAppSharer/com.yschi.MyAppSharer.MyAppSharer
```

##### 找出目前 Android 設備上畫面所屬的 App Activity 名稱

```shell
# For Mac/Linux
adb shell dumpsys window | grep -E 'mCurrentFocus' 

# For Windows:
adb shell dumpsys window | find "mCurrentFocus"
```

[參考資料](https://support.testsigma.com/support/solutions/articles/32000019977-how-to-find-app-package-and-app-activity-of-your-android-app)