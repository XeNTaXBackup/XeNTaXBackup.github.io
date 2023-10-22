## Post #1
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2012-02-03T14:48:03+00:00
- Post Title: [PC] Monkey Island 2 LeChucks Revenge Special Edition

Hi there,
Could somebody make BMS script for this file, please?
Game is made by LucasArts, so I assume it uses the same engine as Lucidity has. But unfortunately, script for Lucidity doesn't work with this file. 


Thx in advance.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-02-03T16:42:06+00:00
- Post Title: [PC] Monkey Island 2 LeChucks Revenge Special Edition

```
# script for QuickBMS http://quickbms.aluigi.org

idstring "KAPL"
get VERSION long
get TABLE_OFF long
get INFO_OFF long
get NAME_OFF long
get FILE_OFF long
get TABLE_SIZE long
get INFO_SIZE long
get NAME_SIZE long
get FILE_SIZE long
get PAK_SIZE long
get DUMMY long

log MEMORY_FILE NAME_OFF NAME_SIZE
comtype deflate
set FILES long INFO_SIZE
math FILES /= 32
goto INFO_OFF

math XNAMEOFF = 0
for i = 0 < FILES
    get OFFSET long
    math OFFSET += FILE_OFF
    get NAMEOFF long
    get ZSIZE long
    get SIZE long
    get TYPE long

    goto XNAMEOFF MEMORY_FILE
    get NAME string MEMORY_FILE
    savepos XNAMEOFF MEMORY_FILE

    if TYPE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: spider91
- Rank: advanced
- Number of posts: 78
- Joined date: Mon Feb 14, 2011 3:09 pm
- Post datetime: 2015-03-05T02:04:11+00:00
- Post Title: [PC] Monkey Island 2 LeChucks Revenge Special Edition

> math FILES /= 32

Seems to be wrong. Math FILES /= 20 is correct.
