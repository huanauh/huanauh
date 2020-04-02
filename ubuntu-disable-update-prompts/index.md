# Ubuntu 禁止升级提示

### 禁用更新
修改`/etc/update-manager/release-upgrades`中的配置项`Prompt=lts`为`Prompt=never`
```
$ sed -i s/Prompt=lts/Prompt=never/g /etc/update-manager/release-upgrades
```
### 清除缓存
删除`/var/lib/ubuntu-release-upgrader/release-upgrade-available`文件
```
$ rm /var/lib/ubuntu-release-upgrader/release-upgrade-available
```
### 重启
```
$ reboot
```
