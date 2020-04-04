# Linux 修改时区的方法

### 查看时区
```bash
$ date -R
```
### 调整时区
```bash
$ tzselect  #根据提示选择时区
```
### 复制文件
```bash
$ cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```
### 更新时间
```bash
$ ntpdate cn.ntp.org.cn
```
