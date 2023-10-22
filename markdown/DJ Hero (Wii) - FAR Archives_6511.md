## Post #1
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-04-26T15:55:15+00:00
- Post Title: DJ Hero (Wii) - FAR Archives

Hello. Could someone please consider writing an extractor for the .FAR archives of the Wii version of DJ Hero?

The archives share the header, "FSAR," and contain the following file extensions:
.cams - Camera(?)
.cent - Entity List
.fnt - Font
.gr2 - Animation
.img - Texture
.msb - Model
.vscreen - Video Projection
.wld - World(?)
.xml - Extensible Markup Language
...And possibly more.

File names are included in the archives with directories and sub-directories. The archive is arranged with file names at the start of the archive, with varying spaces between each file name. The data for each file is below these names in a single group. Seeing as the archives contain possibly easily readable files, I think it would be worthwhile to extract from them.

Thank you for reading my post.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-26T16:51:26+00:00
- Post Title: DJ Hero (Wii) - FAR Archives

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "FSAR"
get DUMMY long
get BASE_OFF long
get FILES long
goto 0x20
for i = 0 < FILES
    getdstring NAME 0x100
    get SIZE longlong
    get ZSIZE longlong
    get OFFSET longlong
    get ZIP long
    get DUMMY long
    math OFFSET += BASE_OFF
    if ZIP == 1
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-04-26T17:07:30+00:00
- Post Title: DJ Hero (Wii) - FAR Archives

And that's how aluigi rolls.
Thanks.
