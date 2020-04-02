# Crontab 的安装及使用

### 安装 crontab
```
$ yum install vixie-cron crontabs
```
### 添加开机启动
```
$ chkconfig –level 35 crond on
```
### crontab 文件位置（root）
```
/var/spool/cron/root
```
### 查看 corntab 服务状态
```
$ service crond status
```
### 启动 corntab 服务
```
$ service crond start
```
### 查看 crontab 列表
```
$ crontab -l
```
### 编辑 crontab
```
$ crontab -e
```
