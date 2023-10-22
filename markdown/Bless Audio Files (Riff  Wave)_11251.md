## Post #1
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T09:48:42+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Hey Guys!

Want to give a short question about Bless Sound Files.

Format is *.wem (SWTOR Tool not work) and File Header is RIFF/WAVE

Here samples:

[http://www.multiupload.nl/ZUYY14G031](http://www.multiupload.nl/ZUYY14G031)



Thanks guys
## Post #2
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-02-25T10:33:49+00:00
- Post Title: Bless Audio Files (Riff / Wave)

> Reply from ehnoah
>
> Hey Guys!
Format is *.wem (SWTOR Tool not work) and File Header is RIFF/WAVE

Use ww2ogg.exe by hcs
## Post #3
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T11:07:01+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Any command I need use for it? I know Drag & Drop but dosn't work at all.
## Post #4
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-02-25T11:51:35+00:00
- Post Title: Bless Audio Files (Riff / Wave)

ww2ogg input.wem --pcb packed_codebooks_aoTuV_603.bin
this is for ww2ogg.

after that use revorb.exe on output file to be able to hear that.
revorb output.ogg
## Post #5
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T12:10:48+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Thanks!

Working like a charm 

```
pause
revorb input.ogg
```
## Post #6
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T12:25:07+00:00
- Post Title: Bless Audio Files (Riff / Wave)

It seems there are a few files that working.

other also have Data in the header. Is there any command for that? Can upload if needed.

RIFF/WAV/JUNK/DATA
## Post #7
- Username: deepshit
- Rank: advanced
- Number of posts: 76
- Joined date: Wed Feb 01, 2012 4:43 am
- Post datetime: 2014-02-25T14:27:13+00:00
- Post Title: Bless Audio Files (Riff / Wave)

ww2ogg parses wav chunks correctly.
It should work with them too.
Send me some files to test.
## Post #8
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T15:05:42+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Here is the File:

[http://www.multiupload.nl/60I5FRLQ2X](http://www.multiupload.nl/60I5FRLQ2X)

Thanks! 

Yeah, I remember it should work but it simply nothing happen. Dunno.
## Post #9
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2014-02-25T20:31:29+00:00
- Post Title: Bless Audio Files (Riff / Wave)

In general if you see a JUNK chunk it probably isn't vorbis. In this case it is the magic Audiokinetic Wwise Screwed MS IMA APDCM format.

ima_rejigger2: [http://hcs64.com/files/ima_rejigger2.zip](http://hcs64.com/files/ima_rejigger2.zip)

can convert these files into normal MS IMA. Just run

```
ima_rejigger2.exe 17839192861298.wem
```

and the .wem will be modified in place, you should then be able to open it in Audacity (or rename it to .wav to open in many other players, Winamp notably doesn't seem to like ADPCM wavs though).

I have been reluctant to publicize this tool as there were some early reports of distorted files, so it seemed there was some slightly different decoder at work, but a lot of these seem to come up recently and the distortion doesn't seem to be an issue. That first game may have just had shitty audio, or the format may be slightly different on different platforms.
## Post #10
- Username: ehnoah
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Feb 29, 2012 6:21 am
- Post datetime: 2014-02-25T22:22:47+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Thats working, thanks for this clarification.
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2014-02-26T03:15:42+00:00
- Post Title: Bless Audio Files (Riff / Wave)

Argh well this is clearly not quite right (treating it as MS IMA after the rejiggering). I keep looking at it and there are oddities, and it just sounds a little fuzzily off. The scale index at the start of each frame is always off by one from what you would expect from decoding the previous frame, except when it pins to 0. This is consistently the case with this file, one another guy sent me just recently, and the one I was dealing with back here: [http://www.hcs64.com/mboard/forum.php?showthread=35147](http://www.hcs64.com/mboard/forum.php?showthread=35147)
That file actually keeps clipping a lot, which is a sure sign that something is going wrong with the decode. I have exhausted the obvious things, don't really want to have to dig into Wwise again if I can avoid it. I assume that something is tweaked away from the standard MS IMA decoder. Gonna give up on it for now, if anyone wants to bash their head against it I'd love for someone else to solve it. Now I remember why I'd not remembered this as a victory.
