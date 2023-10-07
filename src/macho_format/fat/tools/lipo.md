# lipo

* `lipo`：常用于多架构Mach-O文件的处理
  * 查看架构信息
    ```bash
    lipo -info inputMacOFile
    ```
  * 导出某种特定架构
    ```bash
    lipo inputMachOFile -thin ArchType -output OutputFile
    ```
  * 合并多种架构
    ```bash
    lipo inputMachOFile1 inputMachOFile2 -output OutputFile
    ```

## 举例

* 瘦身=导出单个架构
  * 导出arm64架构
    ```bash
    lipo -thin arm64 debugserver_orig -output debugserver_arm64
    ```

其中，`arm64`是从`file`中查看到包含的多个架构中的其中一个：

```bash
crifan@licrifandeMacBook-Pro  ~/dev/dev_root/iosReverse/AppleStore/dynamicDebug/debugserver_lldb  file fromiPhone11/debugserver_orig
fromiPhone11/debugserver_orig: Mach-O universal binary with 2 architectures: [arm64:Mach-O 64-bit executable arm64] [arm64e:Mach-O 64-bit executable arm64e]
fromiPhone11/debugserver_orig (for architecture arm64):    Mach-O 64-bit executable arm64
fromiPhone11/debugserver_orig (for architecture arm64e):    Mach-O 64-bit executable arm64e
```
