# otool用法

* 单个参数
  * `-l`: print the **l**oad commands
    ```bash
    otool -l iOSBinaryFile
    ```
  * `-L`: print shared **L**ibraries used
    ```bash
    otool -L iOSBinaryFile
    ```
  * `-o`: print the **O**bjective-C segment
  * `-V`: print disassembled operands symbolically
* 参数组合
  * `-oV`
    ```bash
    otool -oV iOSBinaryFile
    ```
  * `-tV`
    ```bash
    otool -tV iOSBinaryFile
    ```
* 用途
  * 用otool去手动计算地址转函数
    ```bash
    otool -arch <arch> -l <path_to_dsym> | grep __TEXT -m 2 -A 1 | grep vmaddr
    ```

## 常见问题

### is not an object file

otool只支持查看Mach-O格式的文件，不支持其他格式的文件。

比如如果用otool查看ELF格式的话，会报错：

```bash
➜  arm64-v8a otool -L libtacker.so
libtacker.so: is not an object file

➜  arm64-v8a otool -oV libtacker.so
libtacker.so: is not an object file
```
