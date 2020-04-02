# CentOS 6 更换内核

### 查看 CentOS 版本
```
$ cat /etc/issue
```
### 查看内核版本
```
$ uname -a
```
### 下载需要更换的内核
```
$ wget http://ftp.scientificlinux.org/linux/scientific/6.6/x86_64/updates/security/kernel-2.6.32-504.3.3.el6.x86_64.rpm
```
### 安装内核
```
$ rpm -ivh kernel-2.6.32-504.3.3.el6.x86_64.rpm --force
```
### 重启
```
$ reboot
```
