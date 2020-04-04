# 修复 LookingGlass 在 PHP7 上无法使用的问题

LookingGlass 在 PHP7 环境无法使用，解决方案如下：
在根目录下`ajax.php`文件中找到以下内容
```php
// execute command
$output = $lg->$_GET['cmd']($_GET['host']);
```
修改为
```php
// execute command
$output = $lg->{$_GET['cmd']}($_GET['host']);
```
即可。
