## Post #1
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-05-10T15:10:32+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-05-10T15:45:30+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

Looks the music it's in the file IOP_mus.pak
## Post #3
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-05-10T16:07:36+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

> Reply from Savage
>
> Looks the music it's in the file IOP_mus.pak
No prob, man. I can upload this PAK, if needed. Give me 30-40 minutes.

p.s. links updated.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-13T20:52:38+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

if there are other archives that are not supported (the script will show an error) it's enough that you upload only the first 100 kilobytes of each one of them:

```

goto 0x20
get FILES long
goto 0x114
get TYPE string
if TYPE == "bnk"
    goto 0x198
    set NAME string ""
    for i = 0 < FILES
        get OFFSET threebyte
        get BASE_NAMESZ byte
        get NAMESZ byte
        get DUMMY short
        get SIZE long
        getdstring TMP NAMESZ
        math OFFSET *= 0x800
        putvarchr NAME BASE_NAMESZ 0
        string NAME += TMP
        string NAME -= 1
        log NAME OFFSET SIZE
    next i
elif TYPE == "mus"
    goto 0x20c
    for i = 0 < FILES
        get SIZE long
        get OFFSET long
        if OFFSET != 0
            math OFFSET *= 0x800
            log "" OFFSET SIZE
            math i += 1
        endif
    next
else
    print "Error: unsupported type %TYPE%, contact me"
    cleanexit
endif
```
## Post #5
- Username: prysm
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Jun 15, 2009 6:38 am
- Post datetime: 2010-05-19T16:44:49+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

aluigi, you ROCK!!!   

Thanks a lot!! I've already extracted music layers from Black Monday. In a few days will try next PAK from the first Getaway.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-14T15:48:11+00:00
- Post Title: [PS2] The Getaway 1 & 2 [.PAK]

I give up for the other types of this file format because it's enough chaotic.
it supports various types that are included in the same archive and so it requires a better reversing of all the fields, and at the moment I'm not interested
