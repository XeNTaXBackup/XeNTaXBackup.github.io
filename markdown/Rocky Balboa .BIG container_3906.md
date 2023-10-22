## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T21:25:48+00:00
- Post Title: Rocky Balboa *.BIG container

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-11-29T22:50:29+00:00
- Post Title: Rocky Balboa *.BIG container

you need to include at least some of the file part like the first 10mb of the file so we know what compression is used.
also did you try offzip first as it looks like the name table max be encrypted or in another location.
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-29T23:42:20+00:00
- Post Title: Rocky Balboa *.BIG container

Ok, sorry about that. Here's aout 16MB of the file: [http://www.sendspace.com/file/ukob3w](http://www.sendspace.com/file/ukob3w)

I've tried offzip (thanks for the tip!) and it says "1 valid ziop block found" but can't extract any of the files. Only tells that the data is not in zip format or uses another Windows bits format. This is the only big file inside the game so I guess the file information is somehow compressed or encrypted.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-11-30T17:52:24+00:00
- Post Title: Rocky Balboa *.BIG container

try this one:
[http://aluigi.org/papers/bms/yeti_gear.bms](http://aluigi.org/papers/bms/yeti_gear.bms)
## Post #5
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-11-30T23:00:23+00:00
- Post Title: Rocky Balboa *.BIG container

Thanks, that worked as far as it extracted the files. But is there a possibility to retrieve the original filenames and extensions?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T00:46:27+00:00
- Post Title: Rocky Balboa *.BIG container

there are no filenames stored in the archive, the only thing available are the checksums (aka crc) of them so there is nothing to do.
that's why the script saves the files using the crc as name instead of a sequential number
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-01T07:56:14+00:00
- Post Title: Rocky Balboa *.BIG container

Ok, thanks. I'll rewrite the script a bit and add a sequential number then because the CRC gets negative at some point.
Thanks for pointing me to the script.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-12-01T13:41:53+00:00
- Post Title: Rocky Balboa *.BIG container

from:

```
log CRC OFFSET SIZE
```
to

```
log "" OFFSET SIZE
```
:)
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2009-12-01T14:38:01+00:00
- Post Title: Rocky Balboa *.BIG container

Hehe, I know
