## Post #1
- Username: SiPlus
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 05, 2011 6:30 pm
- Post datetime: 2011-12-06T08:14:29+00:00
- Post Title: Delta Force: Land Warrior SBF - clicks and jumpy volume

I wrote a simple program to play sound files from DFLW [SBF](http://wiki.xentax.com/index.php?title=SBF0), but there are clicks repeating at a constant amount of time, and the volume is very jumpy. Does anybody know how to fix that?

The program is in attachment. Requires .NET Framework 2 and DirectX9. Executable is in Delta Force Music Extractor\Delta Force Music Extractor\bin\Release. Currently supports only playback, no saving to WAV file (the save button only exports files selected in right column to program directory), to play select a file in the left column and press Play.
[sbfext-061211-prealpha-xentaxforums-2.zip](https://xentaxbackup.github.io/file/4892_sbfext-061211-prealpha-xentaxforums-2.zip)
## Post #2
- Username: Controller
- Rank: n00b
- Number of posts: 11
- Joined date: Mon May 25, 2009 8:44 am
- Post datetime: 2019-06-04T17:26:48+00:00
- Post Title: Delta Force: Land Warrior SBF - clicks and jumpy volume

Struggling at those files as well...

Assuming the Delta Force 1 data format is identically:
For the clicks, you must parse the data a bit, see the part "// for each segment" here: [http://wiki.xentax.com/index.php/SBF0](http://wiki.xentax.com/index.php/SBF0)
These are 8 bytes info + 0x1000 bytes wavedata. Skip the 8 bytes info and use the waveform only.

Also, the first 4 bytes of info contains some length information. If you ignore this the sound is fine. However, it appears there are pops/clicks if you merge the audio data together afterwards.
