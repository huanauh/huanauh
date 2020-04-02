# Teredo Tunneling Adapter 驱动黄色叹号解决方法

打开`注册表编辑器`，定位到
```
HKEY_LOCAL_MACHINE\SYSTEM\CURRENTCONTROLSET\SERVICES\TCPIP6\PARAMETERS
```
右键`Disabled Components`将值修改为`0`，重启电脑。
