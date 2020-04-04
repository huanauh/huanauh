# Termux 使用教程

### 安装部署
因为 Termux 官方服务器在国外，第一次打开可能需要科学上网
进入后更新一下
```bash
$ apt update
$ apt upgrade
```
安装nano编辑器
```bash
$ apt install nano  #非必须，我个人喜欢使用nano编辑器
```
因为官方源在国外，建议修改为国内中科大源
```bash
$ nano /data/data/com.termux/files/usr/etc/apt/sources.list
```
将`https://termux.net`替换成`https://mirrors.ustc.edu.cn/termux`，保存退出
换源以后，重新更新一下
```bash
$ apt update
$ apt upgrade
```
即可正常使用了。
### 使用技巧
开启外置存储权限
```bash
$ termux-setup-storage
```
常用快捷键
```
音量键↑ + Q 打开扩展功能键  #强烈建议打开
音量键↑ + W 上
音量键↑ + S 下
音量键↑ + A 左
音量键↑ + D 右
音量键↓ + C 取消
音量键↓ + L 清屏
```
