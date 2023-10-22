## Post #1
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2017-07-08T04:52:50+00:00
- Post Title: evil within font (.dat)

guys... i want to know how can i edit this .dat file (font) from evil within
for edit Xoffset & Yoffset and other things
a exsample file
[48.rar](https://xentaxbackup.github.io/file/13086_48.rar)
## Post #2
- Username: GHOST DEAD
- Rank: mega-veteran
- Number of posts: 191
- Joined date: Sat Nov 26, 2016 10:39 pm
- Post datetime: 2018-05-21T07:02:08+00:00
- Post Title: evil within font (.dat)

How can i edit .dat font files from The Evil Within 1?
I really need to know that...
## Post #3
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-21T08:57:18+00:00
- Post Title: evil within font (.dat)

This is an .idf file, but i don't know how open
## Post #4
- Username: Zotya0330
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Dec 17, 2014 12:47 am
- Post datetime: 2018-05-27T07:16:43+00:00
- Post Title: evil within font (.dat)

I found the fonts in: \extracted\Loc1\generated\textures\fonts\
There are six folders,  each with a bimage file.
Bimage file convert to dds with these script:

# iD Tech 5 engine
# BIMAGE to DDS converter (PC/PS3)
# by MerlinSVK    Oct 2014
# version 1.1
# script for QuickBMS    [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

set MEMORY_FILE binary "\x44\x44\x53\x20\x7C\x00\x00\x00\x07\x10\x08\x00\xAA\xAA\xAA\xAA\xBB\xBB\xBB\xBB\xCC\xCC\xCC\xCC\x00\x00\x00\x00\x01\x00\x00\x00\x4D\x45\x52\x4C\x49\x4E\x3A\x29\x01\x00\x03\x00\x59\x43\x47\x31\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x20\x00\x00\x00\x04\x00\x00\x00\x44\x58\x54\x35\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x10\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00"

get NAME basename
string HNAME = NAME
string HNAME += ".head"
string NAME += ".dds"

get ASIZE asize
get ID long

if ID == "0x644FD853"      # PC
     goto 0x10
     endian big
     get WIDTH long
     get HEIGHT long
    endian little
     goto 0x42
     savepos START
    xmath DATASIZE "ASIZE - START"
    log HNAME 0 START   # save header for backward conversion
else
     goto 0xC
     endian big
     get WIDTH long
     get HEIGHT long
    endian little
     goto 0x3E
     savepos START
    xmath DATASIZE "ASIZE - START"
    log HNAME 0 START   # save header for backward conversion
endif

putVarChr MEMORY_FILE 0XC HEIGHT long
putVarChr MEMORY_FILE 0x10 WIDTH long
putVarChr MEMORY_FILE 0x14 DATASIZE long

append
log MEMORY_FILE START DATASIZE
append

get DDSSIZE asize MEMORY_FILE
log NAME 0 DDSSIZE MEMORY_FILE
==========================
edit dds and use these script to backpack:
==========================
# idTech 5 Engine
# DDS to BIMAGE converter (PC/PS3)
# version 1.1
# by MerlinSVK    Oct 2014
# script for QuickBMS    [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)

open FDDE DDS 0 
open FDDE HEAD 1

get NAME basename
string NAME += ".bimage_NEW"

get DSIZE asize 0
math DSIZE -= 0x80
get HSIZE asize 1

math FINAL_SIZE = HSIZE + DSIZE
putvarchr MEMORY_FILE FINAL_SIZE 0
log MEMORY_FILE 0 0

log MEMORY_FILE 0 HSIZE 1      # copy header into memory_file
append
log MEMORY_FILE 0x80 DSIZE 0   # append texture data
append

get BIMGSIZE asize MEMORY_FILE
log NAME 0 BIMGSIZE MEMORY_FILE
