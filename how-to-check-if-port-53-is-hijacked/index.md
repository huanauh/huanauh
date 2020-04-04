# DNS 53 端口被劫持的判断方法

### Windows 系统
在命令提示符中运行
```cmd
$ nslookup dnscheck.not-available-sub.sgfu.org
```
非权威应答中 Address 如为123.45.67.89则未被劫持，如为127.0.0.1则被劫持。
### Linux 系统
在终端中运行
```bash
$ dig dnscheck.not-available-sub.sgfu.org a
```
