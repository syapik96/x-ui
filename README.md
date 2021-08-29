# x-ui
Support multi-protocol and multi-user xray panel

# Features
-System status monitoring
-Support multi-user and multi-protocol, web page visualization operation
-Supported protocols: vmess, vless, trojan, shadowsocks, dokodemo-door, socks, http
-Support to configure more transmission configurations
-Traffic statistics, limit traffic, limit expiration time
-Customizable xray configuration template
-Support https access panel (bring your own domain name + ssl certificate)
-More advanced configuration items, see the panel for details

# Installation & Upgrade
```
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

## Manual installation & upgrade
1. First download the latest compressed package from https://github.com/vaxilu/x-ui/releases, generally choose the `amd64` architecture
2. Then upload the compressed package to the `/root/` directory of the server, and use the `root` user to log in to the server

> If your server cpu architecture is not `amd64`, replace `amd64` in the command with another architecture

```
cd /root/
rm x-ui/ /usr/local/x-ui/ /usr/bin/x-ui -rf
tar zxvf x-ui-linux-amd64.tar.gz
chmod +x x-ui/x-ui x-ui/bin/xray-linux-* x-ui/x-ui.sh
cp x-ui/x-ui.sh /usr/bin/x-ui
cp -f x-ui/x-ui.service /etc/systemd/system/
mv x-ui/ /usr/local/
systemctl daemon-reload
systemctl enable x-ui
systemctl restart x-ui
```

## Suggestion System
- CentOS 7+
- Ubuntu 16+
- Debian 8+

# common problem
## Relationship with v2-ui
x-ui is equivalent to an enhanced version of v2-ui, and more features will be added in the future. After the x-ui function is stable, v2-ui will no longer provide updates

x-ui can coexist with v2-ui, the data is not interoperable, and does not affect the operation of the other party

## 从 v2-ui 迁移
首先在安装了 v2-ui 的服务器上安装最新版 x-ui，然后使用以下命令进行迁移，将迁移本机 v2-ui 的`所有 inbound 账号数据`至 x-ui，`面板设置和用户名密码不会迁移`
> 迁移成功后请`关闭 v2-ui` 并且`重启 x-ui`，否则 v2-ui 的 inbound 会与 x-ui 的 inbound 会产生`端口冲突`
```
x-ui v2-ui
```

## Stargazers over time

[![Stargazers over time](https://starchart.cc/vaxilu/x-ui.svg)](https://starchart.cc/vaxilu/x-ui)
