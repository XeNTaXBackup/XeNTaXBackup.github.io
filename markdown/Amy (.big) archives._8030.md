## Post #1
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-01-11T20:20:17+00:00
- Post Title: Amy (.big) archives.

if someone could write up a bms script or somthing for these archives i would much appreciate, thank you.

example .big archive [http://www.multiupload.com/NL1UGK7O8X](http://www.multiupload.com/NL1UGK7O8X)
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T21:25:15+00:00
- Post Title: Amy (.big) archives.

that's it, made on the fly but looks correct:

```
# script for QuickBMS http://quickbms.aluigi.org

comtype gzip
endian big
idstring "BIG "
get DUMMY long
get NAMES long
get NAMES_IDX long
get DUMMY long
get NAMES_OFF long
get FOLDERS long
get FOLDERS_OFF long
get FILES long
get INFO_OFF long
get FILES_OFF long

for i = 0 < NAMES
    goto NAMES_IDX
    get CRC long
    get NAME_OFF long
    savepos NAMES_IDX

    goto NAME_OFF
    get NAME string
    putarray 0 i NAME
next i

goto FOLDERS_OFF
for i = 0 < FOLDERS
    get PREV long
    get NAME long
    getarray NAME 0 NAME
    putarray 2 i NAME
    set PATH string ""
    if PREV >= 0
        getarray PATH 1 PREV
    endif
    string PATH += NAME
    string PATH += /
    putarray 1 i PATH
next i

goto INFO_OFF
for i = 0 < FILES
    get PATH long
    get NAME long
    get ZSIZE long
    get OFFSET long
    get SIZE long
    getarray PATH 1 PATH
    getarray NAME 0 NAME
    set FNAME string PATH
    string FNAME += NAME
    if ZSIZE == SIZE
        log FNAME OFFSET SIZE
    else
        clog FNAME OFFSET ZSIZE SIZE
    endif
next i
```
*updated script*
## Post #3
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-01-11T22:28:10+00:00
- Post Title: Amy (.big) archives.

works on all the archives except common.big, returns with this error

```
------------------------------
  00000279 2667063    data/shader_xbox.hier

Error: there is an error with the decompression
       the returned output size is negative (-1)
```


heres the common.big archive (if you need it) [http://www.multiupload.com/WB5T08EZ1L](http://www.multiupload.com/WB5T08EZ1L)


btw thanks you very much for looking at this in the first place.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-01-11T22:40:32+00:00
- Post Title: Amy (.big) archives.

fixed, recheck the previous post
## Post #5
- Username: nickx
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jun 25, 2011 7:08 am
- Post datetime: 2012-01-11T22:52:21+00:00
- Post Title: Amy (.big) archives.

thank you, works perfect.
