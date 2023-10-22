## Post #1
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-08-14T19:50:50+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

Hi there, i have extracted voice & music from Blood Omen: Legacy Of Kain's pill.big 

here example files:
[http://darkmaster.quakedev.com/work/5026760E.vag](http://darkmaster.quakedev.com/work/5026760E.vag) <-- voice
[http://darkmaster.quakedev.com/work/257C636C.vag](http://darkmaster.quakedev.com/work/257C636C.vag) <-- music

this files appear to be a raw 4-bit ADPCM streams, no header, no end number 7. Voice should be played with 11025hz, music with 22050. They have VAG extension
they could be played in GoldWave by using "Vox ADPCM 4-bit" raw mode, although music has some 'volume gaps & unexpected fades' artefact which is not experienced ingame, guess because "Vox ADPCM 4-bit" is not a clear case for those files

i need a code or commandline util that does conversion job

I have tried a VAG depack tools, but they have failed:
 - [http://www.tinyted.net/eddie/decode.cpp](http://www.tinyted.net/eddie/decode.cpp) one prints alot of "Predictor X!" messages and creates broken file
 - bITmASTER's VAG depacker just creates broken file (i've modified this to not skip the starting 64 bits because that VAGS do not have header, and replaced if (flags & 7) break; by if(eof(vag)) break;)

please help, what i'm doing wrong?
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-08-14T20:58:16+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

For some reason or another [SoX](http://sourceforge.net/projects/sox/) seems to be able to decode it okay with this command line:

```
sox -t ima -r 22050 -c 1 257C636C.vag 257C636C.wav
```

(well actually it's not decoding it, but rather it creates a wave file that can be decoded by most audio players)
## Post #3
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-08-19T05:23:50+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

Zench: thank you, that helps
## Post #4
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-08-19T15:01:47+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

Hm... since it's not decoding it, what it does? 
any idea how to convert that RIFF files back?

i checked out in hex - WAV data chunk size differs from this .vag raw size.
## Post #5
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-08-21T22:27:50+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

> Reply from VorteX
>
> i checked out in hex - WAV data chunk size differs from this .vag raw size.The reason for that is the data is divided up into blocks, and each of the blocks has a header. As for converting it back, probably the best thing to do would be to check the command line options of SoX and see if a file can be converted into raw IMA ADPCM.
## Post #6
- Username: VorteX
- Rank: n00b
- Number of posts: 15
- Joined date: Sat May 02, 2009 8:53 pm
- Post datetime: 2009-08-28T15:19:46+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

Thanks for replies Zench
SoX is a great util, problem is solved
I was able to write a program that does automatic conversion job 

here is it:



Download: [http://darkmaster.quakedev.com/files/bo ... 0.3rc1.zip](http://darkmaster.quakedev.com/files/bo/bpill_0.3rc1.zip)
## Post #7
- Username: UltimatumActive
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 17, 2022 9:59 am
- Post datetime: 2022-11-17T02:57:02+00:00
- Post Title: Blood Omen (PC port) - weird ADPCM

Man, I've used your BloodPill v1.1 app and it's awesome, I tried to translate Blood Omen PSX into my language (Spanish), but when I wanted to encode ".wav" to ".fag/.vag" I couldn't, so I found an app called "MFAudio" which can decode and encode, if you still find it useful, you can download it from this  
[MFAudio_ (BloodOmenAudio).zip](https://www.mediafire.com/file/9j1y2slawx015do/MFAudio__%2528BloodOmenAudio%2529.zip/file/)
I also found it curious that BloodPill worked wonderfully to pack ".big" on PC but on PSX game gets corrupted, do you know if "SoulSpiral" can pack?, since it turns out that when replacing each file manually the game is still free of mistakes.
