# __TEXT

`__TEXT`segment的section：

* 概述
  * 图
    * ![macho_segment_text_section](../../../assets/img/macho_segment_text_section.png)
  * 文字
    * `__TEXT,__text`: The compiled machine code for the executable
    * `__TEXT,__const`: The general constant data for the executable
    * `__TEXT,__cstring`: Literal string constants (quoted strings in source code)
    * `__TEXT,__picsymbol_stub`: Position-independent code stub routines used by the dynamic linker (dyld).
* 详解
  * `__TEXT,__text`
    * Executable machine code
      * The compiler generally places only executable code in this section, no tables or data of any sort.
    * 代码节，存放机器编译后的代码
  * `__TEXT,__const`
    * Initialized constant variables
      * The compiler places all nonrelocatable data declared const in this section. (The compiler typically places uninitialized constant variables in a zero-filled section.)
    * 存储const修饰的常量
  * `__TEXT,__cstring`
    * Constant C strings
      * A C string is a sequence of non-null bytes that ends with a null byte (`'\0'`). The static linker coalesces constant C string values, removing duplicates, when building the final product.
    * 代码运行中包含的字符串常量
      * 比如
        * 代码中定义`#define kGeTuiPushAESKey @"DWE2#@e2!"`,那`DWE2#@e2!`会存在这个区里
  * `__TEXT,__objc_classname`
    * objc类名
  * `__TEXT,__objc_methname`
    * objc的方法名称
  * `__TEXT,__objc_methtype`
    * objc方法类型
  * `__TEXT,__picsymbol_stub`
    * Position-independent indirect symbol stubs
      * See  in Mach-O Programming Topics for more information.
  * `__TEXT,__stubs`
    * 用于辅助做动态链接代码（dyld）
  * `__TEXT,__stub_helper`
    * 用于辅助做动态链接（dyld）
  * `__TEXT,__symbol_stub`
    * Indirect symbol stubs
      * 详见：[PIC](../../../macho_overview/background/pic.md)
  * `__TEXT,__literal4`
    * 4-byte literal values
      * The compiler places single-precision floating point constants in this section. The static linker coalesces these values, removing duplicates, when building the final product. With some architectures, it’s more efficient for the compiler to use immediate load instructions rather than adding to this section.
  * `__TEXT,__literal8`
    * 8-byte literal values
      * The compiler places double-precision floating point constants in this section. The static linker coalesces these values, removing duplicates, when building the final product. With some architectures, it’s more efficient for the compiler to use immediate load instructions rather than adding to this section.
  * `__TEXT,__gcc_except_tab`
  * `__TEXT,__dof_RACSignal`
  * `__TEXT,__dof_RACCompou`
  * `__TEXT,__unwind_info`
  * `__TEXT,__ustring`
