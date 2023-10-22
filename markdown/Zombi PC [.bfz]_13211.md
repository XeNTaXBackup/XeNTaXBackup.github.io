## Post #1
- Username: ShivShubh
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Sep 02, 2014 11:58 pm
- Post datetime: 2015-08-18T13:20:01+00:00
- Post Title: Zombi PC [.bfz]

Zombi game is just released, and it seems to use the same format .BFZ as in its WiiU version.

Can anyone pls try to make an unpacker and hopefully a repacker too ?

Samples :-

```
https://dl.dropboxusercontent.com/u/33463092/bfz.zip
```
## Post #2
- Username: Haoose
- Rank: mega-veteran
- Number of posts: 280
- Joined date: Wed Mar 02, 2011 4:34 am
- Post datetime: 2015-08-20T19:21:41+00:00
- Post Title: Zombi PC [.bfz]

BMS
©aluigi & spider91

```
#   Note that this script has not been tested on the full files.
#   Provide the full files and contact me if it doesn't work.
# script for QuickBMS http://quickbms.aluigi.org

quickbmsver "0.6.3"

comtype lzo1x

idstring "ABE"
goto 0x28
get FILES_OFF longlong
get FOLDERS_OFF longlong
get CHUNKS_OFF longlong
get FILES long
get FOLDERS long
get CHUNKS long
get FILES long
get DUMMY long  # 1
get REAL_CHUNKS long

goto FILES_OFF
get FILES long
get DUMMY long
get DUMMY longlong
for i = 0 < FILES
    get OFFSET longlong
    get SIZE longlong
    get DUMMY long
    get DUMMY long
    putarray 0 i OFFSET
    putarray 1 i SIZE
next i
for i = 0 < FILES
    getdstring NAME 0x40
    get SIZE longlong
    get ZERO longlong
    get DUMMY longlong
    get ID long
    get DUMMY long
    putarray 2 i NAME
next i

goto CHUNKS_OFF
get CHUNKS long
get DUMMY long
get DUMMY longlong
savepos CHUNKS_OFF

math MAX_OFF = 0
goto CHUNKS_OFF
for i = 0 < REAL_CHUNKS
    get NEW_OFFSET longlong
    get OFFSET longlong
    get DUMMY longlong
    get SIZE long
    get ZSIZE long
    math NEW_OFFSET + SIZE
    if NEW_OFFSET u> MAX_OFF
        math MAX_OFF = NEW_OFFSET
    endif
next i

log MEMORY_FILE 0 0
putvarchr MEMORY_FILE MAX_OFF 0
append 1
goto CHUNKS_OFF
for i = 0 < REAL_CHUNKS
    get NEW_OFFSET longlong
    get OFFSET longlong
    get DUMMY longlong
    get SIZE long
    get ZSIZE long

    goto NEW_OFFSET MEMORY_FILE
    clog MEMORY_FILE OFFSET ZSIZE SIZE
next i
append

for i = 0 < FILES
    getarray OFFSET 0 i
    getarray SIZE   1 i
    getarray NAME   2 i
    log NAME OFFSET SIZE MEMORY_FILE
next i

```
## Post #3
- Username: Godxon1
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 06, 2015 2:35 am
- Post datetime: 2015-09-01T13:32:20+00:00
- Post Title: Zombi PC [.bfz]

Anyone know where is texts? And how to open them?
