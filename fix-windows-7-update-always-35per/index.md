# Windows 7 更新配置卡 35% 的解决方案

进入 PE ，打开命令提示符
```cmd
$ DISM /Image:X:\ /Cleanup-Image /RevertPendingActions
```
`X`改为系统的实际盘符。
