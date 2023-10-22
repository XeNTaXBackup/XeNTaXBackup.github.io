## Post #1
- Username: victordm09
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Mar 15, 2016 2:22 am
- Post datetime: 2016-12-19T02:31:32+00:00
- Post Title: Persona 5 .bin

I'm trying to get the portraits from Persona 5, I've had luck extracting the game files, but inside there are these .bin files in which I'm sure the portraits are. Opening some of them on a hex editor reveals a .dds and .dds2 files inside them




Some samples to help converting
[http://puu.sh/sUcUg/010e9300cb.rar](http://puu.sh/sUcUg/010e9300cb.rar)

Thanks in advance
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-12-19T17:25:25+00:00
- Post Title: Persona 5 .bin

here is generic bms script to split the textures with names  

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x44\x44\x53\x20" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE - OFFSET
    math OFFSET - 0x24 
    goto OFFSET
    getdstring NAME 0x24
    savepos OFFSET
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```
