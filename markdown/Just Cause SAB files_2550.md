## Post #1
- Username: Aceman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 25, 2007 6:45 am
- Post datetime: 2007-03-24T23:12:21+00:00
- Post Title: Just Cause SAB files

Greetings,

I'll get straight to it, I've come here to ask for help extracting the SAB files from Just Cause, as no extractor in existence seems capable, and I've certainly tried quite a few.    

Here's a link to the demo:

[http://www.gamershell.com/download_15145.shtml](http://www.gamershell.com/download_15145.shtml)

I would attach a file cutter extract, but it's too big,  I would email it to somebody through. 

Cheers.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-25T00:43:48+00:00
- Post Title: Just Cause SAB files

I remember SAB files. are raw pcm audio, with a modified header, get oggdec and make this:

1. oggenc --raw file.sab 
2. play the ogg

oggenc=> [http://www.vorbis.com](http://www.vorbis.com)

This post must to be in audio section
## Post #3
- Username: Aceman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 25, 2007 6:45 am
- Post datetime: 2007-03-25T02:21:31+00:00
- Post Title: Just Cause SAB files

Ok,

So I got a oggdec V1.9.3 file, now I have to download either:

libvorbis
libogg
vorbis-tools
libtheora

Which one exactly?

And then I do start > run > cmd, and type in this:

oggenc --raw file.sab 

Changing the file name to match the file being extracted yes? and it gets converted into an OGG file? And then I convert it?

Sorry for the questions, I'm a bit green.
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-03-25T11:06:01+00:00
- Post Title: Just Cause SAB files

> Changing the file name to match the file being extracted yes? and it gets converted into an OGG file? And then I convert it?

If you do 
```
oggenc --raw name.sab
```
 you file must be name.ogg, play it with ffplay/mplayer/vlc/winamp or any player, maybe sounds too fast, no problem

Now do this:

```
oggdec --raw name.ogg
```
 
You must obtain a name.raw, next you need to make a fake header, the game check this, get the first 1 kbytes of the original game, save it and do:

```

```


After this the game recognizes the audio, but!!! only the voices, NOT the music

I know it's silly method, but works, maybe somebody can make a small exe of this
## Post #5
- Username: Aceman
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 25, 2007 6:45 am
- Post datetime: 2007-04-01T22:30:15+00:00
- Post Title: Just Cause SAB files

Ok,

I tried and failed, and I've spent too much time on this already just for the music  

Instead I respectfully ask that the SAB file format is included in future releases of Multiex, so that future users are spared.

Cheers for the help Savage, but I'm just too green.
## Post #6
- Username: Vess
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 08, 2006 2:14 am
- Post datetime: 2009-02-19T21:58:35+00:00
- Post Title: Just Cause SAB files

I've just encountered this pretty fun game, and, curious about the possibility of extracting its main title music, checked for help here. As it turns out, there is a faster and lossless way: simply open the *.SAB file(s) as RAW, 22050, stereo, 16-bit, Intel PCM file, et voila. There will be a half-a-second click in the beginning, due to the file's header, so just cut it off.

The issue then is to divide the file properly. There should be 52 tracks, named:
MUSIC_ACTION_HIGH_01
MUSIC_ACTION_HIGH_02
MUSIC_ACTION_HIGH_03
MUSIC_ACTION_HIGH_04
MUSIC_ACTION_HIGH_05
MUSIC_ACTION_HIGH_06
MUSIC_ACTION_HIGH_07
MUSIC_ACTION_HIGH_08
MUSIC_ACTION_LOW_01
MUSIC_ACTION_LOW_02
MUSIC_ACTION_LOW_03
MUSIC_ACTION_LOW_04
MUSIC_ACTION_LOW_05
MUSIC_BLACKHAND_01
MUSIC_CARAMICAS_SPEECH
MUSIC_CARDRIVE_01
MUSIC_CARDRIVE_02
MUSIC_CARDRIVE_03
MUSIC_CARTEL_01
MUSIC_CIA_01
MUSIC_FLYING_01
MUSIC_FLYING_02
MUSIC_FLYING_03
MUSIC_LIBERATE_SETTLEMENT_01
MUSIC_LIBERATE_SETTLEMENT_02
MUSIC_LIBERATE_SETTLEMENT_03
MUSIC_LIGHT_01
MUSIC_LIGHT_02
MUSIC_MENU_01
MUSIC_MISSION_COMPLETE_01
MUSIC_MISSION_FAILED_01
MUSIC_OBJECTIVE_01
MUSIC_OBJECTIVE_02
MUSIC_OBJECTIVE_03
MUSIC_OBJECTIVE_04
MUSIC_RADIO_01
MUSIC_RADIO_02
MUSIC_REBEL_01
MUSIC_RICO_DEAD_01
MUSIC_ROMANCE_01
MUSIC_SAFEHOUSE_AGENCY_01
MUSIC_SAFEHOUSE_CARTEL_01
MUSIC_SAFEHOUSE_REBEL_01
MUSIC_SEXY_01
MUSIC_SEXY_02
MUSIC_SKYDIVE_01
MUSIC_SPEEDBOAT_01
MUSIC_SPEEDBOAT_02
MUSIC_SPEEDBOAT_03
MUSIC_STEALTH_012
MUSIC_STEALTH_023
MUSIC_COUNTDOWN_M16

I split the file automatically, with a tool from Softpedia (or maybe Tucows?) that could cut WAV files based on detecting silence periods in them. I fiddled with the silence threshold setting in it and I think it's split correctly, but only the composer could verify all this. 

(The SFX files have to be treated either as mono or 11025, by the way - I haven't really checked.)
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-07-30T19:13:00+00:00
- Post Title: Just Cause SAB files

Can attach the program you used? or the name?
## Post #8
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2009-08-06T15:40:05+00:00
- Post Title: Just Cause SAB files

@ Vess....

Yes. I also got it right with MEN OF VALOR PC. There is one archive file named music.sab, which I succesfully rip in the same way you mentioned. I also found some individual music files in .sab format. Some are playable after ripping the pcm audio, but others have a curious way of playing in thousands of chunks with background noise inbetween. i tried encoding to ogg but get the same result. I try to open audacity in case of multiple channels, but still get 2 channels. Seems to have something to do with being dynamic layers....

Will your wav splitter work here?
