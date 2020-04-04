# V2Ray 流量转发配置

### Caddy 配置
修改`Caddyfile`文件
```json
yourdomian.com {
  tls youremail@gmail.com
  proxy /www localhost:8990 {
    websocket
    header_upstream -Origin
  }
}
```
### Apache 配置一
编辑`/usr/local/apache/conf/vhost`目录下`yourdomian.com.conf`文件，将 443 端口配置修改为
```html
<VirtualHost *:443>
    ServerAdmin youremail@gmail.com
    ServerName yourdomian.com
    ServerAlias yourdomian.com
    SSLEngine On
    RewriteEngine On
    RewriteCond %{HTTP:Upgrade} =websocket [NC]
    RewriteRule /(.*)           ws://localhost:8990/$1 [P,L]
    RewriteCond %{HTTP:Upgrade} !=websocket [NC]
    RewriteRule /(.*)           http://localhost:8990/$1 [P,L]
    SSLProxyEngine On
    Proxypass /www http://127.0.0.1:8990
    ProxyPassReverse /www http://127.0.0.1:8990
    SSLCertificateFile /etc/letsencrypt/live/yourdomian.com/fullchain.pem
    SSLCertificateKeyFile /etc/letsencrypt/live/yourdomian.com/privkey.pem
 </VirtualHost>
```
以上配置会造成 https 网页无法正常访问。建议使用下面配置二。
### Apache 配置二
同配置一，编辑`yourdomian.com.conf`文件。在原配置文件内容不变的情况下，在 443 端口配置中添加以下内容
```html
<LocationMatch "/www">
    ProxyPass ws://127.0.0.1:8990/www upgrade=WebSocket
    ProxyAddHeaders Off
    ProxyPreserveHost On
    RequestHeader set Host %{HTTP_HOST}s
    RequestHeader set X-Forwarded-For %{REMOTE_ADDR}s
</LocationMatch>
```
该配置可以同时兼顾 https 网页访问和 websocket 流量转发。

注意事项：
Apache 依赖以下几个 mods

- mod_ssl
- mod_proxy
- mod_proxy_wstunnel

打开`/usr/local/apache/conf/httpd.conf`文件，搜索相应关键字，取消对应行注释后重启 Apache 即可。
