## Post #1
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-01T21:24:49+00:00
- Post Title: [Request] Midnight Club3 Dub Edition - PS2

Another request:

Midnight Club 3: Dub Edition for Playstation 2. (Files from german version SLES_52942)


* --- *

Thanks a lot!
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-10-01T22:58:16+00:00
- Post Title: [Request] Midnight Club3 Dub Edition - PS2

for streams.dat and padding.dat you can use the following quickbms script for dumping all the rstm data (music files to play with vgmstream):

```
get FILES long
for i = 0 < FILES
    get DUMMY long
    get OFFSET long
    get SIZE long

    set NAME string i
    string NAME += ".rstm"

    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-02T14:32:43+00:00
- Post Title: [Request] Midnight Club3 Dub Edition - PS2

Thank you Bugtest, good job,

but I'm especially interested in the texture.dat files, cause I plan to convert some decals to use in other games.

In spite of that, special thanks.
## Post #4
- Username: Andreas
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Sep 30, 2009 9:24 pm
- Post datetime: 2009-10-14T16:30:27+00:00
- Post Title: [Request] Midnight Club3 Dub Edition - PS2

I've tested it with IRipper - No problem.

Bye Andreas
