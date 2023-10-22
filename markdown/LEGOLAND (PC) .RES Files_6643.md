## Post #1
- Username: gaming1233
- Rank: advanced
- Number of posts: 48
- Joined date: Mon Oct 11, 2010 4:36 am
- Post datetime: 2011-05-19T15:35:35+00:00
- Post Title: LEGOLAND (PC) .RES Files

Could someone help me unpack these .RES files? Archive format reminds me of I.M. Meen's .LAB files. 

Download Graphics1.res: [http://www.mediafire.com/?0u1bz5vea5fgbhx](http://www.mediafire.com/?0u1bz5vea5fgbhx)
Download Graphics2.res: [http://www.mediafire.com/?rzvpwfk2kzpwk2f](http://www.mediafire.com/?rzvpwfk2kzpwk2f)
Download Legoland.res: [http://www.mediafire.com/?8adsdqgo2qxx676](http://www.mediafire.com/?8adsdqgo2qxx676)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-05-27T22:20:44+00:00
- Post Title: LEGOLAND (PC) .RES Files

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get OFFSET long
get SIZE asize
math SIZE -= OFFSET
log MEMORY_FILE OFFSET SIZE
set NAME string ""
set PATH string ""
callfunction EXTRACT

startfunction EXTRACT
    string PATH += NAME
    string PATH += /
    for
        padding 4 MEMORY_FILE
        get ENTRY1 long MEMORY_FILE
        get ENTRY2 long MEMORY_FILE
        get TYPE long MEMORY_FILE
        get SIZE long MEMORY_FILE
        get OFFSET long MEMORY_FILE
        get NAME string MEMORY_FILE
        if TYPE == 0
            set FNAME string PATH
            string FNAME += NAME
            log FNAME OFFSET SIZE
        else
            if ENTRY1 != -1
                goto ENTRY1 MEMORY_FILE
                callfunction EXTRACT
            endif
        endif
        if ENTRY2 == -1
            break
        endif
        goto ENTRY2 MEMORY_FILE
    next
endfunction
```
