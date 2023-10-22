## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2007-04-30T16:02:13+00:00
- Post Title: Soldier Front "sff" file format?

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-05T10:20:18+00:00
- Post Title: Soldier Front "sff" file format?

```

uint32 {4}   - Number Of Files

// FILES DIRECTORY
    // for each file
        char {128}   - Path Filename (included null and filled with 0xCC char)
        uint32 {4}   - File Offset (start from end of File Directory)
        uint32 {4}   - File Length

// FILE DATA
    // for each file
        byte {X}     - File Data




```


I will write a BMS script for you
## Post #3
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-05T10:43:15+00:00
- Post Title: Soldier Front "sff" file format?

BMS script

```
Get NOF Long 0 ;
Set SHIFT Long 136 ;
Math SHIFT *= NOF ;
Math SHIFT += 4 ;
For I = 1 to NOF ;
SavePos T 0 ;
Get PN String 0 ;
Math T += 128 ;
Goto T 0 ;
SavePos OFO 0 ;
Get FO Long 0 ;
Math FO += SHIFT ;
SavePos OFL 0 ;
Get FL Long 0 ;
Log PN FO FL OFO OFL ;
NEXT I ;

```


Bye
## Post #4
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2007-05-05T13:37:52+00:00
- Post Title: Soldier Front "sff" file format?

Thanks very much!!

You are a star!!
## Post #5
- Username: baccello
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Sep 23, 2004 1:44 am
- Post datetime: 2007-05-05T17:17:04+00:00
- Post Title: Soldier Front "sff" file format?

You're welcome!
