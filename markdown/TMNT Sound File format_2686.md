## Post #1
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-03T16:33:38+00:00
- Post Title: TMNT Sound File format

Loaded TMNT yesterday and it has a sound.big and sound.fat file pair. I wrote an extractor that uses the sound.fat to pick apart the sound.big file. The resulting files look like:

1.sb0   19.sb0  1o.sb0  1y.sb0  29.sb0  2q.sb0  36.sb0  e.sb0        q.sb0
10.sb0  1c.sb0  1q.sb0  2.sb0   2a.sb0  2r.sb0  37.sb0  english      r.sb0
11.sb0  1d.sb0  1r.sb0  22.sb0  2c.sb0  2x.sb0  39.sb0  french       spanish
12.sb0  1e.sb0  1s.sb0  23.sb0  2e.sb0  2z.sb0  3a.sb0  gamesnd.sp0  stream.ss0
13.sb0  1g.sb0  1t.sb0  24.sb0  2g.sb0  3.sb0   5.sb0   i.sb0        t.sb0
14.sb0  1h.sb0  1u.sb0  25.sb0  2j.sb0  32.sb0  7.sb0   j.sb0        u.sb0
15.sb0  1j.sb0  1v.sb0  26.sb0  2k.sb0  33.sb0  8.sb0   l.sb0        v.sb0
16.sb0  1m.sb0  1w.sb0  27.sb0  2m.sb0  34.sb0  9.sb0   o.sb0        y.sb0
18.sb0  1n.sb0  1x.sb0  28.sb0  2n.sb0  35.sb0  d.sb0   out          z.sb0

.SB0 suffix as best as I can find on Google is an Ogg format that has a high sample rate, but no more info.  The various players can't seem to decipher them.

Here's a filedmp of the beginning of 1.sb0

0000  02001900  05000000  03000000  01000000  *................*
0010  00000000  ffffffff  ffffffff  00002700  *..............'.*
0020  01000000  00000000  00000000  00000100  *................*
0030  00000000  00000000  feffffff  feffffff  *................*
0040  feffffff  feffffff  00000000  00000000  *................*
0050  01000000  01000000  00000000  01000000  *................*
0060  01000000  00000000  01000000  00000000  *................*
0070  01000000  00000000  00000000  00000000  *................*
0080  00000000  01002700  02000000  00000000  *......'.........*
0090  00000000  00000000  00000000  00000000  *................*
....
00b0  00000000  00000000  01000000  01000000  *................*

Anothing here look familar to anyone?  Any suggests on how to get these to play?

I can post one of the smaller files is it would help. Just let me know.

TIA!
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-08T01:50:37+00:00
- Post Title: TMNT Sound File format

I only know Ubisoft changes in every game the "alg" of the audio, so if you have the conversor from Prince if persia Two Thrones this dont' works with the nexts games from ubisoft   

Maybe somebody knows the "algorithm" and can make some tools (decode/encode) and then play the game with your audios
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-08T07:40:14+00:00
- Post Title: TMNT Sound File format

> Reply from Dandapani
>
> Loaded TMNT yesterday and it has a sound.big and sound.fat file pair. I wrote an extractor that uses the sound.fat to pick apart the sound.big file.

if you create tools, why not share them with the community ? 
We could host them for you, if you'd like.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-08T12:09:30+00:00
- Post Title: TMNT Sound File format

Can be great a "conversor" sb0>wav and wav>sb0
## Post #5
- Username: kimkalisto
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Apr 16, 2007 7:26 am
- Post datetime: 2007-07-08T17:01:13+00:00
- Post Title: TMNT Sound File format

Holy crap you know how much i hate ubisoft for changing the formats everytiem for there games? i have been tryign to extract splinter cell DA and GRAW and GRAW 2 from 360 but no success.
## Post #6
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-09T11:43:45+00:00
- Post Title: TMNT Sound File format

> Reply from Mr.Mouse
>
> Dandapani wrote:Loaded TMNT yesterday and it has a sound.big and sound.fat file pair. I wrote an extractor that uses the sound.fat to pick apart the sound.big file. 

if you create tools, why not share them with the community ? 
We could host them for you, if you'd like.

I can share the tools, but I'm a Unix/Linux C++ programmer by profession so the little tools I've created are written in C++ and compiled to run within a cygwin environment on my PC.  [http://www.cygwin.com/](http://www.cygwin.com/)  My tools would require someone to install cygwin to run the binary.  I can post the source, but many people don' t have a compilation system.  I'd be happy to share any way I can.
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-09T12:42:40+00:00
- Post Title: TMNT Sound File format

Well, I can set you up for some space at the Xentax repository and you can upload tools as you see fit. Just let me know! 

People can either download the needed environment or take a look at the source and replicate it. It's always good to have such tools documented IMHO, could save some people from reinventing the wheel.
## Post #8
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-09T12:52:22+00:00
- Post Title: TMNT Sound File format

> Reply from Mr.Mouse
>
> Well, I can set you up for some space at the Xentax repository and you can upload tools as you see fit. Just let me know! 

People can either download the needed environment or take a look at the source and replicate it. It's always good to have such tools documented IMHO, could save some people from reinventing the wheel.

Ok, send me some info on where I can upload my source tools. I'll clean them up a bit and add some more comments
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-07-09T13:20:10+00:00
- Post Title: TMNT Sound File format

I have no problem with Linux (i use too and a lot of time), if you upload the binaries for linux will be great   
Thanks!
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-07-09T13:56:52+00:00
- Post Title: TMNT Sound File format

> Reply from Dandapani
>
> Ok, send me some info on where I can upload my source tools. I'll clean them up a bit and add some more comments

You have mail.
## Post #11
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-10T13:19:05+00:00
- Post Title: TMNT Sound File format

> Reply from Savage
>
> I have no problem with Linux (i use too and a lot of time), if you upload the binaries for linux will be great   
Thanks!

I uploaded the source.  That's portable to Linux 

[http://www.xentax.com/uploads/author/dandapani/fat.cpp](http://www.xentax.com/uploads/author/dandapani/fat.cpp)
