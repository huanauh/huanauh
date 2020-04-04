# Windows 查看设备管理器所有设备

进入命令提示符执行
```cmd
$ set devmgr_show_nonpresent_devices=1
```
然后执行
```cmd
$ Start DEVMGMT.MSC
```
即可进入设备管理，点击顶部菜单`查看`勾选`显示隐藏的设备`即可查看全部设备。
### 附：解决网络连接无法重命名的问题。
#### 方法一：
按以上方法进入设备管理器，删除相应的灰色的同名称网卡（后缀一般为 #2，#3 之类）驱动，重启后即可重命名网络连接名称。
#### 方法二：
进入注册表编辑器，定位到
```
HKEY_LOCAL_MCHINE\SYSTEM\CurrentControlSet\Control\Network\{4D36E972-E325-11CE-BFC1-08002BE10318}
```
该目录下有多个目录，除`Descriptions`目录外其他均为网卡配置。每个网卡配置目录内均有`Connection`目录，选中`Connection`目录即可查看具体内容。依据实际情况可进行相应删除。
