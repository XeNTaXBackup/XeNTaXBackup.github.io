## Post #1
- Username: Kane
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 28, 2010 5:50 pm
- Post datetime: 2010-12-28T09:55:36+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

Hello!
I want to do some modification and translation, but I don't know how is possible to decompress these .lp files.

Here is a sample: [http://www.megaupload.com/?d=0S8L3TF0](http://www.megaupload.com/?d=0S8L3TF0)

If somebody can make or help to make a QuickBMS script, please help me.
## Post #2
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-12-28T18:00:41+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

Use xbdecompress in the SDK to decompress the .wad files. After that I have no clue, the .lp files are in some archive format.
## Post #3
- Username: Kane
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 28, 2010 5:50 pm
- Post datetime: 2010-12-28T18:07:45+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

The uploaded file is decompressed with xbdecomp, but the .lp is encrypted or still compressed.
Hex editor shows "LWAD" type at the begining of the file.
## Post #4
- Username: szbstr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 17, 2010 7:25 pm
- Post datetime: 2010-12-31T18:16:24+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

Yes, true.
This compression used for endor dlc too.
I think if somebody can decompress that "LWAD" file type it"s possible to port the ENDOR dlc to PC.
I already tried it, but some files are needed from xbox version.
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-31T18:43:09+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

You cant port console dlc to pc because the endian is reversed.
## Post #6
- Username: szbstr
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Apr 17, 2010 7:25 pm
- Post datetime: 2010-12-31T19:21:11+00:00
- Post Title: How to decompress SWTFU2 .lp (x360) files?

But the FMV movies are the same...
Also i deleted the LWAD hex values, now the file starts with "APak":
