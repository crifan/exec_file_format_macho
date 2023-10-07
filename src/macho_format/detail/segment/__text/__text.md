# __TEXT,__text

* section:`__TEXT,__text`
  * 含义
    * Executable machine code
      * The compiler generally places only executable code in this section, no tables or data of any sort.
    * 代码节，存放机器编译后的代码

## 举例

### arm64的akd中的`__TEXT,__text`

#### jtool2

```bash
 jtool2 --pages ./akd
0x0-0xf4000 __TEXT    (999424 bytes)
    0x43d0-0xbbf24 __TEXT.__text    (752468 bytes)
...
```

->

* 整个TEXT代码段范围：`0x0-0xf4000 __TEXT    (999424 bytes)` = 976KB
  * 代码段内代码的二进制数据opcode的范围：`0x43d0-0xbbf24 __TEXT.__text    (752468  bytes)` = 0xB7B54 = 约734.8KB

#### rabin2

```bash
rabin2 -S ./akd
...
0   0x000043d0  0xb7b54 0x1000043d0  0xb7b54 -r-x 0.__TEXT.__text
```

->

* text代码段的
  * 起始地址：0x000043d0
    * `vaddr`=虚拟地址：0x1000043d0
  * 大小：0xb7b54
    * = 0xB7B54 = 752468

#### MachOView

* 代码段的代码信息
  * 概述：`Executable (ARM64_ALL)`->`Load Commands`->`LC_SEGMENT_64 (__TEXT)`->`Section64 Header (__text)`
    * ![machoview_text_text_akd](../../../../assets/img/machoview_text_text_akd.png)
  * 真正数据：`Executable (ARM64_ALL)`->`Section64 (__TEXT, __text)`
    * ![machoview_akd_code_1](../../../../assets/img/machoview_akd_code_1.png)
    * ![machoview_akd_code_2](../../../../assets/img/machoview_akd_code_2.png)
  * 另外：`Executable (ARM64_ALL)`->`Section64 (__TEXT, __text)`->`Assembly`
    * MachOView还提供了，该二进制数据对应的反汇编结果Assembly（仅供参考）
      * ![machoview_akd_code_assembly_1](../../../../assets/img/machoview_akd_code_assembly_1.png)
      * ![machoview_akd_code_assembly_2](../../../../assets/img/machoview_akd_code_assembly_2.png)
