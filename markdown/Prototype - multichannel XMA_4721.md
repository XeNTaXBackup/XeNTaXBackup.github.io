## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-06T21:07:21+00:00
- Post Title: Prototype - multichannel XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-07-07T13:34:28+00:00
- Post Title: Prototype - multichannel XMA

Hmm. This really is a weird structure...also, it looks like you cut out the P3D/D3P header.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-07T23:18:54+00:00
- Post Title: Prototype - multichannel XMA

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-07-08T12:13:35+00:00
- Post Title: Prototype - multichannel XMA

What is it that you're trying to do? decode bgm, sfx/voices, or all?
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-08T15:32:56+00:00
- Post Title: Prototype - multichannel XMA

> Reply from bxaimc
>
> What is it that you're trying to do? decode bgm, sfx/voices, or all?
Actually music. Why does that matter?
I found out a tiny thing about the stream: Obviously it's XMA2 multichannel, but it's not 'well-behaved' as HSC would say.  I don't know what's different though but I'm guessing the block size. Here's how you normally decode multichannel XMA2:
1. extract the stereo channels out of the file (xma_parse with -x and offsets 0x0, 0x800 and 0x1000)
2. rebuild each channel pair to XMA1 (xma_parse with -r)
3. add a stereo header to each channel (addXMARIFFHeader.bms)
4. decode with toWAV
If you follow this procedure, you'll only get interleaved channels. However you get a better result when you deinterleave the whole file with 0x800 bytes first and extract and rebuild from there on - but it's still not correct. Any other ideas?
## Post #6
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-07-08T20:46:32+00:00
- Post Title: Prototype - multichannel XMA

I think this is the only weird bgm file. This one has P3D (LE) in its header but all other music has D3P (Big Endian P3D)
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-09T00:27:16+00:00
- Post Title: Prototype - multichannel XMA

> Reply from bxaimc
>
> I think this is the only weird bgm file. This one has P3D (LE) in its header but all other music has D3P (Big Endian P3D)
True but doesn't solve the problem.
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-07-17T12:51:19+00:00
- Post Title: Prototype - multichannel XMA

Ok, got it. It's really just a standard multichannal XMA2 file with 0x3000 bytes blocksize. Wrote a little [script](http://forum.xentax.com/viewtopic.php?f=13&t=4450&p=40655#p40655) that adds a multichannel header to the headerless file.
Problem solved.
