# Lighttpd 下 Typecho 伪静态设置

编辑`lighttpd.conf`文件，添加以下内容
```
#pseudo static
url.rewrite = (
"^/(admin|usr)/(.*)"  => "/$1/$2",
"^/(.*).html$" => "/index.php/$1.html",
"^/archives/(.*)" => "/index.php/archives/$1",
"^/category/(.*)" => "/index.php/category/$1",
"^/([0-9]+)/([0-9]+)/$" => "/index.php/$1/$2/",
"^/tag/(.*)/$" => "/index.php/tag/$1",
"^/search/(.*)/$" => "/index.php/search/$1",
"^/(.*)page/(.*)" => "/index.php/$1page/$2",
"^/(feed.*)" => "/index.php/$1",
"^/action/(.*)" => "/index.php/action/$1",
"^/(.*)comment" => "/index.php/$1/comment"
)
```
即可。
