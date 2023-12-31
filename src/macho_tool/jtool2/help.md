# jtool2的help语法

```bash
➜  ~ jtool2 --help
Usage: jtool [options] _filename_

OTool Compatible Options:
   -h         	Dump Mach-O (or DYLD Shared Cache) header
   -l         	List sections/commands in binary
   -L         	print shared libraries used

JTool (classic) Options:
   -S         	List Symbols (like NM)
   -v[v]      	Toggle verbosity (vv = very verbose)
   -e         	extract fat slice, Mach-O segment/section, dyld shared cache dylib or (NEW) kernelcache kext
   -q         	Quick operation - do not process any symbols in the Mach-O
   -F         	find all occurrences of _string_ in binary
   -a         	Find offset/segment corresponding to virtual address _addr_
   -o         	Find address corresponding to offset _offset_
   -d         	Dump (smart dump, will disassemble text and dump data by autodetecting)

Code Signing Options:
   --sig      	Show code signature in binary (if any)
   --stripsig 	Remove existing code signature (useful for MacOS unrestricting)
   --ent      	Show entitlements in binary (if any)
   -+ent=...[,...]	Inject entitlements into binary (implies resigning inplace)
   -+platformize	Platformize binary (injects platform-application, also implies resigning inplace)

Joker Compatible Options (applicable on kernel caches only):
   -k         	List kexts
   -K         	Kextract™ a kernel extension by its bundle ID
   -dec       	Decompress a kernelcache to /tmp/kernel (no longer necessary since JTool can now operate on compressed caches)

dyldinfo Compatible Options:
   --bind     		print addresses dyld will set based on symbolic lookups
   --lazy_bind		print addresses dyld will lazily set on first use
   --opcodes  		print opcodes used to generate the rebase and binding information
   --function_starts	print table of function start addresses

Newer (JTool 2) Options:
   --analyze  	Analyze file and create a companion file
   --symbolicate	Symbolicate an .ips panic file
   --machoize 	 [text=0x...-0x...] [strings=0x....-0x...] [data=0x....-0x....] _filename_
   --tbd      	Create a .tbd file (for *OS private frameworks only - you'll need the dyld shared cache for this)
   --objc     	Like old -d objc and/or classdumpZ - Mike, this is for you :-)
   -D         	Decompile (totally experimental - would love your feedback if you're reading this)
   -G         	Gadget search (specify gadgets as comma delimited mnemonics)
   -W         	Write [address] [value] - [value] is a string or 0x....

Environment Variables:
   ARCH                	Select architecture slice. Set to arm64, arm64e, arm64_32, armv7, armv7k, x86_64 or (not for long) i386
   JCOLOR              	ANSI Colors. Note you'll need 'less -R' if piping output
   JTOOLDIR            	path to search for companion jtool files (default: $PWD).
			Use this to force create a file, if one does not exist
   NOPSUP              	Suppress NOPs in disassembly
   JENTS               	Default entitlements (comma separated) for --sign
   JHASH               	Choice of Hash algorithm for signing (SHA1,SHA256 (default), SHA256T, SHA384)
   JSHUDDUP            	Suppress stderr (risky, but useful)
   JDEBUG              	Enhanced debug output. May be very verbose
   JDEBUGCS            	Debug output specifically for code signing operations. Useful to watch these step-by-step
   WITHSIGBLOB         	Code signing: Also create an empty CMS blob (no longer a default due to CoreTrust)
```
