# Ubuntu 安装 Shadowsocks 教程

写在前面：建议直接使用网上各种一键脚本，本教程仅适用于 Python 版 Shadowsocks
### 安装 PIP
```
$ apt update
$ apt install python-pip
$ apt install python-setuptools m2crypto
```
### 安装 Shadowsocks
```
$ pip install shadowsocks
$ apt install shadowsocks
```
如果报错执行以下命令
```
$ python -m pip install --upgrade pip
```
### 配置参数
新建`/home/shadowsocks.json`文件，并键入以下内容
``` shell
{
"server":"11.22.33.44"  #服务器IP
"server_port":443  #服务端口
"local_port":1080  #本地端口
"password":"123456"  #密码
"timeout":300,  #超时设置
"method":"aes-256-cfb"  #加密方法
}
```
## 设置开机启动
在`/etc/rc.local`文件中添加
```
ssserver -c /home/shadowsocks.json -d start
```
