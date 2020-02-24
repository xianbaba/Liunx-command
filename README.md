# Liunx-command

## shadowsocks-all.sh
==================
- Auto Install Shadowsocks Server (all version) for CentOS/Debian/Ubuntu
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
## AWS开root权限代码

##### 创建instance时,点击add launch script,将下列代码复制进去(注意更改root密码).
##### 对于EC2,GCE等机器也可以使用. 不能添加代码的机器,可以登录进ssh,再执行上面的代码. 也可以开启root登陆
```
#!/bin/bash
echo root:7758521kkk |sudo chpasswd root
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo reboot
```

## Screen命令
### 常用screen参数
```
screen -S yourname      -> 新建一个叫yourname的session
screen -ls              -> 列出当前所有的session
screen -r yourname      -> 回到yourname这个session
screen -d yourname      -> 远程detach某个session
screen -d -r yourname   -> 结束当前session并回到yourname这个session
```
