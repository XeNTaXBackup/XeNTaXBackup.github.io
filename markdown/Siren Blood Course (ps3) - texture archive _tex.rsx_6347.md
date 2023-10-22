## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T00:48:29+00:00
- Post Title: Siren Blood Course (ps3) - texture archive *_tex.rsx

Help me to extract this kind of archive, i know that inside it are several textures: diffuse, normal and maybe something else, i sought this textures in Texture Finder.

[sample](http://dl.dropbox.com/u/9919707/blogs/xentax.com/siren-blood-course-ps3/stage15_tex.rsx)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-04T13:08:02+00:00
- Post Title: Siren Blood Course (ps3) - texture archive *_tex.rsx

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
get DUMMY long
get DUMMY short
get DUMMY short
get FILE_OFF long
get DUMMY_OFF long
get INFO2_OFF long
get SKIP_OFF long
get DUMMY long
get DUMMY long
get DUMMY long  # TEX
get FILES long
get NAME_BASE long
get INFO_OFF long
goto INFO_OFF
for i = 0 < FILES
    get OFFSET long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get SIZE long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    get DUMMY long
    savepos TMP
    goto NAME_BASE
    get NAME_OFF long
    savepos NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP
    math SIZE -= 0x2c
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-04T16:15:29+00:00
- Post Title: Siren Blood Course (ps3) - texture archive *_tex.rsx

> Reply from aluigi
>
> script for quickbms
thanks Luigi, works great
