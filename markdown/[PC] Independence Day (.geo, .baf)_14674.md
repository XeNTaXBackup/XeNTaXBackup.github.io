## Post #1
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-22T21:55:51+00:00
- Post Title: [PC] Independence Day (*.geo, *.baf)

This is an old game from 1997, the *.geo files are the models  



bachi_geo.png (35.28 KiB) Viewed 44 times



the *.baf files are uncompressed archives containing bmp textures
i made a bms script to extract them here
[http://zenhax.com/viewtopic.php?f=9&t=2728](http://zenhax.com/viewtopic.php?f=9&t=2728)

```
get SKIP long
get tableOff long
get FILES long
goto tableOff
for i = 0 < FILES
    getdstring NAME 0x10
    get Offset long
    get SIZE long
    getdstring SKIP 40
    log NAME OFFSET SIZE
next i
```
