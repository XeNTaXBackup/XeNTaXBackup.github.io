## Post #1
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T01:19:39+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T01:24:59+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

Packed geometry commands, what might that mean?

Anyways I took a quick look at it, and the offset in the material struct that you have in the outline is the offset to the next material. If the offset == 0, then there is no "next" material and so you know that's the last one.

Then you can jump to the mesh offset.
## Post #3
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T05:59:43+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

> Reply from finale00
>
> Packed geometry commands, what might that mean?

Anyways I took a quick look at it, and the offset in the material struct that you have in the outline is the offset to the next material. If the offset == 0, then there is no "next" material and so you know that's the last one.

Then you can jump to the mesh offset.

Can you whip up a script or two for it?
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T06:16:00+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

Don't know the vertex format or how the faces are drawn.

Or even how to get to the vertices.

The bone struct is not consistent either. For example, many of them are 80 bytes, but some of them are bigger.
## Post #5
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T06:24:46+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

> Reply from finale00
>
> Don't know the vertex format or how the faces are drawn.

Or even how to get to the vertices.

The bone struct is not consistent either. For example, many of them are 80 bytes, but some of them are bigger.

Damn. So in other words, it's a spaghetti of sorts. As in a little more or less scrambled.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T06:29:52+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

There's probably a value in there that determines how many extra bytes to read.
There are three offsets at the top of the file, and the material offset is easy to work out, same with the bones offset.

But then the third offset just takes me to the bottom of the file with a bunch of other offsets that I'm not sure what to do with.
## Post #7
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T06:40:01+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

> Reply from finale00
>
> There's probably a value in there that determines how many extra bytes to read.
There are three offsets at the top of the file, and the material offset is easy to work out, same with the bones offset.

But then the third offset just takes me to the bottom of the file with a bunch of other offsets that I'm not sure what to do with.

So, was it a lot more complicated than it seems to be?
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T06:42:06+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

It seemed complicated from the start cause I saw "NDS" and thought "must contain all sorts of ways to squeeze as much info as they can into a small file"

Upload a couple dozen more of different sizes (particularly objects that do NOT have bones).
Maybe it will become more obvious what the values mean.

I rarely get anything done with only one file.

For example, the third offset sends me to a section that tells me how many offsets there are, and it seems to coincide with the number of bones.

In fact, they may not even be bones despite being called "RightShoulder"
## Post #9
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T06:52:29+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T07:12:15+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

What did low lines use to decompress it.
I found a "batchlz77" tool for NDS games but it doesn't recognize this.
## Post #11
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-22T08:33:08+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

> Reply from finale00
>
> What did low lines use to decompress it.
I found a "batchlz77" tool for NDS games but it doesn't recognize this.

Might try asking him on how did he decompress the files, but he doesn't seem to be online ATM.
## Post #12
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T17:55:53+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

Decompress script: [viewtopic.php?f=21&t=8373](http://forum.xentax.com/viewtopic.php?f=21&t=8373)

You can see that some of the files don't even have that third offset and just end with what I would assume to be geometry data.
## Post #13
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-23T02:28:47+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

Thanks. If you need some more files to be RE'd, let me know. I actually needed the models for some game conversion, and, well, just for the lulz. I could've used them 3D ripping tools instead, but none of them work well on any DS emulator, perhaps due to the way how the DS GPU works.
## Post #14
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-23T02:49:52+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

Since the models are extremely small I wouldn't mind if you just uploaded all of them  
That way I can go through them myself and look for what's good to compare with.
## Post #15
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-23T03:18:10+00:00
- Post Title: [NDS] The Four Seasons Cake .n3d, part 2

The contents of this post was deleted because of possible forum rules violation.
## Post #16
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-26T04:12:54+00:00
- Post Title: Re: [NDS] The Four Seasons Cake .n3d, part 2

Sorry for the double post, but any progress on the model formats?
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-26T17:36:06+00:00
- Post Title: Re: [NDS] The Four Seasons Cake .n3d, part 2

Nope none at all.
Can't figure out the vertices at all.
## Post #18
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-02-27T01:46:39+00:00
- Post Title: Re: [NDS] The Four Seasons Cake .n3d, part 2

> Reply from finale00
>
> Nope none at all.
Can't figure out the vertices at all.

Damn, that's too bad.
