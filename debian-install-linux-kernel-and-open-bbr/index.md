# Debian 手动安装 Linux 4.9+ 内核并开启 BBR

### 安装内核
选择需要安装的内核版本[下载地址](http://kernel.ubuntu.com/~kernel-ppa/mainline)
下载内核（以 Linux 4.9.0 内核为例）
```
$ wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.9/linux-image-4.9.0-040900-generic_4.9.0-040900.201612111631_amd64.deb
```
安装内核
```
$ dpkg -i linux-image-4.*.deb
```
移除旧内核（可选）
```
$ apt-get autoremove
```
更新引导文件
```
$ update-grub
```
重启
```
$ reboot
```
### 开启 BBR
查看内核
```
$ uname -r 
```
查看 BBR 是否开启
```
$ lsmod | grep bbr
```
如果结果中没有`tcp_bbr`的话。执行
```
$ modprobe tcp_bbr
$ echo "tcp_bbr" >> /etc/modules-load.d/modules.conf
$ echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
$ echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
$ sysctl -p
```
检查是否开启 BBR
```
$ sysctl net.ipv4.tcp_available_congestion_control
$ sysctl net.ipv4.tcp_congestion_control
```
如果结果都有`bbr`, 则内核已开启 BBR。
重启
```
$ reboot
```
