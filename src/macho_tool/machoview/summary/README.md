# MachOView使用心得

一些心得：

* 如果二进制太大，或者本身防护做的比较好，则：MachOView完全加载出来二进制信息
  * 往往耗时很久
  * 也往往会直接崩溃，无法继续使用
    * 比如抖音的二进制加载到最后，就被崩溃。
      * 只能在崩溃之前，及时查看（大）部分已解析出的信息
