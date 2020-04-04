# Android 开启 Telnet 服务

### 前提条件
1.需要 Root
2.安装 Busybox
3.安装终端模拟器
### 开启服务器
在终端模拟器执行
```shell
$ su
$ telnetd -l /system/bin/sh
```
即可开启 telnet 服务器。
### 关闭服务器
执行
```shell
$ ps
```
找到`COMMAND`是`telnetd -l /system/bin/sh`的进程的 pid，然后执行
```shell
$ kill pid
```
即可终止服务器。
