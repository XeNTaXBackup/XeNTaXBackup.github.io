## Post #1
- Username: mappy2012
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Jul 03, 2011 11:40 am
- Post datetime: 2014-07-30T09:59:15+00:00
- Post Title: Concursion (.eno)

Can someone help me to extract .eno files from this game?thx!
<link removed due forum rules violation>
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2014-07-30T14:19:46+00:00
- Post Title: Concursion (.eno)

.eno = xored OGG Vorbis files
.end = xored DDS textures

Use this BMS for them:

```

get SIZE asize
get NAME filename
get EXT extension
 if EXT = "eno"
    string NAME += ".ogg"
 elseif EXT = "end"
    string NAME += ".dds"
endif
filexor "0x78"
log NAME 0 SIZE
```
