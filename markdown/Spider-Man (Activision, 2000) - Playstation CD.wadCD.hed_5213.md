## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-10-15T18:19:23+00:00
- Post Title: Spider-Man (Activision, 2000) - Playstation CD.wad/CD.hed

I don't know where else to put it and I didn't want to take it into my script collection because it's too special. So if anyone wants to extract the contents of the game, just use this script. 

```
open FDDE WAD 1

for i
    savepos OFF
    get TEST byte
    if TEST == 0xff
        cleanexit
    else
        goto OFF
    endif
    get NAME string 0
    strlen NAMEL NAME
    goto OFF
    if NAMEL < 0x4
        getDstring NAME 0x4 0
    elif NAMEL < 0x8
        getDstring NAME 0x8 0
    elif NAMEL < 0xc
        getDstring NAME 0xc 0
    elif NAMEL < 0x10
        getDstring NAME 0x10 0
    endif
    get OFFSET long 0
    get SIZE long 0
    log NAME OFFSET SIZE 1
next i
```
I know I'm using a workaround which isn't very aesthetic but well, it works. 
Have fun!
