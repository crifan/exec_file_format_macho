# Mach-O的Header

## Mach-O的Header结构图

* Header的详细定义
  * ![macho_layout_detail_headers](../../../assets/img/macho_layout_detail_headers.png)
* MachOView显示Mach-O的Header举例
  * ![macho_header_machoview](../../../assets/img/macho_header_machoview.png)
    * 说明
      * 该文件是可执行文件
      * 文件的构架是x86_64
      * number of Load commands表示有74个load commond
      * MH_TWOLEVEL二级名字空间
      * MH_PIE 随机地址空间
* Mach-O Core Dump File Structure
  * ![macho_file_structure_fields](../../../assets/img/macho_file_structure_fields.png)
* 内存映射 = 结构体偏移 = 结构体字段
  * ![macho_fields_detail](../../../assets/img/macho_fields_detail.png)

## mach_header定义

* 精简定义

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

* 详细定义

[源码定义](https://opensource.apple.com/source/xnu/xnu-2050.18.24/EXTERNAL_HEADERS/mach-o/loader.h)：

```c
/*
 * The 32-bit mach header appears at the very beginning of the object file for
 * 32-bit architectures.
 */
struct mach_header {
	uint32_t	magic;		/* mach magic number identifier */
	cpu_type_t	cputype;	/* cpu specifier */
	cpu_subtype_t	cpusubtype;	/* machine specifier */
	uint32_t	filetype;	/* type of file */
	uint32_t	ncmds;		/* number of load commands */
	uint32_t	sizeofcmds;	/* the size of all the load commands */
	uint32_t	flags;		/* flags */
};

/* Constant for the magic field of the mach_header (32-bit architectures) */
#define	MH_MAGIC	0xfeedface	/* the mach magic number */
#define MH_CIGAM	0xcefaedfe	/* NXSwapInt(MH_MAGIC) */

/*
 * The 64-bit mach header appears at the very beginning of object files for
 * 64-bit architectures.
 */
struct mach_header_64 {
	uint32_t	magic;		/* mach magic number identifier */
	cpu_type_t	cputype;	/* cpu specifier */
	cpu_subtype_t	cpusubtype;	/* machine specifier */
	uint32_t	filetype;	/* type of file */
	uint32_t	ncmds;		/* number of load commands */
	uint32_t	sizeofcmds;	/* the size of all the load commands */
	uint32_t	flags;		/* flags */
	uint32_t	reserved;	/* reserved */
};

/* Constant for the magic field of the mach_header_64 (64-bit architectures) */
#define MH_MAGIC_64 0xfeedfacf /* the 64-bit mach magic number */
#define MH_CIGAM_64 0xcffaedfe /* NXSwapInt(MH_MAGIC_64) */
```
