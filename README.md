# 可执行文件格式：Mach-O

* 最新版本：`v1.0.1`
* 更新时间：`20240325`

## 简介

介绍Mac和iOS等Apple苹果系统的常见可执行文件格式：Mach-O；先是Mach-O概览；包括背景知识的XNU、PIC等；然后介绍Mach-O格式，包括结构概述和结构图，以及结构详情，包括Header、Load Commands和Segment的data；其中Header包括magic、cputype和cpusubtype、filetype、flags；Load Commands包括LC_UUID、LC_SEGMENT、LC_SEGMENT_64、LC_SYMTAB、LC_DYLD_CHAINED_FIXUPS、LC_DYLD_EXPORTS_TRIE等；Segment包括__TEXT、__DATA、__IMPORT、__LINKEDIT、__OBJC；以及各个Segment的section，比如symbol、strings等；然后是Mach-O格式的子项，包括FAT、codesign、虚拟地址、大小限制等；然后整理Mach-O的各种工具，包括MachOView、rabin2、jtool2、otool、pagestuff，以及每个工具的用法、举例、help语法等；

## 源码+浏览+下载

本书的各种源码、在线浏览地址、多种格式文件下载如下：

### HonKit源码

* [crifan/exec_file_format_macho: 可执行文件格式：Mach-O](https://github.com/crifan/exec_file_format_macho)

#### 如何使用此HonKit源码去生成发布为电子书

详见：[crifan/honkit_template: demo how to use crifan honkit template and demo](https://github.com/crifan/honkit_template)

### 在线浏览

* [可执行文件格式：Mach-O book.crifan.org](https://book.crifan.org/books/exec_file_format_macho/website/)
* [可执行文件格式：Mach-O crifan.github.io](https://crifan.github.io/exec_file_format_macho/website/)

### 离线下载阅读

* [可执行文件格式：Mach-O PDF](https://book.crifan.org/books/exec_file_format_macho/pdf/exec_file_format_macho.pdf)
* [可执行文件格式：Mach-O ePub](https://book.crifan.org/books/exec_file_format_macho/epub/exec_file_format_macho.epub)
* [可执行文件格式：Mach-O Mobi](https://book.crifan.org/books/exec_file_format_macho/mobi/exec_file_format_macho.mobi)

## 版权和用途说明

此电子书教程的全部内容，如无特别说明，均为本人原创。其中部分内容参考自网络，均已备注了出处。如发现有侵权，请通过邮箱联系我 `admin 艾特 crifan.com`，我会尽快删除。谢谢合作。

各种技术类教程，仅作为学习和研究使用。请勿用于任何非法用途。如有非法用途，均与本人无关。

## 鸣谢

感谢我的老婆**陈雪**的包容理解和悉心照料，才使得我`crifan`有更多精力去专注技术专研和整理归纳出这些电子书和技术教程，特此鸣谢。

## 其他

### 作者的其他电子书

本人`crifan`还写了其他`150+`本电子书教程，感兴趣可移步至：

[crifan/crifan_ebook_readme: Crifan的电子书的使用说明](https://github.com/crifan/crifan_ebook_readme)

### 关于作者

关于作者更多介绍，详见：

[关于CrifanLi李茂 – 在路上](https://www.crifan.org/about/)
