# Mach-O格式

## Mach-O格式的常见文件类型

* Mach-O格式的常见文件类型
  * 图
    * ![mach_o_format_files](../assets/img/mach_o_format_files.jpg)
  * 文字
    * `MH_EXECUTE`=可执行文件=`executable`=应用
      * 文件：`.app/xxx`
    * `MH_OBJECT`
      * 目标文件
        * 文件：`.o`
      * 静态库文件=静态链接库=`static library`：N个`.o`合并在一起
        * 文件：`.a`
    * `MH_DYLIB`=动态链接库=`dylib library`：类似于Win中的`DLL`
      * 文件：`.dylib`、`.framework/xxx`
    * `MH_DYLINKER`：动态链接编辑器
      * 文件：`/usr/lib/dyld`
    * `MH_DSYM`：存储着二进制文件符号信息的文件
      * 文件：`.dSYM/Contents/Resources/DWARF/xxx`
        * 常用于分析APP的崩溃信息

## Mach-O vs ELF

![macho_vs_elf](../assets/img/macho_vs_elf.png)
