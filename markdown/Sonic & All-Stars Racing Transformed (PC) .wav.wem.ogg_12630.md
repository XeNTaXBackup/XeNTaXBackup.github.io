## Post #1
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2015-02-21T22:22:48+00:00
- Post Title: Sonic & All-Stars Racing Transformed (PC) .wav/.wem/.ogg

Hello, I managed to extract SoundBanks.pck, and later on all of It's .bnk however I noticed that most of the sounds will not work with ww2ogg or revorb, returning:

```

```


I'm using the packed_codebooks_aoTuV_603.bin provided with ww2ogg

Sample files contain working an non working ".wav"(.wem?), .ogg and .bnk
[7zip](http://www.mediafire.com/download/ep2nrffdvp3gmdc/SoundBanks.7z)
[Zip](http://www.mediafire.com/download/tsbd5mgtiyqv0sd/SoundBanks.zip)

Tool Used:
.pck QuickBMS script by AlphaTwentyThree
bnkextr by CTPAX-X Team
ww2ogg by hcs
revorb by Yirkha
## Post #2
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-02-22T23:11:41+00:00
- Post Title: Sonic & All-Stars Racing Transformed (PC) .wav/.wem/.ogg

> Reply from Gistix
>
> Hello, I managed to extract SoundBanks.pck, and later on all of It's .bnk however I noticed that most of the sounds will not work with ww2ogg or revorb, returning:
Code: Select allParse error: expected 0x42 fmt if vorb missing


I'm using the packed_codebooks_aoTuV_603.bin provided with ww2ogg

Sample files contain working an non working ".wav"(.wem?), .ogg and .bnk
7zip
Zip

Tool Used:
.pck QuickBMS script by AlphaTwentyThree
bnkextr by CTPAX-X Team
ww2ogg by hcs
revorb by Yirkha
wwise also has another audio type besides vorbis, they also have an adpcm format. hcs helped me out with this issue in payday the heist, I'll copy paste what he wrote:

> The audio is Microsoft-style IMA ADPCM, Audiokinetic has this weird tendency to interleave these files wrong. I'd written a tool for this earlier but it doesn't work so well on these files (they've decided to altogether abandon reason and use codec id 0x02 instead of the 0x69 they used to, should be 0x11 anyway), so here's a revised version: hcs64.com/files/ima_rejigger2.zip Run ima_rejigger2.exe on every .wav and it should put them in the standard MS IMA interleave, it modifies the files directly.

Edit: Could not get it to work for any of the non working files though. all gave errors depending on which ima rejigger build i used (there are three in total) This is from the pc game right? if it's the xbox 360 one, it might be xma in there past the riff/rifx header.
## Post #3
- Username: Gistix
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Dec 20, 2010 5:45 am
- Post datetime: 2015-02-24T18:05:52+00:00
- Post Title: Sonic & All-Stars Racing Transformed (PC) .wav/.wem/.ogg

Hello Pepper, ima_rejigger2.exe worked fine even for the non working samples and yes It is the PC version of the game, Thank you so much for your help!
