## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-19T04:50:52+00:00
- Post Title: LithTech dtx and calculating pixeldata size

I think these are lithtech dtx images anyways.
I used texturefinder and it looks like r8g8b8a8 format, but I don't know how to determine the size of the pixel data.

There should be only one texture in the ones I uploaded.

There are tools that convert these files to tga, but I haven't found any source for them.
In general, is there a way to calculate the size of the pixeldata if I have some idea what the pixel format is, as well as the dimensions of the image?
[LithTech.7z](https://xentaxbackup.github.io/file/5084_LithTech.7z)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-21T04:14:03+00:00
- Post Title: LithTech dtx and calculating pixeldata size

After searching around, it looks like there are actually two similar formats for dtx.

I've confirmed that the pixel format is RGBA32 (for the ones I'm looking at anyways) and am just doing a rough "seek to pixel data start offset and read everything in"

Which isn't the right way to do it.

But it looks like a single dtx file may contain multiple images.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-02-21T04:58:02+00:00
- Post Title: LithTech dtx and calculating pixeldata size

It looks like the image dimensions are at 0x8 and 0xA
80 = 128
40 = 64

CHANDELIER2.DTX = 128x128 
THRONE.DTX = 128x128
VIALS.DTX = 64x64
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-29T14:42:16+00:00
- Post Title: LithTech dtx and calculating pixeldata size

It looks like not all images are rgba32, cause 4*height*width doesn't produce anything.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T09:43:06+00:00
- Post Title: LithTech dtx and calculating pixeldata size

Hmm, it looks like one format of the dtx works, but the other format doesn't.
I don't see that much of a difference between the two. What's the problem?

[http://db.tt/jVR8Q8kr](http://db.tt/jVR8Q8kr)
[dtx.7z](https://xentaxbackup.github.io/file/5263_dtx.7z)
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-04-06T18:48:42+00:00
- Post Title: LithTech dtx and calculating pixeldata size

dh_c007_xunyegui.dtx seems to have the image dimensions at 0x1 and 0x3 instead of 0x8 and 0xA and was the only sample that worked with your import script.

01 = 256

dh_c007_xunyegui.dtx = 256x256

I'm not a programmer so i don't know how or if this would affect your code.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-06T18:56:30+00:00
- Post Title: LithTech dtx and calculating pixeldata size

Ya, I've handled the cases where the dimensions are stored in different places.

I think it is my pixel format.
I mean, it works for some of them, but it doesn't work for the rest. It's like if I'm lucky, I'll just happen to get something.

Guess I'll have to spend some time reading about image formats.
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2012-04-07T01:05:29+00:00
- Post Title: LithTech dtx and calculating pixeldata size

The dtx plugin for Photoshop can open all of your samples except for dh_c007_xunyegui.dtx
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-07T01:32:03+00:00
- Post Title: LithTech dtx and calculating pixeldata size

Lol that's amusing, cause those are the only ones I can open more often. I think there are mipmaps in there as well, and but that shouldn't be my issue atm. I was reading about dtx and some people distinguish between lithtech and nexon format, but I don't think they are that different.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-07T03:32:47+00:00
- Post Title: LithTech dtx and calculating pixeldata size

Oh what, I think I see the problem.

I said that each pixel is 32-bits for the RGBA, and assuming it is RGBA, all of the A values are 0.
Reading about alpha channel, it looks like 0 means it's completely transparent.

.......So maybe if I just specified RGB24 with a 4-byte stride it will work out! There's probably a value that indicates whether the alpha channel is used or not.

The other textures that actually worked didn't have all 0's for their alpha value, so that's probably why they showed up.

EDIT:

AND......

It works! Sort of. Some of the textures are still messed up, but at least it shows up now.
I just need to make it more efficient now...



Now the other problem is that some of the pixels are compressed it seems.
Like, you have a 256x256 image, which is 65536 pixels so there should be at least that many bytes of data...but the entire file is like 43520 bytes.
[CEILINGS.7z](https://xentaxbackup.github.io/file/5274_CEILINGS.7z)
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-11T18:05:44+00:00
- Post Title: LithTech dtx and calculating pixeldata size

Turns out the pixel format was BGR(A) and not RGB(A)
Lol was wondering why everything was so blue.

And it looks like DTXView can read the files.
Damn it I want to figure out what the pixel data is but not sure how to do so.
## Post #12
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-06-09T00:44:34+00:00
- Post Title: LithTech dtx and calculating pixeldata size

is this the same format used in combat arms??
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-16T00:00:45+00:00
- Post Title: LithTech dtx and calculating pixeldata size

I'm assuming all dtx formats are standard to the engine.
There seems to be an odd dtx format as well, mainly used for wall/floor textures. Couldn't figure that one out.
