# rabin2用法举例：MaskPro.dylib

## `-I`

```bash
➜  DynamicLibraries rabin2 -I MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_I_identification.txt
```

输出：

```bash
arch     arm
baddr    0x0
binsz    311296
bintype  mach0
bits     32
canary   true
class    MACH0
crypto   false
endian   little
havecode true
laddr    0x0
lang     objc with blocks
linenum  false
lsyms    false
machine  v7
maxopsz  4
minopsz  4
nx       false
os       ios
pcalign  4
pic      false
relocs   false
sanitiz  false
static   false
stripped true
subsys   darwin
va       true
```

## `-i`

```bash
➜  DynamicLibraries rabin2 -i MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_i_imports.txt
```

输出：

```bash
[Imports]
nth vaddr      bind type           lib name
―――――――――――――――――――――――――――――――――――――――――――
0   0x0003b124 NONE FUNC               CC_MD5
1   0x0003b134 NONE FUNC               MGCopyAnswer
2   0x0003b144 NONE FUNC               MSHookFunction
3   0x0003b154 NONE FUNC               MSHookMessageEx
4   0x0003b164 NONE FUNC               NSClassFromString
5   0x00000000 NONE FUNC               NSFileSystemFreeSize
6   0x0003b174 NONE FUNC               NSHomeDirectory
7   0x00000000 NONE OBJC_CLASS         ASIdentifierManager
8   0x00000000 NONE OBJC_CLASS         NSBundle
9   0x00000000 NONE OBJC_CLASS         NSData
10  0x00000000 NONE OBJC_CLASS         NSDate
11  0x00000000 NONE OBJC_CLASS         NSDateFormatter
12  0x00000000 NONE OBJC_CLASS         NSDictionary
13  0x00000000 NONE OBJC_CLASS         NSFileManager
14  0x00000000 NONE OBJC_CLASS         NSJSONSerialization
15  0x00000000 NONE OBJC_CLASS         NSMutableData
16  0x00000000 NONE OBJC_CLASS         NSMutableDictionary
17  0x00000000 NONE OBJC_CLASS         NSMutableString
18  0x00000000 NONE OBJC_CLASS         NSMutableURLRequest
19  0x00000000 NONE OBJC_CLASS         NSNumber
20  0x00000000 NONE OBJC_CLASS         NSObject
21  0x00000000 NONE OBJC_CLASS         NSString
22  0x00000000 NONE OBJC_CLASS         NSTimeZone
23  0x00000000 NONE OBJC_CLASS         NSURL
24  0x00000000 NONE OBJC_CLASS         NSURLConnection
25  0x00000000 NONE OBJC_CLASS         NSURLRequest
26  0x00000000 NONE OBJC_CLASS         NSURLSession
27  0x00000000 NONE OBJC_CLASS         NSURLSessionConfiguration
28  0x00000000 NONE OBJC_CLASS         UIDevice
29  0x00000000 NONE OBJC_METACLASS     NSObject
30  0x0003b184 NONE FUNC               _Block_object_assign
31  0x0003b194 NONE FUNC               _Block_object_dispose
32  0x00000000 NONE FUNC               _NSConcreteGlobalBlock
33  0x00000000 NONE FUNC               _NSConcreteStackBlock
34  0x0003b1a4 NONE FUNC               _Unwind_SjLj_Register
35  0x0003b1b4 NONE FUNC               _Unwind_SjLj_Resume
36  0x0003b1c4 NONE FUNC               _Unwind_SjLj_Unregister
37  0x00000000 NONE FUNC               __CFConstantStringClassReference
38  0x0003b1d4 NONE FUNC               __assert_rtn
39  0x00000000 NONE FUNC               __gxx_personality_sj0
40  0x00000000 NONE FUNC               __objc_personality_v0
41  0x0003b1e4 NONE FUNC               __stack_chk_fail
42  0x00000000 NONE FUNC               __stack_chk_guard
43  0x0003b1f4 NONE FUNC               _dyld_get_image_vmaddr_slide
44  0x00000000 NONE FUNC               _objc_empty_cache
45  0x0003b204 NONE FUNC               dispatch_async
46  0x0003b214 NONE FUNC               dispatch_get_global_queue
47  0x0003b224 NONE FUNC               dispatch_semaphore_create
48  0x0003b234 NONE FUNC               dispatch_semaphore_signal
49  0x0003b244 NONE FUNC               dispatch_semaphore_wait
50  0x0003b254 NONE FUNC               dispatch_time
51  0x0003b264 NONE FUNC               dlclose
52  0x0003b274 NONE FUNC               dlopen
53  0x0003b284 NONE FUNC               dlsym
54  0x0003b294 NONE FUNC               exit
55  0x0003b2a4 NONE FUNC               free
56  0x0003b2b4 NONE FUNC               getpid
57  0x0003b2c4 NONE FUNC               ioctl
58  0x0003b2d4 NONE FUNC               isatty
59  0x0003b2e4 NONE FUNC               malloc
60  0x0003b2f4 NONE FUNC               memset
61  0x0003b304 NONE FUNC               objc_autorelease
62  0x0003b314 NONE FUNC               objc_autoreleaseReturnValue
63  0x0003b324 NONE FUNC               objc_getClass
64  0x0003b334 NONE FUNC               objc_msgSend
65  0x0003b344 NONE FUNC               objc_release
66  0x0003b354 NONE FUNC               objc_retain
67  0x0003b364 NONE FUNC               objc_retainAutorelease
68  0x0003b374 NONE FUNC               objc_retainAutoreleasedReturnValue
69  0x0003b384 NONE FUNC               perror
70  0x0003b394 NONE FUNC               pthread_create
71  0x0003b3a4 NONE FUNC               sleep
72  0x0003b3b4 NONE FUNC               strstr
73  0x0003b3c4 NONE FUNC               syscall
74  0x0003b3d4 NONE FUNC               sysctl
75  0x0003b3e4 NONE FUNC               uname
76  0x00000000 NONE FUNC               dyld_stub_binder
```

