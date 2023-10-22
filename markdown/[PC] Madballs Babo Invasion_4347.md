## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-04-18T13:15:25+00:00
- Post Title: [PC] Madballs Babo: Invasion

Hi,

I have this game and i want to extract/mod the files from this game.
The game use zlib compression.

[http://www.sendspace.com/file/n2uk98](http://www.sendspace.com/file/n2uk98)
[http://www.sendspace.com/file/cv3i3c](http://www.sendspace.com/file/cv3i3c)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-18T16:12:46+00:00
- Post Title: [PC] Madballs Babo: Invasion

```

get HGP unicode
get DUMMY long
get DUMMY long
get OFFSET long
goto OFFSET
get FILES short
for i = 0 < FILES
    get NAME unicode
    get OFFSET long
    get ZSIZE long
    get ZIPPED byte
    if ZIPPED == 0
        log NAME OFFSET ZSIZE
    else
        savepos TMP
        goto OFFSET
        get SIZE long
        savepos OFFSET
        clog NAME OFFSET ZSIZE SIZE
        goto TMP
    endif
next i
```
## Post #3
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2010-04-19T08:00:45+00:00
- Post Title: [PC] Madballs Babo: Invasion

Thanks
