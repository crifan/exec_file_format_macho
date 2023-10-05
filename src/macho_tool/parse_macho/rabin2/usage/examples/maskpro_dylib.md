# MaskPro.dylib

TODO：

整理

【记录】静态分析Mask的动态库：MaskPro.dylib

相关内容过来

---

```bash
rabin2 -I MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_I_identification.txt
rabin2 -i MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_i_imports.txt
rabin2 -E MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_E_exports.txt
rabin2 -l MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_l_libraries.txt
rabin2 -z MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_z_strings.txt
rabin2 -s MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_s_symbols.txt
rabin2 -S MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_S_sections.txt
```
