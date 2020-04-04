# Debian 安装配置 iptables 防火墙

### 查看规则
```bash
$ iptables -L
```
### 编辑规则
```bash
$ vim /etc/iptables.test.rules
```
### 使规则生效
```bash
$ iptables-restore < /etc/iptables.test.rules
```
### 保存生效配置
```bash
$ iptables-save > /etc/iptables.up.rules
```
### 设置开机自动载入配置
```bash
$ touch /etc/network/if-pre-up.d/iptables
```
#### 在 iptables 文件中输入以下内容
```shell
#!/bin/bash
/sbin/iptables-restore < /etc/iptables.up.rules
```
#### 设置执行仅限
```bash
$ chmod +x /etc/network/if-pre-up.d/iptables
```
