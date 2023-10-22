## Post #1
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-12-05T16:45:29+00:00
- Post Title: [PS2] Gumball 3000 .BAD File

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-07T01:42:04+00:00
- Post Title: [PS2] Gumball 3000 .BAD File

done, anyway the provided archive doesn't have compressed files in it so I don't know if the ZSIZE/SIZE decompression is correct but don't worry because if there is a problem then quickbms will tell you that it's not possible to decompress the data and so you can send me the part of the BAD (and the whole BAH) file with it:

```
# script for QuickBMS http://quickbms.aluigi.org

open FDDE bah
open FDDE bad 1
idstring "Woof"
get VER string
get DUMMY short
set NAME string ""
set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
    get NAMESZ long
    get FILES long
    get FOLDERS long
    get DUMMY long
    getdstring NAME NAMESZ
    string PATH += NAME
    string PATH += /
    for i = 0 < FILES
        get NAMESZ long
        get OFFSET long
        get ZSIZE long  # ???
        get SIZE long
        get DUMMY long
        getdstring NAME NAMESZ
        set FNAME string PATH
        string FNAME += NAME
        if ZSIZE == SIZE
            log FNAME OFFSET SIZE 1
        else
            clog FNAME OFFSET ZSIZE SIZE 1
        endif
    next i
    for i = 0 < FOLDERS
        callfunction EXTRACT
    next i
endfunction
```
## Post #3
- Username: RacingFreak
- Rank: veteran
- Number of posts: 136
- Joined date: Fri Feb 11, 2011 5:44 pm
- Post datetime: 2011-12-19T15:25:46+00:00
- Post Title: [PS2] Gumball 3000 .BAD File

Thank you very much! It does work fine and exported the needed data
