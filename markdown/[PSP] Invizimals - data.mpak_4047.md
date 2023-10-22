## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-15T13:30:47+00:00
- Post Title: [PSP] Invizimals - data.mpak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-15T16:21:09+00:00
- Post Title: [PSP] Invizimals - data.mpak

```

idstring FPAK
get MPAK_SIZE long
get DUMMY long
get FILES long
for i = 0 < FILES
    getdstring NAME 0x20
    get DUMMY long
    get OFFSET long
    get SIZE long
    get DUMMY long

    savepos TMP # add an extension... maybe useful
    goto OFFSET
    getdstring SIGN 4
    goto TMP
    if SIGN == "RIFF"
        string NAME += ".wav"
    elif SIGN == "FPAK"
        string NAME += ".mpak"
    elif SIGN == "ptex"
        string NAME += ".ptex"
    elif SIGN == "‰PNG"
        string NAME += ".png"
    endif

    log NAME OFFSET SIZE
next i
```
I have added also the auto-assigning of an extension to the files, maybe it's useful (after all it costed me nothing to add it ih ih ih)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-01-18T09:25:41+00:00
- Post Title: [PSP] Invizimals - data.mpak

Thanks a lot, worked perfectly!
