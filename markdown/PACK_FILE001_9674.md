## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-09-25T11:12:27+00:00
- Post Title: PACK_FILE001

note that the key may change in other implementations of the format.

```
comtype copy
idstring "PACK_FILE001"
get FILES long
get SIZE long
savepos OFFSET
encryption blowfish KEY
log MEMORY_FILE OFFSET SIZE
math OFFSET += SIZE
for i = 0 < FILES
    math OFFSET += 1
    get SIZE long MEMORY_FILE
    get NAME string MEMORY_FILE
    get XSIZE long MEMORY_FILE
    encryption blowfish KEY
    clog NAME OFFSET XSIZE SIZE
    math OFFSET += XSIZE
next i
```
The game I tested was called Dungeon something (dungeon.exe)
