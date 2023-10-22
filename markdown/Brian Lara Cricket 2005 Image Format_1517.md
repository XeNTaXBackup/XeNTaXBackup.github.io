## Post #1
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-09-21T00:27:30+00:00
- Post Title: Brian Lara Cricket 2005 Image Format

Its not usual that I start a post here, but I'm hoping Mr Mouse and/or others can help out cause I don't really know what I am doing.

I am trying to determine the structure of an image format used in the game Brian Lara International Cricket 2005 on PS2. The structure seems simple enough, but I can't get the colors or anything really working like they are supposed to.

The structure is as follows...

```
2 - Image Height/Width
2 - Image Height/Width
2 - Unknown Constant (5)
2 - Number Of Mipmaps
8 - Padding? (all 251's)

// IMAGES

// for each mipmap
  // for each pixel
    1 - Color palette index

// COLOR PALETTE
// for each color (256)
  1 - Red
  1 - Green
  1 - Blue
  1 - Alpha? (always 127)

```


The mipmaps are stored similarly to the Direct-X format - ie each mipmap is half the dimensions of the previous mipmap. So, if the first mipmap is 128x256, the next is 64x128, then 32x64, etc. I have confirmed that this is definately the case, so there is no need to test that the mipmaps are stored this way or anything.

The issue is that the colors are wrong, but in general the image *kinda* looks like it should. For example, here is the largest mipmap for a cricket bat image...



It does look like a cricket bat on its side, and my assumption is that the grainy appearance would not exist once the colors are being picked from the index correctly.

In my code, I know I am loading the colors correctly, and I have tried with the RGBA in different orders but to no avail.

Thanks anyone that can help - I have attached 3 images for those willing to help.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[cricket.zip](https://xentaxbackup.github.io/file/445_cricket.zip)
