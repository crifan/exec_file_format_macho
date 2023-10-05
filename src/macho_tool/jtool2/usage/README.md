# jtool2用法

* `-h`：查看基本头文件header信息
  ```bash
  jtool2 -h yourBinary
  ```
* `-l`：列出段
  ```bash
  jtool2 -l yourBinary
  ```
* `-L`：查看使用了哪些共享库Library
  ```bash
  jtool2 -L yourBinary
  ```
* `-S`：列出符号表Symbol == nm
  ```bash
  jtool2 -S yourBinary
  ```
* `--analyze`：分析analyze -》 导出类和函数名等
  ```bash
  jtool2 --analyze yourBinary
  ```
