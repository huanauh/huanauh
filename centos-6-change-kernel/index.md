# CentOS 6 更换内核

### 查看 CentOS 版本
```bash
$ cat /etc/issue
```
### 查看内核版本
```bash
$ uname -a
```
### 下载需要更换的内核
```bash
$ wget http://ftp.scientificlinux.org/linux/scientific/6.6/x86_64/updates/security/kernel-2.6.32-504.3.3.el6.x86_64.rpm
```
### 安装内核
```bash
$ rpm -ivh kernel-2.6.32-504.3.3.el6.x86_64.rpm --force
```
### 重启
```bash
$ reboot
```
