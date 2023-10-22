## Post #1
- Username: aptyp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 15, 2014 1:09 am
- Post datetime: 2014-08-14T17:57:09+00:00
- Post Title: [X360] Just Dance 2014 *.ipk archive

Hello. Is there any solution to unpack JD .ipk resources (video *.isc.ckd *.wav.ckd etc)? I've tried some scripts 4 quickbms, but not successful.

quickbms -v rayman_origins.bms Bundle_1_X360.ipk test

```

```
## Post #2
- Username: aptyp
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Aug 15, 2014 1:09 am
- Post datetime: 2014-08-15T21:43:56+00:00
- Post Title: [X360] Just Dance 2014 *.ipk archive

nevermind, all works fine.

```
# script for QuickBMS http://quickbms.aluigi.org

endian big
goto 0xc
get BASE_OFF long
goto 0x2c
get FILES long
for i = 0 < FILES
    get DUMMY1 long
    get SIZE long
    get ZSIZE long
    get TSTAMP longlong
    get OFFSET longlong
    if DUMMY1 == 2
        get DUMMY4 long
        get DUMMY5 long
    endif
    get FOLDERSZ long
   getdstring FOLDER FOLDERSZ
   get NAMESZ long
   getdstring NAME NAMESZ
   string FOLDER + NAME
   string NAME = FOLDER
    math OFFSET += BASE_OFF
    if ZSIZE == 0
        log NAME OFFSET SIZE
    else
        clog NAME OFFSET ZSIZE SIZE
    endif
   get DUMMY6 long
   get DUMMY7 long
next i

```
## Post #3
- Username: Martinike
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 03, 2018 6:23 pm
- Post datetime: 2018-06-30T19:45:58+00:00
- Post Title: [X360] Just Dance 2014 *.ipk archive

can't extract audio :v
