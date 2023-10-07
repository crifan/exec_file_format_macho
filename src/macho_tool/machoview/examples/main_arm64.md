# main_arm64

用MachOView去查看这个`main_arm64: Mach-O 64-bit executable arm64`

## Mach64 Header

![machoview_main_arm64_header](../../../assets/img/machoview_main_arm64_header.png)

内容：

* Mach64 Header
  * `MH_MAGIC_64`
  * `CPU_TYPE_ARM64`
  * `CPU_SUBTYPE_ARM64_ALL`
  * `MH_EXECUTE`
  * Number for Load Commands: `17`
  * Flags
    * `MH_NOUNDEFS`
    * `MH_DYLDLINK`
    * `MH_TWOLEVEL`
    * `MH_PIC`
  * Reserved: 0

## Load Commands

![machoview_main_arm64_load_commands](../../../assets/img/machoview_main_arm64_load_commands.png)

### LC_SEGMENT_64 (`__PAGEZERO`)

![machoview_main_command_pagezero](../../../assets/img/machoview_main_command_pagezero.png)

### LC_SEGMENT_64 (`__TEXT`)

![machoview_main_command_text_sections](../../../assets/img/machoview_main_command_text_sections.png)

#### `__TEXT,__text`

![machoview_main_text_text](../../../assets/img/machoview_main_text_text.png)

#### `__TEXT,__stubs`

![machoview_main_text_stubs](../../../assets/img/machoview_main_text_stubs.png)

#### `__TEXT,__stub_helper`

![machoview_main_text_stub_helper](../../../assets/img/machoview_main_text_stub_helper.png)

#### `__TEXT,__cstring`

![machoview_main_text_cstring](../../../assets/img/machoview_main_text_cstring.png)

#### `__TEXT,__unwind_info`

![machoview_main_text_unwind_info](../../../assets/img/machoview_main_text_unwind_info.png)

### LC_SEGMENT_64 (`__DATA_CONST`)

![machoview_main_command_data_const_sections](../../../assets/img/machoview_main_command_data_const_sections.png)

#### `__DATA_CONST,__got`

![machoview_main_data_const_got](../../../assets/img/machoview_main_data_const_got.png)

### LC_SEGMENT_64 (`__DATA`)

![machoview_main_command_data_sections](../../../assets/img/machoview_main_command_data_sections.png)

#### `__DATA,__la_symbol_ptr`

![machoview_main_data_la_symbol_ptr](../../../assets/img/machoview_main_data_la_symbol_ptr.png)

#### `__DATA,__data`

![machoview_main_data_data](../../../assets/img/machoview_main_data_data.png)

#### `__DATA,__common`

![machoview_main_data_common](../../../assets/img/machoview_main_data_common.png)

### LC_SEGMENT_64 (`__LINKEDIT`)

![machoview_main_command_linkedit](../../../assets/img/machoview_main_command_linkedit.png)

### LC_DYLD_INFO_ONLY

![machoview_main_command_lc_dyld_info_only](../../../assets/img/machoview_main_command_lc_dyld_info_only.png)

### LC_SYMTAB

![machoview_main_command_lc_symtab](../../../assets/img/machoview_main_command_lc_symtab.png)

### LC_DYSYMTAB

![machoview_main_command_lc_dysymtab](../../../assets/img/machoview_main_command_lc_dysymtab.png)

### LC_LOAD_DYLINKER

![machoview_main_command_lc_load_dylinker](../../../assets/img/machoview_main_command_lc_load_dylinker.png)

### LC_UUID

![machoview_main_command_lc_uuid](../../../assets/img/machoview_main_command_lc_uuid.png)

### ??? (unsupported)

![machoview_main_command_unsupported](../../../assets/img/machoview_main_command_unsupported.png)

### LC_SOURCE_VERSION

![machoview_main_command_lc_source_version](../../../assets/img/machoview_main_command_lc_source_version.png)

### LC_MAIN

![machoview_main_command_lc_main](../../../assets/img/machoview_main_command_lc_main.png)

估计就是 入口函数 入口地址 = 一般叫做 main函数的 地方了

