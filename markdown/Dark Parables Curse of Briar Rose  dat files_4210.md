## Post #1
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-03-13T06:11:21+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T09:51:18+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

it's encrypted with a 64bit block cipher algorithm like blowfish.
no key, no party
## Post #3
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-03-13T13:00:56+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

> Reply from aluigi
>
> it's encrypted with a 64bit block cipher algorithm like blowfish.
no key, no party

Is there any way to decrypt these files?  If have exe file?
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-13T13:35:02+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

yeah, it could be possible.
try to upload the exe and dlls and maybe we could be lucky
## Post #5
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-03-14T01:56:07+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T11:39:31+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

the algorithm is tea/xtea but being a partial installation there are no all the files.
so do the following:
- start the game and remove the full-screen from the options
- when you arrive at the menu start ollydbg and attach it to the process
- set a breakpoint at offset 457d30
- when it breaks take a screen shot of the ollydbg window (moreover the right-down part)
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-03-14T16:37:13+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

```

encryption blowfish "012483 btg"
get HOSIZE asize
log MEMORY_FILE 0 HOSIZE
encryption "" ""

idstring MEMORY_FILE "HiddenObject"
getdstring VER 3 MEMORY_FILE
get PATH basename
string PATH += /

math FILES = 1
for i = 0
    get SIZE long MEMORY_FILE
    savepos OFFSET MEMORY_FILE
        math TMP = OFFSET
        math TMP += SIZE
        goto TMP MEMORY_FILE
    set NAME string PATH
    string NAME += i
    string NAME += ".dat"
    log NAME OFFSET SIZE MEMORY_FILE
    if i >= FILES
        cleanexit
    endif
    if i == 0
        get FILES long MEMORY_FILE
    endif
    getdstring DUMMY 24 MEMORY_FILE
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
next i
```
## Post #8
- Username: stevenx
- Rank: veteran
- Number of posts: 130
- Joined date: Sat Nov 01, 2008 7:02 pm
- Post datetime: 2010-04-03T10:45:36+00:00
- Post Title: Dark Parables Curse of Briar Rose  dat files

> Reply from aluigi
>
> Code: Select all# script for QuickBMS http://aluigi.org/papers.htm#quickbms

encryption blowfish "012483 btg"
get HOSIZE asize
log MEMORY_FILE 0 HOSIZE
encryption "" ""

idstring MEMORY_FILE "HiddenObject"
getdstring VER 3 MEMORY_FILE
get PATH basename
string PATH += /

math FILES = 1
for i = 0
    get SIZE long MEMORY_FILE
    savepos OFFSET MEMORY_FILE
        math TMP = OFFSET
        math TMP += SIZE
        goto TMP MEMORY_FILE
    set NAME string PATH
    string NAME += i
    string NAME += ".dat"
    log NAME OFFSET SIZE MEMORY_FILE
    if i >= FILES
        cleanexit
    endif
    if i == 0
        get FILES long MEMORY_FILE
    endif
    getdstring DUMMY 24 MEMORY_FILE
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
next i

I seen this script today,very thanks!
