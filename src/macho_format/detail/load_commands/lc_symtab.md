# LC_SYMTAB

* `LC_SYMTAB`
  * 数据结构定义：`symtab_command`
  * 含义：Specifies the symbol table for this file. This information is used by both static and dynamic linkers when linking the file, and also by debuggers to map symbols to the original source code files from which the symbols were generated.

## symtab_command定义

![macho_detail_string_table](../../../assets/img/macho_detail_string_table.png)

源码定义：

* 精简定义

```c
struct symtab_command {
   uint32_t cmd;
   uint32_t cmdsize;
   uint32_t symoff;
   uint32_t nsyms;
   uint32_t stroff;
   uint32_t strsize;
};
```

* 详细定义

```c
/*
 * The symtab_command contains the offsets and sizes of the link-edit 4.3BSD
 * "stab" style symbol table information as described in the header files
 * <nlist.h> and <stab.h>.
 * symtab_command 包含了符号表、字符串索引表 的偏移量和大小 。
 */
struct symtab_command {
	uint32_t	cmd;		/* LC_SYMTAB */
	uint32_t	cmdsize;	/* sizeof(struct symtab_command) */
	uint32_t	symoff;		/* symbol table offset */
	uint32_t	nsyms;		/* number of symbol table entries */
	uint32_t	stroff;		/* string table offset */
	uint32_t	strsize;	/* string table size in bytes */
};
```

## 举例

* MachOView查看到某`LC_SYMTAB`的效果
  * ![machoview_lc_symtab_example](../../../assets/img/machoview_lc_symtab_example.png)
    * 说明
      * 命令的大小是24 （十进制）
      * 符号表在物理文件的偏移量是 77360448
      * 符号表的大小 1069179
      * String表的物理文件偏移量是94479244
      * string表的大小是22093264
