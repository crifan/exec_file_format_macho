# Mach-O概览

* `Mach-O`
  * `Mach-O`=`Mach Object`=`Mach Object file format`
  * 是什么：`Mac`和`iOS`等`Apple`平台中的[可执行文件格式](https://book.crifan.org/books/executable_file_format/website/)
  * 名词解释
    * `Mach-O` = `Mach` + `O`
      * `Mach`
        * iOS的内核是`XNU`
          * `XNU`由多个部分组成
            * 其中一部分是`Mach`微内核microkernel
              * ![ios_kernel_xnu_arch](../assets/img/ios_kernel_xnu_arch.png)
      * `O`=`Object`=对象
  * 用到`Mach-O`的系统
    * `Mach kernel`
    * `NeXTSTEP`
    * `macOS`
    * `iOS`
