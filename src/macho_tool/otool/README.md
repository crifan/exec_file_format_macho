# otool

TODO：

* 【记录】用otool查看分析二进制和库文件信息
* 【记录】用otool去分析抖音二进制AwemeCore
* 【未解决】iOS中从otool输出的B16@0:8搞懂函数类型和参数定义

---

* `otool`
  * =`object file displaying tool`
  * 是什么：查看目标文件信息的工具
  * 用途：用来发现应用中使用到了哪些系统库，调用了其中哪些方法，使用了库中哪些对象及属性
    * 比如
      * 查看iOS的`Mach-O`格式的二进制文件的信息
  * 来源：Xcode自带的常用工具
* 相关
  * 比otool更好的：`jtool`
  * `otool`的`GUI`版：`otx`
    * x43x61x69/otx: The Mach-O disassembler. Now 64bit and Xcode 6 compatible.
      * https://github.com/x43x61x69/otx

## 下载安装otool

Mac自带otool，无需额外安装。

查看当前otool位置：

```bash
✘ crifan@licrifandeMacBook-Pro  ~  which otool
/usr/bin/otool
```

当前版本：

```bash
✘ crifan@licrifandeMacBook-Pro  ~  otool --version
llvm-otool(1): Apple Inc. version cctools-927.0.2
Apple LLVM version 10.0.1 (clang-1001.0.46.4)
  Optimized build.
  Default target: x86_64-apple-darwin19.2.0
  Host CPU: broadwell

  Registered Targets:
    aarch64    - AArch64 (little endian)
    aarch64_be - AArch64 (big endian)
    arm        - ARM
    arm64      - ARM64 (little endian)
    armeb      - ARM (big endian)
    thumb      - Thumb
    thumbeb    - Thumb (big endian)
    x86        - 32-bit X86: Pentium-Pro and above
    x86-64     - 64-bit X86: EM64T and AMD64
```
