# Liunx-command
```
scp -P 12345 /data/wwwroot/www.wzfou.com/ root@198.xxx.xxx.xxx:/data/wwwroot/www.wzfou.net/
```
```
-P 12345 表示B主机的SSH不是默认的端口22。
上面的命令就是将A主机下的/data/wwwroot/www.wzfou.com/所有文件复制到B主机/data/wwwroot/www.wzfou.net/下
```
如果两个VPS主机在同一个内网，你可以将IP地址改成内网IP，这样传输速度将更快，因此特别适合大型网站搬家和大数据文件迁移服务器使用。




# AWS开root权限代码

##创建instance时,点击add launch script,将下列代码复制进去(注意更改root密码).

##对于EC2,GCE等机器也可以使用. 不能添加代码的机器,可以登录进ssh,再执行上面的代码. 也可以开启root登陆
```
#!/bin/bash
echo root:7758521kkk |sudo chpasswd root
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo reboot
```
