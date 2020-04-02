# KMS 激活 Windows 与 Office

### 查看激活状态
#### 查看 Office 激活状态：
```
$ cscript.exe "C:\Program Files\Microsoft Office\Office14\OSPP.VBS" /dstatus
```
#### 查看 Windows 激活状态：
```
$ slmgr.vbs -dlv
```
### 激活方法
#### Windows 激活
```
$ slmgr.vbs -upk  #卸载密钥
$ slmgr /ipk xxxx-xxxx-xxxx-xxxx  #对应版本密钥
$ slmgr /skms 0.0.0.0  #激活服务器域名或 IP
$ slmgr /ato
$ slmgr /dli
```
#### Office 激活
```
$ cd C:\Program Files\Microsoft Office\Office14  #实际 Office 安装目录
$ CSCRIPT OSPP.VBS /SETHST:0.0.0.0  #激活服务器域名或 IP
$ CSCRIPT OSPP.VBS /ACT
$ CSCRIPT OSPP.VBS /DSTATUS
```
### 密钥对照表

| 操作系统 | KMS 激活序列号 |
| --- | --- |
| Windows 10 Professional | W269N-WFGWX-YVC9B-4J6C9-T83GX |
| Windows 10 Enterprise | NPPR9-FWDCX-D2C8J-H872K-2YT43 |
| Windows 10 Enterprise 2016 LTSB | DCPHK-NFMTC-H88MJ-PFHPY-QJ4BJ |
| Windows 7 Professional | FJ82H-XT6CR-J8D7P-XQJJ2-GPDD4 |