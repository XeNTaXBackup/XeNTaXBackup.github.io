## Post #1
- Username: Denis
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Oct 03, 2009 10:15 pm
- Post datetime: 2011-10-07T00:14:57+00:00
- Post Title: Beach Volleyball Online

Help to unpack archives from this game. Official site [http://www.bvogame.com/](http://www.bvogame.com/)
Here some archives [http://www.megaupload.com/?d=QV7BP3I2](http://www.megaupload.com/?d=QV7BP3I2)
I think game use Gamebryo Engine
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-10-07T01:40:47+00:00
- Post Title: Beach Volleyball Online

```
# script for quickbms by wrs
idstring "SFILESYSTEM"

goto 0x120
get TOTSIZE asize

for
  get ISCOM long

  if ISCOM != 1
    print "may not be compressed?"
  endif

  getdstring FNAME 256
  get ZSIZE long
  get SIZE long
  get DUMMY long
  get DUMMY long

  savepos OFFSET
  clog FNAME OFFSET ZSIZE SIZE

  math OFFSET += ZSIZE

  if OFFSET == TOTSIZE
    cleanexit
  endif

  goto OFFSET
next

```
