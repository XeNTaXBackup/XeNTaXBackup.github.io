## Post #1
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-11-05T18:09:46+00:00
- Post Title: WRC Generations .PKG bms

Hello, the existing WRC 10 script does not work.
Can you please make a bms script for this game.

A sample file is below.
[https://www.mediafire.com/file/lwqgp029 ... 2.PKG/file](https://www.mediafire.com/file/lwqgp029pu2xkmw/CHUNK_22.PKG/file)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2022-11-14T20:34:03+00:00
- Post Title: WRC Generations .PKG bms

The file information is XORed with the following key:

```
ANPpYggyakreWkJfy35DsFsyDFFUC4NV
```
## Post #3
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-11-15T18:17:26+00:00
- Post Title: WRC Generations .PKG bms

> Reply from Mr.Mouse ↑Tue Nov 15, 2022 4:34 am at Tue Nov 15, 2022 4:34 am
>
> 
The file information is XORed with the following key:
Code: Select allANPpYggyakreWkJfy35DsFsyDFFUC4NV

Thank you very much. But how do I use this key?
So can you please create a script to open the file.
## Post #4
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-11-22T17:07:57+00:00
- Post Title: WRC Generations .PKG bms

Can someone please take a look?
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-11-22T21:29:37+00:00
- Post Title: WRC Generations .PKG bms

Some fields are now 64-bit

```
# WRC Generations
# script for QuickBMS http://quickbms.aluigi.org

comtype lz4f    # "\x04\x22\x4d\x18" magic is lz4f

set KEY string ""
getdstring SIGN 4
goto 0
if SIGN u!= "PPKG"
    # the key is "35DsFsyDFFUC4NVANPpYggyakreWkJfy" (quickbms gives problems using the key as-is...)
    set KEY string "0x33 0x35 0x44 0x73 0x46 0x73 0x79 0x44 0x46 0x46 0x55 0x43 0x34 0x4E 0x56 0x41 0x4E 0x50 0x70 0x59 0x67 0x67 0x79 0x61 0x6B 0x72 0x65 0x57 0x6B 0x4A 0x66 0x79"
    filexor KEY
    getdstring DUMMY 0x180  # unknown data
endif

idstring "PPKG"
get VER long    # 2 or 4 (WRC Generations)
get FILES long
get INFO_SIZE long
getdstring ZERO 0x20
for i = 0 < FILES
    filexor KEY 0
    get NAMESZ long
    getdstring NAME NAMESZ
    get NAME_CRC long
    get OFFSET longlong
    get TSTAMP longlong
    get ZSIZE longlong  # PKGB + ZSIZE + PKGE
    get SIZE longlong   # PKGB + SIZE  + PKGE
    get ZIP long
	
    if VER == 2
       get ZCRC long
       get CRC long
    elif VER == 4
       get ZCRC longlong
       get CRC longlong
    else
       print "Error: unsupported version -> %VER% contact me"
       cleanexit
    endif
	
    getdstring ZERO 0x20
    filexor ""

    math OFFSET + 4     # PKGB
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

```
## Post #6
- Username: Franco
- Rank: beginner
- Number of posts: 37
- Joined date: Sat May 28, 2022 7:03 am
- Post datetime: 2022-11-23T15:40:24+00:00
- Post Title: WRC Generations .PKG bms

> Reply from Ekey ↑Wed Nov 23, 2022 5:29 am at Wed Nov 23, 2022 5:29 am
>
> 
Some fields are now 64-bit
Code: Select all# WRC 7 / WRC 10 FIA World Rally Championship (script 0.2.2)
# WRC Generations
# script for QuickBMS http://quickbms.aluigi.org

comtype lz4f    # "\x04\x22\x4d\x18" magic is lz4f

set KEY string ""
getdstring SIGN 4
goto 0
if SIGN u!= "PPKG"
    # the key is "35DsFsyDFFUC4NVANPpYggyakreWkJfy" (quickbms gives problems using the key as-is...)
    set KEY string "0x33 0x35 0x44 0x73 0x46 0x73 0x79 0x44 0x46 0x46 0x55 0x43 0x34 0x4E 0x56 0x41 0x4E 0x50 0x70 0x59 0x67 0x67 0x79 0x61 0x6B 0x72 0x65 0x57 0x6B 0x4A 0x66 0x79"
    filexor KEY
    getdstring DUMMY 0x180  # unknown data
endif

idstring "PPKG"
get VER long    # 2 or 4 (WRC Generations)
get FILES long
get INFO_SIZE long
getdstring ZERO 0x20
for i = 0 < FILES
    filexor KEY 0
    get NAMESZ long
    getdstring NAME NAMESZ
    get NAME_CRC long
    get OFFSET longlong
    get TSTAMP longlong
    get ZSIZE longlong  # PKGB + ZSIZE + PKGE
    get SIZE longlong   # PKGB + SIZE  + PKGE
    get ZIP long
	
    if VER == 2
       get ZCRC long
       get CRC long
    elif VER == 4
       get ZCRC longlong
       get CRC longlong
    else
       print "Error: unsupported version -> %VER% contact me"
       cleanexit
    endif
	
    getdstring ZERO 0x20
    filexor ""

    math OFFSET + 4     # PKGB
    if ZIP == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i

Ekey thank you very much. You're the king man, thanks
