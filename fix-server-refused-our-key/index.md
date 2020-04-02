# SSH 私钥登陆提示 Server refused our key 的解决办法

原因为`authorized_keys`文件没有 selinux 上下文属性，导致无法通过 selinux 认证。
执行以下命令：
```
$ restorecon -R -v /root
```
即可解决。
