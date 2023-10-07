# __DATA

`__DATA`segment的section：

* 概述
  * 图
    * ![macho_segment_data_section](../../../../assets/img/macho_segment_data_section.png)
  * 文字
    * `__DATA,__data`: Initialized global variables (for example `int a = 1;` or `static int a = 1;`).
    * `__DATA,__const`: Constant data needing relocation (for example, `char * const p = "foo";`).
    * `__DATA,__bss`: Uninitialized static variables (for example, `static int a;`).
    * `__DATA,__common`: Uninitialized external globals (for example, `int a;` outside function blocks).
    * `__DATA,__dyld`: A placeholder section, used by the dynamic linker.
    * `__DATA,__la_symbol_ptr`: **Lazy** symbol pointers. Symbol pointers for each undefined function called by the executable.
    * `__DATA,__nl_symbol_ptr`: **Non lazy** symbol pointers. Symbol pointers for each undefined data symbol referenced by the executable.
* 详解
  * `__DATA,__bss`
    * Data for uninitialized static variables (for example, `static int i;`).
    * 存储未初始化的静态量。比如：`static NSThread *_networkRequestThread = nil;`
      * 其中这里面的size表示应用运行占用的内存，不是实际的占用空间。所以计算大小的时候应该去掉这部分数据。
  * `__DATA,__common`
    * Uninitialized imported symbol definitions (for example, `int i;`) located in the global scope (outside of a function declaration).
    * 存储导出的全局的数据。类似于`static`，但是没有用`static`修饰
      * 比如
        * KSCrash里面`NSDictionary* g_registerOrders;`, `g_registerOrders`就存储在`__common`里面
  * `__DATA,__data`
    * Initialized mutable variables, such as writable C strings and data arrays.
    * 放了协议和一些固定了地址（已经初始化）的静态量
  * `__DATA,__la_symbol_ptr`
    * Lazy symbol pointers, which are indirect references to functions imported from a different file
      * 详见：[PIC](../../../macho_overview/background/pic.md)
    * 懒加载的函数指针地址。和`__stubs`和`__stub_helper`配合使用
  * `__DATA,__nl_symbol_ptr`
    * Non-lazy symbol pointers, which are indirect references to data items imported from a different file
      * 详见：[PIC](../../../macho_overview/background/pic.md)
  * `__DATA,__dyld`
    * Placeholder section used by the dynamic linker.
  * `__DATA,__cfstring`
    * 使用Core Foundation字符串
  * `__DATA,__const`
    * Initialized relocatable constant variables.
    * 存储constant常量的数据。比如使用extern导出的const修饰的常量
  * `__DATA,__mod_init_func`
    * Module initialization functions. The C++ compiler places static constructors here.
    * 模块初始化的方法
  * `__DATA,__mod_term_func`
    * Module termination functions.
  * `__DATA,__objc_classlist`
    * objc类列表,保存类信息，映射了`__objc_data`的地址
  * `__DATA,__objc_data`
    * objc的数据。用于保存类需要的数据。最主要的内容是映射`__objc_const`地址，用于找到类的相关数据
  * `__DATA,__objc_nlclslist`
    * `Objective-C`的`+load`函数列表，比`__mod_init_func`更早执行
  * `__DATA,__objc_catlist`
    * categories
  * `__DATA,__objc_nlcatlist`
    * `Objective-C`的categories的`+load`函数列表
  * `__DATA,__objc_protolist`
    * objc协议列表
  * `__DATA,__objc_imageinfo`
    * objc镜像信息
  * `__DATA,__got`
    * 存储引用符号的实际地址，类似于动态符号表
  * `__DATA,__objc_const`
    * objc常量。保存`objc_classdata`结构体数据。用于映射类相关数据的地址，比如类名，方法名等
  * `__DATA,__objc_selrefs`
    * 引用到的objc方法
  * `__DATA,__objc_protorefs`
    * 引用到的objc协议
  * `__DATA,__objc_classrefs`
    * 引用到的objc类
  * `__DATA,__objc_superrefs`
    * objc超类引用
  * `__DATA,__objc_ivar`
    * objc的`ivar`指针,存储属性

## 举例

* MachOView查看
  * zzzzHeiBaoLib.dylib
    * ![machoview_heibao_text_data](../../../../assets/img/machoview_heibao_text_data.png)
  * 某app
    * `__DATA`的segment commond
      * ![machoview_data_segment_example](../../../../assets/img/machoview_data_segment_example.png)
        * 说明
          * 命令类型是LC_SEGMENT_64
          * 命令的大小1832
          * segment 命令的名称是__DATA
          * 映射的内存地址是4360744960（十进制）
          * 内存的大小12488704
          * 文件的偏移量是65777664
          * 需要映射的文件的大小10424320
          * 最大内存保护权限：读写执行
          * 初始内存权限：读写
          * 这个端附属了22个 section，也就是说1832大小的segment_command包括了22个section命令的大小。
          * 看的方法：offset代表文件的便宜量、Data表示内存地址中存储的值、description表示这段内存地址的名称的描述、value表示存储的值的可视描述。
        * 后续的22个section
          * ![machoview_data_segment_more](../../../../assets/img/machoview_data_segment_more.png)
