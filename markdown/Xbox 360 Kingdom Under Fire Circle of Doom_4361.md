## Post #1
- Username: noazett
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-21T00:22:57+00:00
- Post Title: Xbox 360 Kingdom Under Fire: Circle of Doom

Here is a bms script to extract it.

```
#Kingdom Under Fire Xbox 360
#from chrrox

endian big

open FDDE PAK 0
open FDDE SOX 1


get id longlong 1
get files long 1
goto 0x220C 1
for i = 0 < files
    get FILENUM long 1
    get NAMESIZE short 1
    getdstring name NAMESIZE 1
    get DUMMYSIZE short 1
    getdstring DUMMY DUMMYSIZE 1
    get offset long 1
    get zsize long 1
    get size long 1
        clog name offset zsize size
next i

```
## Post #2
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-04-25T13:55:30+00:00
- Post Title: Xbox 360 Kingdom Under Fire: Circle of Doom

hello this is my first post here and i would like to thank you for the bms script you posted above. i was able to extract pak file and i wanted to know how to import model into 3dmax program. So if you have a maxscript or a code to compile, can you please share it?

and by the way thanks for the yukes model converter^^
## Post #3
- Username: Blank9
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Jul 10, 2012 11:09 pm
- Post datetime: 2015-03-09T15:23:56+00:00
- Post Title: Xbox 360 Kingdom Under Fire: Circle of Doom

Hello, ultra noob here:

I tried running the script on the ISO but nothing seemed to work. What type of file should i be running the script on and how do i turn my ISO into that?

Thank you for your help guys
