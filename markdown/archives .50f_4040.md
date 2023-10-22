## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-01-12T10:20:46+00:00
- Post Title: archives .50f

Hi,

Somebody can make a bms script for this archives?
This file come from Attack of the 50ft Robot! a free game.
[http://www.2shared.com/file/10607356/40 ... evels.html](http://www.2shared.com/file/10607356/408cb666/levels.html)

Thanks
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-12T11:10:32+00:00
- Post Title: archives .50f

```

idstring "50FPACK"
goto 12
get FILES long
goto 0x24
for i = 0 < FILES
    getdstring NAME 0x100
    get SIZE long
    get OFFSET long
    log NAME OFFSET SIZE
next i
```
