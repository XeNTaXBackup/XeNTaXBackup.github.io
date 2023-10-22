## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T02:16:54+00:00
- Post Title: D. Grayman TIPS images

PS2 game.

There is some header information at the top, followed by the image data afterwards.
There can be multiple images stored in a single TIPS file.

Anyone want to try it out? The images themselves are uncompressed so it's probably just something common like rgba32 or rgb24, and the only thing that needs to be figured out is the structure of the header.

Each header is 64 bytes in size, with lots of null bytes so there's probably only 5-6 pieces of data.
[dgray.7z](https://xentaxbackup.github.io/file/5501_dgray.7z)
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-20T18:53:50+00:00
- Post Title: D. Grayman TIPS images

complicated format. some look standard rgba, others do not.
some files look like some type of RLE (see bottom of file and repetitious 007CFFFFFFFF). in fact, i'm thinking not all TIPS are textures.

FACE_05 look like this as a 32-bit bitmap. need to see original in-game footage of the file below to figure out organization.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T19:10:02+00:00
- Post Title: D. Grayman TIPS images

Here's a video of a battle scene: [http://www.youtube.com/watch?v=_55iVIGedMg](http://www.youtube.com/watch?v=_55iVIGedMg)

Here's the background loaded as rgba32: 



Definitely looks like it's a little jumbled up.
What usually causes an image to look like this? RLE compression?

The type of data may be stored in the header. The ones that are rgba32-like have very similar values.
[BTL_BG00.7z](https://xentaxbackup.github.io/file/5503_BTL_BG00.7z)
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-20T19:36:06+00:00
- Post Title: D. Grayman TIPS images

BTL_CHARA TIPS look like a different format; I thought maybe RLE, but doesn't look like it. FACE and BG00 look swizzled in some way. the width and height are right there... it appears to be the way the data is ordered. i'm too lazy to try a morton on it right now; don't think it would work... morton usually makes it look more messed up than that. did you try a morton on it using noesis?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T19:42:19+00:00
- Post Title: D. Grayman TIPS images

What's a morton? lol

```
   int32 header_size
   int32 ?
   int16 width
   int16 height
   ...
}

```


I was thinking it might be something like that, and then the offset is stored somewhere after, but the first entry usually has a height value of 0. Maybe it's not an image entry.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-20T20:00:10+00:00
- Post Title: D. Grayman TIPS images

[a swizzling algorithm](http://forum.xentax.com/viewtopic.php?f=16&t=7269&start=30). it's not a morton... just tried it... made it even worse lol. i tried various offsets... nothing seems to straighten it out.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T20:12:42+00:00
- Post Title: D. Grayman TIPS images

Was hoping to see what kind of resources they have quickly lol

If it's similar to the archive format maybe one of the integers is supposed to be multiplied by something to get the starting offset. And if they're not all images then presumably they must store the size as well.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-20T20:30:25+00:00
- Post Title: D. Grayman TIPS images

yeah, sometimes the way they store things can be really fucked up. one game i was trying i had the original source image...



but I loaded this and no matter what I did to tweak the data I could not figure out their storage algorithm.



you can see they look nearly the same but not quite... reminds me of that lol. it can drive you crazy; i would give up before it gives you any more headaches lol.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-06-20T20:46:52+00:00
- Post Title: D. Grayman TIPS images

you can also try a tiling algorithm and see if that works
[http://fgiesen.wordpress.com/2011/01/17 ... swizzling/](http://fgiesen.wordpress.com/2011/01/17/texture-tiling-and-swizzling/)
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-20T21:21:35+00:00
- Post Title: D. Grayman TIPS images

World needs more dgrayman merchandise, but that was probably 4 years ago
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-06-22T02:56:16+00:00
- Post Title: D. Grayman TIPS images

Looks like there are several types of TIPS files; can be identified by reading the first 4 bytes.
The ones that start with 0x40 are the images.

There doesn't seem to be a number that indicates how many image entries there are, but you can determine that by reading an integer, checking if it's 0x40, and read the rest of the header, and then read another integer and see if it's 0x40 again. Headers end when you read a 0 instead of an 0x40.

Hmm, the background one looks like the entire image was split up into smaller rectangles.
In the case of BG00, there are 5 rectangles across and 8 rectangles down.

Looking at the top-left rectangle, the "V" wall-pattern is sort of there, but it looks like the "V" on the right is overlapping it.

The fact that all of the images look like they went through a shredder may suggest that each rectangle is further split up into a bunch of rows, and then rows are swapped with other rectangles to produce that interleaving look. However, the overlap doesn't seem to make any sense.

Unless, of course, it's not the same as the one I'm seeing in the video (could be a similar one).

If I can parse the whole TIPS file to quickly look at what they have it might become easier to figure out what's going on.

But the data headers don't make much sense to me.
Assuming it is similar to the archives, it could be the 16th byte into each header, which is always increasing as you iterate over each header.

It might also be the fact that I'm not copying the correct chunk of data out so it's not obvious why the V's are overlapping.
