## Post #1
- Username: supersniper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 13, 2012 2:21 pm
- Post datetime: 2012-08-13T06:31:12+00:00
- Post Title: trouble opening this .dds file

I'm having major issues opening this .dds file and after reading [this](http://forum.xentax.com/viewtopic.php?f=18&t=8793) topic from april I thought I'd register here and ask for help.

I'm currently trying to make an image higher quality by using the .svg file format.   Well in order for me to do that I need to first open the .dds file and convert it to a .png which then I can go from there however I am having trouble opening this .dds file.


Here is all the info on what it looks like and the format it is.


The game is Halo 2 Vista (Based on Halo 2 so the file format is probably 32bit but for some reason photoshop cannot open it)  It reads disk error when I try to open it in photoshop cs6

I read the topic before and noticed a program you guys use called IrfranView, well it opens in there but it's how I expected it to to open (all other .dds viewers and editors I've tried opened it like this)


Help is greatly appreciated, I want to be able to to open these files

Here is the file if you want to try opening it yourself


 Rank 1.zip
Rank 1 (large) .dds bitmap file (885 Bytes) Downloaded 27 times
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-08-13T12:38:15+00:00
- Post Title: trouble opening this .dds file

rank 1 is a valid 32 x 26 DDS file. nothing wrong with it. without knowing what to expect, without knowing what the original looks like, it's hard to be of any help. whatever extractor you used might have read from the wrong offset or something... which is why maybe it looks tilted. can't really tell.

btw, the photoshop disk error is very common. i get it on this computer as well. the NVIDIA plugin is a piece of shit. it works on some people's computers but not on others. lol i noticed it tends to work on pirated versions but not on legal versions of the software. it really is a piece of shit.

EDIT:
Actually, it is invalid after looking at it. I see RGBA masks so datasize should be 0xD00 minimum. Yours is only 0xB60, a little short. So somehow, somewhere the data got cut off.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-08-13T13:08:49+00:00
- Post Title: trouble opening this .dds file

If you just want to open it for converting then TextureFinder can do this. 

8888 = 24+8
Width = 28
Shift = 128

Click on the camera icon to save it as bmp then convert to whatever you want.
## Post #4
- Username: supersniper
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 13, 2012 2:21 pm
- Post datetime: 2012-08-14T04:49:06+00:00
- Post Title: trouble opening this .dds file

Well I've looked into Halo 2 texture bitmaps and it turns out, they are different than normal bitmaps.


You have to decode the raw chunks and shift the surface areas.

It was called deswizzling.  it's within the source code of the extractor I'm using I'm getting one of my buddies to fix the extracting method to implement the deswizziling when it saves.  It views fine which always confused me on my it never saved fine.


Thanks for the help though

If any of you guys want a solution I'll post it.
