## Post #1
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2015-06-24T11:32:30+00:00
- Post Title: Texture format in DMC4: Special Edition

Can anyone make sense of this?

Texture from DMC4 SE: [http://www.tzarsectus.com/temp/wp002_Yamato_NM.tex](http://www.tzarsectus.com/temp/wp002_Yamato_NM.tex)
Resolution: 512x1024
Mipmaps: 10
Image data starts at offset 0x38

Here's how the texture should look like (taken from DMC4): [http://www.tzarsectus.com/temp/wp002_Yamato_NM.dds](http://www.tzarsectus.com/temp/wp002_Yamato_NM.dds)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2015-06-25T10:08:56+00:00
- Post Title: Texture format in DMC4: Special Edition

looks like something is different with the colors ma-bee. but the data seems to be in the right order.
you could try an endian swap.
## Post #3
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2015-06-25T14:30:10+00:00
- Post Title: Texture format in DMC4: Special Edition

First mip of each texture:
[http://www.tzarsectus.com/temp/wp002_Ya ... rstmip.tex](http://www.tzarsectus.com/temp/wp002_Yamato_NM-DMC4-firstmip.tex) (from DMC4)
[http://www.tzarsectus.com/temp/wp002_Ya ... rstmip.tex](http://www.tzarsectus.com/temp/wp002_Yamato_NM-DMC4SE-firstmip.tex) (from DMC4: SE)

I'm pretty sure the endianness is the same. I'm wondering if this is a variant of the DXT5 format optimized for the colours you usually see in normal maps? If you look at the end of the image data which is supposed to be a solid colour, it's defined a bit differently in each version.
## Post #4
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2015-06-28T13:21:59+00:00
- Post Title: Texture format in DMC4: Special Edition

Figured it out, it's 3Dc (aka bc5) compression:
## Post #5
- Username: Creelien
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jul 05, 2015 10:24 pm
- Post datetime: 2015-07-05T14:38:32+00:00
- Post Title: Texture format in DMC4: Special Edition

Is there a tool or method to edit these files without messing the textures up?