### LC_LOAD_DYLIB (libSystem.B.dylib)

![machoview_main_command_lc_load_dylib](../../../assets/img/machoview_main_command_lc_load_dylib.png)

### LC_FUNCTION_STARTS

![machoview_main_command_lc_function_starts](../../../assets/img/machoview_main_command_lc_function_starts.png)

好像是：需要启动运行的函数的列表？

### LC_DATA_IN_CODE

![machoview_main_command_lc_data_in_code](../../../assets/img/machoview_main_command_lc_data_in_code.png)

### LC_CODE_SIGNATURE

![machoview_main_command_lc_code_signature](../../../assets/img/machoview_main_command_lc_code_signature.png)

## Sections

### Section64 (`__TEXT,__text`)

* ![machoview_main_sections_text_text](../../../assets/img/machoview_main_sections_text_text.png)
  * Assembly
    * ![machoview_main_sections_text_text_assembly_1](../../../assets/img/machoview_main_sections_text_text_assembly_1.png)
    * ![machoview_main_sections_text_text_assembly_2](../../../assets/img/machoview_main_sections_text_text_assembly_2.png)

### Section64 (`__TEXT,__stubs`)

* ![machoview_main_sections_text_stubs](../../../assets/img/machoview_main_sections_text_stubs.png)
  * Symbol Stubs
    * ![machoview_main_sections_text_stubs_symbol_stubs](../../../assets/img/machoview_main_sections_text_stubs_symbol_stubs.png)

好像是：

stub=表示 桩 ，地基

表示，代码运行前，要打地基 = 做好准备

所以此处表示：所引用的外部的函数

此处分别是：

* `___strcpy_chk`
* `_free`
* `_malloc`
* `_printf`

### Section64 (`__TEXT,__stub_helper`)

* ![machoview_main_sections_text_stub_helper](../../../assets/img/machoview_main_sections_text_stub_helper.png)
  * Assembly
    * ![machoview_main_sections_text_stub_helper_assembly](../../../assets/img/machoview_main_sections_text_stub_helper_assembly.png)

### Section64 (`__TEXT,__cstring`)

* ![machoview_main_sections_text_cstring](../../../assets/img/machoview_main_sections_text_cstring.png)
  * C String Literals
    * ![machoview_main_sections_text_cstring_c_string_literals_1](../../../assets/img/machoview_main_sections_text_cstring_c_string_literals_1.png)
    * ![machoview_main_sections_text_cstring_c_string_literals_2](../../../assets/img/machoview_main_sections_text_cstring_c_string_literals_2.png)

### Section64 (`__TEXT,__unwind_info`)

* ![machoview_main_sections_text_unwind_info](../../../assets/img/machoview_main_sections_text_unwind_info.png)

### Section64 (`__DATA_CONST,__got`)

* ![machoview_main_sections_data_const_got](../../../assets/img/machoview_main_sections_data_const_got.png)
  * Non-Lazy Symbol Pointers
    * ![machoview_main_sections_data_const_got_non_lazy_symbols_pointers](../../../assets/img/machoview_main_sections_data_const_got_non_lazy_symbols_pointers.png)

### Section64 (`__DATA,__la_symbol_ptr`)

* ![machoview_main_sections_data_la_symbol_ptr](../../../assets/img/machoview_main_sections_data_la_symbol_ptr.png)
  * Lazy Symbol Pointers
    * ![machoview_main_sections_data_lazy_symbol_pointers](../../../assets/img/machoview_main_sections_data_lazy_symbol_pointers.png)

### Section64 (`__DATA,__data`)

* ![machoview_main_sections_data_data](../../../assets/img/machoview_main_sections_data_data.png)

## Dynamic Loader Info

