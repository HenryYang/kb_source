---
title: "CLI command / 常見 CLI 指令 "
date: "2020-07-07"
---

### Let's Encrypt

安裝指令
```shell
# For macOS
$ brew install letsencrypt

# For Ubuntu
$ apt install certbot
```

</br>

手動產生憑證（可用於驗證 Private IP 或無法安裝 agent 的主機上）
```shell
$ certbot certonly --manual --config-dir ~/Desktop/letsencrypt --work-dir ~/Desktop/letsencrypt --logs-dir ~/Desktop/letsencrypt --preferred-challenges dns
```

</br>

自動產生憑證（用於外網可以直接連線到 agent 的主機上）
```shell
$ certbot certonly --standalone -n --agree-tos --email 你的電子信箱 --preferred-challenges http -d 你的網域
```

</br>

### 關閉 SSH 密碼登入

```shell
# /etc/ssh/sshd_config

PasswordAuthentication no
ChallengeResponseAuthentication no
UsePAM no
```

</br>

### ESXi 重起管理服務

```shell
/etc/init.d/hostd restart
/etc/init.d/vpxa restart
```


</br>

### Docker 清理
```shell
$ docker system prune -a
$ docker image prune -a
```

</br>

### Openssl 相關指令
* https://ssorc.tw/42/

</br>

### 用 ffmpeg 合併影片
```shell
#clips.txt
file 'first.mp4'
file 'second.mp4'
...
```

```shell
ffmpeg -f concat -i clips.txt -c copy output.mp4
```

</br>

### 掛載 NFS 磁碟
```shell
#掛載
sudo mount -t nfs 192.168.1.21:/DATA   /Users/henryyang/Desktop/NAS_DATA
#ESXi 掛載
esxcfg-nas -a -o 1192.168.1.21 -s /DATA NAS_DATA
```


</br>


### 用 wget 砍站
```shell
#完整指令
wget --mirror --page-requisites --convert-links --directory-prefix ./  https://example.com/
#簡寫指令
wget -mpkP ./  https://example.com/
```


</br>


### 刪除 Gitlab Rack Attack Ban 的 IP
```shell
#查目前所被 Ban 的 IP
grep "Rack_Attack" /var/log/gitlab/gitlab-rails/auth.log

#進入 Redius 刪除該 IP
/opt/gitlab/embedded/bin/redis-cli -s /var/opt/gitlab/redis/redis.socket
del cache:gitlab:rack::attack:allow2ban:ban:<ip>
```

參考資料：https://docs.gitlab.com/ee/security/rack_attack.html


</br>

### Firefox 開啟強制 https 模式

```
偏好設定 -> 隱私權與安全性 -> 純 HTTPS 模式 -> 在所有視窗都開啟純 HTTPS 模式
```