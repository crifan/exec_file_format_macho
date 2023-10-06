# Mach-O的Header的flags

## flags含义解释

* `MH_NOUNDEFS`
  * The object file contained no undefined references when it was built.
* `MH_INCRLINK`
  * The object file is the output of an incremental link against a base file and cannot be linked again.
* `MH_DYLDLINK`
  * The file is input for the dynamic linker and cannot be statically linked again.
* `MH_TWOLEVEL`
  * The image is using two-level namespace bindings.
* `MH_BINDATLOAD`
  * The dynamic linker should bind the undefined references when the file is loaded.
* `MH_PREBOUND`
  * The file’s undefined references are prebound.
* `MH_PREBINDABLE`
  * This file is not prebound but can have its prebinding redone. Used only when MH_PREBEOUND is not set.
* `MH_NOFIXPREBINDING`
  * The dynamic linker doesn’t notify the prebinding agent about this executable.
* `MH_ALLMODSBOUND`
  * Indicates that this binary binds to all two-level namespace modules of its dependent libraries. Used only when MH_PREBINDABLE and MH_TWOLEVEL are set.
* `MH_CANONICAL`
  * This file has been canonicalized by unprebinding—clearing prebinding information from the file. See the redo_prebinding man page for details.
* `MH_SPLIT_SEGS`
  * The file has its read-only and read-write segments split.
* `MH_FORCE_FLAT`
  * The executable is forcing all images to use flat namespace bindings.
* `MH_SUBSECTIONS_VIA_SYMBOLS`
  * The sections of the object file can be divided into individual blocks. These blocks are dead-stripped if they are not used by other code. See Linking for details.
* `MH_NOMULTIDEFS`
  * This umbrella guarantees there are no multiple definitions of symbols in its subimages. As a result, the two-level namespace hints can always be used.

## flags定义

* ![macho_headers_filetype_flags](../../../assets/img/macho_headers_filetype_flags.png)

[源码定义](https://opensource.apple.com/source/xnu/xnu-2050.18.24/EXTERNAL_HEADERS/mach-o/loader.h)：

```c
/* Constants for the flags field of the mach_header */
#define	MH_NOUNDEFS	0x1		/* the object file has no undefined
					   references */
#define	MH_INCRLINK	0x2		/* the object file is the output of an
					   incremental link against a base file
					   and can't be link edited again */
#define MH_DYLDLINK	0x4		/* the object file is input for the
					   dynamic linker and can't be staticly
					   link edited again */
#define MH_BINDATLOAD	0x8		/* the object file's undefined
					   references are bound by the dynamic
					   linker when loaded. */
#define MH_PREBOUND	0x10		/* the file has its dynamic undefined
					   references prebound. */
#define MH_SPLIT_SEGS	0x20		/* the file has its read-only and
					   read-write segments split */
#define MH_LAZY_INIT	0x40		/* the shared library init routine is
					   to be run lazily via catching memory
					   faults to its writeable segments
					   (obsolete) */
#define MH_TWOLEVEL	0x80		/* the image is using two-level name
					   space bindings */
#define MH_FORCE_FLAT	0x100		/* the executable is forcing all images
					   to use flat name space bindings */
#define MH_NOMULTIDEFS	0x200		/* this umbrella guarantees no multiple
					   defintions of symbols in its
					   sub-images so the two-level namespace
					   hints can always be used. */
#define MH_NOFIXPREBINDING 0x400	/* do not have dyld notify the
					   prebinding agent about this
					   executable */
#define MH_PREBINDABLE  0x800           /* the binary is not prebound but can
					   have its prebinding redone. only used
                                           when MH_PREBOUND is not set. */
#define MH_ALLMODSBOUND 0x1000		/* indicates that this binary binds to
                                           all two-level namespace modules of
					   its dependent libraries. only used
					   when MH_PREBINDABLE and MH_TWOLEVEL
					   are both set. */ 
#define MH_SUBSECTIONS_VIA_SYMBOLS 0x2000/* safe to divide up the sections into
					    sub-sections via symbols for dead
					    code stripping */
#define MH_CANONICAL    0x4000		/* the binary has been canonicalized
					   via the unprebind operation */
#define MH_WEAK_DEFINES	0x8000		/* the final linked image contains
					   external weak symbols */
#define MH_BINDS_TO_WEAK 0x10000	/* the final linked image uses
					   weak symbols */

#define MH_ALLOW_STACK_EXECUTION 0x20000/* When this bit is set, all stacks 
					   in the task will be given stack
					   execution privilege.  Only used in
					   MH_EXECUTE filetypes. */
#define MH_ROOT_SAFE 0x40000           /* When this bit is set, the binary 
					  declares it is safe for use in
					  processes with uid zero */
                                         
#define MH_SETUID_SAFE 0x80000         /* When this bit is set, the binary 
					  declares it is safe for use in
					  processes when issetugid() is true */

#define MH_NO_REEXPORTED_DYLIBS 0x100000 /* When this bit is set on a dylib, 
					  the static linker does not need to
					  examine dependent dylibs to see
					  if any are re-exported */
#define	MH_PIE 0x200000			/* When this bit is set, the OS will
					   load the main executable at a
					   random address.  Only used in
					   MH_EXECUTE filetypes. */
#define	MH_DEAD_STRIPPABLE_DYLIB 0x400000 /* Only for use on dylibs.  When
					     linking against a dylib that
					     has this bit set, the static linker
					     will automatically not create a
					     LC_LOAD_DYLIB load command to the
					     dylib if no symbols are being
					     referenced from the dylib. */
#define MH_HAS_TLV_DESCRIPTORS 0x800000 /* Contains a section of type 
					    S_THREAD_LOCAL_VARIABLES */

#define MH_NO_HEAP_EXECUTION 0x1000000	/* When this bit is set, the OS will
					   run the main executable with
					   a non-executable heap even on
					   platforms (e.g. i386) that don't
					   require it. Only used in MH_EXECUTE
					   filetypes. */
```
