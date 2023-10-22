## Post #1
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-12-18T14:14:59+00:00
- Post Title: NCIS The Game

The contents of this post was deleted because of possible forum rules violation.
[(cut)_ncis.7z](https://xentaxbackup.github.io/file/4913_(cut)_ncis.7z)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-18T14:28:25+00:00
- Post Title: NCIS The Game

try uploading 10 megabytes or more.
the format looks chaotic but maybe I can give it a quick look.
## Post #3
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-12-18T18:45:54+00:00
- Post Title: NCIS The Game

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-12-18T21:28:48+00:00
- Post Title: NCIS The Game

I have serious doubts about the script (mainly the correct names for the correct files) anyway it will extract everything:

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "BIG\0"
get DUMMY long
get FILES long
math INFO_OFF = 0x44
math NAMES_OFF = 0x99444

        goto INFO_OFF
        get OFFSET long
        get DUMMY long
        savepos INFO_OFF
for i = 1 <= FILES
    if i == FILES
        get NEXT_OFFSET asize
    else
        goto INFO_OFF
        get NEXT_OFFSET long
        get DUMMY long
        savepos INFO_OFF
    endif

    goto NAMES_OFF
    get DUMMY long
    get XNEXT long
    get XPREV long
    get DUMMY long
    get TSTAMP long
    getdstring NAME 0x40
    get DUMMY long
    getdstring HASH 0x20
    get DUMMY long
    get DUMMY long
    savepos NAMES_OFF

    math SIZE = NEXT_OFFSET
    math SIZE -= OFFSET
    string NAME R= "_" "/"
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
next i
```
## Post #5
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-12-19T12:38:11+00:00
- Post Title: NCIS The Game

It works.
Thank you.
