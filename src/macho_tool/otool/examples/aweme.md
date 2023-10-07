# otool用法举例：Aweme

## `-l`

```bash
➜  Aweme.app otool -l Aweme
Aweme:
Load command 0
      cmd LC_SEGMENT_64
  cmdsize 72
  segname __PAGEZERO
   vmaddr 0x0000000000000000
   vmsize 0x0000000100000000
  fileoff 0
 filesize 0
  maxprot 0x00000000
 initprot 0x00000000
   nsects 0
    flags 0x0
Load command 1
      cmd LC_SEGMENT_64
  cmdsize 552
  segname __TEXT
   vmaddr 0x0000000100000000
   vmsize 0x0000000000008000
  fileoff 0
 filesize 32768
  maxprot 0x00000005
 initprot 0x00000005
   nsects 6
    flags 0x0
Section
  sectname __text
   segname __TEXT
      addr 0x0000000100006af4
      size 0x00000000000011bc
    offset 27380
     align 2^2 (4)
    reloff 0
    nreloc 0
     flags 0x80000400
 reserved1 0
 reserved2 0
Section
  sectname __stubs
   segname __TEXT
      addr 0x0000000100007cb0
      size 0x00000000000000f0
    offset 31920
     align 2^2 (4)
    reloff 0
    nreloc 0
     flags 0x80000408
 reserved1 0 (index into indirect symbol table)
 reserved2 12 (size of stubs)
Section
  sectname __stub_helper
   segname __TEXT
      addr 0x0000000100007da0
      size 0x0000000000000108
    offset 32160
     align 2^2 (4)
    reloff 0
    nreloc 0
     flags 0x80000400
 reserved1 0
 reserved2 0
Section
  sectname __const
   segname __TEXT
      addr 0x0000000100007ea8
      size 0x0000000000000011
    offset 32424
     align 2^1 (2)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __cstring
   segname __TEXT
      addr 0x0000000100007eb9
      size 0x000000000000009b
    offset 32441
     align 2^0 (1)
    reloff 0
    nreloc 0
     flags 0x00000002
 reserved1 0
 reserved2 0
Section
  sectname __unwind_info
   segname __TEXT
      addr 0x0000000100007f54
      size 0x00000000000000ac
    offset 32596
     align 2^2 (4)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Load command 2
      cmd LC_SEGMENT_64
  cmdsize 792
  segname __DATA
   vmaddr 0x0000000100008000
   vmsize 0x0000000000004000
  fileoff 32768
 filesize 16384
  maxprot 0x00000003
 initprot 0x00000003
   nsects 9
    flags 0x0
Section
  sectname __got
   segname __DATA
      addr 0x0000000100008000
      size 0x0000000000000010
    offset 32768
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000006
 reserved1 20 (index into indirect symbol table)
 reserved2 0
Section
  sectname __la_symbol_ptr
   segname __DATA
      addr 0x0000000100008010
      size 0x00000000000000a0
    offset 32784
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000007
 reserved1 22 (index into indirect symbol table)
 reserved2 0
Section
  sectname __mod_init_func
   segname __DATA
      addr 0x00000001000080b0
      size 0x0000000000000008
    offset 32944
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000009
 reserved1 0
 reserved2 0
Section
  sectname __const
   segname __DATA
      addr 0x00000001000080b8
      size 0x0000000000000018
    offset 32952
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __objc_imageinfo
   segname __DATA
      addr 0x00000001000080d0
      size 0x0000000000000008
    offset 32976
     align 2^2 (4)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __swift_hooks
   segname __DATA
      addr 0x00000001000080d8
      size 0x00000000000000b8
    offset 32984
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __data
   segname __DATA
      addr 0x0000000100008190
      size 0x0000000000000015
    offset 33168
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __swift51_hooks
   segname __DATA
      addr 0x00000001000081a8
      size 0x00000000000000b8
    offset 33192
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Section
  sectname __bss
   segname __DATA
      addr 0x0000000100008260
      size 0x00000000000000d8
    offset 0
     align 2^3 (8)
    reloff 0
    nreloc 0
     flags 0x00000001
 reserved1 0
 reserved2 0
Load command 3
      cmd LC_SEGMENT_64
  cmdsize 152
  segname __DATA_CONST
   vmaddr 0x000000010000c000
   vmsize 0x0000000000208000
  fileoff 49152
 filesize 0
  maxprot 0x00000003
 initprot 0x00000003
   nsects 1
    flags 0x0
Section
  sectname __objc_selrefs
   segname __DATA_CONST
      addr 0x000000010000c000
      size 0x00000000002054d2
    offset 0
     align 2^0 (1)
    reloff 0
    nreloc 0
     flags 0x00000001
 reserved1 0
 reserved2 0
Load command 4
      cmd LC_SEGMENT_64
  cmdsize 152
  segname __OBJC
   vmaddr 0x0000000100214000
   vmsize 0x0000000000000000
  fileoff 49152
 filesize 0
  maxprot 0x00000001
 initprot 0x00000001
   nsects 1
    flags 0x0
Section
  sectname __message_refs
   segname __OBJC
      addr 0x0000000100214000
      size 0x0000000000000000
    offset 49152
     align 2^0 (1)
    reloff 0
    nreloc 0
     flags 0x00000000
 reserved1 0
 reserved2 0
Load command 5
      cmd LC_SEGMENT_64
  cmdsize 72
  segname __LINKEDIT
   vmaddr 0x0000000100214000
   vmsize 0x0000000000008000
  fileoff 49152
 filesize 24304
  maxprot 0x00000001
 initprot 0x00000001
   nsects 0
    flags 0x0
Load command 6
            cmd LC_DYLD_INFO_ONLY
        cmdsize 48
     rebase_off 49152
    rebase_size 16
       bind_off 49168
      bind_size 56
  weak_bind_off 0
 weak_bind_size 0
  lazy_bind_off 49224
 lazy_bind_size 416
     export_off 0
    export_size 0
Load command 7
     cmd LC_SYMTAB
 cmdsize 24
  symoff 49672
   nsyms 22
  stroff 50192
 strsize 320
Load command 8
            cmd LC_DYSYMTAB
        cmdsize 80
      ilocalsym 0
      nlocalsym 1
     iextdefsym 1
     nextdefsym 0
      iundefsym 1
      nundefsym 21
         tocoff 0
           ntoc 0
      modtaboff 0
        nmodtab 0
   extrefsymoff 0
    nextrefsyms 0
 indirectsymoff 50024
  nindirectsyms 42
      extreloff 0
        nextrel 0
      locreloff 0
        nlocrel 0
Load command 9
          cmd LC_LOAD_DYLINKER
      cmdsize 32
         name /usr/lib/dyld (offset 12)
Load command 10
     cmd LC_UUID
 cmdsize 24
    uuid 31ED6D91-1868-36F5-89B8-C39FBF7D01E3
Load command 11
      cmd LC_VERSION_MIN_IPHONEOS
  cmdsize 16
  version 10.0
      sdk 15.0
Load command 12
      cmd LC_SOURCE_VERSION
  cmdsize 16
  version 0.0
Load command 13
       cmd LC_MAIN
   cmdsize 24
  entryoff 31896
 stacksize 0
Load command 14
          cmd LC_ENCRYPTION_INFO_64
      cmdsize 24
     cryptoff 28672
    cryptsize 4096
      cryptid 1
          pad 0
Load command 15
          cmd LC_LOAD_DYLIB
      cmdsize 64
         name @rpath/AwemeCore.framework/AwemeCore (offset 24)
   time stamp 2 Thu Jan  1 08:00:02 1970
      current version 1.0.0
compatibility version 1.0.0
Load command 16
          cmd LC_LOAD_DYLIB
      cmdsize 88
         name /System/Library/Frameworks/Foundation.framework/Foundation (offset 24)
   time stamp 2 Thu Jan  1 08:00:02 1970
      current version 1854.0.0
compatibility version 300.0.0
Load command 17
          cmd LC_LOAD_DYLIB
      cmdsize 56
         name /usr/lib/libobjc.A.dylib (offset 24)
   time stamp 2 Thu Jan  1 08:00:02 1970
      current version 228.0.0
compatibility version 1.0.0
Load command 18
          cmd LC_LOAD_DYLIB
      cmdsize 56
         name /usr/lib/libSystem.B.dylib (offset 24)
   time stamp 2 Thu Jan  1 08:00:02 1970
      current version 1311.0.0
compatibility version 1.0.0
Load command 19
          cmd LC_LOAD_DYLIB
      cmdsize 56
         name @rpath/libswiftCore.dylib (offset 24)
   time stamp 2 Thu Jan  1 08:00:02 1970
      current version 1300.0.29
compatibility version 1.0.0
Load command 20
          cmd LC_RPATH
      cmdsize 32
         path /usr/lib/swift (offset 12)
Load command 21
          cmd LC_RPATH
      cmdsize 40
         path @executable_path/Frameworks (offset 12)
Load command 22
      cmd LC_FUNCTION_STARTS
  cmdsize 16
  dataoff 49640
 datasize 32
Load command 23
      cmd LC_DATA_IN_CODE
  cmdsize 16
  dataoff 49672
 datasize 0
Load command 24
      cmd LC_CODE_SIGNATURE
  cmdsize 16
  dataoff 50512
 datasize 22944
```

### 查看是否加密=脱壳

* 未加密
  ```bash
  ➜  Aweme.app otool -l Aweme | grep crypt
      cryptoff 28672
      cryptsize 4096
        cryptid 0
  ```
    * 说明
      * `cryptid 0`：表示未加密 = 已脱壳
* 已加密
  ```bash
  ➜  Aweme.app pwd
  xxx/Aweme抖音/iPhone7-137black/Aweme.app
  ➜  Aweme.app otool -l Aweme | grep crypt
      cryptoff 28672
      cryptsize 4096
        cryptid 1
  ```
    * 说明
      * `cryptid 1`：表示已加密 = 未脱壳

## `-L`

```bash
➜  Aweme.app otool -L Aweme
Aweme:
    @rpath/AwemeCore.framework/AwemeCore (compatibility version 1.0.0, current version 1.0.0)
    /System/Library/Frameworks/Foundation.framework/Foundation (compatibility version 300.0.0, current version 1854.0.0)
    /usr/lib/libobjc.A.dylib (compatibility version 1.0.0, current version 228.0.0)
    /usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1311.0.0)
    @rpath/libswiftCore.dylib (compatibility version 1.0.0, current version 1300.0.29)
```
