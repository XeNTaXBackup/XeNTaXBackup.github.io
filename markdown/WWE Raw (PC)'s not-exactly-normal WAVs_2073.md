## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-03T23:21:34+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

After a while of piddling with this game I've realised a few things. This among them. At first glance all WAVs appear normal, play normal, etc. Normal are they? No.

Each of them are MPEG Layer-3 at 96kbs and 48kHz. Not only this but in a hex editor there are oddities, at least from what I've experienced of what is the norm for a WAV.

With some hex editing and sound editing I was able to make a MPEG Layer-3 96kbs and 48kHz and it sounded decent, although I had to really slow it down, yet still somthing was different as the game could not play it when I selected it. I believe it has to do with the fact that the WWE wavs have a thing about "q fact" instead of the standard "q data" not sure here. I'll provide an example of the WAV format WWE Raw uses.

Any idea what it is exactly that differs it from an average wav? It seems that it is play only. Nothing I've found can actually save to this format, like play only.
[mu_win.rar](https://xentaxbackup.github.io/file/837_mu_win.rar)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-04T16:57:35+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

mm. i converted the mp3-waved to mp3 conventional, and the structure looks the same,,,but!! this maybe help.

Looking inside the waved mp3 (the attached file):



and now from the mp3 conventional:


Can be this difference?
## Post #3
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-04T19:52:49+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

I belive the mp3 is encoded with GoGo mp3 encoder.

[http://www.mp3-tech.org/encoders_win.html](http://www.mp3-tech.org/encoders_win.html)

You could also strip out the RIFF header completely and just
rename it to mp3.  (header ends after "data"+4 bytes longword).

Remember that WAVE files kan contain any data. I can squeeze in an
Ogg Vorbis audio file in it, as long as I specify the correct codec in the
AudioID Header of the RIFF.

what im trying to say is that this is not really abnormal,
its occuring everywhere 

And the "q fact" is actually not abnormal either. the "fact" header is written by some encoders to hold information about the stream. some other encoders just put "data" , the "data" tag tells the parser where the stream is starting, and the following 4 bytes contains a longword on how long the stream is.

and the q in "q fact" is just coincidental, the q is part of a longword number just before the "fact" actually :X

so....from my point of view! perfectly normal RIFF-WAVE files =DD

And open Windows Soundrecorder (windows/sndrec32.exe), and you can save files in RIFF using mp3 codec.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-04T21:02:08+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

> you can save files in RIFF using mp3 codec
I do with ffmpeg:

> ffmpeg -i name.wav -acodec mp3 namefinal.wav
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-04T23:21:37+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

So this would create a WAV very similar to the WAV example given?

And I know about saving a WAV in MPEG-3 format. But creating one that fits the criteria of the example WAV is the problem I'm facing. As with everything I try the game does not read the ones I make even if I can make them MPEG-3 with the same bitrate and kHz.
## Post #6
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-05T11:57:19+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

Hey darkfox. could you create an WAV-MP3 and upload somewhere
that doesnt work in the game?

I want to analyze the differences. so please make a small file, like
300-400 kb maybe.

The analyzation would cover:
The differences between the games RIFF header, and the RIFF header
you are trying to create with your programs.
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-06T00:02:09+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

If you mean a MPEG Layer-3 encoded WAV. Here is an example that doesn't work.
[FestersQuestBossLoop.rar](https://xentaxbackup.github.io/file/839_FestersQuestBossLoop.rar)
## Post #8
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-06T00:19:17+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

i downloaded the example(the last one) try if works
[test1.rar](https://xentaxbackup.github.io/file/840_test1.rar)
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-06T03:35:48+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

Darn. I'm afraid not. Though trying the same from sounds of the same game, they work. So somthing is going on here.
## Post #10
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-06T04:52:47+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

=O ...try this....maybe maybe.....

(its cutted though to fit the limits :X )
[test5.rar](https://xentaxbackup.github.io/file/841_test5.rar)
## Post #11
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-06T06:15:22+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

No maybes about it. That worked 100%, I heard the clip and everything ingame, what did you do?
## Post #12
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-06T09:03:16+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

I re-encoded it in Sndrec32 using LAME mp3 encoder in 48khz 96kbit,
and as a precaution i hexedited the longword before the "fact" tag to look exactly as the tag in the original game WAVE. however if this is neccessary i dont know. maybe it works just good if you have encoded in 48khz and just having a fact tag?....the ones you had (test1.rar) was encoded at 24khz. (and your original FestersQuestLoop was also read as 24khz, atleast what the header states).

so maybe it will work just if you encode it in 48khz properly?
maybe its just that easy =)
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-09-06T14:24:56+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

uops, really interesting  can teach us?
## Post #14
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-06T15:19:55+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

=o

i just saved it with 48khz instead.
(as you can see on the original file it reads 24khz). and the original had no
"fact" tag. but saving with SndRec32 it will get an fact tag automatically.
[harharll.gif](https://xentaxbackup.github.io/file/843_harharll.gif)
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2006-09-06T20:11:49+00:00
- Post Title: WWE Raw (PC)'s not-exactly-normal WAVs

Alright, now sndrec32 supports it. Thanks! And it does work perfectly now too  thanks!
## Post #16
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-07T17:09:14+00:00
- Post Title: lol

I r teh r0xx0rs! ;XX
## Post #17
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2006-09-22T14:31:42+00:00
- Post Title: lol

Wow, this brings up very old memories.  I was one of the first guys to mod this game, and helped figure out many things in the game.  I also made several mods, like a roster update, RVD move set, Chavo Guerrero mod, and Brock Lesnar entrance mod.  I also released a few guides to help mod the game.  As far as the wav files go, I think I remember using the lame commandline utility to make wavs for the game, but it has been such a long time, that it may have been a different game I did this on.  It seems you've figured it out though, so good luck.
