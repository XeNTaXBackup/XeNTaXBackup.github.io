## Post #1
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2009-12-22T16:12:48+00:00
- Post Title: TR X360 texture format

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2009-12-23T15:24:42+00:00
- Post Title: TR X360 texture format

The contents of this post was deleted because of possible forum rules violation.
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-12-24T08:43:24+00:00
- Post Title: TR X360 texture format

Hi this is mariokart64n, I PM'd you on the tombraider forum...

haha seems I was right. these are indeed DDS textures. and yes are swizzled aswell. ^.^

example of the header;
00000000   58 33 36 30 1A 20 01 54  00 00 00 00 00 00 00 00   X360. .T........
00000010   02 00 02 00 00 09 00 03                            ........

DDS compression is 54 = DXT5, 52, DXt1... etc
the dimension are 0200 x 0200 = 512x512 in dec.
## Post #4
- Username: kekko
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Nov 01, 2008 9:26 pm
- Post datetime: 2009-12-24T08:55:17+00:00
- Post Title: TR X360 texture format

Hi mariokart, thank you for your help.
I'd like to add the "unswizzle" algorithm to the unpacker, how does it work?
bye!
## Post #5
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-12-24T13:35:42+00:00
- Post Title: TR X360 texture format

personally I can't code or program, and since its a tiling type of swizzle I was able to create a automation to rearrange the pixels in paintshoppro.

although there are a few sources that have working unswizzle code. it's either borrowed from someone else, or illegally obtained from the SDK...  so I guess if you wanted to, you could email Surveyor, he's converted someone elses python scripts into C# I believe?
