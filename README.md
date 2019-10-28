# Liunx-SCP-transmission
```
scp -P 12345 /data/wwwroot/www.wzfou.com/ root@198.xxx.xxx.xxx:/data/wwwroot/www.wzfou.net/
```
```
-P 12345 表示B主机的SSH不是默认的端口22。
上面的命令就是将A主机下的/data/wwwroot/www.wzfou.com/所有文件复制到B主机/data/wwwroot/www.wzfou.net/下
```
如果两个VPS主机在同一个内网，你可以将IP地址改成内网IP，这样传输速度将更快，因此特别适合大型网站搬家和大数据文件迁移服务器使用。
