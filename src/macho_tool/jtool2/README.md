# jtool2

* `jtool2`
  * 旧版叫：`jtool`
  * 类似于`otool`的，解析查看`Mach-O`文件格式信息
    * 区别：添加了许多`Mach-O`相关的命令
      * `jtool`/`jtool2`比`otool`功能更完善
  * 支持多种运行平台
    * `OS X`=`Mac`
    * `iOS`
    * `Linux`
  * 功能
    * in-binary search functionality
    * symbol injection
    * built-in disassembler functionality with (limited but constantly improving) emulation capabilities, which already outdo fancy commercial GUI disassemblers.
    * Color terminal output, enabled by JCOLOR=1
  * 资料
    * 官网
      * JTool2 - Taking the O out of otool - squared
        * http://www.newosxbook.com/tools/jtool.html

## 安装jtool2

`Mac`中安装`jtool2`：

* Intel的CPU的Mac = Intel Mac
  * 方式1：`brew`
    ```bash
    brew install --cask jtool2
    ```
  * 方式2：官网下载二进制
    * 从[JTool2官网](http://www.newosxbook.com/tools/jtool.html)下载[jtool2.tgz](http://www.newosxbook.com/tools/jtool2.tgz)
    * 解压得到：`jtool2`（和`disarm`）
      * 提示：可以把路径加到启动脚本的`PATH`中（再source），使得命令行中可以使用
* （M1/M2等）M系列CPU的Mac = Apple Silicon Mac
  ```bash
  brew tap excitedplus1s/repo/jtool2
  brew install --no-quarantine excitedplus1s/repo/jtool2
  ```

### 常见问题

#### killed

* 问题：`Mac M2 Max` + `macOS Ventura 13.2.1`中，用brew安装的原始版本=[官网版本的jtool2](http://www.newosxbook.com/tools/jtool2.tgz)，运行崩溃Killed
  ```bash
  ➜  ~ which jtool2
  /usr/local/bin/jtool2
  ➜  ~ jtool2 --version
  [1]    69975 killed     jtool2 --version
  ➜  ~ jtool2 --help
  [1]    70025 killed     jtool2 --help
  ```
* 原因：签名问题
  * 找崩溃日志，找到原因了
    * ![jtool2_killed_log_amfi_no_blob](../../assets/img/jtool2_killed_log_amfi_no_blob.jpg)
      ```bash
      默认    17:41:55.432539+0800    kernel    Checking in with amfid for DER jtool2.arm64e
      默认    17:41:55.433342+0800    kernel    AMFI: /Users/crifan/dev/dev_tool/reverse_security/iOS/jtool2/jtool2_old/jtool2 doesn't have DER entitlements and will not work in a future release
      默认    17:41:55.433439+0800    kernel    AMFI: '/Users/crifan/dev/dev_tool/reverse_security/iOS/jtool2/jtool2_old/jtool2' has no CMS blob?
      默认    17:41:55.433454+0800    kernel    AMFI: '/Users/crifan/dev/dev_tool/reverse_security/iOS/jtool2/jtool2_old/jtool2': Unrecoverable CT signature issue, bailing out.
      默认    17:41:55.433480+0800    kernel    AMFI: Releasing transmuted blob for jtool2.arm64e - <private> 94x
      默认    17:41:55.433516+0800    kernel    proc 77535: load code signature error 4 for file "jtool2"
      默认    17:41:55.434075+0800    kernel    exec_mach_imgact: not running binary "jtool2" built against preview arm64e ABI
      默认    17:41:55.434268+0800    kernel    ASP: Security policy would not allow process: 77535, /Users/crifan/dev/dev_tool/reverse_security/iOS/jtool2/jtool2_old/jtool2
      ```
* 解决办法：换装另外的版本：
  * https://github.com/excitedplus1s/jtool2
    ```bash
    brew tap excitedplus1s/repo/jtool2
    brew install --no-quarantine excitedplus1s/repo/jtool2
    ```
  * 即可正常使用jtool2
    ```bash
    ➜  jtool2 which jtool2
    /usr/local/bin/jtool2
    ➜  jtool2 jtool2 --version
    This is 2.1-The Resurgence compiled on Dec 21 2020 21:09:04
    ```

## jtool2相关资料

* 官网
  * [JTool2 - Taking the O out of otool - squared (newosxbook.com)](http://www.newosxbook.com/tools/jtool.html)

### 常见命令的常见用法举例

官网[JTool2 - Taking the O out of otool - squared (newosxbook.com)](http://www.newosxbook.com/tools/jtool.html)中就有语法介绍：

```bash
* Otool Compatible options
* dyldinfo Compatible options
* Advanced options:
    * -pages (get layout)
    * -a (lookup address)
    * -S
* Code Singing options
    * --sig
    * --ent
    * --sign
* Objective-C
* Darn Cool Options
```

对应的别人的中文翻译：

[【OSG】jtool - Taking the O out of otool(1)-iOS安全-看雪论坛-安全社区|安全招聘|bbs.pediy.com](https://bbs.pediy.com/thread-220100.htm)
