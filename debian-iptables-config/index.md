# Debian 安装配置 iptables 防火墙

### 查看规则
```
$ iptables -L
```
### 编辑规则
```
$ vim /etc/iptables.test.rules
```
### 使规则生效
```
$ iptables-restore < /etc/iptables.test.rules
```
### 保存生效配置
```
$ iptables-save > /etc/iptables.up.rules
```
### 设置开机自动载入配置
```
$ touch /etc/network/if-pre-up.d/iptables
```
#### 在 iptables 文件中输入以下内容
```
#!/bin/bash
/sbin/iptables-restore < /etc/iptables.up.rules
```
#### 设置执行仅限
```
$ chmod +x /etc/network/if-pre-up.d/iptables
```
