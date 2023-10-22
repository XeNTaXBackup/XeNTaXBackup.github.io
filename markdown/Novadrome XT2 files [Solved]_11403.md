## Post #1
- Username: Errol
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 11, 2014 4:34 am
- Post datetime: 2014-04-10T20:58:12+00:00
- Post Title: Novadrome XT2 files [Solved]

'ello,

I'm having a bit of a dabble trying to work out the XT2 files used by X360 Arcade game Novadrome.  At first glance they seemed pretty simple, bigendian, 76 byte header (with width at 0x12 and height at 0x14) and then 4 bytes per pixel in ARGB order.

Simply reading the bytes and creating the pixels from 0,0 to width,height resulted in...



I then had a try at doing sequential 32x32 (0,0 to 31,31 then 32,0 to 63,32 and so on) blocks (not too sure why I tried this to be honest) and got...



This was promising!  However, I've not actually made any headway since.  I can pop a copy of CONTROLLER360.XT2 from the Novadrome demo somewhere if necessary but really I was just hoping for some general hints as to what to try next.

UPDATE:


I decided to read back through the pages here to see if anyone had a similar problem and came across [[DOC] Xbox360 texture basics, swizzling, endian](http://forum.xentax.com/viewtopic.php?f=18&t=10857) by Dageron which linked through to this [excellent article here](http://dageron.com/?page_id=5238&lang=en).  My deepest thanks Dageron for taking the time to write such a useful article.

Cheers,
Errol
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2014-04-11T07:46:42+00:00
- Post Title: Novadrome XT2 files [Solved]

Good!
