# LC_DYLD_EXPORTS_TRIE

* `LC_DYLD_EXPORTS_TRIE`
  * 说明： `iOS 15.0+`新出现的Load Command
  * 含义
    * If the binary is targeted at iOS 14+ or is linked with `-fixup_chains` linker flag, the same information is stored in `LC_DYLD_EXPORTS_TRIE` load command instead. The detail of this change is discussed at [Chained Fixups](https://github.com/qyang-nj/llios/blob/main/dynamic_linking/chained_fixups.md).
