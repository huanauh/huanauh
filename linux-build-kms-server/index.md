# Linux 搭建 KMS 服务器教程

以下教程以 CentOS 7 为例。
### 软件下载
vlmcsd 软件 [Github下载](https://github.com/sunflyer/vlmcsd)，下载后自行编译。嫌麻烦的，可以从 GitHub 页面的链接进入作者的论坛发布页面，下载编译好的二进制文件。
下载好后解压，找到`\binaries\Linux\intel\glibc`目录下的 vlmcsd-x64-glibc 文件（如果是32位系统则使用 vlmcsd-x86-glibc），并改名为 kms-server。
### 开始搭建
将 kms-server 放置在`/root`目录下，添加可执行权限
```bash
$ chmod +x kms-server
```
运行软件
```bash
$ ./kms-server
```
查看进程
```bash
$ ps aux|grep kms-server
```
开放端口
```bash
$ firewall-cmd --zone=public --add-port=1688/tcp --permanent
```
设置开机启动，在`/etc/rc.d/rc.local`文件中，添加
```bash
/root/kms-server
```
