# LC_DYLD_CHAINED_FIXUPS

* `LC_DYLD_CHAINED_FIXUPS`
  * 说明： `iOS 15.0+`新出现的Load Command
  * 含义
    * Chained fixups is a new way to store information that will be used by `dyld`. Replacing `LC_DYLD_INFO`(_ONLY), the chained fixups can save binary size and reduce launch time.
    * Traditionally, `dyld`, at launch time, needs to slide the fixed addresses with a random number, known as `ASLR`. This operation is called `rebasing`. Also, `dyld` needs to connect symbols from current binary with its linked dynamic libraries. This is called `binding`. Under the new format, both `rebasing` and `binding` have a new name, **fixup**, because they need to be "fixed up" before main function.
    * Chained fixups is enabled by default if the binary is built for device and targeted at iOS 14+. We can also manually enable it by passing `-fixup_chains` to ld. To disable it, use `-no_fixup_chains`.