## `-E`

```bash
➜  DynamicLibraries rabin2 -E MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_E_exports.txt
```

输出：

```bash
[Exports]

nth paddr       vaddr      bind   type size lib name
――――――――――――――――――――――――――――――――――――――――――――――――――――
0    0x0004089c 0x0003c89c GLOBAL FUNC 0        _OBJC_CLASS_$_NbGzxsksqtAxgN
1    0x0004084c 0x0003c84c GLOBAL FUNC 0        _OBJC_CLASS_$_NxNXRxsbBxexSx
2    0x00040874 0x0003c874 GLOBAL FUNC 0        _OBJC_CLASS_$_daAxbxbayGwxtxdcca
3    0x000408c4 0x0003c8c4 GLOBAL FUNC 0        _OBJC_CLASS_$_xrxleWZnuCXPEx
4    0x000408ec 0x0003c8ec GLOBAL FUNC 0        _OBJC_CLASS_$_xxWxKxrETCxJpx
5    0x00040888 0x0003c888 GLOBAL FUNC 0        _OBJC_METACLASS_$_NbGzxsksqtAxgN
6    0x00040838 0x0003c838 GLOBAL FUNC 0        _OBJC_METACLASS_$_NxNXRxsbBxexSx
7    0x00040860 0x0003c860 GLOBAL FUNC 0        _OBJC_METACLASS_$_daAxbxbayGwxtxdcca
8    0x000408b0 0x0003c8b0 GLOBAL FUNC 0        _OBJC_METACLASS_$_xrxleWZnuCXPEx
9    0x000408d8 0x0003c8d8 GLOBAL FUNC 0        _OBJC_METACLASS_$_xxWxKxrETCxJpx
10   0x00043420 0x0003f420 GLOBAL FUNC 0        _g_slide
11   0x00043564 0x0003f564 GLOBAL FUNC 0        _x
12   0x00043568 0x0003f568 GLOBAL FUNC 0        _x.146
13   0x0004356c 0x0003f56c GLOBAL FUNC 0        _x.148
...
119  0x00043444 0x0003f444 GLOBAL FUNC 0        _y.380
120  0x00043448 0x0003f448 GLOBAL FUNC 0        _y.382
```

## `-l`

```bash
➜  DynamicLibraries rabin2 -l MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_l_libraries.txt
```

输出：

```bash
[Linked libraries]
/System/Library/Frameworks/AdSupport.framework/AdSupport
/usr/lib/libMobileGestalt.dylib
/System/Library/Frameworks/UIKit.framework/UIKit
/System/Library/Frameworks/Foundation.framework/Foundation
/Library/Frameworks/CydiaSubstrate.framework/CydiaSubstrate
/usr/lib/libobjc.A.dylib
/usr/lib/libc++.1.dylib
/usr/lib/libSystem.B.dylib
/System/Library/Frameworks/CoreFoundation.framework/CoreFoundation

9 libraries
```

