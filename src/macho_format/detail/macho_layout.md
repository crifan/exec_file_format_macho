# Mach-O结构图

## 概览

* ![macho_layout_core](../../assets/img/macho_layout_core.png)

### 普通单架构 vs FAT多架构

* 普通：单架构 = Mach-O文件
  * ![macho_layout_core_single](../../assets/img/macho_layout_core_single.png)
* 特殊：多架构=`FAT`=Universal通用文件
  * ![macho_layout_core_fat](../../assets/img/macho_layout_core_fat.png)
  * 文字版
    ```bash
    +---------------------+        /* header (fat_header: 0x8) */
    |                     |
    |     FAT HEADER      |
    |                     |
    +---------------------+        /* archs (fat_arch: 0x14) */
    |     FAT ARCH #1     |
    +---------------------+
    |     FAT ARCH #2     |
    +---------------------+
    |         ...         |        /* other eventual fat archs... */
    +---------------------+        /* Mach-Os section (variable size) */
    |                     |
    |                     |
    |                     |
    |                     |
    |      MACH-O #1      |
    |                     |
    |                     |
    |                     |
    |                     |
    |                     |
    +---------------------+
    |                     |
    |                     |
    |                     |
    |                     |
    |                     |
    |      MACH-O #2      |
    |                     |
    |                     |
    |                     |
    |                     |
    +---------------------+
    |         ...         |        /* other eventual Mach-Os... */
    +---------------------+
    ```

## 详解

* 带字段的Mach-O结构图
  * ![macho_layout_fields_overall](../../assets/img/macho_layout_fields_overall.png)
* ![macho_layout_detail_colorful](../../assets/img/macho_layout_detail_colorful.jpg)
* ![macho_layout_detail_basic](../../assets/img/macho_layout_detail_basic.png)
* ![macho_layout_detail_sub_group](../../assets/img/macho_layout_detail_sub_group.png)
* ![macho_layout_detail_line](../../assets/img/macho_layout_detail_line.jpg)
* ![macho_layout_detail_yellow](../../assets/img/macho_layout_detail_yellow.png)
