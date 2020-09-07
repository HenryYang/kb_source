---
title: "Cool Tips for PC  / 各種無法歸類的冷門指令"
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
