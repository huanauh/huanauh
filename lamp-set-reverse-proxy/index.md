# LAMP 设置反向代理

举例说明，将 1.test.com 和 2.test.com 两个域名通过反向代理指向 localhost:8080 端口
首先在 LAMP 添加任意域名，假设为 0.test.com
修改`/usr/local/apache/conf/vhost`目录下`0.test.com.conf`的配置文件，将文件修改为
```
<VirtualHost *:80>
ServerAdmin mail@mail.com
ServerName 0.test.com
ServerAlias 1.test.com 2.test.com
ProxyPreserveHost On
ProxyPass / http://localhost:8088/
ProxyPassReverse / http://localhost:8088/
</VirtualHost>
```
即可。
