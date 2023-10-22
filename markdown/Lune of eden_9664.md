## Post #1
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-22T12:39:56+00:00
- Post Title: Lune of eden

[http://www.luneofeden.com/main/index.do](http://www.luneofeden.com/main/index.do)

New game with nice models, a little like blade and soul I think



I don't know if posting files is ok anymore. The models are not zipped so they are in plain sight of the game directory
## Post #2
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2012-09-23T15:07:14+00:00
- Post Title: Lune of eden

Using Big Boobs picture of the game for attract rippers.
## Post #3
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-24T09:52:24+00:00
- Post Title: Lune of eden

that was my exact thought
## Post #4
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2012-09-24T17:52:05+00:00
- Post Title: Lune of eden

You got my attention   

T.
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-24T19:20:33+00:00
- Post Title: Lune of eden

I see people are starting to post some samples here and there again. How is the general rule now? This game has no archives at all, it's all in the open
## Post #6
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-09-24T20:03:27+00:00
- Post Title: Lune of eden

Maybe, link to the client, please!?
## Post #7
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2012-09-24T21:02:37+00:00
- Post Title: Lune of eden

[http://4b67xxel60.c-cdn.tcloudbiz.com/L ... 0920_T.zip](http://4b67xxel60.c-cdn.tcloudbiz.com/LOE_Setup_20120920_T.zip)
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-24T23:19:12+00:00
- Post Title: Lune of eden

> Reply from pixellegolas
>
> I see people are starting to post some samples here and there again. How is the general rule now? This game has no archives at all, it's all in the open

Nah rule is still there.
## Post #9
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-12T01:02:49+00:00
- Post Title: Lune of eden

Should have a converter soon static meshes are much simpler then skeletal just need to parse out the header a bit.
## Post #10
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-10-12T05:25:22+00:00
- Post Title: Lune of eden

Do you matching the texture manually? Or is there any index/string for the texture?
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-12T20:03:05+00:00
- Post Title: Lune of eden

there are matching id's in the file lists and the model material sections.
for instance
CF 1F 00 00 = B.a.t.t.l.e.M.a.g.e._.b.o.d.y._.D...d.d.s
D0 1F 00 00 = B.a.t.t.l.e.M.a.g.e._.b.o.d.y._.N...d.d.s
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-10-13T16:17:51+00:00
- Post Title: Lune of eden

this format is pretty dumb.
the say to read models with textures you need to.
create a dictionary with the file sDataList.lit
this contains the mesh, bone , animation names matching to id's
64 73 00 00 = B.a.t.t.l.e.M.a.g.e._.B.o.d.y._.0.0...s.k.m.
65 73 00 00 = B.a.t.t.l.e.M.a.g.e._.B.o.d.y._.0.1...s.k.m.
ext
then
Parts.Dat
contains material and model defenition
ED 58 00 00 = B.a.t.t.l.e.M.a.g.e...p.t.s
and it contains 6 model values
64 73 00 00 
65 73 00 00 
66 73 00 00 
67 73 00 00 
68 73 00 00 
69 73 00 00
it also contains 12 materials
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 D0 1F 00 00
CF 1F 00 00 = B.a.t.t.l.e.M.a.g.e._.b.o.d.y._.D...d.d.s
D0 1F 00 00 = B.a.t.t.l.e.M.a.g.e._.b.o.d.y._.N...d.d.s 
the first 6 are normal and diffuse info
the 2nd 6 is lighting information
like
D2 1F 00 00 = 0.2.d.g._.0.0.1.L.i.g.h.t.i.n.g.M.a.p...d.d.s
and the texture reference is in
sTextureList.lit
the bone names are referenced in
Bone.Dat
## Post #13
- Username: jacquel
- Rank: n00b
- Number of posts: 13
- Joined date: Sun May 29, 2011 5:21 pm
- Post datetime: 2012-12-04T10:09:26+00:00
- Post Title: Lune of eden

hello
how read .lit and .dat?

with what kind of soft on win 7?

or can you post or attach the complete list for make good textures on .mesh, please.

how change the header for .skm?

thank very well
