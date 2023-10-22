## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-13T17:33:46+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

I have some images that are obfuscated. Rows and columns have been shifted all over the place, rotated, etc.

Though fortunately the only operations are shifting and rotating...

Are there any GUI tools where I can load up the image and then manually start moving rows/columns/blocks of pixels around to try and figure out an algorithm? Kind of like one of those puzzle games except more general-purpose.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-14T10:45:13+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> Are there any GUI tools where I can load up the image and then manually start moving rows/columns/blocks of pixels around to try and figure out an algorithm?Wouldn't it be the easiest way to get some image loading library and code this for yourself? With "C" there's GetPixel() and SetPixel(). You could "scan" the loaded image using RGBval= GetPixel(hdc, x, y) and create a copy using SetPixel(hdc,x+xOffs+x_screen_width/2,y+yOffs, RGBval).

(xOffs and yOffs choosen depending on your algo. There would arise some problem if the image size crossed half of your x screen width.)
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-14T16:21:12+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

Code the image manipulation GUI? Well, I would if I had some idea how to go about it.

If you mean it would be easier to just write some code to move pixels around, I have no idea how to manipulate the image in such a way that I would be getting close to the solution. if anything I would just be blinding shifting rows and columns around. Maybe if I did enough of these "puzzles" I could just look at it and figure out how it works (kind of like how some people look at a rubick's cube and solve it in 15 seconds)

The purpose of the tool is to allow users to fiddle around with pixels to see if they can come up with such an algorithm.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-14T16:33:52+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> The purpose of the tool is to allow users to fiddle around with pixels to see if they can come up with such an algorithm.Ok, I think I got the point now (when you spoke of "shifting and rotating" I thought you had some imagnation of an algo).

Could you upload or PM an example image?
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-02-14T22:03:24+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> I have some images that are obfuscated. Rows and columns have been shifted all over the place, rotated, etc.

Though fortunately the only operations are shifting and rotating...

Are there any GUI tools where I can load up the image and then manually start moving rows/columns/blocks of pixels around to try and figure out an algorithm? Kind of like one of those puzzle games except more general-purpose.
Are you sure it isn't just swizzled?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-14T23:20:22+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

It might be, but I believe "swizzling" is the term that's used to describe images that have been obfuscated and not an actual algorithm?

Here's an example:
## Post #7
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-02-15T04:03:25+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> It might be, but I believe "swizzling" is the term that's used to describe images that have been obfuscated and not an actual algorithm?

Here's an example:
No, swizzled textures are not obfuscated, just in the direction that is faster read from the cache, for the GPU that uses them.

[http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)

Actually, from the looks of the image, it looks swizzled to me.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-02-15T05:18:33+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

@finale00: thx for the image

> Reply from brienj
>
> No, swizzled textures are not obfuscated, just in the direction that is faster read from the cache, for the GPU that uses them.

http://fgiesen.wordpress.com/2011/01/17 ... swizzling/

Actually, from the looks of the image, it looks swizzled to me.Looks like you're right:

smallest entity seems to be a 8x4 pixel block.
So from your linked text: "– all you need are the right masks".
Nice text, unswizzeling code included.  

This is what I wrote before reading that text:

Smallest "intact" entity seems to be a 8x4 pixel block.
So there would be 32x90= 2880 of these blocks.

Estimated portion of black pixels maybe 40%.

We would have approximately 1700 blocks to shift and rotate;
to be honest I don't believe this can be solved without having the original image.

I suppose it's an images from a game?
If so there might be a chance to get original images using 3D ripper on the game.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-15T14:27:07+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

@brienj thanks for the clarification.

@shakotay2 I will try 3D ripper on it. It's a 2D game but images are just images no matter whether it's for a 3D game or not so it should work as well.
## Post #10
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-02-15T15:09:14+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> @brienj thanks for the clarification.

@shakotay2 I will try 3D ripper on it. It's a 2D game but images are just images no matter whether it's for a 3D game or not so it should work as well.
No problem.  I always like to think of swizzling as a different endianness for GPUs.  LOL

I even have some more swizzling source code somewhere on my computer, if you need more examples.
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-15T18:23:41+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

After reading through the blog post I have some idea behind swizzling. 
Are there any tools that implement the various algorithms that I can just throw my images at and see if I get something?
## Post #12
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2013-02-15T23:07:13+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

> Reply from finale00
>
> After reading through the blog post I have some idea behind swizzling. 
Are there any tools that implement the various algorithms that I can just throw my images at and see if I get something?
Not that I know of.  Basically, you have to have source code, and a general idea of how it is being swizzled, then change stuff until you get it correctly.  Looking up the data on the GPU is a good way to figure it out too.
## Post #13
- Username: finale00
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-02-16T01:02:27+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

Did you try morton ordering that is a pretty common swizzle.
There is an example in noesis in the script for time splitters 2.

```
		data = bytearray()
		for y in range(0, imgHeight):
			for x in range(0, imgWidth):
				idx = noesis.morton2D(y, x)
				if (idx*4+4) > datasize:
					idx = 0
				bs.seek(128 + idx*4, NOESEEK_ABS)
				data += bs.readBytes(4)
		data = rapi.imageDecodeRaw(data, imgWidth, imgHeight, "b8g8r8a8")
		texFmt = noesis.NOESISTEX_RGBA32
```
also
[http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)
## Post #14
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2013-02-16T09:46:47+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

Be sure to post the unswizzled image if you get it; I'm wanting to know what it is now. =3
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-16T16:39:43+00:00
- Post Title: Tools for manipulating images at pixel-level and block-level

I guess I will work for the things I want 
lol but yes noesis would make thing easier.