## `-z`

```bash
➜  DynamicLibraries rabin2 -z MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_z_strings.txt
```

输出：

```bash
[Strings]
nth paddr      vaddr      len size section                   type  string
―――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――――
0   0x0003b634 0x0003b634 13  14   3.__TEXT.__objc_methname  ascii currentDevice
1   0x0003b642 0x0003b642 4   5    3.__TEXT.__objc_methname  ascii name
2   0x0003b647 0x0003b647 13  14   3.__TEXT.__objc_methname  ascii systemVersion
3   0x0003b655 0x0003b655 10  11   3.__TEXT.__objc_methname  ascii systemName
4   0x0003b660 0x0003b660 14  15   3.__TEXT.__objc_methname  ascii xJWlxsPxxExAux
5   0x0003b66f 0x0003b66f 19  20   3.__TEXT.__objc_methname  ascii identifierForVendor
6   0x0003b683 0x0003b683 10  11   3.__TEXT.__objc_methname  ascii UUIDString
7   0x0003b68e 0x0003b68e 13  14   3.__TEXT.__objc_methname  ascii sharedManager
8   0x0003b69c 0x0003b69c 21  22   3.__TEXT.__objc_methname  ascii advertisingIdentifier
9   0x0003b6b2 0x0003b6b2 29  30   3.__TEXT.__objc_methname  ascii dictionaryWithObjectsAndKeys:
10  0x0003b6d0 0x0003b6d0 14  15   3.__TEXT.__objc_methname  ascii URLWithString:
11  0x0003b6df 0x0003b6df 39  40   3.__TEXT.__objc_methname  ascii stringWithContentsOfURL:encoding:error:
12  0x0003b707 0x0003b707 10  11   3.__TEXT.__objc_methname  ascii hasPrefix:
13  0x0003b712 0x0003b712 24  25   3.__TEXT.__objc_methname  ascii deleteCharactersInRange:
14  0x0003b72b 0x0003b72b 6   7    3.__TEXT.__objc_methname  ascii length
15  0x0003b732 0x0003b732 17  18   3.__TEXT.__objc_methname  ascii substringToIndex:
16  0x0003b744 0x0003b744 18  19   3.__TEXT.__objc_methname  ascii dataUsingEncoding:
17  0x0003b757 0x0003b757 33  34   3.__TEXT.__objc_methname  ascii JSONObjectWithData:options:error:
18  0x0003b779 0x0003b779 24  25   3.__TEXT.__objc_methname  ascii objectForKeyedSubscript:
19  0x0003b792 0x0003b792 27  28   3.__TEXT.__objc_methname  ascii stringWithCString:encoding:
20  0x0003b7ae 0x0003b7ae 16  17   3.__TEXT.__objc_methname  ascii isEqualToString:
21  0x0003b7bf 0x0003b7bf 14  15   3.__TEXT.__objc_methname  ascii eKGEGSRRxxxPxt
22  0x0003b7ce 0x0003b7ce 14  15   3.__TEXT.__objc_methname  ascii PHcNExxxUJIxxH
23  0x0003b7dd 0x0003b7dd 14  15   3.__TEXT.__objc_methname  ascii graGqxxPtxaoBY
24  0x0003b7ec 0x0003b7ec 14  15   3.__TEXT.__objc_methname  ascii xHvTCxxxxxXVxm
25  0x0003b7fb 0x0003b7fb 15  16   3.__TEXT.__objc_methname  ascii bundleWithPath:
26  0x0003b80b 0x0003b80b 4   5    3.__TEXT.__objc_methname  ascii load
27  0x0003b810 0x0003b810 18  19   3.__TEXT.__objc_methname  ascii numberWithInteger:
28  0x0003b823 0x0003b823 63  64   3.__TEXT.__objc_methname  ascii setAppWirelessDataOption:forBundleIdentifier:completionHandler:
29  0x0003b863 0x0003b863 14  15   3.__TEXT.__objc_methname  ascii numberWithInt:
30  0x0003b872 0x0003b872 64  65   3.__TEXT.__objc_methname  ascii setAppCellularDataEnabled:forBundleIdentifier:completionHandler:
31  0x0003b8b3 0x0003b8b3 14  15   3.__TEXT.__objc_methname  ascii sharedInstance
32  0x0003b8c2 0x0003b8c2 40  41   3.__TEXT.__objc_methname  ascii setUsagePoliciesForBundle:cellular:wifi:
33  0x0003b8eb 0x0003b8eb 40  41   3.__TEXT.__objc_methname  ascii resolveNetworkProblmeForAppWithBundleId:
34  0x0003b914 0x0003b914 4   5    3.__TEXT.__objc_methname  ascii date
35  0x0003b919 0x0003b919 5   6    3.__TEXT.__objc_methname  ascii alloc
36  0x0003b91f 0x0003b91f 4   5    3.__TEXT.__objc_methname  ascii init
37  0x0003b924 0x0003b924 17  18   3.__TEXT.__objc_methname  ascii timeZoneWithName:
38  0x0003b936 0x0003b936 12  13   3.__TEXT.__objc_methname  ascii setTimeZone:
39  0x0003b943 0x0003b943 14  15   3.__TEXT.__objc_methname  ascii setDateFormat:
40  0x0003b952 0x0003b952 15  16   3.__TEXT.__objc_methname  ascii stringFromDate:
41  0x0003b962 0x0003b962 14  15   3.__TEXT.__objc_methname  ascii defaultManager
42  0x0003b971 0x0003b971 36  37   3.__TEXT.__objc_methname  ascii attributesOfFileSystemForPath:error:
43  0x0003b996 0x0003b996 13  14   3.__TEXT.__objc_methname  ascii objectForKey:
44  0x0003b9a4 0x0003b9a4 11  12   3.__TEXT.__objc_methname  ascii stringValue
45  0x0003b9b0 0x0003b9b0 40  41   3.__TEXT.__objc_methname  ascii initWithURL:cachePolicy:timeoutInterval:
46  0x0003b9d9 0x0003b9d9 47  48   3.__TEXT.__objc_methname  ascii sendSynchronousRequest:returningResponse:error:
47  0x0003ba09 0x0003ba09 28  29   3.__TEXT.__objc_methname  ascii componentsSeparatedByString:
48  0x0003ba26 0x0003ba26 5   6    3.__TEXT.__objc_methname  ascii count
49  0x0003ba2c 0x0003ba2c 25  26   3.__TEXT.__objc_methname  ascii objectAtIndexedSubscript:
50  0x0003ba46 0x0003ba46 12  13   3.__TEXT.__objc_methname  ascii integerValue
51  0x0003ba53 0x0003ba53 18  19   3.__TEXT.__objc_methname  ascii isValidJSONObject:
52  0x0003ba66 0x0003ba66 33  34   3.__TEXT.__objc_methname  ascii dataWithJSONObject:options:error:
53  0x0003ba88 0x0003ba88 22  23   3.__TEXT.__objc_methname  ascii initWithData:encoding:
54  0x0003ba9f 0x0003ba9f 7   8    3.__TEXT.__objc_methname  ascii setURL:
55  0x0003baa7 0x0003baa7 19  20   3.__TEXT.__objc_methname  ascii setTimeoutInterval:
56  0x0003babb 0x0003babb 14  15   3.__TEXT.__objc_methname  ascii setHTTPMethod:
57  0x0003baca 0x0003baca 28  29   3.__TEXT.__objc_methname  ascii setValue:forHTTPHeaderField:
58  0x0003bae7 0x0003bae7 17  18   3.__TEXT.__objc_methname  ascii fileExistsAtPath:
59  0x0003baf9 0x0003baf9 29  30   3.__TEXT.__objc_methname  ascii ephemeralSessionConfiguration
60  0x0003bb17 0x0003bb17 36  37   3.__TEXT.__objc_methname  ascii dictionaryWithObjects:forKeys:count:
61  0x0003bb3c 0x0003bb3c 29  30   3.__TEXT.__objc_methname  ascii setConnectionProxyDictionary:
62  0x0003bb5a 0x0003bb5a 25  26   3.__TEXT.__objc_methname  ascii sessionWithConfiguration:
63  0x0003bb74 0x0003bb74 13  14   3.__TEXT.__objc_methname  ascii sharedSession
64  0x0003bb82 0x0003bb82 10  11   3.__TEXT.__objc_methname  ascii statusCode
65  0x0003bb8d 0x0003bb8d 38  39   3.__TEXT.__objc_methname  ascii dataTaskWithRequest:completionHandler:
66  0x0003bbb4 0x0003bbb4 6   7    3.__TEXT.__objc_methname  ascii resume
67  0x0003bbbb 0x0003bbbb 17  18   3.__TEXT.__objc_methname  ascii stringWithFormat:
68  0x0003bbcd 0x0003bbcd 12  13   3.__TEXT.__objc_methname  ascii setHTTPBody:
69  0x0003bbda 0x0003bbda 29  30   3.__TEXT.__objc_methname  ascii fileExistsAtPath:isDirectory:
70  0x0003bbf8 0x0003bbf8 23  24   3.__TEXT.__objc_methname  ascii dataWithContentsOfFile:
71  0x0003bc10 0x0003bc10 5   6    3.__TEXT.__objc_methname  ascii bytes
72  0x0003bc16 0x0003bc16 19  20   3.__TEXT.__objc_methname  ascii stringWithCapacity:
73  0x0003bc2a 0x0003bc2a 13  14   3.__TEXT.__objc_methname  ascii appendFormat:
74  0x0003bc38 0x0003bc38 14  15   3.__TEXT.__objc_methname  ascii exASdcLNKxJfAM
75  0x0003bc47 0x0003bc47 14  15   3.__TEXT.__objc_methname  ascii xKxcixmmxdxPxZ
76  0x0003bc56 0x0003bc56 15  16   3.__TEXT.__objc_methname  ascii xKxcixmmxdxPxZ:
77  0x0003bc66 0x0003bc66 15  16   3.__TEXT.__objc_methname  ascii MxJgqzxvqFtQxV:
78  0x0003bc76 0x0003bc76 37  38   3.__TEXT.__objc_methname  ascii dVxAxlNLgYxxYh:compareVersionNumberB:
79  0x0003bc9c 0x0003bc9c 15  16   3.__TEXT.__objc_methname  ascii xxfxuGtxxxtRxx:
80  0x0003bcac 0x0003bcac 15  16   3.__TEXT.__objc_methname  ascii OxxXdjxnoanKzL:
81  0x0003bcbc 0x0003bcbc 15  16   3.__TEXT.__objc_methname  ascii NZufxnxxcFkCxb:
82  0x0003bccc 0x0003bccc 16  17   3.__TEXT.__objc_methname  ascii fcVwxqxhwdnpxa::
83  0x0003bcdd 0x0003bcdd 18  19   3.__TEXT.__objc_methname  ascii emxqoxrXzxPUvx::::
84  0x0003bcf0 0x0003bcf0 15  16   3.__TEXT.__objc_methname  ascii xxxxtpHhXMwfjx:
85  0x0003bd00 0x0003bd00 49  50   3.__TEXT.__objc_methname  ascii initWithBytesNoCopy:length:encoding:freeWhenDone:
86  0x0003bd32 0x0003bd32 17  18   3.__TEXT.__objc_methname  ascii characterAtIndex:
87  0x0003bd44 0x0003bd44 15  16   3.__TEXT.__objc_methname  ascii xMRExdxMxkhxxx:
88  0x0003bd54 0x0003bd54 19  20   3.__TEXT.__objc_methname  ascii appendBytes:length:
89  0x0003bd68 0x0003bd68 15  16   3.__TEXT.__objc_methname  ascii LUxxxfWDhvpGxJ:
90  0x0003bd78 0x0003bd78 15  16   3.__TEXT.__objc_methname  ascii fexkIvlCfxhxsy:
91  0x0003bd88 0x0003bd88 14  15   3.__TEXT.__objc_methname  ascii MjOhDBJSUcxxxu
92  0x0003bd97 0x0003bd97 14  15   3.__TEXT.__objc_methname  ascii gxcyxmxxxIxNux
93  0x0003bda6 0x0003bda6 14  15   3.__TEXT.__objc_methname  ascii OxlpxkxxFLzEnr
94  0x0003bdb5 0x0003bdb5 14  15   3.__TEXT.__objc_methname  ascii fDjCxxvxTjxWeL
95  0x0003bdc4 0x0003bdc4 14  15   3.__TEXT.__objc_methname  ascii xouxVIvlOloYFX
96  0x0003bdd3 0x0003bdd3 14  15   3.__TEXT.__objc_methname  ascii xtxNTxxxsxVGxk
97  0x0003bde2 0x0003bde2 10  11   3.__TEXT.__objc_methname  ascii floatValue
98  0x0003bded 0x0003bded 10  11   3.__TEXT.__objc_methname  ascii mainBundle
99  0x0003bdf8 0x0003bdf8 16  17   3.__TEXT.__objc_methname  ascii bundleIdentifier
100 0x0003be09 0x0003be09 15  16   3.__TEXT.__objc_methname  ascii jailBrokenMask:
101 0x0003be19 0x0003be19 8   9    3.__TEXT.__objc_methname  ascii loadView
102 0x0003be22 0x0003be22 12  13   3.__TEXT.__objc_methname  ascii currentTitle
103 0x0003be2f 0x0003be2f 21  22   3.__TEXT.__objc_methname  ascii dataWithBytes:length:
104 0x0003be45 0x0003be45 10  11   3.__TEXT.__objc_methname  ascii UTF8String
105 0x0003be50 0x0003be50 43  44   3.__TEXT.__objc_methname  ascii requestWithURL:cachePolicy:timeoutInterval:
0   0x0003be7d 0x0003be7d 45  46   4.__TEXT.__cstring        ascii v16@?0@"NSData"4@"NSURLResponse"8@"NSError"12
1   0x0003beab 0x0003beab 5   6    4.__TEXT.__cstring        ascii v4@?0
0   0x0003beb1 0x0003beb1 14  15   5.__TEXT.__objc_classname ascii NxNXRxsbBxexSx
1   0x0003bec0 0x0003bec0 18  19   5.__TEXT.__objc_classname ascii daAxbxbayGwxtxdcca
2   0x0003bed3 0x0003bed3 14  15   5.__TEXT.__objc_classname ascii NbGzxsksqtAxgN
3   0x0003bee2 0x0003bee2 14  15   5.__TEXT.__objc_classname ascii xrxleWZnuCXPEx
4   0x0003bef1 0x0003bef1 14  15   5.__TEXT.__objc_classname ascii xxWxKxrETCxJpx
0   0x0003bf00 0x0003bf00 6   7    6.__TEXT.__objc_methtype  ascii @8@0:4
1   0x0003bf07 0x0003bf07 9   10   6.__TEXT.__objc_methtype  ascii v12@0:4@8
2   0x0003bf11 0x0003bf11 15  16   6.__TEXT.__objc_methtype  ascii v20@0:4@8@12@16
3   0x0003bf21 0x0003bf21 15  16   6.__TEXT.__objc_methtype  ascii v20@0:4@8c12c16
4   0x0003bf31 0x0003bf31 9   10   6.__TEXT.__objc_methtype  ascii @12@0:4@8
5   0x0003bf3b 0x0003bf3b 12  13   6.__TEXT.__objc_methtype  ascii i16@0:4@8@12
6   0x0003bf48 0x0003bf48 13  14   6.__TEXT.__objc_methtype  ascii @16@0:4@8^i12
7   0x0003bf56 0x0003bf56 19  20   6.__TEXT.__objc_methtype  ascii @24@0:4@8@12^i16i20
8   0x0003bf6a 0x0003bf6a 9   10   6.__TEXT.__objc_methtype  ascii i12@0:4c8
```

