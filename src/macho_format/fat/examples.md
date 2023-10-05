# FAT举例

* 注：可以用`file`：查看Mach-O的文件类型
  * 语法：`file inputMacOFile`

## FAT格式的rsync

```bash
➜  ~ which rsync
/usr/bin/rsync
➜  ~ file /usr/bin/rsync
/usr/bin/rsync: Mach-O universal binary with 2 architectures: [x86_64:Mach-O 64-bit executable x86_64] [arm64e:Mach-O 64-bit executable arm64e]
/usr/bin/rsync (for architecture x86_64):    Mach-O 64-bit executable x86_64
/usr/bin/rsync (for architecture arm64e):    Mach-O 64-bit executable arm64e
```

## FAT格式的adb

```bash
➜  platform-tools pwd
/Users/crifan/dev/dev_tool/android/AndroidSDK/platform-tools
➜  platform-tools ll
total 49520
...
-rwxr-xr-x@ 1 crifan  staff    13M  7 24 15:26 adb
...
➜  platform-tools file adb
adb: Mach-O universal binary with 2 architectures: [x86_64:Mach-O 64-bit executable x86_64] [arm64]
adb (for architecture x86_64):    Mach-O 64-bit executable x86_64
adb (for architecture arm64):    Mach-O 64-bit executable arm64
```

## FAT格式的lldb

```bash
➜  ~ file /usr/bin/lldb
/usr/bin/lldb: Mach-O universal binary with 2 architectures: [x86_64:Mach-O 64-bit executable x86_64] [arm64e:Mach-O 64-bit executable arm64e]
/usr/bin/lldb (for architecture x86_64):    Mach-O 64-bit executable x86_64
/usr/bin/lldb (for architecture arm64e):    Mach-O 64-bit executable arm64e
```

## FAT格式的RevealServer

```bash
crifan@licrifandeMacBook-Pro  ~/dev/dev_tool/reverse_security/iOS/Tweak/Reveal2Loader/lemon4ex  file Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer: Mach-O universal binary with 5 architectures: [i386:Mach-O dynamically linked shared library i386] [x86_64] [arm_v7] [arm64] [arm64e]
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer (for architecture i386):    Mach-O dynamically linked shared library i386
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer (for architecture x86_64):    Mach-O 64-bit dynamically linked shared library x86_64
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer (for architecture armv7):    Mach-O dynamically linked shared library arm_v7
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer (for architecture arm64):    Mach-O 64-bit dynamically linked shared library arm64
Reveal2Loader/Reveal2Loader/Package/Library/Frameworks/RevealServer.framework/RevealServer (for architecture arm64e):    Mach-O 64-bit dynamically linked shared library arm64e
```
