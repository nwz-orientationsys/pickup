## GIT 个人信息设置

<br />

* Git用户名配置
```
git config user.name #命令查看自己当前git用户名
git config --global user.name ‘yourname’ #配置用户名
```

<br />

* Git邮箱配置
```
git config user.email #查看当前邮箱
git config --global user.email ‘youremail’ #配置邮箱
```


## GIT 保存用户名密码

在终端输入：

```
git config --global credential.helper store
```

然后git pull一次，输入一次用户名密码就会自动保存该用户名密码；

查看配置的用户信息：

git config --list
