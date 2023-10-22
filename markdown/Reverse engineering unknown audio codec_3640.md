## Post #1
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2009-08-08T09:44:39+00:00
- Post Title: Reverse engineering unknown audio codec

Does anyone have any tips on how I can reverse engineer an unknown audio codec related to MP3 audio? Its EALayer3 and its used by a number of EA games (including the latest C&C series games and the new Sims game)

The game binaries (for the games I have at least) are full of FPU and MMX/SSE and hard to reverse engineer as a result. No known encoder or decoder exists outside of EA.

Reading code (e.g. FFMPEG code) for MP3 decoding makes my eyes glaze over with all that math.

Any tips anyone can share on reverse engineering this code?
Any documents or other things that can make MPEG audio easier to understand?
Anyone out there who understands how MPEG audio works?

Or is this one of those formats that just wont be figured out unless EA releases some info on it or something?
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-08-08T20:02:20+00:00
- Post Title: Reverse engineering unknown audio codec

> Reply from jfwfreo
>
> No known encoder or decoder exists outside of EA.Have you looked into [Electronic Arts Sound eXchange](http://wiki.multimedia.cx/index.php?title=Electronic_Arts_Sound_eXchange) yet? (Attached at bottom) It was released by EA, and I not really sure but there are a few indications that it can decode EALayer3.
[sx.rar](https://xentaxbackup.github.io/file/2266_sx.rar)
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-08-08T20:24:05+00:00
- Post Title: Reverse engineering unknown audio codec

I dont think sx can decode layer 3 unless im wrong about that, isnt this a 2004 tool or old tool?
## Post #4
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-08-08T20:35:11+00:00
- Post Title: Reverse engineering unknown audio codec

> Reply from OrangeC
>
> I dont think sx can decode layer 3 unless im wrong about that, isnt this a 2004 tool or old tool?I guess the only way to find out for sure is to try it. The strings in the executable strongly suggest that it is able to decode EALayer3, unless the format/codec has changed.
## Post #5
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2009-08-09T00:16:57+00:00
- Post Title: Reverse engineering unknown audio codec

Format has changed - EA has cutted all page and headerinformation out of that stream - its still EA-Layer but as a Raw format therefore its not possible to decode.
