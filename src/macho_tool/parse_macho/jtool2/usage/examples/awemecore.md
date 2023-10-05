# AwemeCore

## -h：查看header头信息

```bash
➜  AwemeCore jtool2 -h v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
Magic:    64-bit MachO (Little Endian)
Type:    dylib
CPU:    ARM64 (ARMv8)
Cmds:    133
Size:    18720
Flags:    0x910085
```

## list列出段

```bash
jtool2 -l v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
```

## 查看使用了哪些共享库Library

```bash
jtool2 -L v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
```

## 列出符号表Symbol == nm

```bash
jtool2 -S v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_jtool2_S.txt
```

## 分析analyze -》 导出类和函数名等

```bash
jtool2 --analyze v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
```

总体来说，还是有点用的。尤其是`--analyze`
