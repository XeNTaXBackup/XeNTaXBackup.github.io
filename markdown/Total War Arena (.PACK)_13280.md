## Post #1
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-09-04T18:55:44+00:00
- Post Title: Total War: Arena (*.PACK)

```
# Game: http://store.steampowered.com/app/227520
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "PFH4"
get TYPE long
goto 0x10
get FILES long
get BASEOFF long
math BASEOFF += 28
get DUMMY long
set OFFSET BASEOFF

for i = 0 < FILES
    get SIZE long
    if TYPE >= 20
      get DUMMY long
    endif
    get NAME string
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next i
```
