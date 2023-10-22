## Post #1
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-04-23T01:24:38+00:00
- Post Title: Def Jam Vendetta .BIN file

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-23T10:47:22+00:00
- Post Title: Def Jam Vendetta .BIN file

try uploading SLES_514.79 but in my opinion there will be no results
## Post #3
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-04-23T14:00:22+00:00
- Post Title: Def Jam Vendetta .BIN file

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-23T21:30:37+00:00
- Post Title: Def Jam Vendetta .BIN file

the executable doesn't contain names and although I have found some references to some file sizes there is not a classical file information table.
that's what I meant with no results.

anyway I had some free time and so I made an experiment and the following is the result:

```

get FULLSIZE asize
for OFFSET = 0 < FULLSIZE
    savepos OFFSET
    getdstring SIGN 4
    if SIGN == "TIM2"
        get DUMMY long
        get DUMMY long
        get DUMMY long
        get SIZE long
        math SIZE += 0x10
    elif SIGN == "PAK "
        get SIZE long
        math SIZE += 8
    elif SIGN == "WAZA"
        math SIZE = 0x2d000 # fixed
    elif SIGN == "WRS "
        getdstring DUMMY 0x54
        get SIZE long
        math SIZE += 0x58
    elif SIGN == "AUD "
        get SIZE long
        math SIZE += 8
    elif SIGN == "PRM "
        get SIZE long
        math SIZE += 8
    elif SIGN == ""
        math SIZE = 0
    else
        getvarchr SIGN SIGN 0
        if SIGN == 0x80
            get SIZE long
            math SIZE += 0x80
        else
            do
                findloc SIZE string "\0\0\0\0\0\0\0\0\0\0\0\x80\x00\x00\x00" ""
                if SIZE == ""
                    # end of the archive
                    cleanexit
                endif
                goto SIZE
                findloc SIZE string "\x80\x00\x00\x00"
                if SIZE % 0x800
                    goto SIZE
                    math SIZE = 0
                endif
            while SIZE == 0
            math SIZE -= OFFSET
        endif
    endif
    if SIZE == 0
        math SIZE = 1
    else
        log "" OFFSET SIZE
    endif
    math OFFSET += SIZE
    goto OFFSET
    get DUMMY long
    if DUMMY == 0
        math OFFSET x= 0x800
    endif
    goto OFFSET
next
```
better than nothing
## Post #5
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-04-23T23:50:11+00:00
- Post Title: Def Jam Vendetta .BIN file

The file extracted.

I have reasons to believe that the moves are either in the .pak files or some other formats.

edit: can anyone help me with those formats?
## Post #6
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-04-28T05:03:50+00:00
- Post Title: Def Jam Vendetta .BIN file

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-29T09:47:21+00:00
- Post Title: Def Jam Vendetta .BIN file

script for quickbms:

```
get SIZE long
get FILES long
get OFFSET long
for i = 1 <= FILES
    if i < FILES
        get NEXT long
        math SIZE = NEXT
        math SIZE -= OFFSET
    else
        get SIZE asize
    endif
    math OFFSET += 0xc
    math TMP = i
    math TMP -= 1
    math TMP *= 4
    math OFFSET += TMP
    if i >= FILES
        math SIZE -= OFFSET
    endif
    log "" OFFSET SIZE
    math OFFSET = NEXT
next i
```
