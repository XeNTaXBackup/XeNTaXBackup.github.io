## Post #1
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-19T16:14:36+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-19T16:41:20+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

Its using the xbox 360 sdk compression you can extract it with xbedecompress
## Post #3
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-20T13:10:16+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

I think the program should be "xbox sdk" I download it! Right?

Can someone link to put this program? Or to help so where can I download for free?
## Post #4
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-21T09:50:25+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

The software How can I download?
Please help me.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-21T11:26:35+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-21T11:32:24+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

tanks
## Post #7
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-21T11:48:53+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-21T13:31:51+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

this is the quickbms script I posted in the thread you deleted:

```
# simply dump each encrypted UDP packet sent/received from *.quazal.net in a file and pass it to this script

comtype xmemdecompress
endian big
idstring "pack"
get DUMMY long
get DUMMY long
get OFFSET long
get SIZE long
get NAME_BASE long
get FILES long
math NAME_BASE += OFFSET
goto OFFSET
for i = 0 < FILES
    get OFFSET longlong
    get ZSIZE longlong
    get SIZE longlong
    get NAME_OFF long
    get DUMMY long
    savepos TMP
    math NAME_OFF += NAME_BASE
    goto NAME_OFF
    get NAME string
    goto TMP
    if ZSIZE == SIZE
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #9
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-23T05:07:26+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: hamidvip1
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Apr 19, 2011 11:51 pm
- Post datetime: 2011-04-26T11:35:30+00:00
- Post Title: Megamind: Ultimate Showdown [XBOX]

I'm a texture change.
