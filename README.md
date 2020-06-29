# Liunx-command

## shadowsocks-all.sh
- 自动安装CentOS / Debian / Ubuntu的Shadowsocks服务器（所有版本）
```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/xianbaba/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```
## Linux-NetSpeed
```
wget -N --no-check-certificate "https://raw.githubusercontent.com/xianbaba/Linux-NetSpeed/master/tcp.sh"
chmod +x tcp.sh
./tcp.sh
```

# serverspeeder锐速一键破解安装版

## 锐速破解版安装方法：
```
   wget -N --no-check-certificate https://github.com/xianbaba/serverspeeder/raw/master/serverspeeder.sh && bash serverspeeder.sh
```
## 锐速破解版卸载方法：
```
    chattr -i /serverspeeder/etc/apx* && /serverspeeder/bin/serverSpeeder.sh uninstall -f
```

## AWS开root权限代码
```
#!/bin/bash
echo root:7758521kkk |sudo chpasswd root
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo reboot
```
## 常用screen参数
```
screen -S yourname      -> 新建一个叫yourname的session
screen -ls              -> 列出当前所有的session
screen -r yourname      -> 回到yourname这个session
screen -d yourname      -> 远程detach某个session
screen -d -r yourname   -> 结束当前session并回到yourname这个session
```
