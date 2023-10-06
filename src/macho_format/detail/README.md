# Mach-O结构详情

* Mach-O基本结构
  * `Header`：文件类型、目标架构类型等
  * `Load Commands`：描述文件在虚拟内存中的逻辑结构、布局
  * (Raw segment) `data`：在Load commands中定义的Segment的原始数据
    * 一个或多个segment=段
        * 每个segment包含 一个或多个 section=节
            * 每个section包含 （某种类型的）代码 或 数据

## Mach-O详细定义

### 相关源码

* Mach-O详细定义
  * 相关源码
    * xnu源码
      * https://opensource.apple.com/tarballs/xnu/
        * `EXTERNAL_HEADERS/mach-o/fat.h`
        * `EXTERNAL_HEADERS/mach-o/loader.h`
          * 举例
            * https://opensource.apple.com/source/xnu/xnu-2050.18.24/EXTERNAL_HEADERS/mach-o/loader.h
