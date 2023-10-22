## Post #1
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-02T17:30:38+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

[https://www.mediafire.com/file/ndv6ynb0 ... c.tga/file](https://www.mediafire.com/file/ndv6ynb06g4nil8/cccccc.tga/file)



Hello guys , please help me with this tga image.
Extracted from a 2006 psp game , Miami v T g.
I think It 32 bit tga image rgba.

I want to create my own image of this types. Does anyone no any program which can.
addtional info(hex editor): TGAImage header  00 02 00 02 00 00 05 02 00
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-02T21:09:52+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

It's not a TGA file and it seems to be swizzled.

By the way, it's a good practice to include full game's name in the title...
Did you mean "Miami Vice: The Game"?
## Post #3
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-03T16:35:57+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Yeah I manage to open it with noesis plugin ( tex_JB007FromRussiawithLove_PSP_tga.py)
But it shows strange colours. How can I fix the colour?.
Does anyone any program to create such image?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-03T20:30:28+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Can you upload more samples?
(with different sizes, different names etc.)
## Post #5
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-03T21:35:24+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

More images here [https://www.mediafire.com/file/4efkz8gz ... G.zip/file](https://www.mediafire.com/file/4efkz8gzd1n6thn/MIAM+VTG.zip/file)


On noesis it gives me wrong colours but only the main characters/models and some not all.
[Screenshot_20220603-231619.jpg](https://xentaxbackup.github.io/file/22307_Screenshot_20220603-231619.jpg)
## Post #6
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-03T21:37:19+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Noesis screenshot.

No problem on this one
[Screenshot_20220603-231537.jpg](https://xentaxbackup.github.io/file/22308_Screenshot_20220603-231537.jpg)
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-03T22:47:59+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Try this script:
[https://github.com/bartlomiejduda/Tools ... PSP_tga.py](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Miami%20Vice%20The%20Game/tex_Miami_Vice_The_Game_PSP_tga.py)

It works fine on all your samples.
## Post #8
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-04T10:04:53+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Thanks man, image COLOUR  now appear perfect.
so do you know how to create this image format ?
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-06-04T10:50:54+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

> so do you know how to create this image format ?

I think it could be only possible with some custom tool (as Noesis doesn't seem to support twiddling untwiddled PSP images)

So such tool should do the following:
1. Recreate custom header (there are still 2 unknown values there, but they probably can be copied from original image)
2. Save twiddled image data
3. Save unknown binary data between image data and palette.
4. Save palette

as a result a custom TGA image should be created.
## Post #10
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-04T11:15:33+00:00
- Post Title: Miami Vice: The Game (PSP) - TGA image

Well that sounds like mission impossible 3.  

But it ok. thanks again man, I'll see wat I will do.
