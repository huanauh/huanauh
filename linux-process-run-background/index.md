# Linux 进程后台运行的方法

### screen 命令
#### 创建 screen
```bash
$ screen -S test
```
#### 保留 screen
```bash
$ ctrl+a+d
```
*按`ctrl+a`，然后再按`d`即可保留 screen*
#### 查看 screen
```bash
$ screen -ls
```
#### 恢复 screen
```bash
$ screen -r test
```
### nohup 命令
#### 后台运行
```bash
$ nohup server -c ./server.josn &
```
*示例命令为`server -c ./server.josn`*

#### 后台运行并重定向标准输出
```bash
$ nohup server -c ./server.josn 2>&1 &
```
#### 停止后台运行
```bash
$ eval $(ps -ef | grep "server" | awk '{print "kill "$2}')
```
