## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-19T23:37:20+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

I am looking at a pretty simple image format that someone sent me.
Here's the pic:


(looks like a dragon quest character lol)

As you can see, there is a lot of garbage around the actual character.

Under the image, there is a set of 3 black/white images used as the alpha mask. The left one has a couple red-pixels along the side for some reason, the middle has yellow pixels, and the right has blue pixels. It is like 2 or 3 pixels along the very edge so you wouldn't see it from here.

The size of each mask image is 1/3 the size of the actual image.

If I just manually cut up the image, grab one of those masks, stretch it to the size of the image I want and then delete the stuff that should be transparent, I get the correct image.

I would like to write a tool that will automate this process for me, but am not sure how to deal with the masks.
My algorithm looks something like

1: parse header
2: get pixel data
3: for each mask
4: stretch the mask to the size of the image
5: Do some bit-wise AND's on the appropriate color (I'm guessing this is how alpha masks work)

But is "stretching the mask" really the way to do it?
How would a game engine handle this?
## Post #2
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-20T12:11:12+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

Sounds very interesting.
Could it be that the alpha mask(s) have/has a lower bit depth and just appears as three images with some colours?
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-21T01:01:13+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

Ah, I parsed the pixels at 8bpp and it seems to have done the trick 

Here's a sample:
[sample.zip](https://xentaxbackup.github.io/file/6208_sample.zip)
## Post #4
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-21T23:34:57+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

Header size seems to be 32 bytes, with width and height at 0xC (two ushorts). Followed by width*height*RGB, followed by width*height*A.
## Post #5
- Username: Polefish
- Rank: veteran
- Number of posts: 94
- Joined date: Sat Jun 20, 2009 8:47 pm
- Post datetime: 2013-02-22T11:24:43+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

> Reply from Sir Kane
>
> Header size seems to be 32 bytes, with width and height at 0xC (two ushorts). Followed by width*height*RGB, followed by width*height*A.
Could you explain the information after width and height? Do you mean bits per pixel with RGB?
## Post #6
- Username: Sir Kane
- Rank: veteran
- Number of posts: 104
- Joined date: Mon Aug 06, 2012 11:14 am
- Post datetime: 2013-02-22T12:41:16+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

Wrote a simple tool to convert the images to TGA, but not sure if output is correct. Could you upload/send some more samples and possibly a screenshot of them in game so I can compare?
[http://sktest.aruarose.com/sample.tga](http://sktest.aruarose.com/sample.tga)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-22T16:33:10+00:00
- Post Title: Working with RGB24 and RGB alpha masks for transparency

> Reply from Sir Kane
>
> Wrote a simple tool to convert the images to TGA, but not sure if output is correct. Could you upload/send some more samples and possibly a screenshot of them in game so I can compare?
http://sktest.aruarose.com/sample.tga

Unfortunately I don't know where it is in the game LOL
Here are some more samples with an actual character, so I think if you get something you'll know if it's right

[viewtopic.php?p=83197#p83197](http://forum.xentax.com/viewtopic.php?p=83197#p83197)

Note the different image formats as well as skewing.
This pack contains skewed images

[viewtopic.php?p=83207#p83207](http://forum.xentax.com/viewtopic.php?p=83207#p83207)
