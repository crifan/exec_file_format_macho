# __OBJC

* segment:`__OBJC`
  * 相关解释
    * Objective-C是一种Reflection反射型语言，可以在运行时获取和修改自身状态，其中的实现存在于`libobjc.A.dylib`库中，这些“运行时”能力源于objective-c类结构组织较为灵活，并提供了操作自身结构的接口，同时在生成的可执行文件(`Mach-O`)中存在`__OBJC`段，这些节中提供了足够的类构成信息，而Mac端gdb可以解析这些结构，而正由于objc提供了如此多的信息，因此也比c++在同等情况下逆向难度低一些。
