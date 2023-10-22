## Post #1
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2010-12-25T05:49:41+00:00
- Post Title: Sonic 2006 ARC files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Shizo180
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2011 2:25 am
- Post datetime: 2011-03-13T23:30:39+00:00
- Post Title: Sonic 2006 ARC files

Hi shizo here, what kind of data is in these files? (models,music,ect..)
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-14T07:31:16+00:00
- Post Title: Sonic 2006 ARC files

script for QuickBMS:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "\x55\xaa\x38\x2d"
get OFFSET long
get INFO_SIZE long
get BASE_OFFSET long
getdstring DUMMY 0x10
goto OFFSET
set NAME_BASE long 0
set PATH string ""
set NAME string ""
math XLIMIT = 0x7fffffff
putarray 0 0 0
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /
    math LIMIT = XLIMIT
    for
        getarray i 0 0
        if i >= LIMIT
            break
        endif
        math i += 1
        putarray 0 0 i

        get FOLDER short
        get NAME_OFF short
        if FOLDER == 0
            get OFFSET long
            get ZSIZE long
            get SIZE long
        else
            get ID long
            get XLIMIT long
            get DUMMY long
        endif

        if NAME_BASE == 0
            math NAME_BASE = XLIMIT
            math NAME_BASE *= 0x10
            math INFO_SIZE -= NAME_BASE
            math NAME_BASE += OFFSET
            log MEMORY_FILE NAME_BASE INFO_SIZE
            math LIMIT = XLIMIT
        endif
        goto NAME_OFF MEMORY_FILE
        get NAME string MEMORY_FILE

        if FOLDER == 0
            set FNAME string PATH
            string FNAME += NAME
            clog FNAME OFFSET ZSIZE SIZE
        else
            callfunction EXTRACT
        endif
    next
endfunction
```
## Post #4
- Username: Shizo180
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2011 2:25 am
- Post datetime: 2011-03-14T14:42:39+00:00
- Post Title: Sonic 2006 ARC files

well...i'm not a programmer yet, but lucky for you i have the arc extractor for those files. if you want it i can pm you a link b/c it's over the file size limit here.
## Post #5
- Username: Shizo180
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Feb 19, 2011 2:25 am
- Post datetime: 2011-03-18T14:07:41+00:00
- Post Title: Sonic 2006 ARC files

i had a look at the files and all thats in them are sounds and menu screen textures. anyway you can open them with this, but if d/l this please keep it to yourself [Arctools.rar - 0.50MB](http://www.zshare.net/download/8777636647dc422b/)
