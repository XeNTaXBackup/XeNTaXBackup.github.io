## Post #1
- Username: jawharp
- Rank: advanced
- Number of posts: 53
- Joined date: Thu Sep 24, 2009 12:16 am
- Post datetime: 2016-09-11T15:18:34+00:00
- Post Title: MECC Bitmap Compression

Hey guys,

I've been trying to figure out how some bitmap files I extracted from an archive for the game "Opening Night" for quite some years now, and I'm closer than ever but still stumped.  I was wondering if anyone here has ever heard of image compression like this.

The files are in a folder called "CBMP," so I'm 99.999% sure they're bitmaps.  They have been heavily compressed.  Some of the larger files contain multiple images within them (I think it's for animations in the program).

They have a custom 14 Byte header that has the following little endian values:

# of images in the CBMP file (short)
XSize (short)
YSize (short)
Offset of the Bitmap Data (long)
Size of the Bitmap Data (long)

After that is the bitmap data itself.  A while back, someone said they looked like RLE bitmaps, but I think there's something else going on.  From what I've researched, bitmaps draw their images in scanlines from the bottom up, or from the top down.  When I modified some of the bitmap data just to see what it would do in the program, it appeared that the image was being drawn in 8 pixel chunks from the top left down.  It would go down one column, then start the next column from the top again.  Here's a picture to show you what I mean.

There are also separate files for the color palette.  The palette is not encoded in any way, just the bitmap data.

I've included a link to some of the CBMP files and the color palette file here: [http://s000.tinyupload.com/index.php?fi ... 1282341502](http://s000.tinyupload.com/index.php?file_id=04329952711282341502) 

If anyone has a minute, I'd appreciate any info you'd have on compression like this.  It seems like a weird custom thing, and I'm not sure how to go about reverse engineering it.

Thanks,

  jawharp  
[meccmod3.png](https://xentaxbackup.github.io/file/11695_meccmod3.png)
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2017-04-24T06:45:06+00:00
- Post Title: MECC Bitmap Compression

Bumping this so more people can look into reversing the game (and American Girls Premiere for that matter, no thanks to Lazy Game Reviews doing an episode on this).
## Post #3
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2017-05-16T11:59:34+00:00
- Post Title: MECC Bitmap Compression

[https://msdn.microsoft.com/en-us/library/dd240593.aspx](https://msdn.microsoft.com/en-us/library/dd240593.aspx)

I looked shortly at it and came upon that, just a guess but could be interleaved RLE bitmap encoding perhaps, need some programmer try it all out.
