## Post #1
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-05-20T12:21:41+00:00
- Post Title: Quickbms compression algo

Hi
Does anybody know what is the name of the COMP_MSF compression in the quickbms?
I mean the real name.Some kind of name that lets me to find references on google.
Thanks.
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-20T19:26:55+00:00
- Post Title: Quickbms compression algo

you can see what it is doing in the source code of quickbms.
I think I looked at this a long time ago and its doing some kind of encryption thing.
## Post #3
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-05-20T19:53:57+00:00
- Post Title: Quickbms compression algo

> Reply from chrrox
>
> you can see what it is doing in the source code of quickbms.
I think I looked at this a long time ago and its doing some kind of encryption thing.
I've seen the source.All decompression function is in asm byte codes.
all function is a byte array.
## Post #4
- Username: deepshit
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-05-20T20:15:19+00:00
- Post Title: Quickbms compression algo

it was used and published somewhere on this site for the game.
RaiderZ
[viewtopic.php?f=21&t=5899&p=93875&hilit=msf#p93875](http://forum.xentax.com/viewtopic.php?f=21&t=5899&p=93875&hilit=msf#p93875)
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-05-21T05:14:02+00:00
- Post Title: Quickbms compression algo

RaiderZ using LZMA compression
## Post #6
- Username: Thief1987
- Rank: advanced
- Number of posts: 72
- Joined date: Wed Jan 18, 2012 12:11 pm
- Post datetime: 2014-05-24T23:41:51+00:00
- Post Title: Quickbms compression algo

Seems like msf it's lzma without first five bytes
## Post #7
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-05-25T06:51:38+00:00
- Post Title: Quickbms compression algo

> Reply from Thief1987
>
> Seems like msf it's lzma without first five bytes

Thanks, I tested it and you are right. COMP_MSF is lzma without header.
Thanks everybody.
## Post #8
- Username: GMMan
- Rank: veteran
- Number of posts: 139
- Joined date: Sat Nov 06, 2010 5:14 am
- Post datetime: 2014-06-02T22:05:54+00:00
- Post Title: Quickbms compression algo

Interesting. Maybe I can finally finish the BMS for LzmaPack with that compression type.
## Post #9
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2014-07-09T12:41:57+00:00
- Post Title: Quickbms compression algo

In the upcoming version of quickbms you will have the "lzma_0" comtype which does the same of msf.
Additionally I have set the dictionary size to the default 16Mb in msf.
