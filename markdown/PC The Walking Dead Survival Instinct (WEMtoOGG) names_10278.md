## Post #1
- Username: Sparktank
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 25, 2010 7:00 pm
- Post datetime: 2013-03-28T17:19:43+00:00
- Post Title: PC: The Walking Dead: Survival Instinct (WEMtoOGG) names

I found these threads helpful:
[viewtopic.php?p=84023#p84023](http://forum.xentax.com/viewtopic.php?p=84023#p84023) (The Walking Dead SI Archive)
[viewtopic.php?p=63053#p63053](http://forum.xentax.com/viewtopic.php?p=63053#p63053) SW: TOR (quickBMS script for extracting the WEM archives)
[viewtopic.php?p=66311#p66311](http://forum.xentax.com/viewtopic.php?p=66311#p66311) SW: TOR (Guide: Converting .wem to .ogg/Converting .bnk to .wem)

Tools used:
QuickBMS
ww2ogg/packed_codebooks_aoTuV_603
revorb
bnkextr

Game:
The Walking Dead: Survival Instinct (PC)

Formats:
POD5 (archive)
.bnk (BKHD) -> .wav -> .ogg
.wem -> .ogg

Need:
Internal file names/cues

This might be useful for dealing .bnk containers to obtain file names.
[viewtopic.php?p=36450#p36450](http://forum.xentax.com/viewtopic.php?p=36450#p36450) (Wwise *.bnk containers)

I managed to extract the contents of the POD5 archive for W32SOUND.POD.

> POD5Â.2‰Release format assets...........................................................ó.......è...è...................................................................................................................................................................µÍx)>òæ!ë.......ÿÿÿÿÿÿÿÿ................................................................................................RIFF‰±..WAVEfmt B...ÿÿ..D¬..:L......0.......Ù£..æ...á°....g.....æ...J.g.@G..0I..É.'...cue ................data............LIST&...adtllabl........mus_proto_amb_gtr_01..dat

I extracted quite a bit of .bnk and .wem containers and found a way to extract/convert them all to playable .ogg files in Foobar.
Success (thanks to the work of others).

However, all the files are assorted numbers.
2807192.wem
2807192.ogg

Inside the .wem has a cue name for the file/track.
For 2807192.wem:

> RIFFý„".WAVEfmt B...ÿÿ..D¬..øT......0.......)úE.æ...Y„".........æ...€...@G..0I..É.'...cue ................data............LIST"...adtllabl........mus_BG_03_detect..data
NOTE: The cue name (mus_BG_03_detect) seems to be offset at 92 for each file.
I've checked 7 random .wem files and the offset: 92 is consistent.

I would like to know if there's any scripts or tools that can take the internal cue name of the .wem files and apply it to the final output file.

2807192.wem -> mus_BG_03_detect.ogg
instead of
2807192.wem -> 2807192.ogg

This seems to share the same structure and format as Star Wars: TOR, yet all the work done for the file names of TOR is exclusive to TOR and I really have no idea where to begin.

Would I have to open each .wem file to obtain the cue name of the file and create a .txt file and do the same as everyone is doing for the TOR work?
Or is there a QuickBMS script to do all this?

Any help would be appreciated.
