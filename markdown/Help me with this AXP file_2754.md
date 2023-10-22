## Post #1
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-15T20:28:17+00:00
- Post Title: Help me with this AXP file

This file seem be not encoded and compressed, at end of file maybe a file chunk or something, but I can guess that code to extract to sub file, anyone help me pls ^^
[Effect.rar](https://xentaxbackup.github.io/file/1319_Effect.rar)
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-08-16T08:45:23+00:00
- Post Title: Help me with this AXP file

Seems to be only 1 file in there?!

> 001Ch: 28 00 16 00 00 68 5E 00                          (....h^.
At least 1441832 is the startting offset of the data and 6187008 is the size.
## Post #3
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-16T10:36:33+00:00
- Post Title: Help me with this AXP file

Hi there,
that file contant 3 file: all.effect, all.particle and all.skill. Is easly to guess their offset and size number but can't decode to real offset and size Y_Y
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2007-08-16T12:37:21+00:00
- Post Title: Help me with this AXP file

Just a quick note: At offset 16 you will find the offset of the entry table (393256 in this case), the next uint32 is probably the number of entries. There you can read the actual data offsets and sizes, which in this sample are:
- offset 1441832, size 549848
- offset 1991720, size 4659043
- offset 6650920, size 977442
- offset 7628584, size 99

The last "file" is actually a descriptor table containing the file names, the sizes (once again ...) and "something else". Maybe a checksum or whatever ...
## Post #5
- Username: babebabe
- Rank: beginner
- Number of posts: 36
- Joined date: Sat Jan 07, 2006 12:19 am
- Post datetime: 2007-08-17T16:06:32+00:00
- Post Title: Help me with this AXP file

> Reply from Deniz Oezmen
>
> Just a quick note: At offset 16 you will find the offset of the entry table (393256 in this case), the next uint32 is probably the number of entries. There you can read the actual data offsets and sizes, which in this sample are:
- offset 1441832, size 549848
- offset 1991720, size 4659043
- offset 6650920, size 977442
- offset 7628584, size 99

The last "file" is actually a descriptor table containing the file names, the sizes (once again ...) and "something else". Maybe a checksum or whatever ...
Thanks Deniz, is quite helpful ^^
I found Extractor (Nova Software) can search and extract all music file I need !!! ^^
Maybe I no needed to extract AXP file anymore!
