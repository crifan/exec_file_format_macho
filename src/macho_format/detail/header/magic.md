# magic

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
  * 32bit：`0xfeedface`
  * 64bit：`0xfeedfacf`
