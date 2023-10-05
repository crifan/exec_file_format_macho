# AwemeCore

用rabin2查看抖音AwemeCore二进制的信息：

* (1) File Identification
  ```bash
  rabin2 -I v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
  ```
* (2) Entrypoint
  ```bash
  rabin2 -e v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
  ```
* (3) Imports
  ```bash
  rabin2 -i v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore
  ```
* (4) Exports
  ```bash
  rabin2 -E v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_E.txt
  ```
* (5) Symbols
  ```bash
  rabin2 -s v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_s.txt
  rabin2 -sr v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_sr.txt
  ```
* (6) Libraries
  ```bash
  rabin2 -l v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_l.txt
  ```
* (7) Strings
  ```bash
  rabin2 -z v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_z.txt
  rabin2 -zr v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_zr.txt
  ```
* (8) Program Sections
  ```bash
  rabin2 -S v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_S_section.txt
  rabin2 -Sr v18.9.0/Payload/Aweme.app/Frameworks/AwemeCore.framework/AwemeCore > AwemeCore_rabin2_Sr_section.txt
  ```
