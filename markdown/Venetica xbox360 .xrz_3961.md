## Post #1
- Username: blacktick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 20, 2009 6:59 pm
- Post datetime: 2009-12-20T12:06:43+00:00
- Post Title: Venetica xbox360 .xrz

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T14:25:49+00:00
- Post Title: Venetica xbox360 .xrz

this is an usual "0f f5 12 e?" archive (used also in various other games), there is no solution for it yet
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T15:39:50+00:00
- Post Title: Venetica xbox360 .xrz

finally I'm near to a solution for these files, everything was written in xcompress.h
stay tuned for the updates
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T16:09:15+00:00
- Post Title: Venetica xbox360 .xrz

and the following is the quickbms script which does the job:
[http://aluigi.org/papers/bms/xcompress_file.bms](http://aluigi.org/papers/bms/xcompress_file.bms)

it should work with all the 0x0FF512EE (0F F5 12 EE) files but does NOT work with the tdecode files which have the signature 0x0FF512ED.
luckily the tdecode file seems to be related to text only so they are not a big miss.

please TEST the script with any other 0x0FF512EE file you can see in any other existent x360 game for being 100% sure that it's all correct (the format is that one so shouldn't exist problems).
## Post #5
- Username: blacktick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 20, 2009 6:59 pm
- Post datetime: 2009-12-20T20:26:20+00:00
- Post Title: Venetica xbox360 .xrz

Thanks,great work on the script.  

Now I'm not sure I used quickbms properly,but can I ask what you got when you extracted the xrz file I included?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-20T20:42:04+00:00
- Post Title: Venetica xbox360 .xrz

it was a XPR2 file but I don't know what type of file it is (no knowledge about graphics/3d/models files).

I need to add to this topic the same info I wrote for SoulCalibur4: use xbdecompress for doing the job instead of my quickbms script:
[viewtopic.php?p=34175#p34175](http://forum.xentax.com/viewtopic.php?p=34175#p34175)

that tool supports both the available types of compressed files so there are no limitations or other problems with them, and then it's the OFFICIAL tool :)
## Post #7
- Username: blacktick
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 20, 2009 6:59 pm
- Post datetime: 2009-12-20T21:23:29+00:00
- Post Title: Venetica xbox360 .xrz

Thanks man,you are a lifesaver. 
The tool worked great and I'm a bit closer to my goal.
All I need to do now is to find a way to extract english.bin from the decompressed xrz file.
