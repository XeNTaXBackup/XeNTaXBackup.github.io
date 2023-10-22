## Post #1
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-01-09T10:51:02+00:00
- Post Title: [Wii] U-Sing *.myspd Audiofiles

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Lifestyle
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 09, 2010 10:50 am
- Post datetime: 2010-01-09T14:07:51+00:00
- Post Title: [Wii] U-Sing *.myspd Audiofiles

There is also an directory called axdemo which contains spd/spt pairs.

There is also a directory compressor.

I thing it's possible, that the myspd file is compressed with this tool.
## Post #3
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-10T20:52:53+00:00
- Post Title: [Wii] U-Sing *.myspd Audiofiles

IMA (DVI-order), one channel in its entirety then the other.  If you want to decode it right now, try sox:

sox -r 32000 -N -t ima audio1.myspd out.wav

I'll poke at adding it to vgmstream.

Not DVI, the other one.  Added to [vgmstream](http://hcs64.com/vgmstream.html) r724.
## Post #4
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2010-01-10T21:48:31+00:00
- Post Title: [Wii] U-Sing *.myspd Audiofiles

Wow, this was fast    Thank you.
Out of curiosity how did you found out? Could you explain what the bytes in the header are for pls?
Would be nice to learn more about such things.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-10T22:51:24+00:00
- Post Title: [Wii] U-Sing *.myspd Audiofiles

The data just had an IMA-y look to it, so I ran it through sox and sure enough it worked.  I don't know what all of the header means, but I do have the following (32-bit big endian as is native for Wii):

0x00: size of a channel, in bytes (there are two channels per file, first starts at 0x20, second is this many bytes later)
0x04: sample rate (32khz)
0x08 and 0x0c: unknown (seems to be channel size * 8 - 4, maybe bit offset of last sample as IMA is 4-bit?)
0x10: last sample (sample count -1, also channel size * 2 - 1 as there are 2 samples per byte)
0x14: unknown (FF FF 00 00 on one and 00 00 00 00 on the other)

Didn't have a whole lot to look at, but this was enough to be able to play it, at least for those two files.  All I use is the channel size and sample rate.
