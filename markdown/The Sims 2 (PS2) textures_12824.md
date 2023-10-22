## Post #1
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-05-07T18:40:06+00:00
- Post Title: The Sims 2 (PS2) textures?

Supposedly this game has a boatload of unused stuff, and most of it is in the textures. I got somebody (aluigi) to extract the .ARC files, but the textures have no extension to them. I will attach a few textures that were extracted, and if anybody can make a program that can convert these to .PNG, or .JPG, then please do.

Link to zipped folder with 5 different textures:

[https://www.dropbox.com/s/otu0pxpg7vpib ... s.zip?dl=1](https://www.dropbox.com/s/otu0pxpg7vpib7w/Texures.zip?dl=1)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-07T19:26:12+00:00
- Post Title: The Sims 2 (PS2) textures?

Check out Dageron's [Console Texture Explorer](http://dageron.com/?page_id=2535&lang=en). It'll help you extract textures from PS2 games:
## Post #3
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-05-07T20:01:57+00:00
- Post Title: The Sims 2 (PS2) textures?

Seems to me this program works, but not entirely. The textures which I tried didn't work, unfortunately. The program does display stuff, but it is mostly a pixelated mess.
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-05-07T20:57:37+00:00
- Post Title: The Sims 2 (PS2) textures?

Can you send some more samples? Preferably larger ones, since it's somewhat difficult to make anything from the ones in the OP.
## Post #5
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-05-07T21:30:01+00:00
- Post Title: The Sims 2 (PS2) textures?

oops! Here are the biggest ones

[https://www.dropbox.com/s/ngi3s7e7xb881 ... s.zip?dl=1](https://www.dropbox.com/s/ngi3s7e7xb881zd/sims2textures.zip?dl=1)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-08T03:03:06+00:00
- Post Title: The Sims 2 (PS2) textures?

nice tool!



team_picture.JPG (123.55 KiB) Viewed 286 times
## Post #7
- Username: Dageron
- Rank: advanced
- Number of posts: 56
- Joined date: Mon May 25, 2009 3:22 pm
- Post datetime: 2015-05-10T06:08:22+00:00
- Post Title: The Sims 2 (PS2) textures?

> Reply from frogz2007
>
> Seems to me this program works, but not entirely. The textures which I tried didn't work, unfortunately. The program does display stuff, but it is mostly a pixelated mess.
Try to turn on or disable swizzling, check both cases.
Also if your texture is not 4bpp or 8bpp this tool seems to be useless.
## Post #8
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-06-29T06:25:20+00:00
- Post Title: The Sims 2 (PS2) textures?

Sorry to bump the thread, but does anyone have a tutorial of some sort that will help me determine the offset of the image and such?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-30T10:08:19+00:00
- Post Title: The Sims 2 (PS2) textures?

seriously?
The picture in my previous post should show all you need.
The offset 65 (dec.) is addr 0x41.
## Post #10
- Username: frogz2007
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Nov 10, 2014 9:13 am
- Post datetime: 2015-06-30T11:16:32+00:00
- Post Title: The Sims 2 (PS2) textures?

Yes, seriously. The offset shown works for that one image, but the others, no. I am terrible with hex editors. I'll attach one of the images I'm trying to figure out;

[https://www.dropbox.com/s/2jtigjbbmhzks ... creen?dl=1](https://www.dropbox.com/s/2jtigjbbmhzksfj/boot_screen?dl=1)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-06-30T20:56:53+00:00
- Post Title: The Sims 2 (PS2) textures?

the offsets vary a little bit depending on the length of the texture name which starts at 0x10:


boot_screen.JPG (83.54 KiB) Viewed 228 times
## Post #12
- Username: moonsarito1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jul 03, 2023 9:45 am
- Post datetime: 2023-07-03T03:47:23+00:00
- Post Title: The Sims 2 (PS2) textures?

Where can I download this Console Texture explorer [psp/ps2] ?

I'm trying to open Need for Speed Carbon: Own the City files from PSP and Zeebo.
## Post #13
- Username: moonsarito1
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-03T18:52:12+00:00
- Post Title: The Sims 2 (PS2) textures?

> Reply from moonsarito1 ↑Mon Jul 03, 2023 11:47 am at Mon Jul 03, 2023 11:47 am
>
> 
Where can I download this Console Texture explorer [psp/ps2] ?

Here [viewtopic.php?t=15540](https://forum.xentax.com/viewtopic.php?t=15540)
