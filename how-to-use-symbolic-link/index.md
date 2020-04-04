# 如何使用符号链接

### 使用缘由
Windows 电脑上有多个硬盘分区，但文件服务器又不支持虚拟目录，所以跨硬盘分区分享文件不太好操作。使用符号链接能方便的解决这个问题。
### 使用方法
以管理员身份运行`cmd`
假设服务器目录为`www`，位于`c:\www`
1、将整个`d`盘链接过来
```cmd
$ mklink /d c:\www\disk_d d:\
```
2、将`d`盘的`folder`目录链接过来
```cmd
$ mklink /d c:\www\folder d:\folder
```
