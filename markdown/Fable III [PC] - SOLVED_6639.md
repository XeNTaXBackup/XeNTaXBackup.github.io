## Post #1
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2011-05-18T13:47:51+00:00
- Post Title: Fable III [PC] - SOLVED

Okay, so the PC version of Fable III uses PCM WAV / xWMA for its music.

To extract the xWMA's, modify Alpha23's WaveFormatScanner script to scan for "XWMAfmt" instead of "WAVEfmt" and then convert those files into PCM WAV using xWMAEncode.

To deinterleave the crescendo_track.bnk.dat files, you need to use this [deinterleave tool](http://www.mirrorcreator.com/files/RHQN25VD/Deinterleave_2011-01-18.7z_links) created by the wonderful Snakemeat. Use the code below to deinterleave:

```
deinterleave 7 0x8000 0x30 crescendo_track_xx.bnk.dat
```


All the crescendo tracks are standard 16-bit Little Endian PCM WAV at 48000Hz

All credit goes to Snakemeat for his assistance on the crescendo tracks.
## Post #2
- Username: ericthered7
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 18, 2012 2:24 am
- Post datetime: 2012-02-17T18:37:03+00:00
- Post Title: Fable III [PC] - SOLVED

I've been trying to figure out how to extract the audio files for Fable 3 (PC).  I saw the post above and tried to follow the steps.

I was able to use TodX's tool to extract streaming.bnk / streaming.bnk.dat.  That gave me a big interesting file called "music_region.bnk.dat" which I believe has a lot of the songs I want in it, but since it doesn't have a "music_region.bnk" file I can't open it using TodX's tool.

I'm kind of new to all this... Brendan, how did you managed to extract the xWMA files from the .bnk.dat files?

Thanks!
## Post #3
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2012-02-19T09:16:46+00:00
- Post Title: Fable III [PC] - SOLVED

You have to manually extract the songs from the .dat archive

You can do it using VGM Toolbox.
[http://sourceforge.net/projects/vgmtoolbox/](http://sourceforge.net/projects/vgmtoolbox/)

You have to use the Advanced Cutter and use the preset "RIFF Style Header"
Misc. Tools > Extraction Tools > Generic > Advanced Cutter/Offset Finder

Presets > RIFF Style Header

Click load and then change the Search String from "RIFF" to "xWMA" and the extension from ".WAV" to ".XWMA" and then drag the music_region.bnk file onto VGM Toolbox.

From there, you have to use the xWMAEncode tool to convert them into listenable PCM WAV.
## Post #4
- Username: ericthered7
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Feb 18, 2012 2:24 am
- Post datetime: 2012-02-20T04:52:01+00:00
- Post Title: Fable III [PC] - SOLVED

Thanks Brendan!

That worked but I had to leave the search string as "RIFF".  Also a couple of the songs were actually in WAVE format, after extracting them using VGM toolbox I just had to change the file extensions to .wav to get them to play (the wav ones said "WAVEfmt" in the header).

Thanks,
Eric
## Post #5
- Username: KiNG
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 05, 2012 11:10 pm
- Post datetime: 2014-03-10T08:08:56+00:00
- Post Title: Fable III [PC] - SOLVED

is there any chance of the deinterleave tool been reposted plz as the link is dead and it doesnt seem to be available anywere else
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-03-10T12:15:53+00:00
- Post Title: Fable III [PC] - SOLVED

Re-uploaded the deinterleave tool. Updated the link on that post
