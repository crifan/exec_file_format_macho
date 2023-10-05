# rabin2用法

* `-I`: File **I**dentification
  ```bash
  rabin2 -I binaryFile
  ```
* `-e`: **E**ntrypoint
  ```bash
  rabin2 -e binaryFile
  ```
* `-i`: **I**mports
  ```bash
  rabin2 -i binaryFile
  ```
* `-E`: **E**xports
  ```bash
  rabin2 -E binaryFile
  ```
* `-s`: **S**ymbols
  ```bash
  rabin2 -s binaryFile
  ```
* `-l`: **L**ibraries
  ```bash
  rabin2 -l binaryFile
  ```
* `-z`: Strings
  ```bash
  rabin2 -z binaryFile
  ```
* `S`: Program **S**ections
  ```bash
  rabin2 -S binaryFile
  ```

## 心得

很多的参数，都可以加上r，表示（输出内容是一致的，但是格式不同）以radare格式输出

举例：

```bash
rabin2 -I
rabin2 -Ir

rabin2 -s
rabin2 -sr

rabin2 -z
rabin2 -zr

rabin2 -S
rabin2 -Sr
```
