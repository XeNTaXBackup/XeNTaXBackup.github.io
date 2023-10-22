## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-29T17:12:40+00:00
- Post Title: Dead Nations sound.pck

script for quickbms for extracting the files from sound.pck:

```

endian big
idstring AKPK
get INFO_SIZE long
get DUMMY long  # 1
get DUMMY long  # 10
get DUMMY long  # 4c
get DUMMY long  # 3004
get DUMMY long  # 1
get DUMMY long  # c
get DUMMY long  # 0
get NAME string

savepos MYOFF
for MYOFF = MYOFF < INFO_SIZE
    do  # lame but works
        get DUMMY long
    while DUMMY != 1
    get ZERO long
    get SIZE long
    get OFFSET long
    savepos MYOFF
    log "" OFFSET SIZE
next
```
## Post #2
- Username: Barnaby
- Rank: advanced
- Number of posts: 47
- Joined date: Tue Dec 15, 2009 12:41 am
- Post datetime: 2011-03-29T17:13:56+00:00
- Post Title: Dead Nations sound.pck

Thanks mate  Great work.
