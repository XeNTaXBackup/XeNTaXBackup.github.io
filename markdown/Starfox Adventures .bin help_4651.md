## Post #1
- Username: Thevoid
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 23, 2010 9:23 pm
- Post datetime: 2010-06-23T20:37:03+00:00
- Post Title: Starfox Adventures .bin help

Well, first of all, hello. I'm new around here and I was reading the forums long time ago.

The reason of this post is I made lot of research finding a way to open the .bin files from Rare's last GC game, Starfox Adventures and seems there's no way to unpack them.

I'm not good using hex editor or looking at the info inside those .bin archives, but I found some parts on with "ZLB"(which I think it is zlb compressed).

Here's an example of those .bin files (thats the original name it has):

[http://www.mediafire.com/?toiwy054zoi](http://www.mediafire.com/?toiwy054zoi)

Hope someone could help, thx in advance!
## Post #2
- Username: surix
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jun 06, 2010 11:17 am
- Post datetime: 2010-06-23T21:42:00+00:00
- Post Title: Starfox Adventures .bin help

just looked quick but yeah everything is in there to decompress the files.

first two headers for compressed files read as follows (big endian)

magicnum
640 //deflated data size
12
256
24
40
0
0
0
ZLB/0
1
640 //deflated data size
216 //compressed data size
[data]

[some white space]


magicnum
185504 //deflated data size
12
107616
24
40
1
858
8512
ZLB/0
1
185504 //deflated data size
107598 //compressed data size
[data]

..etc
## Post #3
- Username: Thevoid
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-23T21:55:55+00:00
- Post Title: Starfox Adventures .bin help

ah it must be zlib found that 58 85 can be a zlib header.

here is a bms script if there is some file with names in it let me know or post the .dol file here as it might contain the names.

```
endian big
for i = 0 < 0xFFFF
findloc start string "ZLB"
goto start
get zlb long
get unk01 long
get size long
get zsize long
savepos offset
set name i
string name + .ext
      clog name OFFSET ZSIZE SIZE
math offset += zsize
goto offset
next i

```
## Post #4
- Username: Thevoid
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 23, 2010 9:23 pm
- Post datetime: 2010-06-25T16:13:10+00:00
- Post Title: Starfox Adventures .bin help

> Reply from chrrox
>
> ah it must be zlib found that 58 85 can be a zlib header.

here is a bms script if there is some file with names in it let me know or post the .dol file here as it might contain the names.

Well, looking again to the structure I didn't found any .dol file but I send one complete folder, what I think is from the game menu to take a look  (basically all the assets for the level and items are on separate folders naming what part of the game is it).

[http://www.mediafire.com/?gmtznywitq0](http://www.mediafire.com/?gmtznywitq0) 

Hope that will help a little more.
## Post #5
- Username: Thevoid
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Jun 23, 2010 9:23 pm
- Post datetime: 2010-07-04T13:54:28+00:00
- Post Title: Starfox Adventures .bin help

Any news about this? using 3dxripper I was capable to get some of the scenes, but the characters got the UV maps screwed   .
