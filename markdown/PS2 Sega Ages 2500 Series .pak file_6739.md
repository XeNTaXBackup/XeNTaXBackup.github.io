## Post #1
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-06-07T02:18:42+00:00
- Post Title: PS2 Sega Ages 2500 Series *.pak file

Hi everyone. 
I need help extracting PAK files from PS2 Sega Ages 2500 Series?
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-06-11T11:13:05+00:00
- Post Title: PS2 Sega Ages 2500 Series *.pak file

script for quickbms:

```
# script for QuickBMS http://aluigi.org/papers.htm#quickbms

endian big
idstring "PAKFILE\0"
get FILES long
get DUMMY long
for i = 0 < FILES
    getdstring NAME 0x38
    get OFFSET long
    get SIZE long
    math OFFSET *= 0x800
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2011-06-14T01:57:33+00:00
- Post Title: PS2 Sega Ages 2500 Series *.pak file

Thanks aluigi that did it!
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-07-02T16:00:30+00:00
- Post Title: PS2 Sega Ages 2500 Series *.pak file

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-07-04T06:19:04+00:00
- Post Title: PS2 Sega Ages 2500 Series *.pak file

I see no problems, then the format is so basic that can't exist similar errors/crashes

FYI, I don't know what algorithm is the "lzs2" one used in the archived files
