## Post #1
- Username: Ameretat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 20, 2010 11:24 am
- Post datetime: 2010-04-20T08:01:38+00:00
- Post Title: Valkyrie Sky .vfs and .vls

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-21T14:08:30+00:00
- Post Title: Valkyrie Sky .vfs and .vls

I have not understood how to retrieve the full tree of the folders so the following script can only extract the files without the folders.
I have added a number_ before the names because various files have the same names (and different folders obviously).
if someone wants to improve it, he is welcome:

```
get VERSION byte
get VFS_SIZE asize
set i long 0
for OFFSET = 0 < VFS_SIZE
    filexor 0xff
    get TYPE long
    getdstring NAME 0x200
    set NAME unicode NAME
    get ZSIZE long
    get SIZE long
    get TYPE2 long
    get CRC long
    get PREV_OFF long
    get NEXT_OFF long
    filexor ""
    if TYPE != 0
        set FULLNAME string i
        string FULLNAME += _
        string FULLNAME += NAME
        math i += 1

        savepos OFFSET
        if SIZE == ZSIZE
            log FULLNAME OFFSET SIZE
            math OFFSET += SIZE
        else
            clog FULLNAME OFFSET ZSIZE SIZE
            math OFFSET += ZSIZE
        endif
        goto OFFSET
    endif
next
```
## Post #3
- Username: Ameretat
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 20, 2010 11:24 am
- Post datetime: 2010-04-21T20:02:26+00:00
- Post Title: Valkyrie Sky .vfs and .vls

Thanks. Worls like a charm. I don't mind about the folders, i'm intrested in the files . 

Anyway, it works for all the other .vfs files to so i'm happy.

This is a great help for me, now I don't have to take screenshots all the time. And i'll be able to get to know the game better etc... like how things work.
## Post #4
- Username: arn0ld
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Apr 09, 2011 10:24 pm
- Post datetime: 2011-04-10T17:01:20+00:00
- Post Title: Valkyrie Sky .vfs and .vls

hello. id like to rip vs sprites from the files but i didint understand how to use this script.can u help me? ty in advance
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-22T23:39:52+00:00
- Post Title: Valkyrie Sky .vfs and .vls

> Reply from arn0ld
>
> hello. id like to rip vs sprites from the files but i didint understand how to use this script.can u help me? ty in advancecopy quickbms and script to folder where you have files, execute quickbms select script, next the file you want extract and last the path where extracted files is all