## `-s`

```bash
➜  DynamicLibraries rabin2 -s MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_s_symbols.txt
```

输出：

```bash
[Symbols]

nth paddr       vaddr      bind   type size lib name
――――――――――――――――――――――――――――――――――――――――――――――――――――
0    0x0004089c 0x0003c89c GLOBAL FUNC 0        _OBJC_CLASS_$_NbGzxsksqtAxgN
1    0x0004084c 0x0003c84c GLOBAL FUNC 0        _OBJC_CLASS_$_NxNXRxsbBxexSx
2    0x00040874 0x0003c874 GLOBAL FUNC 0        _OBJC_CLASS_$_daAxbxbayGwxtxdcca
3    0x000408c4 0x0003c8c4 GLOBAL FUNC 0        _OBJC_CLASS_$_xrxleWZnuCXPEx
4    0x000408ec 0x0003c8ec GLOBAL FUNC 0        _OBJC_CLASS_$_xxWxKxrETCxJpx
5    0x00040888 0x0003c888 GLOBAL FUNC 0        _OBJC_METACLASS_$_NbGzxsksqtAxgN
6    0x00040838 0x0003c838 GLOBAL FUNC 0        _OBJC_METACLASS_$_NxNXRxsbBxexSx
7    0x00040860 0x0003c860 GLOBAL FUNC 0        _OBJC_METACLASS_$_daAxbxbayGwxtxdcca
8    0x000408b0 0x0003c8b0 GLOBAL FUNC 0        _OBJC_METACLASS_$_xrxleWZnuCXPEx
9    0x000408d8 0x0003c8d8 GLOBAL FUNC 0        _OBJC_METACLASS_$_xxWxKxrETCxJpx
10   0x00043420 0x0003f420 GLOBAL FUNC 0        _g_slide
11   0x00043564 0x0003f564 GLOBAL FUNC 0        _x
12   0x00043568 0x0003f568 GLOBAL FUNC 0        _x.146
13   0x0004356c 0x0003f56c GLOBAL FUNC 0        _x.148
...
120  0x00043448 0x0003f448 GLOBAL FUNC 0        _y.382
121  0x00004000 0x05614542 LOCAL  FUNC 0        radr://5614542
122  0x0003f124 0x0003b124 LOCAL  FUNC 0        imp.CC_MD5
123  0x0003f134 0x0003b134 LOCAL  FUNC 0        imp.MGCopyAnswer
124  0x0003f144 0x0003b144 LOCAL  FUNC 0        imp.MSHookFunction
125  0x0003f154 0x0003b154 LOCAL  FUNC 0        imp.MSHookMessageEx
126  0x0003f164 0x0003b164 LOCAL  FUNC 0        imp.NSClassFromString
127  0x0003f174 0x0003b174 LOCAL  FUNC 0        imp.NSHomeDirectory
128  0x0003f184 0x0003b184 LOCAL  FUNC 0        imp._Block_object_assign
129  0x0003f194 0x0003b194 LOCAL  FUNC 0        imp._Block_object_dispose
130  0x0003f1a4 0x0003b1a4 LOCAL  FUNC 0        imp._Unwind_SjLj_Register
131  0x0003f1b4 0x0003b1b4 LOCAL  FUNC 0        imp._Unwind_SjLj_Resume
132  0x0003f1c4 0x0003b1c4 LOCAL  FUNC 0        imp._Unwind_SjLj_Unregister
133  0x0003f1d4 0x0003b1d4 LOCAL  FUNC 0        imp.__assert_rtn
134  0x0003f1e4 0x0003b1e4 LOCAL  FUNC 0        imp.__stack_chk_fail
135  0x0003f1f4 0x0003b1f4 LOCAL  FUNC 0        imp._dyld_get_image_vmaddr_slide
136  0x0003f204 0x0003b204 LOCAL  FUNC 0        imp.dispatch_async
137  0x0003f214 0x0003b214 LOCAL  FUNC 0        imp.dispatch_get_global_queue
138  0x0003f224 0x0003b224 LOCAL  FUNC 0        imp.dispatch_semaphore_create
139  0x0003f234 0x0003b234 LOCAL  FUNC 0        imp.dispatch_semaphore_signal
140  0x0003f244 0x0003b244 LOCAL  FUNC 0        imp.dispatch_semaphore_wait
141  0x0003f254 0x0003b254 LOCAL  FUNC 0        imp.dispatch_time
142  0x0003f264 0x0003b264 LOCAL  FUNC 0        imp.dlclose
143  0x0003f274 0x0003b274 LOCAL  FUNC 0        imp.dlopen
144  0x0003f284 0x0003b284 LOCAL  FUNC 0        imp.dlsym
145  0x0003f294 0x0003b294 LOCAL  FUNC 0        imp.exit
146  0x0003f2a4 0x0003b2a4 LOCAL  FUNC 0        imp.free
147  0x0003f2b4 0x0003b2b4 LOCAL  FUNC 0        imp.getpid
148  0x0003f2c4 0x0003b2c4 LOCAL  FUNC 0        imp.ioctl
149  0x0003f2d4 0x0003b2d4 LOCAL  FUNC 0        imp.isatty
150  0x0003f2e4 0x0003b2e4 LOCAL  FUNC 0        imp.malloc
151  0x0003f2f4 0x0003b2f4 LOCAL  FUNC 0        imp.memset
152  0x0003f304 0x0003b304 LOCAL  FUNC 0        imp.objc_autorelease
153  0x0003f314 0x0003b314 LOCAL  FUNC 0        imp.objc_autoreleaseReturnValue
154  0x0003f324 0x0003b324 LOCAL  FUNC 0        imp.objc_getClass
155  0x0003f334 0x0003b334 LOCAL  FUNC 0        imp.objc_msgSend
156  0x0003f344 0x0003b344 LOCAL  FUNC 0        imp.objc_release
157  0x0003f354 0x0003b354 LOCAL  FUNC 0        imp.objc_retain
158  0x0003f364 0x0003b364 LOCAL  FUNC 0        imp.objc_retainAutorelease
159  0x0003f374 0x0003b374 LOCAL  FUNC 0        imp.objc_retainAutoreleasedReturnValue
160  0x0003f384 0x0003b384 LOCAL  FUNC 0        imp.perror
161  0x0003f394 0x0003b394 LOCAL  FUNC 0        imp.pthread_create
162  0x0003f3a4 0x0003b3a4 LOCAL  FUNC 0        imp.sleep
163  0x0003f3b4 0x0003b3b4 LOCAL  FUNC 0        imp.strstr
164  0x0003f3c4 0x0003b3c4 LOCAL  FUNC 0        imp.syscall
165  0x0003f3d4 0x0003b3d4 LOCAL  FUNC 0        imp.sysctl
166  0x0003f3e4 0x0003b3e4 LOCAL  FUNC 0        imp.uname
167  0x00004160 0x00004160 LOCAL  FUNC 0        func.00004161
168  0x00005b10 0x00005b10 LOCAL  FUNC 0        func.00005b11
...
223  0x00039220 0x00039220 LOCAL  FUNC 0        func.00039221
224  0x0003939e 0x0003939e LOCAL  FUNC 0        func.0003939f
225  0x000394dc 0x000394dc LOCAL  FUNC 0        func.000394dd
```

