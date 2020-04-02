# Crt 与 key 格式证书转换为 pem 格式

执行
```
$ cat test.key test.crt > test.pem
```
即可转换为 pem 格式。

- 注：因 pem 文件将 cer 和 key 文件内容合并，文件内容中`END PRIVATE KEY`与`EBEGIN CERTIFICATE`分别占用一行。不同 Web server 对 pem 文件内容格式要求不甚相同，可能需要将`END PRIVATE KEY`与`EBEGIN CERTIFICATE`合并在同一行。
