# LAMP 禁止 IP 直接访问

针对开启了虚拟主机的 LAMP，修改`conf/extra/httpd-vhosts.conf`文件，添加以下内容：
```html
<virtualhost 1.1.1.1:80>  #1.1.1.1为你的 IP
ServerName 1.1.1.1
<Directory />
    Order Allow,Deny
    Deny from all
</Directory>
</VirtualHost>
```
没有开启虚拟主机的 LAMP 直接修改`httpd.conf`文件。
需要注意的是，原`.conf`文件中的`ServerName`或`ServerAlias`项要修改你的域名，保证你的域名可以正常访问。
