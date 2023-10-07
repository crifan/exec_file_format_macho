# 自己编译

* 需求：想要自己编译[gdbinit的MachOView](https://github.com/gdbinit/MachOView)
* 步骤

下载代码：

```bash
git clone https://github.com/gdbinit/MachOView.git
```

双击`machoview.xcodeproj`用XCode打开

即可自己编译

## 常见报错

### unable to find sdk ‘macosx10.9'

* 解决办法
  * `TARGETS`->`Build Settings`->`Architecture`->`Base SDK`，从`macosx 10.9(SDK not found)`改为：`macOS`

### MachOView/FatLayout.mm:9:10: 'string' file not found

* 解决办法
  * `TARGETS`->`Build Settings`->`Deployment`->`macOS Deployment Target`，从`macOS10.7`改为和你当前macOS版本一致或最接近的版本
    * 此处系统是`macOS 11.6`，但此处选项`macOS 11.6`，所以选了最接近的`macOS 11.5`
