# Mach-O的Header的magic

* `magic`=`魔数`

[源码定义](https://opensource.apple.com/source/xnu/xnu-2050.18.24/EXTERNAL_HEADERS/mach-o/loader.h)：

```c
/* Constant for the magic field of the mach_header (32-bit architectures) */
#define MH_MAGIC       0xfeedface      /* the mach magic number */
#define MH_CIGAM       0xcefaedfe      /* NXSwapInt(MH_MAGIC) */

/* Constant for the magic field of the mach_header_64 (64-bit architectures) */
#define MH_MAGIC_64 0xfeedfacf /* the 64-bit mach magic number */
#define MH_CIGAM_64 0xcffaedfe /* NXSwapInt(MH_MAGIC_64) */
```

->

* magic
  * 通用格式：`0xcafebabe`
  * （`armv7`等）32bit：`0xfeedface`
  * （`arm64`等）64bit：`0xfeedfacf`
