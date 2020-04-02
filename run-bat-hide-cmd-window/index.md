# 运行 bat 脚本时隐藏 cmd 窗口

在需要运行的 bat 脚本前添加以下内容：
```
@echo off
if "%1" == "h" goto begin
mshta vbscript:createobject("wscript.shell").run("""%~nx0"" h",0)(window.close)&&exit
:begin
REM
```
即可。运行时 cmd 窗口会闪烁一下。
