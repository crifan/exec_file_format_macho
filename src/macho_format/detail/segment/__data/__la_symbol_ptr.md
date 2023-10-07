# __DATA,__la_symbol_ptr

## 举例

### MachOView查看zzzzHeiBaoLib.dylib

![machoview_heibao_la_symbol_ptr](../../../../assets/img/machoview_heibao_la_symbol_ptr.jpg)

![machoview_heibao_lazy_symbol_pointers_1](../../../../assets/img/machoview_heibao_lazy_symbol_pointers_1.jpg)

![machoview_heibao_lazy_symbol_pointers_2](../../../../assets/img/machoview_heibao_lazy_symbol_pointers_2.jpg)

分析：

其中很多函数，就是IDA中Imports的函数：

![machoview_lazy_symbol_pointers_functions](../../../../assets/img/machoview_lazy_symbol_pointers_functions.jpg)
