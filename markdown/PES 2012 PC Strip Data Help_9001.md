## Post #1
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-05-28T14:20:23+00:00
- Post Title: PES 2012 PC Strip Data Help

Hi, I was wondering if some one could help me please, I managed to import PS3 Data.bin files into the Xbox CON Files to allow imported PNG strips to function on the Xbox (currently not supported ) but I would like to move away from the PS3 as a donor & move to the PC, but here is the problem Xbox & PS3 are Big-Endian & PC is Little-Endian.

I need a script to do the flipping of the bytes, they are 32 byte & 16 Byte flips & this isn't in my area  I have tried.

You can find all the files you need on my SVN here
[Pes2012 SVN](http://my-random-modding-stuff.googlecode.com/svn/trunk/PES2012)

[Kit Data Files](http://my-random-modding-stuff.googlecode.com/svn/trunk/PES2012/Kit%20Extracted%20Files) is where the file you want to look at are stored, these are the extracted Strip data for all NG Platforms.

Thank you in advance.

Also would it be possible to find out what graphics type these files are? They are created from importing PNG files, there compressed in some way.
## Post #2
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-05-31T14:52:35+00:00
- Post Title: PES 2012 PC Strip Data Help

More research done on my part, I can convert any platform to PC now but not PC to Xbox :@

Green = Flipped 32 bytes
Blue = Flipped 16 bytes
Red = Nulled/Changed/Same
Orange = changes when encrypted & unencrypted.

Xbox Strip Data = 0B00 0001 0004 0003 686D 1800 0000 0190 0001 0000 0000 0000 0000 006A 0000 0000 01
XBPC Strip Data = 0B00 0001 0300 0400 686D 1800 0000 0000 0100 0000 0000 0000 6A00 0000 0000 0000 01

Yup 100% Works.  the only problem the now is the 0190 value I need to check some more Xbox files but I think its different sometimes.

[](http://img696.imageshack.us/img696/2917/17942061.png)


OK the value 0190 changes per file :\ alot are the same but some are different so far I have found 0000, 0064, 00C8, 012C & 0190 all in Raw Hex its 100, 200, 300 & 400.

It seems the values 0190 differ randomly, but they seem to be needed. If the PC file is 0000 its still shows up as corrupt :@ but I can convert any Xbox strip to PC.
________________________________________________

I dont know if this means anything but

0400 = 1024 (could this be file dimensions)
0300 = 768 (could this be file dimensions)
0100 = 256 (could this be colour count)
## Post #3
- Username: Rocky5
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Jun 21, 2007 6:30 am
- Post datetime: 2012-06-06T00:43:27+00:00
- Post Title: PES 2012 PC Strip Data Help

Don't need help now, I worked it out myself.
