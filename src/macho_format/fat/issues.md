# FAT常见问题

## Select an architecture setting the ARCH= environment variable

用jtool2导出Mask的dylib信息期间就遇到了`FAT Binary`：

```bash
➜  DynamicLibraries jtool2 -h MaskPro.dylib > MaskProDylib/MaskProDylib_jtool2_h_header.txt
Fat binary, little-endian, 2 architectures: armv7, arm64
Select an architecture setting the ARCH= environment variable
```

即，一个Dylib中，包含了多种架构，此处是`armv7`和`arm64`

此处要指定具体架构，才能继续用`jtool2`查看信息：

```bash
➜  DynamicLibraries export ARCH=arm64
➜  DynamicLibraries jtool2 -h MaskPro.dylib > MaskProDylib/MaskProDylib_jtool2_h_header.txt
```

类似的，后续去用`MachOView`查看信息，也能看到是：`FAT Binary`

* ![fat_bin_machoview_header](../../assets/img/fat_bin_machoview_header.png)
  * ARMV7
    * ![macho_header_fat_armv7](../../assets/img/macho_header_fat_armv7.png)
  * ARM64
    * ![macho_header_fat_arm64](../../assets/img/macho_header_fat_arm64.png)
