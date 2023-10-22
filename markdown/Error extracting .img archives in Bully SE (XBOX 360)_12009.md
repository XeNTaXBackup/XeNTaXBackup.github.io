## Post #1
- Username: huskinatorr2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 25, 2014 7:49 pm
- Post datetime: 2014-09-25T12:03:25+00:00
- Post Title: Error extracting .img archives in Bully SE (XBOX 360)

I was using quickbms to extract world.img in Bully Scholarship Edition, and everything was extracting fine, until this popped up;





this is the script I used;  [viewtopic.php?f=10&t=10331](http://forum.xentax.com/viewtopic.php?f=10&t=10331) (

```
# 
# Written by Ekey (h4x0r)
# 
# script for QuickBMS http://quickbms.aluigi.org

open FDDE DIR 0
open FDDE IMG 1

get DSIZE asize 0

for
    get OFFSET long 0
    get SIZE long 0
    math OFFSET *= 2048
    math SIZE *= 2048
    getdstring NAME 0x18 0
    log NAME OFFSET SIZE 1
    savepos TMP
    if TMP == DSIZE
  cleanexit
endif
next

```


I know for sure that it had not been completed, since the files I needed hadn't been extracted.

I'm assuming its because the script was written for the pc version of the game, but is there any way to re-write the script to make it work for the xbox 360?

or is there any way I could possibly just extract only the files that I need instead of extracting the whole archive, since straight after asking for a script, archive and output folder it automatically starts extracting the the entire thing?
