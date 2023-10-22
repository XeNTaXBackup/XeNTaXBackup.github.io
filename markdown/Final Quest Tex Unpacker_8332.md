## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-18T20:22:02+00:00
- Post Title: Final Quest Tex Unpacker

Hello guys, well here I share this script of chrrox for unpack textures of Final Quest.

```
goto 0x200
get UNK1 long
get SIZE long
get ZSIZE long
get UNK2 long
savepos OFFSET
get NAME filename
string NAME -= 4
set EXT STRING ".dds" 
string NAME += EXT
clog NAME OFFSET ZSIZE SIZE
next i
```


Some DDS of NPC
