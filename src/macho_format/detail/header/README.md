# Mach-O的Header

## mach_header

[源码定义](https://opensource.apple.com/source/xnu/xnu-2050.18.24/EXTERNAL_HEADERS/mach-o/loader.h)：

```c
struct mach_header {
    unsigned long magic; /* Mach magic number identifier */
    cpu_type_t cputype; /* cpu specifier */
    cpu_subtype_t cpusubtype; /* machine specifier */
    unsigned long filetype; /* type of file */
    unsigned long ncmds; /* number of load commands */
    unsigned long sizeofcmds; /* size of all load commands */
    unsigned long flags; /* flags */
};
```

或：

```c
struct mach_header {
  uint32_t      magic;
  cpu_type_t    cputype;
  cpu_subtype_t cpusubtype;
  uint32_t      filetype;
  uint32_t      ncmds;
  uint32_t      sizeofcmds;
  uint32_t      flags;
};
```

## Mach-O的Header结构图

* 内存映射 = 结构体偏移 = 结构体字段
  * ![macho_fields_detail](../../../assets/img/macho_fields_detail.png)
* Mach-O Core Dump File Structure
  * ![macho_file_structure_fields](../../../assets/img/macho_file_structure_fields.png)
* Header的详细定义
  * ![macho_layout_detail_headers](../../../assets/img/macho_layout_detail_headers.png)
