## Post #1
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-07-19T04:51:25+00:00
- Post Title: RE5 GE DLC

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-07-19T05:20:23+00:00
- Post Title: RE5 GE DLC

EDIT: Nevermind... just noticed the byte order is reversed from my PC arc files. the tools posted on here are for the PC version. I don't recall seeing an extractor other than for the PC version.
## Post #3
- Username: maniacoloco
- Rank: advanced
- Number of posts: 49
- Joined date: Sat Mar 05, 2011 10:19 pm
- Post datetime: 2011-07-19T05:45:26+00:00
- Post Title: RE5 GE DLC

> Reply from howfie
>
> EDIT: Nevermind... just noticed the byte order is reversed from my PC arc files. the tools posted on here are for the PC version. I don't recall seeing an extractor other than for the PC version.

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

quickbmsver 0.3.13
set HFS long 0
set BASE_OFF long 0

get SIGN long
if SIGN == 0x00534648   # " SFH"
    endian big
    set HFS long 1
elif SIGN == 0x48465300 # "HFS "
    endian little
    set HFS long 1
endif

if HFS != 0
    get DUMMY short
    get TYPE short
    if TYPE == 0
        set BASE_OFF long 0x20000
    else
        set BASE_OFF long 0x10
    endif
    goto BASE_OFF
    get SIGN long
endif

if SIGN == 0x00435241   # " CRA"
    endian little
elif SIGN == 0x41524300 # "ARC "
    endian big
else
    cleanexit
endif
get VERSION short
if VERSION == 4
    comtype zlib
elif VERSION == 8
    set TYPE2 ".ps3"
    comtype deflate
elif VERSION == 0x11
    set TYPE2 ".360"
    comtype XMemDecompress 0x8000   # yeah 0x8000 is the "magic" for RE5
else
    comtype zlib
    print "unknown version %VERSION%, I try zlib compression"
endif
get FILES short

for i = 0 < FILES
    getdstring NAME 0x40
    string name + TYPE2
    get TYPE long
    get ZSIZE long
    get SIZE long
    get OFFSET long
    print %TYPE%
    if TYPE == 606035435
     string name + .TEX
    elif TYPE == 1486968918
    string name + .DOM
    elif TYPE == 659146920
    string name + .MRL
    elif TYPE == 1988234625
    string name + .LMT
    elif TYPE == 329180445
    string name + .LMT
    else
    string name + .
    string name + TYPE
    print "unknown TYPE %TYPE%, let me know what it is"
    endif
    if SIZE & 0x40000000
        math SIZE -= 0x40000000
    endif

    if HFS != 0 # used in RE5 PS3
        math ZSIZE += 32
        #math SIZE /= 8
        math TMP = OFFSET
        math TMP /= 0x20000
        math TMP *= 0x10
        math ZSIZE  += TMP
        math SIZE   += TMP
        math OFFSET += TMP
        math OFFSET += 2
    endif

    math OFFSET += BASE_OFF # needed for HFS header
    clog NAME OFFSET ZSIZE SIZE
next i
```


That's the bms to extract it, the same used for MVC3 360.
