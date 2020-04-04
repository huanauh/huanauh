# Crontab 的安装及使用

### 安装 crontab
```bash
$ yum install vixie-cron crontabs
```
### 添加开机启动
```bash
$ chkconfig –level 35 crond on
```
### crontab 文件位置（root）
```bash
/var/spool/cron/root
```
### 查看 corntab 服务状态
```bash
$ service crond status
```
### 启动 corntab 服务
```bash
$ service crond start
```
### 查看 crontab 列表
```bash
$ crontab -l
```
### 编辑 crontab
```bash
$ crontab -e
```
