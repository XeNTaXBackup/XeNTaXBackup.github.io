## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-01T15:23:24+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-02T15:21:48+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Really no-one? Would be a pity because the quality seems to be excellent!
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-02T17:26:44+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

I think ive seen this before, try some of the setting in genh, seems some type of blocked or interleaved adpcm.
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-02T17:50:26+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Played around without success... Some files look like raw PCM, others like some ADPCM variant. Anyone else?
## Post #5
- Username: FordGT90Concept
- Rank: advanced
- Number of posts: 47
- Joined date: Thu Apr 15, 2010 2:16 pm
- Post datetime: 2010-06-04T05:09:49+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Did you try throwing a RIFF WAVE header on it and see what it sounds like?
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-04T14:39:54+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

I uploaded samples so that people could try out some things...
I tried to open the files as RAW with every combination but nothing works. It's some ADPCM compression by the look of the stream. Can anyone help? Thanks
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-06T22:00:15+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Look at these files in a hex editor with 0x21 bytes per row - you'll see that this is a completely new format. Maybe there will be other games that use the format, so maybe someone could post any known information about it like links or specs?
## Post #8
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-12T13:56:57+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2010-11-13T02:58:24+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

It's the same codec but this is little endian compared to the big endian stuff in 007.
## Post #10
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-11-13T15:07:12+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

> Reply from bxaimc
>
> It's the same codec but this is little endian compared to the big endian stuff in 007.
So that means that it's playable, which is great - just need some header specs now! If you would be so kind...
## Post #11
- Username: Manny123
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 25, 2011 1:39 am
- Post datetime: 2011-03-24T17:44:55+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

so no way to open these music files?
## Post #12
- Username: bxaimc
- Rank: advanced
- Number of posts: 78
- Joined date: Mon May 10, 2010 3:54 am
- Post datetime: 2011-03-30T17:44:24+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Well, not yet at least. Trying to figure out how to add support to them in vgmstream without causing conflicts with the other BAF files. The PS3 version uses the same codec and are pretty much the same files except for the fact that they're the playable ones at the moment. Search around for it if you know where it is.
## Post #13
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-06T05:01:32+00:00
- Post Title: Blur [PC version] - unknown audio format (headerless)

Well if you need people to help test I'd be interested in lending a hand.

Modding Blur is one of my side goals/projects now.
