## Post #1
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-04-11T10:00:45+00:00
- Post Title: Megaman Maverick Hunter X [PSP] *.pak

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-12T17:03:29+00:00
- Post Title: Megaman Maverick Hunter X [PSP] *.pak

```
for
    findloc OFFSET string "CPK0"
    goto OFFSET
    idstring CPK0
    get ZSIZE long
    get SIZE long
    get DUMMY long
    savepos OFFSET
    math ZSIZE -= 2
    clog "" OFFSET ZSIZE SIZE
next
```
## Post #3
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2010-04-15T15:55:52+00:00
- Post Title: Megaman Maverick Hunter X [PSP] *.pak

Thanks mate
