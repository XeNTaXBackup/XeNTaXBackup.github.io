## Post #1
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-07-21T14:19:43+00:00
- Post Title: Dead Rising 2 Off-the-record (0x03040506)

just seen this new format with the signature 0x03040506 (probably used to control the endianess of the file):
[http://aluigi.org/papers/bms/deadrising2_otr.bms](http://aluigi.org/papers/bms/deadrising2_otr.bms)
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2012-07-22T02:17:37+00:00
- Post Title: Dead Rising 2 Off-the-record (0x03040506)

Same archive format as Dead Rising 2, 0x03040506 indicates a version 2 archive, and yes, it's used to test endianness as well.
## Post #3
- Username: lllccc
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Thu Apr 12, 2012 7:27 am
- Post datetime: 2012-08-30T01:39:17+00:00
- Post Title: Dead Rising 2 Off-the-record (0x03040506)

> Reply from aluigi
>
> just seen this new format with the signature 0x03040506 (probably used to control the endianess of the file):
http://aluigi.org/papers/bms/deadrising2_otr.bms

hey aluigi i have 2 more datafile.big for the arcades and i just wanted to know if you can add them to your script
the one you have now does extract some of the files but not all of them from the look of the rip  some of the text is missing in the txt files
here they are if your willing to look at them

dead rising case west
[http://www.sendspace.com/file/6kcci3](http://www.sendspace.com/file/6kcci3)
dead rising case zero
[http://www.sendspace.com/file/rbfkjx](http://www.sendspace.com/file/rbfkjx)
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-31T14:05:41+00:00
- Post Title: Dead Rising 2 Off-the-record (0x03040506)

well done, indeed there was a bug.
in short I didn't notice that the compressed files were divided in chunks:
[http://aluigi.org/papers/bms/deadrising2_otr.bms](http://aluigi.org/papers/bms/deadrising2_otr.bms)

the bad news is that it's not possible to reimport the modified files because chunked files are not supported in reinjection mode.
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-08-31T14:09:31+00:00
- Post Title: Dead Rising 2 Off-the-record (0x03040506)

script updated.
sorry for the multiple posting but have been opened 3 different threads and I don't want that the followers of one of them miss this important fix.
