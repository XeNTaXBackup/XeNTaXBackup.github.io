## Post #1
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2016-01-17T03:35:36+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Hello, I have this "DATA.PAK" file from Spy vs. Spy 2005 on PS2 that I want to open up.
I need help with extracting files from it.
Any help would be really appreciated. Thanks!

[DATA.PAK](https://drive.google.com/file/d/0B7neX86ybFxfdzhmaWVpcDc1NU0/view?usp=sharing) [946 MB]
## Post #2
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-13T08:43:58+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Bumpity Bump, i wanna see this pak file opened aswell!
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-13T19:14:12+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Can I ask why do you need that?

The format is really simple...
## Post #4
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-13T19:47:16+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

what would you use to unpack or extract files from it?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-13T20:06:34+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

That depends on what would i need from it. For example, I just extracted music from there with hex editor.
## Post #6
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-13T20:16:09+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Nice! is there anyway to get most of the sound effects? possibly models?
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-13T20:54:16+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

There's always a way. The only question is how much time it could take.

Getting sounds will be easy. I don't know anything about PS2 models though.
## Post #8
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-13T20:58:23+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Ahh i see, i'm sort of more interested in the sounds aspect then the models at the moment, if there's a way to get most of them that'd be awesome
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-14T07:10:10+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

there are many ways.

1. use this scropt [http://aluigi.altervista.org/bms/spy_vs_spy_ps2.bms](http://aluigi.altervista.org/bms/spy_vs_spy_ps2.bms) to unpack archive. Then inside you'll have a number of "map" files. Open them with hex editor, search for audio files and extract them manually.

2. try and find some tool to work with vicious engine. I'm not sure if any exist, but there were many games on it, so its possible.

3. right now I'm thinking of a way to make a tool to automatically detect vag streams inside of any files. I'll use this game for testing. You can wait for me to finish it.
## Post #10
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-14T08:13:56+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Kick ass man, thanks , although finding the sounds within the map files is a little tricky, i think with your program it would be easier to obtain them
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-16T12:27:55+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

The tool is already working  It scans any file for raw vag streams.
## Post #12
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-16T13:25:53+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Wow... the program itself works perfectly! although i have to use MFAudio to play most of the sounds; because i don't really know to much about the second part;

"Create GENH for them with parameters:"

PlayStation 4-bit ADPCM
header 0x40
channels 1
frequency 22050
no loops

"Then decode them with vgmstream "

They come out pretty good! although a few of them are a bit staticy 

Awesome job!
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-16T13:39:52+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Use these parameters to play it with MFAudio:

offset 40
channels 1
frequency 22050

most important is offset and channels, this way there will be no "staticy"
## Post #14
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-16T13:49:17+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Huh, i guess that does fix them a bit 

if only there was a way to convert them all to .wav
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-16T13:58:19+00:00
- Post Title: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

this is just first test 

conversion will be later
## Post #16
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-16T20:55:52+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Kickass! lemme know about any further updates on this thread
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-19T18:16:44+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

I finished stereo/interleaving part of my tool, and now I'm getting to decoding part. I think soon it will be ready.

It was easier than I expected. It's ready. Most maps have same sounds. Some maps have many more!

Note that it will only work correctly for this game, because it has fixed 0x40 offset now. I will make a parameter later.
[vag_scanner.rar](https://xentaxbackup.github.io/file/10803_vag_scanner.rar)
## Post #18
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-20T04:11:16+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

WHOOO!!! you're on FIRE 

this is amazing, outstanding work man.
## Post #19
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-26T16:07:23+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Finished organizing all the sounds from the game! 

amazing tool man; i'm surprised you were able to accomplish what you did in such a short amount of time. BADASS!
## Post #20
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2016-04-27T06:49:46+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

This is great, thank you very much for help! Is there any way to extract textures and models from these files though?
## Post #21
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-04-27T10:05:09+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

> Reply from bVictor
>
> This is great, thank you very much for help! Is there any way to extract textures and models from these files though?

yeah that'd also be something if you could get the models aswell
## Post #22
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-04-27T15:25:02+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Right now I'm looking into different console model & texture formats. Maybe soon I'll be able to do that.
## Post #23
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2016-04-27T17:50:30+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

> Reply from daemon1
>
> Right now I'm looking into different console model & texture formats. Maybe soon I'll be able to do that.

Awesome, here is the xbox classic version which is apparently unpacked DATA.PAK. vag_scanner doesn't work on the xbox .maps though, they're different.

P.S: PS2 version of the game is PAL only, while the uploaded XBOX is NTSC

[[XBOX] Spy vs. Spy (US)](https://drive.google.com/file/d/0B7neX86ybFxfY3ZuMW9COHJkdXc/view?usp=sharing)

I was able to extract some textures from game on PCSX2 using TexMod, but it's slow (since you have to find the texture in the game) and textures need to be color calibrated after this, which slows down the process even more.

[Here's one of them.](https://drive.google.com/file/d/0B7neX86ybFxfd3BYd3BMQkdRS1U/view?usp=sharing)
## Post #24
- Username: Reddance
- Rank: advanced
- Number of posts: 64
- Joined date: Sun Dec 06, 2015 1:03 am
- Post datetime: 2016-05-15T03:13:29+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Any progress model wise?
## Post #25
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-05-15T07:26:54+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Unfortunately no. Xbox360 & PS3 models are closer to PC, so I can extract them. PS2 and xbox are too far from that.
## Post #26
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2016-05-19T20:15:49+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

> Reply from daemon1
>
> Unfortunately no. Xbox360 & PS3 models are closer to PC, so I can extract them. PS2 and xbox are too far from that.

I see.. Are there any known tutorials on the extraction? I could try myself.
## Post #27
- Username: bVictor
- Rank: n00b
- Number of posts: 10
- Joined date: Sun Jan 17, 2016 10:27 am
- Post datetime: 2018-01-05T23:40:47+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

> Reply from daemon1
>
> I finished stereo/interleaving part of my tool, and now I'm getting to decoding part. I think soon it will be ready.

It was easier than I expected. It's ready. Most maps have same sounds. Some maps have many more!

Note that it will only work correctly for this game, because it has fixed 0x40 offset now. I will make a parameter later.
daemon1, could you pass me the source code of your vag_scanner, it won't work through wine properly and now gives me

```
   at vag_scanner.Program.Main(String[] args)
```

both, in wine and on windows xp in qemu (gnome-boxes).
## Post #28
- Username: MrTigroivch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 23, 2019 11:37 pm
- Post datetime: 2019-01-24T15:55:27+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Hi, yeah I know... I writing it too late but your vag_scanner is not working on windows 7, it simply crashes
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-24T16:24:26+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

i made it in windows 7
it cant crash on it
## Post #30
- Username: MrTigroivch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 23, 2019 11:37 pm
- Post datetime: 2019-01-25T16:47:21+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

But it says "vag_scanner has stopped working" when I lauching it
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-01-25T17:13:41+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

dont "launch" it, drag files onto it
## Post #32
- Username: MrTigroivch
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 23, 2019 11:37 pm
- Post datetime: 2019-01-26T10:50:30+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Thanks! Everything now works perfectly
## Post #33
- Username: timonenluca
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 27, 2021 9:45 pm
- Post datetime: 2023-06-30T07:12:46+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Does this work on extracting models and textures? 

Edit: unfortunately not , i really hope someone is able to extract the textures and models. Was my favorite childhood game.
## Post #34
- Username: emanuelect
- Rank: n00b
- Number of posts: 16
- Joined date: Sat Oct 16, 2021 9:34 pm
- Post datetime: 2023-07-02T13:37:21+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

Hi, I am trying to translate the game curious george, if you find a way to extract and replace the audio and text of the game, please let me know even with a private message. (This game also uses Vicious Engine.)
## Post #35
- Username: LemonBR
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 19, 2023 3:22 am
- Post datetime: 2023-08-20T01:22:57+00:00
- Post Title: Re: [HELP] [.PAK] Spy vs. Spy (2005) [PS2] [Vicious Engine]

> Reply from timonenluca ↑Fri Jun 30, 2023 3:12 pm at Fri Jun 30, 2023 3:12 pm
>
> 
Does this work on extracting models and textures? 

Edit: unfortunately not , i really hope someone is able to extract the textures and models. Was my favorite childhood game.

Hello budy, how are you? I saw your comment and decided to try to help in some way, but I'm not any kind of expert in this area so I did some research on the internet and found a video that can help you, if you don't understand what is being said in the video you can use the automatic subtitle translation feature (maybe some moments the subtitle is not very accurate).

The tutorial is a little old and the person who made it said that this method doesn't work for 100% of the games, but it might work for you   

This tutorial is divided into 2 parts.

Video 1 shows how to extract textures:

[https://www.youtube.com/watch?v=OmL__TuAP3I](https://www.youtube.com/watch?v=OmL__TuAP3I)

Video 2 shows how to extract the templates:

[https://www.youtube.com/watch?v=57xRx1VOCuU](https://www.youtube.com/watch?v=57xRx1VOCuU)

hope this can help you
