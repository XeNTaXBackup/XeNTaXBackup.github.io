## Post #1
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-01-08T13:47:11+00:00
- Post Title: Dreamkiller

Hello guys!Someone know how convert models from dreamkiller to OBJ or 3DS?I just interested for gothic cathedral   Thanks for all help!
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-01-08T15:19:37+00:00
- Post Title: Dreamkiller

well it seems to be an offline game so 3d ripper should work for you
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-08T19:51:25+00:00
- Post Title: Dreamkiller

Post some samples.
Of variable sizes.
From small to large.
## Post #4
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-09T03:14:08+00:00
- Post Title: Dreamkiller

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T03:33:26+00:00
- Post Title: Dreamkiller

Were these files extracted or they just came like this with the game?
Some of the files look weird.
## Post #6
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-09T10:47:51+00:00
- Post Title: Dreamkiller

They extracted using quickbms script found here:

[viewtopic.php?f=10&t=3777&hilit=dreamkiller](http://forum.xentax.com/viewtopic.php?f=10&t=3777&hilit=dreamkiller)
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T12:40:32+00:00
- Post Title: Dreamkiller

So the stuff was originally weird.
Lol one of the files looks like it's just part of another file cause it starts with a bunch of floats, followed by an index buffer, and that's it.
## Post #8
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2012-01-09T15:34:55+00:00
- Post Title: Dreamkiller

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-09T20:43:52+00:00
- Post Title: Dreamkiller

I looked at 166.dat to 171.dat, and then looked at 172.dat
It looks like 166 and 172 both start with the same 4 bytes. That may be significant, but I don't know how many files may be in the same set.

The file that follows the one with the header is always a small one (like 1-2KB).
Followed by a file that contains nothing but floats and int16's.

Another file may follow (don't know when), followed by a file that has the NXS MESH, followed by the last file before the start of the next set.
## Post #10
- Username: bruno021
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Dec 02, 2011 6:50 am
- Post datetime: 2012-01-09T23:54:22+00:00
- Post Title: Dreamkiller

3D ripper rly not work in that game.I guess need as that convert dat to obj.Hmm...
P.S someone tried GA(gameassasin) in that game?
