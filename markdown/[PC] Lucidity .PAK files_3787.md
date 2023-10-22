## Post #1
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-10-16T06:42:51+00:00
- Post Title: [PC] Lucidity .PAK files

Hi!
It's new game from LucasArts - Lucidity.
Anyone knows how to unpack game archives?
They got header "KAPL".
Sample - [http://multi-up.com/156036](http://multi-up.com/156036)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-16T12:25:29+00:00
- Post Title: [PC] Lucidity .PAK files

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

idstring KAPL
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

for i = 0 < FILES
    get OFFSET long
    math OFFSET += FILE_OFF
    get NAMEOFF long
    get ZSIZE long
    get SIZE long
    get TYPE long
    get DUMMY long
    get DUMMY long
    get DUMMY long

    goto NAMEOFF MEMORY_FILE
    get NAME string MEMORY_FILE

    if TYPE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
next i
```
## Post #3
- Username: johntus
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Jun 14, 2009 2:31 am
- Post datetime: 2009-10-16T12:55:26+00:00
- Post Title: [PC] Lucidity .PAK files

aluigi
Thx! Great work.
But all files inside encrypted in XNB.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-16T13:15:38+00:00
- Post Title: [PC] Lucidity .PAK files

xnb is an undocumented format used for images on xbox360.
you can find more (or less) about it on internet
