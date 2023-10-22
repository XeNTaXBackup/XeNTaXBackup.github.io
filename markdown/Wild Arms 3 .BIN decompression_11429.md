## Post #1
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-04-18T03:44:40+00:00
- Post Title: Wild Arms 3 .BIN decompression?

Hello, all. I am here to find a way to decompress the BTLMON.BIN file for the guy behind PS23DFormat. According to him, the files us some sort of LZ compression to house the character and enemy models.

Sample file:
[http://www.mediafire.com/download/gwmki ... BTLMON.BIN](http://www.mediafire.com/download/gwmkibsbek6omgf/BTLMON.BIN)

EDIT: Here is a pic of the first few bytes in the file
## Post #2
- Username: SmashFan127
- Rank: advanced
- Number of posts: 51
- Joined date: Sun Jun 17, 2012 9:09 am
- Post datetime: 2014-04-23T02:27:07+00:00
- Post Title: Wild Arms 3 .BIN decompression?

Is there anyone available?

First post has been edited to include the first few bytes.
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-02-13T00:52:50+00:00
- Post Title: Wild Arms 3 .BIN decompression?

quickbms script to decompress files.
Needs to add support for extracting sub archives (align data to 0x800 after last file and start over again)
Run this first for now.

```
goto 0
for
findloc OFFSET string DIV
print "%OFFSET%"
getdstring TMP 0x20
findloc SIZE string DIV
goto SIZE
math SIZE - OFFSET
log "" OFFSET SIZE
next

```

then you can do this

> quickbms.exe -d -F "*.dat" "C:\Users\Downloads\Wild Arms 3 (USA)\Wild Arms 3 (USA)\STG\test.txt" "C:\Users\Downloads\Wild Arms 3 (USA)\Wild Arms 3 (USA)\BTL\1" "C:\Users\Downloads\Wild Arms 3 (USA)\Wild Arms 3 (USA)\BTL\2"

```
savepos BASE
findloc FILES string "\x00\x00\x00\x00"
math FILES / 4
print "%FILES%"
for i = 0 < FILES
get OFFSET long
math OFFSET - 0x1D00000
putarray 0 i OFFSET
next i
math FILES - 1
for i = 0 < FILES
set j i
math j + 1
getarray OFFSET 0 i
getarray SIZE 0 j
math SIZE - OFFSET
if SIZE > 0
math OFFSET + BASE
log MEMORY_FILE OFFSET SIZE
get TSIZE long MEMORY_FILE
get SIZE asize MEMORY_FILE
print "%TSIZE%"
if TSIZE > 0x1FFFFF || TSIZE < 0
log "" 0 SIZE MEMORY_FILE
else
math SIZE - 4
clog "" 4 SIZE TSIZE MEMORY_FILE
endif
endif
next i

```
## Post #4
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-04-09T05:59:41+00:00
- Post Title: Wild Arms 3 .BIN decompression?

Thanks for looking into this I was able to decompress the files .MWO but is there any support to figuring out the monster data in the BTLMON.BIN ? Or even finding out how the bone structure works in the decompressed files. I've studied that script for over a year now and its a mystery. You and daemon are some of the best and if these files are too much then it seems i will never get a working model from this series. I could really use some help. I found by changing the script from seek 20 to seek 31 it finds the world/stages. Some kind of byte stride/padding value ? I can't be the only one who wants this title   any help on compression or how to get the bones/animations would be a major help.
