## Post #1
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2012-05-28T11:35:11+00:00
- Post Title: EA's .big file  (XBOX 360)

Why doesn't this work?

# Electronic Arts BIG4/BIGF archives
#   Fifa 12, Harry Potter, NBA Live and so on
# script for QuickBMS [http://quickbms.aluigi.org](http://quickbms.aluigi.org)

comtype COMP_DK2
endian big
idstring "BIG"
getdstring VER 1
get DUMMY long
get FILES long
get OFFSETX long
for i = 0 < FILES
    get OFFSET long
    get ZSIZE long
    get NAME string

    savepos TMP
    goto OFFSET
    get TYPE short
    get SIZE threebyte
    goto TMP

    if TYPE == 0x10fb
        clog NAME OFFSET ZSIZE SIZE
    else
        log NAME OFFSET ZSIZE
    endif
next i

Here is even a screenshot of the file I opened in a Hex editor.
[https://dl.dropbox.com/u/31190204/scrn.jpg](https://dl.dropbox.com/u/31190204/scrn.jpg)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-28T15:13:14+00:00
- Post Title: EA's .big file  (XBOX 360)

because that archive is compressed:

```
get ZSIZE asize
goto 2
endian big
get SIZE threebyte
get NAME basename
string NAME += "_unpacked.big"
clog NAME 0 ZSIZE SIZE
```
## Post #3
- Username: Thorongil
- Rank: Banned
- Number of posts: 17
- Joined date: Mon Mar 01, 2010 2:42 am
- Post datetime: 2012-05-28T19:07:27+00:00
- Post Title: EA's .big file  (XBOX 360)

Where's that thanks button.. Thank you sir Aluigi!
