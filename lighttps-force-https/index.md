# Lighttpd 强制 Https 访问

编辑`lighttpd.conf`文件，添加以下内容
```html
#force https
$SERVER["socket"] == ":80" {
    $HTTP["host"] =~ "([^:/]+)" {
        url.redirect = ( "^/(.*)" => "https://%0:443/$1" )
    }
}
```
即可。
