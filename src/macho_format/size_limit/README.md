# Mach-O大小限制

Apple会对iOS的app的大小做一定的限制，防止太大，影响用户下载（的体验）。

## iOS的app的大小限制历史

若下载大小超过限制，将无法使用蜂窝网络下载App（`iOS 13 `之前），会收到文件容量太大的提示，需通过 Wi-Fi 网络下载。如下，为苹果历年来对 App 下载大小限制的变化情况：

* 2008 年 7 月，搭载了 App Store 的 iPhone 3G 正式发售，下载限制仅为 10 MB
* 2010 年 2 月，苹果将 iPhone 3G 的下载限制从 10 MB 提升到 20 MB
* 2012 年 3 月，iOS 5.1 正式版后，下载限制从 20 MB 提升到 50 MB
* 2013 年 9 月，iOS 7 正式版后，下载限制从 50 MB 提升至 100 MB
* 2017 年 9 月，iOS 11 正式版后，下载限制从 100 MB 提升至 150 MB
* 2019 年 5 月，下载限制从 150 MB 提升至 200 MB
* 2019 年 9 月，iOS 13 正式版后，若下载大小超过 200 MB，用户可选择是否使用蜂窝网络下载

如今，App 下载大小超出 200 MB 时 ，会出现两种情况：

* iOS 13 以下的用户，无法通过蜂窝数据下载 App
  * ![ios_app_size_200mb_warn](../../assets/img/ios_app_size_200mb_warn.png)
* iOS 13 及以上的用户，需要手动设置才可以使用蜂窝网络下载 App
  * ![ios_app_size_200mb_settings](../../assets/img/ios_app_size_200mb_settings.png)
  
## Mach-O可执行文件大小限制

苹果对可执行文件大小亦有明确限制，超过该限制会导致 App 审核被拒：

> ERROR: ERROR ITMS-90122: "Invalid ExecutaBe Size. The size of your app's executaBe file 'News.app/News' is 68534272 bytes for architecture 'arm64', which exceeds the maximum allowed size of 60 MB."

具体限制如下：

* `iOS <7.0`：二进制文件中所有的`__TEXT`段总和不得超过**80 MB**
* `iOS 7.x`~`iOS 8.x`：二进制文件中，每个特定架构中的`__TEXT`段不得超过**60 MB**
* `iOS >9.0`：二进制文件中所有的`__TEXT`段总和不得超过**500 MB**
