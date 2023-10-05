# jtool2

* `jtool`
  * 新版叫：`jtool2`
  * 类似于`otool`的，解析查看`Mach-O`文件格式信息
    * 区别：添加了许多`Mach-O`相关的命令
      * `jtool`比`otool`功能更完善
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
  * 注意：不要装brew安装的原始版本=官网版本的jtool2 -> 否则会出现签名问题，运行崩溃Killed
  * 最终是换装另外的版本：
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