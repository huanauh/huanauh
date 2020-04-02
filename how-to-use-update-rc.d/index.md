# Update-rc.d 命令的用法

### 添加启动项
将脚本放入`/etc/init.d`文件夹，并给予可执行权限
```
$ mv xx.sh /etc/init.d
$ chmod +x  /etc/init.d/xx.sh
```
### 设置开机自启
```
$ update-rc.d xx.sh defaults
```
### 删除开机自启
```
$ update-rc.d -f xx.sh remove
```
