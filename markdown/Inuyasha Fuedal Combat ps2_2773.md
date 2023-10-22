## Post #1
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-06T11:55:33+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-06T12:56:56+00:00
- Post Title: Inuyasha Fuedal Combat ps2

This fpk is a simple archive format:

```
dword		unknown //maybe checksum??
dword		numData
dword		tableOffset
dword		fpkSize
}
Struct Table {
char[36]	filename
dword		dataOffset
dword		dataSize
dword		unknown //again maybe checksum??
} Table[numData]
...
Data
...
..
.

```


I am a bit disappointed since the data inside are all encrypted/compressed so you have to decrypt/decompress them before actually got the data!
## Post #3
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-07T08:56:12+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-07T10:37:01+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The link you just post didn't work!?

And the game use renderware engine so dff is 3D models, txd is texture archive. anm is animation.

You can google search for the dff/txd format and you'll see these file are encrypted/compressed. So you need to figure the decrypt/decompress first!

I'm not good in decrypt/decompress things so I can't help on these, once you decrypt/decompress them, I can help with the raw data!
## Post #5
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-07T10:53:30+00:00
- Post Title: Inuyasha Fuedal Combat ps2

I knew I aw dff files somewhere before when I was modding gta 3 long time ago lol. But i cant get these to work like the gta ones. encryption must be different. If some one could help me out. the dff and anm files are all in the rar. I edited the link so its direct to the download instead of the filefront page
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-11T10:14:32+00:00
- Post Title: Inuyasha Fuedal Combat ps2

I have another look yesterday and think that FPK format should be like this:

```
dword      unknown
dword      numData 
dword      tableOffset 
dword      fpkSize 
} 
Struct Table { 
char[36]   filename 
dword      dataOffset 
dword      dataCSize      //Compressed size
dword      dataUSize      //Uncompressed size 
} Table[numData] 
... 
Data 
... 
.. 
. 
```


But I can't figure out the compression method.  I try zlib but not correct!
Hope that anyone who familiar with compression would help.
## Post #7
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-11T13:26:27+00:00
- Post Title: Inuyasha Fuedal Combat ps2

I extracted the files from the archives with game extractor and got some files which I believe to be the player models as theyre dff files. but the dff files are different than the GTA ones because I cannot open them in 3ds Max using the same methods. So thats my issue right now. I relly ant to be able to view these.
## Post #8
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-11T18:14:29+00:00
- Post Title: Inuyasha Fuedal Combat ps2

What sizes are they? Are those form game extractor different from what you uploaded before?

You can try "RW Analyze" to see if they are valid dff/txd!
Could you upload the newly extracted ones if they are different from before?
## Post #9
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-11T21:35:25+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-11T23:38:42+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-12T03:11:02+00:00
- Post Title: Inuyasha Fuedal Combat ps2

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-09-12T07:02:28+00:00
- Post Title: Inuyasha Fuedal Combat ps2

Back to zero again!  The files from game extractor are just the same as your second upload!  It means they are compressed!
## Post #13
- Username: snyperstyle
- Rank: advanced
- Number of posts: 69
- Joined date: Sun May 20, 2007 11:29 am
- Post datetime: 2007-09-12T16:15:13+00:00
- Post Title: Inuyasha Fuedal Combat ps2

damn well Idk how to decompress them so if anyone can me out I'd appreciate it.
