## Post #1
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2014-06-21T18:49:34+00:00
- Post Title: Playstation 2 "r2t" / "rtx" textures

I extracted some texture files from a game archive, and I'm wondering if any of you know how to open them. The file extensions are "r2t" and the first 3 characters of the files are always "rtx."

First 0x70 bytes:

```
72 74 78 54 CD CD CD CD C0 44 00 00 01 00 00 00 01 01 00 00 00 00 00 00 61 00 00 00 00 00 00 00 00 00 08 00 24 04 00 00 00 00 00 00 00 00 00 00 00 00 00 00 04 00 00 00 CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD 24 00 00 00 00 01 00 00 40 00 00 00 00 00 00 00 00 00 00 00 00 00 00 20 CD CD CD CD CD CD CD CD
```
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2014-06-22T00:17:32+00:00
- Post Title: Playstation 2 "r2t" / "rtx" textures

Say the full game title or upload files - samples.
## Post #3
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2014-06-22T04:14:15+00:00
- Post Title: Playstation 2 "r2t" / "rtx" textures

The game title is Star Wars Bounty Hunter

Here are some samples [http://www.mediafire.com/download/cqn61 ... xtures.zip](http://www.mediafire.com/download/cqn6159j532q3al/PS2Textures.zip)
password: xentax
## Post #4
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-08-10T14:51:16+00:00
- Post Title: Playstation 2 "r2t" / "rtx" textures

Seems like RGB data but I can't tell much with those file samples they are all the same size doesn't help with deciphering the header

112byte header
RGB data???
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-12-01T02:50:50+00:00
- Post Title: Playstation 2 "r2t" / "rtx" textures

> Reply from Caboose ↑Sun Jun 22, 2014 12:14 pm at Sun Jun 22, 2014 12:14 pm
>
> 
The game title is Star Wars Bounty Hunter

Here are some samples http://www.mediafire.com/download/cqn61 ... xtures.zip
password: xentax
here is Noesis python script to open your three *.r2t samples.  


 tex_StarWarsBountyHunter_PS2_r2t.zip
(766 Bytes) Downloaded 40 times


supports 8bit rgba with shuffled palette
need more diverse samples to extend the script.
