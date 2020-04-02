# 修复 LookingGlass 在 LAMP 上无法使用的问题

安装 LookingGlass 后发现 ping 和 mtr 等命令无法使用。发现是 PHP 的配置问题，解决方案如下：
编辑`/usr/local/php`目录下`php.ini`文件，找到
```
disable_functions = exec,system,dl,passthru,chown,shell_exec,popen,proc_open
```
将`proc_open`删掉，重启 Apache
```
$ /etc/init.d/httpd restart
```
即可。
