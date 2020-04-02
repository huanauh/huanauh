# Linux 修改时区的方法

### 查看时区
```
$ date -R
```
### 调整时区
```
$ tzselect  #根据提示选择时区
```
### 复制文件
```
$ cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```
### 更新时间
```
$ ntpdate time.windows.com
```
