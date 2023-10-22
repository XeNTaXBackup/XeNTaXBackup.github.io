## Post #1
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-11T09:32:32+00:00
- Post Title: Otomedius

So I ripped Otomedius. I was wondering if anyone knows of a program that can read uncompressed binary X files that are version 0x0303 not 0x0302. The DxViewer provided in the DirectX SDK doesn't seem to be able to read them and it doesn't say why so its not really any help to me.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-05-11T09:43:57+00:00
- Post Title: Otomedius

sample files?
oh that game.
the models look really low grade i never bothered to research it further for that reason.
## Post #3
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-11T10:12:03+00:00
- Post Title: Otomedius

I'll put up a sample later today if anyone is really that interested. You're probably right about the model quality, its not a very good game anyway. It was kind of silly how they did it, a bunch of CAB files and some simple container format inside. Besides that the textures are DDS, easy enough.
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-11T21:10:20+00:00
- Post Title: Otomedius

from skimming over your blog, it looks like your capable of creating your own model importer.
DX specs aren't secret either, I bet its in the directX SDK.
## Post #5
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-12T04:06:28+00:00
- Post Title: Otomedius

Yeah I'm sure I can, but I hate to reinvent the wheel if I don't have to. Pretty sure the facilities for loading them exists in the sdk anyway.
## Post #6
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-12T05:46:41+00:00
- Post Title: Otomedius

Anyway...
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-05-12T23:46:56+00:00
- Post Title: Otomedius

cool, did you have to modify anything, or it just opened in the directx SDK?
## Post #8
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-13T03:57:26+00:00
- Post Title: Otomedius

No changes. It just works. However, not everything works properly and some dont load at all. Looking at a disassembly it looks like they may be using a bit of custom loading.
## Post #9
- Username: FEATHER
- Rank: advanced
- Number of posts: 75
- Joined date: Sun Jun 13, 2010 1:47 pm
- Post datetime: 2011-05-14T05:24:48+00:00
- Post Title: Otomedius

Thanks for the info ameneko, This game have a PC version too
## Post #10
- Username: ameneko
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Sep 10, 2009 9:31 am
- Post datetime: 2011-05-14T08:51:02+00:00
- Post Title: Otomedius

The PC version is actually the arcade version. There is no official PC release. The arcade uses CAB files, the 360 uses xbcompress. The container format for both is the same.
