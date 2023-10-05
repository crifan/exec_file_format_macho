# lipo

* `lipo`：常用于多架构Mach-O文件的处理
  * 查看架构信息：`lipo -info inputMacOFile`
  * 导出某种特定架构：`lipo inputMachOFile -thin ArchType -output OutputFile`
  * 合并多种架构：`lipo inputMachOFile1 inputMachOFile2 -output OutputFile`
