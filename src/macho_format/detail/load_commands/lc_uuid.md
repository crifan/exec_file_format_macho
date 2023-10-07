# LC_UUID

* `LC_UUID`
  * 是什么：Specifies the 128-bit UUID for an image or its corresponding dSYM file
  * 作用：用来标识唯一APP
    * 每个可执行程序都有一个uuid，这样根据不同的uuid能确定包。比如崩溃日志中就会包含uuid字段。表示是哪个包崩溃了
  * 数据结构定义：`uuid_command`

## uuid_command定义

```c
struct uuid_command {
    uint32_t	cmd;		/* LC_UUID */
    uint32_t	cmdsize;	/* sizeof(struct uuid_command) */
    uint8_t	uuid[16];	/* the 128-bit uuid */
};
```

## 举例

* MachOView查看到某`LC_UUID`
  * ![machoview_lc_uuid_example](../../../assets/img/machoview_lc_uuid_example.png)
* [jtool2解析AwemeCore](../../../macho_tool/jtool2/examples/awemecore.md)中`jtool2 -l xxx/AwemeCore`输出的
  ```bash
  LC 09: LC_UUID                   UUID: F1FCF15A-6465-31F0-9300-5BA1B8F91017
  ```
