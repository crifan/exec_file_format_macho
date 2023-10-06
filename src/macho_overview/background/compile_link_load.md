# 编译链接加载过程

* 编译链接加载过程
  * 概述
    * ![compile_link_load_procedure](../../assets/img/compile_link_load_procedure.png)
  * 详解
    * ![macho_load_fields_process](../../assets/img/macho_load_fields_process.png)

## iOS的app启动过程

* iOS的app启动过程
  * 概述
    * ![ios_app_load_process](../../assets/img/ios_app_load_process.png)
  * 详细
    * ![ios_app_load_process_detail](../../assets/img/ios_app_load_process_detail.jpg)
* iOS的app启动的不同阶段
  * `Pre-main`阶段
    * ![ios_app_load_pre_main](../../assets/img/ios_app_load_pre_main.png)
  * `main`阶段
    * ![ios_app_load_main](../../assets/img/ios_app_load_main.png)
* iOS的app启动调用函数
  * ![ios_app_launch_sequence](../../assets/img/ios_app_launch_sequence.png)

## dyld加载过程

* dyld加载过程
  * 图
    * ![dyld_call_process](../../assets/img/dyld_call_process.png)
  * 文字版
    * ![dyld_call_process_text](../../assets/img/dyld_call_process_text.jpg)
* dyld2 vs dyld3
  * ![dyld2_vs_dyld3](../../assets/img/dyld2_vs_dyld3.png)
