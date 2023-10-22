## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-24T22:46:10+00:00
- Post Title: UFC 2010 - sound.pck (AKPK ident)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-26T18:45:16+00:00
- Post Title: UFC 2010 - sound.pck (AKPK ident)

I used a work-around but works:

```
idstring AKPK
get INFO_SIZE long
get DUMMY long  # 1
get DUMMY long  # 24
get DUMMY long  # 154
get DUMMY long  # 41fbc
get DUMMY long  # 2
get DUMMY long  # 14
get DUMMY long  # 1
get DUMMY long  # 20
get DUMMY long  # 0
get NAME string
get FOLDER string

for
    savepos MYOFF
    if MYOFF >= INFO_SIZE
        break
    endif
    get DUMMY long
    get CRC long
    do
        get ALIGN long
    while ALIGN != 0x800
    get ZERO long
    get SIZE long
    get OFFSET long
    math OFFSET *= 0x800
    log "" OFFSET SIZE
next
```
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-05-28T11:33:28+00:00
- Post Title: UFC 2010 - sound.pck (AKPK ident)

Worked, thanks.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-05T14:12:33+00:00
- Post Title: UFC 2010 - sound.pck (AKPK ident)

The contents of this post was deleted because of possible forum rules violation.
