## Post #1
- Username: amantonas
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 11, 2008 7:42 am
- Post datetime: 2008-07-11T11:20:09+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-14T22:26:42+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

It looks like this format uses Dialogic VOX for compression. I decoded it with Cool Edit (I have an old unregistered version, '96 I think) and it was quite audible, except for loud clicks at regular intervals. I haven't done a lot of experimenting so I will get back to you later.
## Post #3
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-18T20:44:56+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

Well, I could not get it to decode in my own code. I don't know how Cool Edit does it, but I even after downloading some source code it didn't work.
## Post #4
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2008-07-19T18:41:27+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

> Reply from Zench
>
> It looks like this format uses Dialogic VOX for compression. I decoded it with Cool Edit (I have an old unregistered version, '96 I think) and it was quite audible, except for loud clicks at regular intervals. I haven't done a lot of experimenting so I will get back to you later.

It's not standard Vox format, I know that much.  I've used four different programs to decode it, and all of them give the same result as you listed above.
## Post #5
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-20T22:22:50+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

> Reply from Teancum
>
> Zench wrote:It looks like this format uses Dialogic VOX for compression. I decoded it with Cool Edit (I have an old unregistered version, '96 I think) and it was quite audible, except for loud clicks at regular intervals. I haven't done a lot of experimenting so I will get back to you later.

It's not standard Vox format, I know that much.  I've used four different programs to decode it, and all of them give the same result as you listed above.Which four? I figured out that the clicks are there because the file is in blocks, which are 32,768 bytes in size (there is a 512 byte header). Perhaps one of them is open source, so I can use its source code to decode it.
## Post #6
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2008-07-20T22:31:31+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

Two were just random decoders I found on the net, but the other two were GoldWave and Audacity.
## Post #7
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2008-07-22T16:29:19+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

Yes, it seems to be VOX ADPCM, and the header is 512 bytes (pretty simple, I've documented it in ScoreHero).

With sox, after removing the first 512 bytes, and decoding from VOX ADPCM, it sounds pretty good, there are some imperfections, but I guess that those are because of the low audio quality.
## Post #8
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-23T17:15:55+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

> Reply from GameZelda
>
> With sox, after removing the first 512 bytes, and decoding from VOX ADPCM, it sounds pretty good, there are some imperfections, but I guess that those are because of the low audio quality.Did you try decoding the file posted above with sox? It doesn't sound very good at all, and it is almost the same as when amantonas decoded it with Audacity. I think it can be decoded better. Can anyone who has played the game verify the quality? [Here is Cool Edit's decoding of this](http://files.openomy.com/public/Zench/IDontWannaStop_song.ogg), which has some clicks or "disturbances".
## Post #9
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-07-23T23:08:15+00:00
- Post Title: Guitar Hero On Tour *.hwas codec

I dont think that this bad quality is in the game with all that disturbances.
No its not the typical vox dialogic codec, its a modified version. 
Convert a file to vox dialogic and compare the beginning with that file you will see the difference.
hmm dont found a way to decode this file too.
