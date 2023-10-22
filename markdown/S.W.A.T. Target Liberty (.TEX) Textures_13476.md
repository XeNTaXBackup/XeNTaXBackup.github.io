## Post #1
- Username: Sleepy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jun 23, 2015 1:59 am
- Post datetime: 2015-10-30T09:26:35+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

Hello guys!

about the game: 
develoled by 3G Studios and published by Sierra. 
Release date: October 26, 2007.

Carluver69 and me figured out the LMP Archives for the game and now we would like to figure out the texture files.

We tried to open it with Dageron's Console Texture Explorer tool but it looks that the palette is not well.
Could anyone help please? 



Samples of .TEX (texture) files 
Settings which we tried in ConsoleTextureExplorer: The textures are swizzled, bpp 8, graphics offset: 640
download: [http://www.mediafire.com/download/n32na ... xfiles.rar](http://www.mediafire.com/download/n32nao09q3i02yj/samples_of_texfiles.rar)

samples uses the following resolutions: 

uzi.TEX's (64*16)
taser_pickup.tex (64*32)
loadscreen.tex (256*64)
fbi_ridel.tex (128*128)
ambulance_tex.tex (256*256)

Thanks, 
   Sleepy
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-30T11:58:22+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

This is the 8 bit grayscale version of a raw file to which one could try to apply the palette data (0x80-0x27F)?



loadscreen_8bitgrayscale.JPG (72.26 KiB) Viewed 190 times
## Post #3
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2015-10-31T22:13:22+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

Thank you so much for your help, shakotay2! It looks like the palette data can't be applied directly, since this is how the colors look in-game (taken from a YouTube video):
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-01T02:08:49+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

> Reply from CarLuver69
>
> It looks like the palette data can't be applied directly, since this is how the colors look in-game (taken from a YouTube video)it should be possible since we've the original colors now - but sadly I'm not capable 



weird.JPG (55.66 KiB) Viewed 168 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-01T11:48:11+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

so this was my nearest hit adding the original palette:



loadscreen_better.JPG (8.06 KiB) Viewed 162 times


but to be honest: I don't know what the problem is...
## Post #6
- Username: Sleepy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jun 23, 2015 1:59 am
- Post datetime: 2015-11-03T13:48:52+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

> Reply from shakotay2
>
> so this was my nearest hit adding the original palette:
loadscreen_better.JPG
but to be honest: I don't know what the problem is...

Looks cool, could you continue trying to figure out it? 
by the way thanks for your and Carluver's help too
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-11-03T16:53:57+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

> Reply from Sleepy
>
> Looks cool, could you continue trying to figure out it?atm my means are exhausted. I tried to interpret the palette data as 16 bit values (5-6-5) but it's just wild guessing.
Do you have a simple .tex file (a picture with less colors) - a monochrome cube for example?
## Post #8
- Username: aaro4130
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Aug 23, 2011 10:01 am
- Post datetime: 2016-01-02T05:44:00+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

The palette is just RGB555 (weird they didn't use the last bit)
## Post #9
- Username: Sleepy
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jun 23, 2015 1:59 am
- Post datetime: 2016-01-04T19:01:15+00:00
- Post Title: S.W.A.T. Target Liberty (*.TEX) Textures

> Reply from aaro4130
>
> The palette is just RGB555 (weird they didn't use the last bit)

Thank you very much. it worked perfectly
