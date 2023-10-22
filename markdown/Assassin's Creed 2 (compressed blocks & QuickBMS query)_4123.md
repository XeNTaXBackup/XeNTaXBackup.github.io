## Post #1
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-02-07T03:23:09+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-02-07T08:11:45+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

```

endian big
get ARCHIVE_NAME filename
get ARCHIVE_SIZE asize
set OFFSET long 0
for PACK = 0
    if OFFSET >= ARCHIVE_SIZE
        cleanexit
    endif
    set CORRECT_SIGN binary "\x10\x04\xFA\x99\x57\xFB\xAA\x33"
    getdstring SIGN 8
    if SIGN != CORRECT_SIGN
        math OFFSET += 4
        goto OFFSET  # skip the initial 00000000
        getdstring SIGN 8
        if SIGN != CORRECT_SIGN
            cleanexit
        endif
    endif

    get VERSION short
    get ZTYPE byte
    if ZTYPE == 0x01
        comtype lzo1x
    elif ZTYPE == 0x02
        comtype lzo2a
    elif ZTYPE == 0x03
        comtype xmemdecompress
    else
        print "Error: unknown compression type %ZTYPE%"
        cleanexit
    endif
    get MAX_SIZE short
    get MAX_ZSIZE short
    get CHUNKS short

    for i = 0 < CHUNKS
        get SIZE short
        get ZSIZE short
        putarray 0 i SIZE
        putarray 1 i ZSIZE
    next i

    math PRE_ALLOCATE = MAX_SIZE
    math PRE_ALLOCATE *= CHUNKS
    putvarchr MEMORY_FILE PRE_ALLOCATE 0
    log MEMORY_FILE 0 0
    append
    for i = 0 < CHUNKS
        getarray SIZE  0 i
        getarray ZSIZE 1 i
        get CRC long
        savepos OFFSET
        if SIZE == ZSIZE
            log MEMORY_FILE OFFSET SIZE
        else
            clog MEMORY_FILE OFFSET ZSIZE SIZE
        endif
        math OFFSET += ZSIZE
        goto OFFSET
    next i
    append

    get SIZE asize MEMORY_FILE
    set NAME string ARCHIVE_NAME
    string NAME += "_"
    string NAME += PACK
    log NAME 0 SIZE MEMORY_FILE
next PACK
```
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2010-02-07T11:04:21+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

you are way too smart luigi
## Post #4
- Username: Insomniac
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Apr 24, 2009 11:11 am
- Post datetime: 2010-02-07T14:00:00+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

> Reply from Itze
>
> you are way too smart luigi
Indeed. 



Thanks for the script aluigi, it works great (it's also a good example of how to combine chunks).    I made an incorrect assumption about the 4 byte zero padding at the start of the header. It's an int32 counter for some 8 byte data that follows the counter.  

I've edited a small portion of the script to account for that:

```
	  goto OFFSET
        get UKNCOUNT long
        set SKIP long 8
        math SKIP *= UKNCOUNT
        math SKIP += 4
        math OFFSET += SKIP
        goto OFFSET  
        getdstring SIGN 8
        if SIGN != CORRECT_SIGN
            cleanexit
        endif
    endif

```
## Post #5
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-08T05:29:58+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

Hello is there any chance to replace 2 lang files in data360.forge file please ??
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-08T09:40:46+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

not with quickbms because the files are divided in chunks and so they are not valid for the reimporting feature
## Post #7
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-08T10:37:25+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

> Reply from michalss
>
> Hello is there any chance to replace 2 lang files in data360.forge file please ??

But there is Tool what can do it fro PC version i think, so where is a different between PC and X360 ?? Thx

EDIT : aluigi i know you are very good with this. Do you think there is any chance to look up to it plsease ?
## Post #8
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-13T19:56:27+00:00
- Post Title: Assassin's Creed 2 (compressed blocks & QuickBMS query)

noone ?:(
