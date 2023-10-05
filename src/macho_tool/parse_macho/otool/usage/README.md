# otool用法

* 单个参数
  * `-l`: print the load commands
    ```bash
    otool -l iOSBinaryFile > iOSBinaryFile_otool_l.txt
    ```
  * `-o`: print the Objective-C segment
  * `-V`: print disassembled operands symbolically
* 参数组合
  ```bash
  otool -oV iOSBinaryFile > iOSBinaryFile_otool_oV.txt
  ```