## `-S`

```bash
➜  DynamicLibraries rabin2 -S MaskPro.dylib > MaskProDylib/MaskProDylib_rabin2_S_sections.txt
```

输出：

```bash
[Sections]

nth paddr          size vaddr         vsize perm name
―――――――――――――――――――――――――――――――――――――――――――――――――――――
0   0x00004160  0x36fc4 0x00004160  0x36fc4 -r-x 0.__TEXT.__text
1   0x0003b124    0x2d0 0x0003b124    0x2d0 -r-x 1.__TEXT.__picsymbolstub4
2   0x0003b3f4    0x240 0x0003b3f4    0x240 -r-x 2.__TEXT.__stub_helper
3   0x0003b634    0x848 0x0003b634    0x848 -r-x 3.__TEXT.__objc_methname
4   0x0003be7c     0x35 0x0003be7c     0x35 -r-x 4.__TEXT.__cstring
5   0x0003beb1     0x4f 0x0003beb1     0x4f -r-x 5.__TEXT.__objc_classname
6   0x0003bf00     0x74 0x0003bf00     0x74 -r-x 6.__TEXT.__objc_methtype
7   0x0003bf74     0x8c 0x0003bf74     0x8c -r-x 7.__TEXT.__gcc_except_tab
8   0x0003c000    0x1d0 0x0003c000    0x1d0 -rw- 8.__DATA.__nl_symbol_ptr
9   0x0003c1d0     0xb4 0x0003c1d0     0xb4 -rw- 9.__DATA.__la_symbol_ptr
10  0x0003c284      0x4 0x0003c284      0x4 -rw- 10.__DATA.__mod_init_func
11  0x0003c288     0x84 0x0003c288     0x84 -rw- 11.__DATA.__const
12  0x0003c30c     0x10 0x0003c30c     0x10 -rw- 12.__DATA.__cfstring
13  0x0003c31c     0x14 0x0003c31c     0x14 -rw- 13.__DATA.__objc_classlist
14  0x0003c330      0x8 0x0003c330      0x8 -rw- 14.__DATA.__objc_imageinfo
15  0x0003c338    0x328 0x0003c338    0x328 -rw- 15.__DATA.__objc_const
16  0x0003c660    0x170 0x0003c660    0x170 -rw- 16.__DATA.__objc_selrefs
17  0x0003c7d0     0x68 0x0003c7d0     0x68 -rw- 17.__DATA.__objc_classrefs
18  0x0003c838     0xc8 0x0003c838     0xc8 -rw- 18.__DATA.__objc_data
19  0x0003c900   0x2a24 0x0003c900   0x2a24 -rw- 19.__DATA.__data
20  0x00000000      0x0 0x0003f324     0xfc -rw- 20.__DATA.__bss
21  0x00000000      0x0 0x0003f420    0x1bc -rw- 21.__DATA.__common
22  0x00040000      0x1 0x00040000      0x1 -rw- 22.__LLVM.__bundle
```
