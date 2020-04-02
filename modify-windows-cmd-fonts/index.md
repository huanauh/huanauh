# 修改 Windows 命令提示符字体

Windows 的`命令提示符`默认使用点阵字体，该字体奇丑无比。更换方法如下：
### 字体下载
cmd 对字体的要求很多，很多字体都无法使用。推荐使用 [Microsoft YaHei Mono](https://github.com/Microsoft/BashOnWindows/files/1362006/Microsoft.YaHei.Mono.zip) 字体。
### 修改注册表
注册表定位到`HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Console\TrueTypeFont`新建`0936`字符串值，填入`*Microsoft YaHei Mono`

+ 注1：936 为简体中文代码页，自行添加字体时，需要在 936 前面加 0，所以添加第一个字体就是 0936，同理添加第二个字体就是 00936。
+ 注2：字体名称前面`*`必须加上。

### 切换字体
经过以上两步，打开`命令提示符`，在`属性`-`字体`里面就可以将字体修改为 Microsoft YaHei Mono 了。
### 注意事项
使用该字体时，建议`命令提示符`的字体大小不要使用 18 号。原因：使用 18 号大小时，数字 0 显示不正常。
