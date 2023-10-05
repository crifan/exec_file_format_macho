# XNU

* `XUN`
  * 名称
    * `XNU`= **X** is **N**ot **U**nix
  * 概述
    * 英文
      * XNU kernel is part of the Darwin operating system for use in macOS and iOS operating systems. 
    * 中文
      * XNU是：iOS（和tvOS、watchOS）的（操作系统）内核
      * XNU也是Darwin的一部分
        * Darwin是MacOS的操作系统内核
  * 特点
    * XNU is a hybrid kernel combining the Mach kernel developed at Carnegie Mellon University with components from FreeBSD and a C++ API for writing drivers called IOKit. XNU runs on x86_64 for both single processor and multi-processor configurations.
  * （开源代码）源码
    * [opensource.apple.com](http://opensource.apple.com/)
      * [Source Browser (apple.com)](https://opensource.apple.com/source/xnu/)
    * Github
      * https://github.com/apple/darwin-xnu
        * apple/darwin-xnu: The Darwin Kernel (mirror)
  * XNU组成
    * 2个主要部分
      * Mach：微内核=microkernel
        * 实现了操作系统的核心部分
      * BSD：内核=kernel
        * BSD在Mach的基础上，实现了更高层的各种功能
  * 代码组成=代码树
    * `config` - configurations for exported apis for supported architecture and platform
    * `SETUP` - Basic set of tools used for configuring the kernel, versioning and kextsymbol management.
    * `EXTERNAL_HEADERS` - Headers sourced from other projects to avoid dependency cycles when building. These headers should be regularly synced when source is updated.
    * `libkern` - C++ IOKit library code for handling of drivers and kexts.
    * `libsa` - kernel bootstrap code for startup
    * `libsyscall` - syscall library interface for userspace programs
    * `libkdd` - source for user library for parsing kernel data like kernel chunked data.
    * `makedefs` - top level rules and defines for kernel build.
    * `osfmk` - Mach kernel based subsystems
    * `pexpert` - Platform specific code like interrupt handling, atomics etc.
    * `security` - Mandatory Access Check policy interfaces and related implementation.
    * `bsd` - BSD subsystems code
    * `tools` - A set of utilities for testing, debugging and profiling kernel.

## 查看系统信息中会有XNU的版本等信息

* iOS 15.1，iPhone8的信息
  ```bash
  iPhone8-150:~ root# uname -a
  Darwin iPhone8-150 21.0.0 Darwin Kernel Version 21.0.0: Sun Aug 15 20:55:55 PDT 2021; root:xnu-8019.12.5~1/RELEASE_ARM64_T8015 iPhone10,1 arm Darwin
  ```
  * `xnu-8019.12.5~1/RELEASE_ARM64_T8015`
    * xnu是：iOS的内核
      * 版本是：8019.12.5
