## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-09-18T06:49:57+00:00
- Post Title: Reincarnations -Awakening- *.bin can't be extracted

I have tried some extrators , but they can't extract the resource completely.
The head-of-file is RESOURCE PACK
Thanks for your helping.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-07T10:06:39+00:00
- Post Title: Reincarnations -Awakening- *.bin can't be extracted

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

comtype lzma
idstring "RESOURCE PACK\r\n"
get OFFSET long
goto OFFSET
get FILES asize
math FILES -= OFFSET
math FILES /= 0x21
for i = 0 < FILES
    getdstring NAME_HASH 20
    get OFFSET long
    get ZSIZE long
    get SIZE long
    get ZIP byte
    if ZIP == 0
        log "" OFFSET SIZE
    else
        math ZSIZE += 5
        clog "" OFFSET ZSIZE SIZE
    endif
next i
```
