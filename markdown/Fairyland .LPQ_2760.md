## Post #1
- Username: Ichigo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2007 10:57 am
- Post datetime: 2007-08-20T21:41:07+00:00
- Post Title: Fairyland .LPQ

this mmo i used to play called Fairyland has files that are .lpq (some form of archive/compression) would be nice to figure out how extract.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-08-20T21:47:47+00:00
- Post Title: Fairyland .LPQ

Any attachment?
Thanks
## Post #3
- Username: Ichigo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2007 10:57 am
- Post datetime: 2007-08-20T22:02:44+00:00
- Post Title: Fairyland .LPQ

oh oops im sorry uh, put it in a rar because it wouldnt allow the file extension and it was too big lol, its the smallest .lpq file in the game files so not quite sure what's in it
[Items00.rar](https://xentaxbackup.github.io/file/1323_Items00.rar)
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-08-21T01:25:50+00:00
- Post Title: Fairyland .LPQ

At first look i see:

[quote]
BMx8
## Post #5
- Username: Ichigo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2007 10:57 am
- Post datetime: 2007-08-21T01:34:25+00:00
- Post Title: Fairyland .LPQ

thank you for working on this lol, its been something thats been bugging me for a bit. i knew it had either graphics or animation files of some sort in it ive just been unsure how its compressed/ how to decompress it. 

ill keep an eye on the forum and keep reading..if u need a 2nd example or anything let me know.

and the game itself im pretty sure they dont want you tweakin the files at all lol so havent checked forums
## Post #6
- Username: Ichigo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2007 10:57 am
- Post datetime: 2007-08-24T00:15:24+00:00
- Post Title: Fairyland .LPQ

here's another example dunno if it'll help at all..didnt see any any hints to bmps in this one but mighta just missed them.
[ui001b_02.rar](https://xentaxbackup.github.io/file/1326_ui001b_02.rar)
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-08-24T01:14:30+00:00
- Post Title: Fairyland .LPQ

At the offset  00000030 you can see the first "BM8" normally it's a bitmap header maybe i'm wrong, but it's more than 15 "BM8" there.

And in the 75% of the file i found this: (listfile)10401.bmp

Like the other example the ratio compression it's aprox the 50%
## Post #8
- Username: Ichigo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Aug 20, 2007 10:57 am
- Post datetime: 2007-08-24T02:45:33+00:00
- Post Title: Fairyland .LPQ

from what ive seen so far theres a remarkable amount of BM8 headers in the file now that ive searched...if each one is actually a compressed bmp thats a very big amount of compression to have such a small file from so many.
## Post #9
- Username: Latency
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 02, 2012 7:56 am
- Post datetime: 2012-07-20T21:28:40+00:00
- Post Title: Fairyland .LPQ

Yes, you are both correct.    They are using a compression utility to archive their images for reasons of security and updating/transfer times.  You will have to uncompress it to extract the data files (in this case images).

There are other games which use this as well.  Kings of Kings III - MMORPG also uses this format schema.
You can see my related post on this site found [here](http://forum.xentax.com/viewtopic.php?f=10&t=8329).
