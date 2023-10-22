## Post #1
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-19T22:06:23+00:00
- Post Title: Super Robot Taisen XO

hey guys i just wanted to know if anyone can help me open theses files im trying to find out how translate the game and see if there's any stats info 

there are some extension i want to know if anyone can open them here are the extensions  .dat,.pak,.cmp,xpu,xvu  i cant find any headers for any of the files 

.dat is spilt in to multi files (aka ~fh)

[http://www.mediafire.com/?clz5l1be0yb6i0x](http://www.mediafire.com/?clz5l1be0yb6i0x)
## Post #2
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-21T02:04:32+00:00
- Post Title: Super Robot Taisen XO

bump anyone?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-01-28T10:59:48+00:00
- Post Title: Super Robot Taisen XO

for fh/fs files:

```
# script for QuickBMS http://quickbms.aluigi.org

get EXT extension
if EXT != "~fh"
    print "Error: you must open the files with fh extension"
    cleanexit
endif
idstring "~fh"
get DUMMY long
get DUMMY long
get TOTAL_SIZE long
get PAKS long

get NAMESZ byte
getdstring NAME NAMESZ

putvarchr MEMORY_FILE TOTAL_SIZE 0
log MEMORY_FILE 0 0

append
for i = 0 < PAKS
    get NAMESZ long
    getdstring NAME NAMESZ
    get SIZE long
    open FDSE NAME 1
    log MEMORY_FILE 0 SIZE 1
next i
append

endian big

    get OFFSET long MEMORY_FILE
do
    get NEXT_OFF long MEMORY_FILE
    if NEXT_OFF == 0
        math SIZE = TOTAL_SIZE
    else
        math SIZE = NEXT_OFF
    endif
    math SIZE -= OFFSET
    log "" OFFSET SIZE MEMORY_FILE
    math OFFSET = NEXT_OFF
while NEXT_OFF != 0
```


pak and cmp use unknown compression
## Post #4
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2013-01-28T13:52:22+00:00
- Post Title: Super Robot Taisen XO

thank you so much i will try it later today
