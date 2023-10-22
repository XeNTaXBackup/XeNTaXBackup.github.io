## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-07-05T19:45:08+00:00
- Post Title: Bounty Hounds Online (*.PAK)

Official Site: [here](https://subagames.com/BOUNTYHOUNDS/News.aspx)
Download: [here](http://release.subagames.com/bho/BHO_NA_1.171.01win.zip)
Screenshots: [here](https://subagames.com/BOUNTYHOUNDS/Media.aspx)

```
# 
# Written by Ekey (h4x0r)
# http://forum.xentax.com
# 
# script for QuickBMS http://quickbms.aluigi.org

comtype lzma_dynamic

goto 0x8
get FILES short
goto 0xC

for i = 0 < FILES
    getdstring NAME 32
    getdstring HASH 16
    get ZASIZE long
    get OFFSET long
    get SIZE long
    get ZSIZE long
    math OFFSET += 1
    math ZSIZE -= 1
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
