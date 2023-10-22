## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-09-05T17:39:48+00:00
- Post Title: Cabal II (*.PAK)

```
# 
# Original script by aluigi, modified by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype deflate

goto -0x16
get PK_sign long
get DUMMY long
get FILES short
goto 0

for i = 0 < FILES
    get SIGN long

    if SIGN != 0x04034b50
        cleanexit
    endif

    get VER short
    get FLAG short
    get METHOD short
    get TIME short
    get DATE short
    get CRC32 long
    get ZSIZE long
    get SIZE long
    get NSIZE long
    getdstring NAME NSIZE
    savepos OFFSET
	
    if METHOD == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif

    math OFFSET += ZSIZE
    goto OFFSET
next i
```


Tested on 1.0.33.3976 client version.

Notes:
METHOD = 11 (Files encrypted by XXTea and compressed)
METHOD = 12 (Files encrypted by xor + mod and compressed)
