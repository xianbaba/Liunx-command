# Liunx-command

## SCP命令
```
scp -P 12345 /data/wwwroot/www.wzfou.com/ root@198.xxx.xxx.xxx:/data/wwwroot/www.wzfou.net/
```
```
-P 12345 表示B主机的SSH不是默认的端口22。
上面的命令就是将A主机下的/data/wwwroot/www.wzfou.com/所有文件复制到B主机/data/wwwroot/www.wzfou.net/下
```
如果两个VPS主机在同一个内网，你可以将IP地址改成内网IP，这样传输速度将更快，因此特别适合大型网站搬家和大数据文件迁移服务器使用。

## rsync命令
### 数据同步方式
#### 从主机拉数据
##### 备机上启动的流程
同步命令：
```
rsync -avzP --delete root@{remoteHost}:{remoteDir} {localDir}
```
参数说明：

-a 参数，相当于-rlptgoD（-r 是递归 -l 是链接文件，意思是拷贝链接文件；-p 表示保持文件原有权限；-t 保持文件原有时间；-g 保持文件原有用户组；-o 保持文件原有属主；-D 相当于块设备文件）；
-z 传输时压缩；
-P 传输进度；
-v 传输时的进度等信息；

示例：
```
rsync -avzP --delete root@192.168.1.100:/www/wwwroot/www.026xs.com
```
#### 向备机推数据
##### 主机上启动的流程

同步命令：
```
rsync -avzP --delete {localDir} root@{remoteHost}:{remoteDir}
```
示例：
```
rsync -avzP --delete /www/wwwroot/www.026xs.com root@192.168.1.101:/www/wwwroot
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