* ![machoview_main_dynamic_loader_info](../../../assets/img/machoview_main_dynamic_loader_info.png)
  * Rebase Info
    * ![machoview_main_dynamic_loader_info_rebase_info](../../../assets/img/machoview_main_dynamic_loader_info_rebase_info.png)
    * Opcodes
      * ![machoview_main_dynamic_loader_info_rebase_info_opcodes](../../../assets/img/machoview_main_dynamic_loader_info_rebase_info_opcodes.png)
    * Actions
      * ![machoview_main_dynamic_loader_info_rebase_info_actions](../../../assets/img/machoview_main_dynamic_loader_info_rebase_info_actions.png)
  * Binding Info
    * ![machoview_main_dynamic_loader_info_binding_info](../../../assets/img/machoview_main_dynamic_loader_info_binding_info.png)
      * Opcodes
        * ![machoview_main_dynamic_loader_info_binding_info_opcodes](../../../assets/img/machoview_main_dynamic_loader_info_binding_info_opcodes.png)
    * Actions
      * ![machoview_main_dynamic_loader_info_binding_info_actions](../../../assets/img/machoview_main_dynamic_loader_info_binding_info_actions.png)
  * Lazy Binding Info
    * ![machoview_main_dynamic_loader_info_lazy_binding_info](../../../assets/img/machoview_main_dynamic_loader_info_lazy_binding_info.png)
      * Opcodes
        * ![machoview_main_dynamic_loader_info_lazy_binding_info_opcodes](../../../assets/img/machoview_main_dynamic_loader_info_lazy_binding_info_opcodes.png)
    * Actions
      * ![machoview_main_dynamic_loader_info_lazy_binding_info_actions](../../../assets/img/machoview_main_dynamic_loader_info_lazy_binding_info_actions.png)
  * Export Info
    * ![machoview_main_dynamic_loader_info_export_info](../../../assets/img/machoview_main_dynamic_loader_info_export_info.png)
      * Opcodes
        * ![machoview_main_dynamic_loader_info_export_info_opcodes_1](../../../assets/img/machoview_main_dynamic_loader_info_export_info_opcodes_1.png)
        * ![machoview_main_dynamic_loader_info_export_info_opcodes_2](../../../assets/img/machoview_main_dynamic_loader_info_export_info_opcodes_2.png)
    * Actions
      * ![machoview_main_dynamic_loader_info_export_info_actions](../../../assets/img/machoview_main_dynamic_loader_info_export_info_actions.png)


对应原先代码中的，全局变量：

```c
// demo Data segment
const char* gAuthor = "crifan"; // demo const string, place where?
char* gFullName = "CrifanLi"; // demo non-const string, place where?
int gInputArgsCount; // demo uninitialized data
int gCurDate = 20230419;  // demo initialized data
```

好像还额外去导出了这些全局变量？

## Function Starts

* ![machoview_main_function_starts](../../../assets/img/machoview_main_function_starts.png)
  * Functions
    * ![machoview_main_function_starts_functions](../../../assets/img/machoview_main_function_starts_functions.png)

## Symbol Table

* ![machoview_main_symbol_table](../../../assets/img/machoview_main_symbol_table.png)
  * Symbols
    * ![machoview_main_symbol_table_symbols_1](../../../assets/img/machoview_main_symbol_table_symbols_1.png)
    * ![machoview_main_symbol_table_symbols_2](../../../assets/img/machoview_main_symbol_table_symbols_2.png)
    * ![machoview_main_symbol_table_symbols_3](../../../assets/img/machoview_main_symbol_table_symbols_3.png)
    * ![machoview_main_symbol_table_symbols_4](../../../assets/img/machoview_main_symbol_table_symbols_4.png)

## Data in Code Entries

* ![machoview_main_data_in_code_entries](../../../assets/img/machoview_main_data_in_code_entries.png)

## Dynamic Symbol Table

* ![machoview_main_dynamic_symbol_table](../../../assets/img/machoview_main_dynamic_symbol_table.png)
  * Indirect Symbols
    * ![machoview_main_dynamic_symbol_table_indirect_symbols](../../../assets/img/machoview_main_dynamic_symbol_table_indirect_symbols.png)

## String Table

* ![machoview_main_dynamic_string_table](../../../assets/img/machoview_main_dynamic_string_table.png)
  * Strings Parse
    * ![machoview_main_dynamic_string_table_strings_parse](../../../assets/img/machoview_main_dynamic_string_table_strings_parse.png)

## Code Signature

* ![machoview_main_code_signature](../../../assets/img/machoview_main_code_signature.png)
