# 参考资料

* 【整理】iOS中的XNU
* 【记录】静态分析Mask的动态库：MaskPro.dylib
* 【整理】去研究Mach-O格式
* 【记录】Mach-O格式相关资料
* 【整理】苹果的二进制格式Mach-O的详细定义
* 【整理】Mach-O格式和启动相关
* 【记录】用otool查看分析二进制和库文件信息
* 【记录】用otool去分析抖音二进制AwemeCore
* 【未解决】Mac中用otool查看ELF格式二进制库文件信息
* 【已解决】Mac M2 Max中安装和使用jtool2
* 【记录】用jtool查看抖音二进制信息
* 【规避解决】Mac M2 Max中jtool2运行崩溃：killed
* 【未解决】Mac中找命令行工具运行jtool2报错killed的崩溃日志文件
* 【已解决】iOS逆向：jtool2在Mac M2 Max中运行崩溃AMFI Unrecoverable CT signature issue, bailing out
* 【规避解决】iOS逆向：jtool2在Mac M2 Max中运行崩溃AMFI unsuitable CT policy 0 for this platform/device, rejecting signature
* 【记录】用radare2查看抖音二进制信息
* 【记录】用rabin2查看抖音AwemeCore二进制的信息
* 【部分解决】用MachOView查看抖音二进制AwemeCore的信息
* 【已解决】Mac中编译生成gdbinit的MachOView的app
* 【已解决】用jtool2查看Mach-O的二进制akd找代码段相关信息
* 【已解决】Mach-O中LC相关Load Command的数值定义和含义
* 【已解决】LC_DYLD_CHAINED_FIXUPS和LC_DYLD_EXPORTS_TRIE等Load Command的含义
* 【未解决】Mach-O中_DATA的__la_symbol_ptr含义
* 【未解决】Mach-O中的__got的含义
* 【记录】用MachOView查看分析黑豹动态库zzzzHeiBaoLib.dylib
* 【整理】iOS二进制包含多个架构：FAT
* 【未解决】iOS逆向iOS15的debugserver出错：用lipo瘦身
* 【已解决】iOS逆向iOS15：用lipo给FAT格式瘦身
* 【记录】Mach-O二进制中的VM Address虚拟内存地址和RAW原始地址
* 【已解决】iOS逆向akd：从Mach-O二进制文件akd中查看代码码段opcode二进制数据
* 【已解决】用MachOView查看arm64的akd的代码段相关信息
* 【记录】Mac中用MachOView查看arm64的main二进制
* 
* [可执行文件格式](https://book.crifan.org/books/executable_file_format/website/)
* [可执行文件格式：ELF](https://book.crifan.org/books/exec_file_format_elf/website/)
* 
* [Confusion about mach-o offsets and addresses : jailbreakdevelopers (reddit.com)](https://www.reddit.com/r/jailbreakdevelopers/comments/ol9m1s/confusion_about_macho_offsets_and_addresses/)
* [XLsn0w/Cydia](https://github.com/XLsn0w/Cydia)
* [XNU - 维基百科，自由的百科全书 (wikipedia.org)](https://zh.wikipedia.org/zh-hans/XNU)
* [Kernel - The iPhone Wiki](https://www.theiphonewiki.com/wiki/Kernel)
* [Apple Open Source](https://opensource.apple.com/)
* [Source Browser (apple.com)](https://opensource.apple.com/source/xnu/)
* [iOS/Mach_and_BSD.md at master · writeups/iOS · GitHub](https://github.com/writeups/iOS/blob/master/About%20iOS/Mach_and_BSD.md)
* [Mach-O - Wikipedia](https://en.wikipedia.org/wiki/Mach-O)
* [Introduction to Code Size Performance Guidelines (apple.com)](https://developer.apple.com/library/archive/documentation/Performance/Conceptual/CodeFootprint/CodeFootprint.html#//apple_ref/doc/uid/10000149-SW1)
* [aidansteele/osx-abi-macho-file-format-reference: Mirror of OS X ABI Mach-O File Format Reference (github.com)](https://github.com/aidansteele/osx-abi-macho-file-format-reference)
* [Understanding the Mach-O File Format | by Travis Matthews | Medium](https://medium.com/@travmath/understanding-the-mach-o-file-format-66cf0354e3f4)
* [Parsing Mach-O files - Low Level Bits](https://lowlevelbits.org/parsing-mach-o-files/)
* [Mach-O Executables · objc.io](https://www.objc.io/issues/6-build-tools/mach-o-executables/)
* [The Mach-O binary file format - Mobile Application Penetration Testing [Book] (oreilly.com)](https://www.oreilly.com/library/view/mobile-application-penetration/9781785883378/ch02s14.html)
* [Understanding the Mach-O File Format - DEV Community](https://dev.to/travmatth/understanding-the-mach-o-file-format-aeh)
* [Overview of Mach-O binary | Efiens Blog](https://blog.efiens.com/post/luibo/osx/macho/)
* [So Macho - A look at Apple executable files | Red Maple Technologies](https://redmaple.tech/blogs/macho-files/)
* [How to Reverse Engineer an iOS App and macOS Software | Apriorit](https://www.apriorit.com/dev-blog/363-how-to-reverse-engineer-os-x-and-ios-software)
* [A Deep Dive into Core Dumps on iOS · iOS Snapshot Fuzzing (tkopf.de)](https://tkopf.de/posts/deep-dive-core-dump/)
* [iOS/Bypassing-AMFI.md at master · writeups/iOS · GitHub](https://github.com/writeups/iOS/blob/master/About%20iOS/Bypassing-AMFI.md)
* [iOS/Mach-O.md at master · writeups/iOS · GitHub](https://github.com/writeups/iOS/blob/master/About%20iOS/Mach-O.md)
* [iOS dyld - 简书 (jianshu.com)](https://www.jianshu.com/p/6894d0f08a44)
* [Package ld - The Go Programming Language (google.cn)](https://golang.google.cn/pkg/cmd/link/internal/ld/)
* [osx-abi-macho-file-format-reference/Mach-O_File_Format.pdf at master · aidansteele/osx-abi-macho-file-format-reference (github.com)](https://github.com/aidansteele/osx-abi-macho-file-format-reference/blob/master/Mach-O_File_Format.pdf)
* [Mac Dev Center: Mac OS X ABI Mach-O File Format Reference](https://web.archive.org/web/20090901205800/http://developer.apple.com/mac/library/documentation/DeveloperTools/Conceptual/MachORuntime/Reference/reference.html)
* [aidansteele/osx-abi-macho-file-format-reference: Mirror of OS X ABI Mach-O File Format Reference (github.com)](https://github.com/aidansteele/osx-abi-macho-file-format-reference)
* [Overview of the Mach-O Executable Format (apple.com)](https://developer.apple.com/library/archive/documentation/Performance/Conceptual/CodeFootprint/Articles/MachOOverview.html)
* [Position-Independent Code](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/MachOTopics/1-Articles/dynamic_code.html#//apple_ref/doc/uid/TP40002528)
* [Mach-O文件结构理解 | LJ小窝 (jianli2017.top)](https://jianli2017.top/wiki/IOS/MachO/MachO_FileStructure/)
* [Edgar's Blog (tbfungeek.github.io)](https://tbfungeek.github.io/page/7/)
* [Building Mach-O Files (apple.com)](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/MachOTopics/1-Articles/building_files.html#//apple_ref/doc/uid/TP40001828-SW1)
* [Crack prevention - iPhone Development Wiki](https://iphonedev.wiki/index.php/Crack_prevention#PT_DENY_ATTACH)
* [iOS逆向----iOS11以后绕过越狱检测-CSDN博客](https://blog.csdn.net/youshaoduo/article/details/90208238)
* [0xced/class-dump at swift-binaries (github.com)](https://github.com/0xced/class-dump/tree/swift-binaries)
* [Symbolicating iOS Crash Reports and Logs | Bugsnag Blog](https://www.bugsnag.com/blog/symbolicating-ios-crashes)
* [求教optool的使用方法 - 技术讨论 | Discussion - iOSRE](https://iosre.com/t/optool/2011)
* [编写dylib_iOS逆向-无需越狱注入动态库 - CodeAntenna](https://codeantenna.com/a/DaRNYIkqzy)
* [excitedplus1s/jtool2: jtool2 support Mac arm64 and x86_64](https://github.com/excitedplus1s/jtool2)
* [Rabin2 - The Official Radare2 Book](https://book.rada.re/tools/rabin2/intro.html)
* [File Identification - The Official Radare2 Book](https://book.rada.re/tools/rabin2/file_identification.html)
* [Imports - The Official Radare2 Book](https://book.rada.re/tools/rabin2/imports.html)
* [Exports - The Official Radare2 Book](https://book.rada.re/tools/rabin2/exports.html)
* [Symbols - The Official Radare2 Book](https://book.rada.re/tools/rabin2/symbols.html)
* [Libraries - The Official Radare2 Book](https://book.rada.re/tools/rabin2/libraries.html)
* [Strings - The Official Radare2 Book](https://book.rada.re/tools/rabin2/strings.html)
* [Program Sections - The Official Radare2 Book](https://book.rada.re/tools/rabin2/program_sections.html)
* [JTool2 - Taking the O out of otool - squared (newosxbook.com)](http://www.newosxbook.com/tools/jtool.html#pages)
* [MachO文件格式 (liangmc.com)](https://liangmc.com/archives/macho-wen-jian-ge-shi)
* [Mach-O/README.md at master · XLsn0w/Mach-O (github.com)](https://github.com/XLsn0w/Mach-O/blob/master/README.md)
* [XLsn0w/Mach-O: Mach-O其实是Mach Object文件格式的缩写，是macOS以及iOS上可执行文件的格式 (github.com)](https://github.com/XLsn0w/Mach-O)
* [How to Reverse Engineer and Patch an iOS Application for Beginners: Part I (inversecos.com)](https://www.inversecos.com/2022/06/how-to-reverse-engineer-and-patch-ios.html)
* [pagestuff(1) [osx man page] (unix.com)](https://www.unix.com/man-page/osx/1/pagestuff/)
* [Mach-O文件介绍之ASLR(进程地址空间布局随机化) | ctinusDev's Blog](https://ctinusdev.github.io/2017/08/20/Mach-OBasis_ASLR/)
* [Jailbreak Detection • Sandbox integrity (slideshare.net)](https://www.slideshare.net/gersic/security-best-practices-for-mobile-development-dreamforce-2013/46-Jailbreak_Detection_Sandbox_integrity_check)
* [macho.rs - source (docs.rs)](https://docs.rs/object/0.24.0/src/object/macho.rs.html#666)
* [llios/chained_fixups.md at main · qyang-nj/llios (github.com)](https://github.com/qyang-nj/llios/blob/main/dynamic_linking/chained_fixups.md)
* [llios/README.md at main · qyang-nj/llios (github.com)](https://github.com/qyang-nj/llios/blob/main/exported_symbol/README.md)
* [iOS逆向分析笔记 - 简书 (jianshu.com)](https://www.jianshu.com/p/157f56d60a59)
* [iOS-Reverse/README.md at master · XLsn0w/iOS-Reverse (github.com)](https://github.com/XLsn0w/iOS-Reverse/blob/master/README.md)
* [[iOS 逆向 12] 加密与动态保护_Eric's Blog-程序员ITS404 - 程序员ITS404](https://www.its404.com/article/m0_38076563/105877079)
* [探究Mach-O文件 - 掘金 (juejin.cn)](https://juejin.cn/post/6850418121506586632)
* [Principle of Dynamic Linking of Imported Functions in Mach-O (apriorit.com)](https://www.apriorit.com/dev-blog/225-dynamic-linking-mach-o)
* [图解 Mach-O 中的 got - 掘金 (juejin.cn)](https://juejin.cn/post/6918645161303998478)
* [Understanding Concepts of VA, RVA and File Offsets (tech-zealots.com)](https://tech-zealots.com/malware-analysis/understanding-concepts-of-va-rva-and-offset/)
* [ida - Mach-O : Convert virtual address to file offset on disk - Reverse Engineering Stack Exchange](https://reverseengineering.stackexchange.com/questions/15221/mach-o-convert-virtual-address-to-file-offset-on-disk)
* [disassembly - Convert Mach-O VM Address To File Offset - Reverse Engineering Stack Exchange](https://reverseengineering.stackexchange.com/questions/8177/convert-mach-o-vm-address-to-file-offset)
* [iOS Tampering and Reverse Engineering - OWASP Mobile Application Security](https://mas.owasp.org/MASTG/iOS/0x06c-Reverse-Engineering-and-Tampering/#unicorn)
* [今日头条优化实践： iOS 包大小二进制优化，一行代码减少 60 MB 下载大小_移动_字节跳动技术团队_InfoQ精选文章](https://www.infoq.cn/article/xujl32htdkyqakz0hkmm)
* 