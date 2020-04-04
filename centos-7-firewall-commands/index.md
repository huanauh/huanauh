# CentOS 7 中 Firewall 相关命令

### 常用命令
#### 查看 firewall 状态
```bash
$ firewall-cmd --state
```
#### 查看 firewall 所有规则
```bash
$ firewall-cmd --list-all
```
#### 添加规则
```bash
$ firewall-cmd --permanent --add-port=80/tcp
$ firewall-cmd --permanent --add-port=80/udp
```
#### 删除规则
```bash
$ firewall-cmd --permanent --remove-port=80/tcp
$ firewall-cmd --permanent --remove-port=80/tcp
```
#### 重启防火墙(修改配置后要重启防火墙)
```bash
$ firewall-cmd --reload
```
### 高级命令
#### 禁止 firewall 开机启动
```bash
$ systemctl disable firewalld.service
```
#### 允许 firewall 开机启动
```bash
$ systemctl enable firewalld.service
```
#### 查看 firewall 服务状态
```bash
$ systemctl status firewalld
```
#### 重启 firewall 服务
```bash
$ service firewalld restart
```
#### 开启 firewall 服务
```bash
$ service firewalld start
```
#### 关闭 firewall 服务
```bash
$ service firewalld stop
```
