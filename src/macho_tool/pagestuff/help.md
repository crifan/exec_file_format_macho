# pagestuff的help语法

```bash
➜  ~ pagestuff
Usage: /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/pagestuff mach-o [-arch name] [-p] [-a] pagenumber [pagenumber ...]
```

## man手册

```bash
PAGESTUFF(1)                                               General Commands Manual                                                 PAGESTUFF(1)

NAME
       pagestuff - Mach-O file page analysis tool

SYNOPSIS
       pagestuff file [-a] [-p] [pagenumber...]

DESCRIPTION
       pagestuff  displays information about the specified logical pages of a file conforming to the Mach-O executable format.  For each specified
       page of code, symbols (function and static data structure names) are displayed.  If no pages are specified, symbols for all  pages  in  the
       __TEXT, __text section are displayed.

       The options to pagestuff(1) are:

       -a     Displays all pages.  All other arguments are ignored.

       -p     Print  a     list  of the sections of the specified Mach-O file, with offsets and lengths.  All other arguments are ignored.  Note that
              the size(1) tool given arguments "-m -l -x" displays a much more concise listing.

SEE ALSO
       Mach-O(5), size(1)

Apple Computer, Inc.                                           January 3, 2001                                                     PAGESTUFF(1)
```
