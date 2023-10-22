## Post #1
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2019-12-03T20:01:48+00:00
- Post Title: Worms Armageddon SPR file (DC)

Hello, I am moving the Dreamcast version of this game to Spanish, I need how to pass this sprite to bmp to be able to edit and replace it

examples


 FR01.rar
(1.08 KiB) Downloaded 17 times



REGARDS
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-03T21:48:46+00:00
- Post Title: Worms Armageddon SPR file (DC)

(There is a Graphics subforum for such - where is the problem not to place your request there?)
.



sprite.png (137.47 KiB) Viewed 85 times
## Post #3
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2019-12-03T22:46:02+00:00
- Post Title: Worms Armageddon SPR file (DC)

Huy, the thing is that I was going to post it there, but I had to make a mistake, and I didn't realice


Is that the image obtained?

The set of rows of this spr are 6 and make the French flag in motion
## Post #4
- Username: domingo
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2019-12-04T00:11:17+00:00
- Post Title: Worms Armageddon SPR file (DC)

> Reply from shakotay2 ↑Wed Dec 04, 2019 5:48 am at Wed Dec 04, 2019 5:48 am
>
> 
(There is a Graphics subforum for such - where is the problem not to place your request there?)

Moved.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-04T08:36:05+00:00
- Post Title: Worms Armageddon SPR file (DC)

> Reply from domingo ↑Wed Dec 04, 2019 6:46 am at Wed Dec 04, 2019 6:46 am
>
> Is that the image obtained?

The set of rows of this spr are 6 and make the French flag in motionYou see what I got with trial 'n error. You need to fiddle around with it, colour depth and so on.
.



test2.png (67.98 KiB) Viewed 72 times
## Post #6
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2019-12-04T13:08:57+00:00
- Post Title: Worms Armageddon SPR file (DC)

I downloaded that program, but trying to open the row gives me an error of "impossible to read header" I tried how raw file the same thing happens to me.

Do I need a plugin or a different version?

Or maybe there is something I do wrong
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-12-04T16:24:46+00:00
- Post Title: Worms Armageddon SPR file (DC)

File/open as/raw file
use raw open parameters
width 110, height 48,  header size 24
8 BPP
## Post #8
- Username: domingo
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Mar 25, 2016 6:43 am
- Post datetime: 2019-12-05T18:50:06+00:00
- Post Title: Worms Armageddon SPR file (DC)

I have tried another "tilemolester" program since the Infaview does not give me options to set parameters when opening it as raw, it always gives me an error when trying to open it.

This "tilemolester" program can adjust bpp, 1 or 2 dimensions while you are looking for the correct resolution, but the most I can see is the image you have placed above.

I think that this row have be compressed since each of 6 that make up the French flag in motion has a different weight in bytes, and if an image with the same resolution and same palette should have the same weigh

If you wish I can upload the other rows
