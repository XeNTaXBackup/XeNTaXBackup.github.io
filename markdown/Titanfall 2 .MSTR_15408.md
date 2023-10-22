## Post #1
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2016-10-24T19:27:57+00:00
- Post Title: Titanfall 2 .MSTR

Hi. How to extract audio? If possible, I would like with the names.
Files -- [https://mega.nz/#F!OAoSBL5D!-3Qo5zb4fHmE33vYCyaxFQ](https://mega.nz/#F!OAoSBL5D!-3Qo5zb4fHmE33vYCyaxFQ)
## Post #2
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2016-10-26T16:47:00+00:00
- Post Title: Titanfall 2 .MSTR

This isn't the reply you were hoping for but I tried my hand at seeing if it was a common format and sadly it isn't, it does look like a separate, new archive from the VPK. 

Titanfall 1 used multilayered waves compressed within the VPK so I tried wav scanner to see if it was perhaps an uncompressed wave archive, no good. I then tried Ravioli game explorer and upon searching the contents it located 7 .swf but I don't think ravioli is accurate. I did a search on the .mstr format and discovered only one other game has used it which was the 2007 ps3 game lair? couldn't find anything else on it if anyone was able to extract it.

Looking inside HxD the offset of the .mstr file begins with  
```
52 54 53 43 02 00 FF FF F0 FF 02 05 00 00 00 00
```
 or 
```
RTSC..ÿÿðÿ......
```
 I'm not familiar with anything that begins with that.  

I know you posted the whole file but I've included a small sample for others to analyze. Hopefully someone will be able to figure this out I really love the sounds in TF2 i'd love to add that to my collection!
[General_stream.zip](https://xentaxbackup.github.io/file/11844_General_stream.zip)
## Post #3
- Username: alexio614
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Nov 03, 2016 10:13 pm
- Post datetime: 2016-11-03T14:16:05+00:00
- Post Title: Titanfall 2 .MSTR

bump
## Post #4
- Username: ImageOne
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 14, 2016 2:59 am
- Post datetime: 2016-11-13T19:06:56+00:00
- Post Title: Titanfall 2 .MSTR

I have also not been able to get past the file located at :\Origin Games\Titanfall2\r2\sound\general_stream.mstr
I know the files in TF1 were located in the vpk folder, these are not.
I'll keep searching and testing.
## Post #5
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-01-20T04:42:57+00:00
- Post Title: Titanfall 2 .MSTR

Ideas at somebody emerged as extract music?
## Post #6
- Username: Norkkom
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jan 31, 2017 10:20 pm
- Post datetime: 2017-02-02T00:10:29+00:00
- Post Title: Titanfall 2 .MSTR

As has been pointed out on other categories on this forum, these .mstr files are associated with the Miles Sound System, by RAD Game Tools. In fact, they even mention on their product page that the most recent version (10) of Miles was "Designed for the game Titanfall 2".

That said, I personally don't know how to open these up, but hopefully having this info moved into this thread will catch the attention of someone who knows better.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-08T16:21:29+00:00
- Post Title: Titanfall 2 .MSTR

I checked the files, identified all the structure. I have all frames for all files. They are variable size. Now only question is, how to decode these frames. According to Miles web, they only use mp3 and ogg. If they didn't invented something new specifically for this game.

What was the codec for previous games of same developer?
## Post #8
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2017-02-11T22:38:03+00:00
- Post Title: Titanfall 2 .MSTR

The original games sound files are uncompressed headerless .WAVs.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-12T06:48:26+00:00
- Post Title: Titanfall 2 .MSTR

Well these are definitely compressed, and variable size. Considering frame sizes, I don't think its mp3 or ogg. So it must be something they invented themselves. Than means I will probably need the game to decode it.
## Post #10
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2017-02-12T15:56:48+00:00
- Post Title: Titanfall 2 .MSTR

> Reply from daemon1
>
> According to Miles web, they only use mp3 and ogg. If they didn't invented something new specifically for this game.They do mention Bink Audio though, which is, from my guess, is what this "invented" audio codec was used for the game.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-12T16:23:59+00:00
- Post Title: Titanfall 2 .MSTR

> Reply from AnonBaiter
>
> They do mention Bink Audio though, which is, from my guess, is what this "invented" audio codec was used for the game.

ok, according to what i see about this codec, it can really be bink audio. Because using 8-bit quantizers. It can easily be seen in the stream. I will try it.
## Post #12
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-05-08T02:48:25+00:00
- Post Title: Titanfall 2 .MSTR

> Reply from daemon1
>
> ok, according to what i see about this codec, it can really be bink audio. Because using 8-bit quantizers. It can easily be seen in the stream. I will try it.
Did succeeded you extract the audio?
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-05-08T05:51:34+00:00
- Post Title: Titanfall 2 .MSTR

I had no time yet to look into this. Was busy with other games.
## Post #14
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-07T12:08:20+00:00
- Post Title: Titanfall 2 .MSTR

Are there any successes in extracted?
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2017-07-14T18:11:16+00:00
- Post Title: Titanfall 2 .MSTR

The game has been cracked, so good chance of more people researching this.
## Post #16
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-10-27T06:36:31+00:00
- Post Title: Re: Titanfall 2 .MSTR

Has anyone got or knows how to extract audio?
## Post #17
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2018-11-11T12:18:51+00:00
- Post Title: Re: Titanfall 2 .MSTR

i don't found how but it's look possible

[https://www.reddit.com/r/titanfall/comm ... enjoyment/](https://www.reddit.com/r/titanfall/comments/5wprza/titanfall_2_voice_lines_for_your_enjoyment/)
## Post #18
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2019-02-14T20:31:42+00:00
- Post Title: Re: Titanfall 2 .MSTR

I've been inquiring around about how to extract the audio from apex legends since it's free and easily accessible. I'm posting this here to see if maybe someone here can figure this out. Happyend on ZenHax, gave me a lead that has allowed me to make some progress but I've hit a brick wall. The MSTR, contains a header 1FCB which corresponds with .binka audio, splitting the file allows me to convert using binka2wav, however the problem is the audio abruptly cuts off, I cannot figure out if i'm A: cutting it wrong, or  B: the program is not compatible. I'm leaning towards A but again I am not sure.  

here is am image of what values I used: [https://pasteboard.co/I1aENca.png](https://pasteboard.co/I1aENca.png)

Another interesting note in my research normal binka extraction requires mss32.dll from whatever game your extracting from, titanfall 2 and apex legends don't use that. Both games use mileswin64.dll, if i'm right it's because it's 64 bit rather than 32 bit. 

Here is a sample of the file I split, if there is anything else needed please let me know I've really been racking my brain out on this one......
[general_stream_00000256.zip](https://xentaxbackup.github.io/file/15724_general_stream_00000256.zip)
## Post #19
- Username: Dralion87
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 21, 2019 8:19 am
- Post datetime: 2019-02-21T00:23:50+00:00
- Post Title: Re: Titanfall 2 .MSTR

@durandal217 Any update on this?

I'm trying to extract the audio files from Apex legends as well right now but I had no luck so far.
## Post #20
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2019-02-21T06:18:40+00:00
- Post Title: Re: Titanfall 2 .MSTR

The update is that no one cares.. 

A lot of the smart guys have moved on and those who are left are slammed with other projects or don't care. My knowledge is limited, my programming skills are kiddy level and non existent.  I did find out that a lot of major audio pieces are multi channel (6 channel) just like the first titanfall however the audio is split into chunks. 

There is one dude who has looked into it, he's made small progress but he just keeps hitting brick walls, like for example can anyone tell us if 
```
{ 0x02, 0x01, 0x80, 0xbb }
```
 is also part of the .binka signature? Every binka file have these 8 bytes at the beginning.

Is it some type of ancient alien language, a hotdog? The world may never truly know....
## Post #21
- Username: Lyxica
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 11, 2019 6:13 pm
- Post datetime: 2019-08-11T10:15:07+00:00
- Post Title: Re: Titanfall 2 .MSTR

[tf2 sound dumper](https://zenhax.com/viewtopic.php?f=6&t=9439&p=50248#p50248)
## Post #22
- Username: Arcalane
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 11, 2009 10:01 pm
- Post datetime: 2019-08-11T20:20:52+00:00
- Post Title: Re: Titanfall 2 .MSTR

> Reply from Lyxica ↑Sun Aug 11, 2019 6:15 pm at Sun Aug 11, 2019 6:15 pm
>
> 
tf2 sound dumper

Tried it out on a few files so far. Works nicely, but volume for dialogue is very low compared to music.
## Post #23
- Username: Lyxica
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Aug 11, 2019 6:13 pm
- Post datetime: 2019-08-11T21:54:03+00:00
- Post Title: Re: Titanfall 2 .MSTR

i'll check if a dialogue volume dial is set low
