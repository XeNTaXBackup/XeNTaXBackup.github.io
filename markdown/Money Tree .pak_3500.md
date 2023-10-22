## Post #1
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-20T14:56:20+00:00
- Post Title: Money Tree .pak

Hi ! 

again i have a problem with a .pak file of a Casual Game

Here you can download.

[http://www.reflexive.com/MoneyTree.html](http://www.reflexive.com/MoneyTree.html)

there is only one main.pak, no sig, nothing 

Before someone asks, why i need that stuff.
I work as a Cover Designer for a CD Publisher of this Casual Games and most of the devs dont want to give us the raw Material of the games. ( i dont know why, but thats not my task )
So i am really happy that i found that forum, with so much help !! THX

So maybe someone can help me with extracting the main.pak

Thx !
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-20T17:28:56+00:00
- Post Title: Money Tree .pak

job done:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

get TOTAL_SIZE asize
log MEMORY_FILE 0 TOTAL_SIZE

set XORNUM long 0xba3abca7
for i = 0 < TOTAL_SIZE
    getvarchr BYTE MEMORY_FILE i
    set TMP long XORNUM
    math TMP &= 0xff
    math BYTE ^= TMP
    putvarchr MEMORY_FILE i BYTE

    set TMP long XORNUM
    math XORNUM >>= 0x1f
    math XORNUM &= 1
    math TMP <<= 1
    math XORNUM |= TMP
next i

idstring MEMORY_FILE "ARC"
get FILES long MEMORY_FILE
for i = 0 < FILES
    get NAMESZ long MEMORY_FILE
    getdstring NAME NAMESZ MEMORY_FILE
    get OFFSET long MEMORY_FILE
    get SIZE long MEMORY_FILE

    log NAME OFFSET SIZE MEMORY_FILE
next i
```
note that the decoding of the file is a bit slow so wait patiently, I will see if I can improve the performances in the next version of quickbms but I doubt

*edit* yes quickbms supports the "rotate" operation natively but it's a signed rotation, in the next version it will be fixed and so will be enough to use simply "math XORNUM l 1" to do the job
## Post #3
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-05-20T18:03:48+00:00
- Post Title: Money Tree .pak

Thank you soo much !!

You made my day )
