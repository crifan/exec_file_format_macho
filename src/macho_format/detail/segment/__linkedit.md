# __LINKEDIT

* 用户层的完全链接后的Mach-O文件，最后一个segment是`link edit`
  * 包含link edit信息
    * `symbol table`
    * `string table`
    * 等等
  * 用于：动态加载器`dynamic loader`去链接所依赖的库
