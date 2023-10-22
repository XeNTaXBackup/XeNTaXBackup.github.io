## Post #1
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2013-04-15T17:31:31+00:00
- Post Title: Soul Nomad & the World Eaters [PS2]

Here is a simple script to extract the DATA.DAT from the root of the DVD of this NIS game.
Make sure that DATA.DAT and SCRIPT.H are in the same location and open either of them.

```
# Script to extract DATA.DAT with SECTOR.H from the disc root
#
# by HenryEx
#
# script for QuickBMS http://quickbms.aluigi.org

open FDSE SECTOR.H 0
open FDSE DATA.DAT 1

# How many files are there? The SECTOR.H has 40 bytes per entry
get FILENUM asize
math FILENUM / 40
math FILENUM - 1  # Last entry is a dummy

for i = 0 < FILENUM

    getdstring NAME 0x20
    get OFFSET long
    get SIZE long

    math OFFSET * 0x800   # Offset is given in read sectors (2048 bytes)

    log NAME OFFSET SIZE 1
next i

CleanExit
```


There are a lot of .lzs files in there that seem to be compressed, but i'm not sure how to unpack them.
