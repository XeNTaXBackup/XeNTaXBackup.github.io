## Post #1
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2012-06-11T13:29:50+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

Okay, here is the deal.
I've extracted the music (.VMU files) from RF_PS2.VPP.
Files can be converted by MFAudio.
BUT:
Here is one of these files. Converts without hitch.
[https://dl.dropbox.com/u/48495960/faction.vmu](https://dl.dropbox.com/u/48495960/faction.vmu)
The second file. Gives only 1-2 seconds of stutter.
[https://dl.dropbox.com/u/48495960/faction_ext.vmu](https://dl.dropbox.com/u/48495960/faction_ext.vmu)
The third file. MFAudio gets stucked, and giving the large unplayable file (some of them can be played in MFAudio, though).
[https://dl.dropbox.com/u/48495960/music1.vmu](https://dl.dropbox.com/u/48495960/music1.vmu)

Any ideas how to move around these issues? Any other program like MFAudio?
## Post #2
- Username: MiLØ
- Rank: veteran
- Number of posts: 114
- Joined date: Sun Dec 11, 2011 3:00 pm
- Post datetime: 2012-06-12T04:24:41+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

Cube Media Player maybe?
## Post #3
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-06-15T15:32:45+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

1) Trim the first 12 bytes of each VMU file.
2) Rename the output from step 1 to have ".mib" file extension.
3) Use vgmstream for playback.
## Post #4
- Username: Herf
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Mar 02, 2012 2:47 pm
- Post datetime: 2012-06-15T17:06:28+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

Thanks for your help, but result isn't so satisfying.
vgstream plays it with tons of stutter, and length is around 3 times longer.
## Post #5
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2012-06-15T20:50:08+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

Ah, only looked at it quickly.  One thing though, the length probably changed compared to MFAudio because one (or more, cannot remember) of the files had loop flags.  Also, I wouldn't use MFAudio as the basis for accuracy with regards to music.

Anyhow, you'll need to make a GENH file out of it or use Alpha23's SS2 header adder script when you figure out the frequency and interleave.  It's Sony ADPCM format by the way.
## Post #6
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-06-19T14:54:10+00:00
- Post Title: Red Faction/Summoner PS2 (.VMU)

Tip: Only resort to MFAudio if you have no idea whatsoever! The player isn't developed any further since several years.

For these files:
1. use my SS2 header adder with OFFSET 0xc, CH 2 and INTERLEAVE 0x4000: [viewtopic.php?f=13&p=44717#p44717](http://forum.xentax.com/viewtopic.php?f=13&p=44717#p44717) 
2. as they have an incomplete last block, re-interleave them to 0x10 bytes with [viewtopic.php?f=13&p=46478#p46478](http://forum.xentax.com/viewtopic.php?f=13&p=46478#p46478) to allow correct playback
3. play the ss2 files with Winamp and the vgmstream plugin or MFaudio
