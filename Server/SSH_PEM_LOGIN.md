如果要登录的服务器只允许pem认证

每次输入ssh -i xxxx.pem 用户@ip 地址  就很烦

这里有个一劳永逸的方法：

进入到自己的用户目录，例如/home/me

把pem文件放在当前目录

然后vi .ssh/config

内容如下
```
  Host *
      ServerAliveInterval 60
  Host denglu
      HostName 你的ip
      User mojie      
      IdentityFile    ~/.ssh/你的pem文件名.pem
```

保存后，更改权限：
```
-rw------- 1 me me 132 12月 18 10:55 .ssh/config
```

然后在当前目录/home/me下输入  
```
ssh denglu
```
即可登录到目标服务器。再也不用每次输入长长的命令了。

---------------------

本文来自 墨羯 的CSDN 博客 ，全文地址请点击：https://blog.csdn.net/jishan7/article/details/78904728?utm_source=copy 
