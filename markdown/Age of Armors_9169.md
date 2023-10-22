## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-29T17:29:43+00:00
- Post Title: Age of Armors

Mecha game from Snail.
Game is now closed (well, the one I saw anyways), but the client is still available on gaming sites.

Sort of reminds me of the gears in xenogear lol



Same format as [viewtopic.php?f=11&t=3451](http://forum.xentax.com/viewtopic.php?f=11&t=3451)

```
# by Fatduck
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "snail_package"
get DUMMY long
get NUMRES long
goto 61

for i = 0 < NUMRES
    get STGLEN byte
    get NEGFLAG byte
    if NEGFLAG == 0xFF
        math STGLEN -= 256
        math STGLEN *= -1
    endif
    getdstring RESNAME STGLEN
    get RESSIZE long
    getdstring STGDUMMY 32
    get OFSRES long
    getdstring STGDUMMY 76
    
    log RESNAME OFSRES RESSIZE
next i
```


Models use granny 2 format like the other game.
Is there a bms or an exe to decompress the files?
