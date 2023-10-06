# string

* String Table
  * String表顺序列出了二进制mach-O文件的中的所有可见字符串。串之间通过0x00分隔。可以通过相对String表起始位置的偏移量随机访问String表中的字符串。符号表结构中的n_strx指定的就是String表中的偏移量。通过这个偏移量可以访问到符号对应的具体字符串

## 举例

* MachOView查看到的某`String Table`
  * ![machoview_string_table_example](../../../assets/img/machoview_string_table_example.png)
    * 说明
      * String表的`0xbbf8`处是不是`[GMRYouHaoHuoReq getRequestURL]`，string表的地址是`0x049C6D40` 加上偏移量`0x000BBFB1` ，等于`0x54d633d`
      * 可以看出string表的`0x54d633d`地址出就是：`[GMRYouHaoHuoReq getRequestURL]`
