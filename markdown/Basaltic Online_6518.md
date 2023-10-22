## Post #1
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-28T00:59:28+00:00
- Post Title: Basaltic Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-04-28T10:33:29+00:00
- Post Title: Basaltic Online

the script for quickbms is the following, but I have no idea what's the algorithm for the obfuscated XML files:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring "PAK\0"
goto 0x19
get OFFSET long
get SIZE long
get ZSIZE long
get BASE_OFF long
clog MEMORY_FILE OFFSET ZSIZE SIZE
set PATH string ""
set NAME string ""
callfunction EXTRACT

startfunction EXTRACT
    get FILES long MEMORY_FILE
    get FOLDERS long MEMORY_FILE
    get NAME string MEMORY_FILE
    string PATH += NAME
    string PATH += /

    for i = 0 < FOLDERS
        callfunction EXTRACT
    next i
    for i = 0 < FILES
        get OFFSET long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get NAME string MEMORY_FILE
        math OFFSET += BASE_OFF
        set FNAME string PATH
        string FNAME += NAME
        log FNAME OFFSET SIZE
    next i
endfunction
```
