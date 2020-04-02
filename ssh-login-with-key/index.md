# SSH 使用密钥登录并禁止密码登录

### 设置权限
修改`.ssh`目录及`authorized_keys`文件权限
```
$ chmod 700 ~/.ssh
$ chmod 600 ~/.ssh/authorized_keys
```
### 编辑文件
将`/etc/ssh/sshd_config`文件中`PasswordAuthentication`项，由`yes`改为`no`。
