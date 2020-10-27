---
title: "Windows Essential App & Tips / Windows 常見軟體與小技巧"
date: "2020-07-07"
---

#### 開啟虛擬化 (WSL2 需要)
```shell
bcdedit /set hypervisorlaunchtype auto
```

#### 關於靜態路由
```shell
# 顯示目前路由表
route print

# 刪除全部路由表
route -f
```
