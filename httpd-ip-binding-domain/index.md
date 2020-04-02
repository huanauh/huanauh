# LAMP IP 绑定域名

在 LAMP 添加的第一个网站根目录下`.htaccess`文件里添加：
```
RewriteCond %{http_host} ^0.0.0.0 [NC]
RewriteRule ^(.*)$ http://www.examples.com/$1 [R=301,L]
```
注意：`0.0.0.0`换成服务器的IP；`www.examples.com`更换为需要绑定的域名。
