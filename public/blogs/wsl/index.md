```c
#列出当前的Lnux
wsl --list  --verbose

#列出当前可安装的Linux
wsl --list --online

#关机所有分发
wsl --shutdown
#关机指定linux
wsl -t Ubuntu-24.04
#启动
wsl -d  Ubuntu-24.04
#在用户主目录中启动
wsl ~

#更新wsl
wsl --update

#查看当前WSL的状态
wsl --status

#wsl的版本
wsl --version

#查看运行中的Linux
wsl -l --running

#备份
wsl --export Ubuntu-24.04 D:\temp\Ubuntu-24.04.tar

#还原
wsl --import Ubuntu-24.04 C:\WSL D:\temp\Ubuntu-24.04.tar

#注销原有的linux系统
wsl --unregister Ubuntu-20.04

#修改默认用户（因为不修改用户名，打开wsl ubuntu之后，默认以root身份登录。）
ubuntu.exe config --default-user <--用户名-->
```


```
当前开机后无法分开

报错：
C:\Users\bhw>wsl -d Ubuntu-24.04 nsenter: failed to parse pid: '1282 1283'报错
```
这个错误是因为 WSL 试图解析进程 ID 时，`nsenter` 收到了多个 PID（1282 和 1283），导致无法正常工作。
可以先关闭wsl，然后再重启
```
wsl --shutdown
wsl.exe -d Ubuntu-24.04
```