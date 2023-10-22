## Post #1
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-02-28T17:26:11+00:00
- Post Title: XBOX360 .big archiv

hi there.

i got some xbox360 data in a *.big file archiv.

here you can get some sample file. [http://xirror.com/spread/17252604/TDUis ... k.big.html](http://xirror.com/spread/17252604/TDUis350LexusCarPack.big.html)

i think its a compressed archiv. exist some big-file reader for 360 data? i didnt find some....
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-02-28T18:47:34+00:00
- Post Title: XBOX360 .big archiv

Is this from an EA game?
## Post #3
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-02-28T19:35:12+00:00
- Post Title: XBOX360 .big archiv

no, its from atari/eden.
## Post #4
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2008-03-02T08:58:51+00:00
- Post Title: XBOX360 .big archiv

0x08 begins a Big Endian Short that indicates the compressed sized. It is followed 78DA which of course is zlib compression. There are a fair amound of zlib compressed packages per archive each begins with the same Big Endian Short. Decompressed first package and can verify it is zlib.

You'll find that .big is a generic file format name and most often custom utilities need be written.
## Post #5
- Username: RacersHardware
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Dec 17, 2007 6:36 pm
- Post datetime: 2008-03-02T16:36:54+00:00
- Post Title: XBOX360 .big archiv

mh, that I thought....

somebody know one who can help with zlib-decrompression ?
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-03-02T20:15:42+00:00
- Post Title: XBOX360 .big archiv

[viewtopic.php?f=21&t=2022](http://forum.xentax.com/viewtopic.php?f=21&t=2022)
## Post #7
- Username: xrevenge
- Rank: veteran
- Number of posts: 119
- Joined date: Thu Jun 05, 2008 10:46 pm
- Post datetime: 2008-06-30T17:39:49+00:00
- Post Title: XBOX360 .big archiv

> Reply from RacersHardware
>
> hi there.

i got some xbox360 data in a *.big file archiv.

here you can get some sample file. http://xirror.com/spread/17252604/TDUis ... k.big.html

i think its a compressed archiv. exist some big-file reader for 360 data? i didnt find some....

ummm...ok stupid question again, how did you take the files from the game disc, whenever I put a game for the 360 in the PC says it is a movie and when I play it there is a screen that says "To play this game put it in your XBOX 360 Console" and that's the end of the movie. It's been bugging me for a while now and I've tried many different tools but I can't see them, so what did you use?
