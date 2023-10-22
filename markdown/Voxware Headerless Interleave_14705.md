## Post #1
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-01T13:30:45+00:00
- Post Title: Voxware Headerless Interleave

Hello, is it possible to know a way to correctly convert the .RAW music files from Monsters vs. Aliens PC? The codec is IMA but doesn't seem to play correctly when I create a GENH header and play with vgmstream.
## Post #2
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T01:02:56+00:00
- Post Title: Voxware Headerless Interleave

It is interleaved at the nibble level, which isn't supported by GENH. Use [denibble](http://hcs64.com/files/denibble.zip) to split it into channels:

```
denibble input outL outR
```
I guessed this due to the file having an odd number of bytes. (Note it's possible that I have the channels reversed)

You can combine them, or you can just make a GENH for each channel, vgmstream will support playing both if they are named like outL.genh and outR.genh due to the dual-file stereo feature.

Edit:
fwiw it is IMA, you can just decode it with

```
sox --combine merge -t ima -r 44100 outL -t ima -r 44100 outR -e signed-integer -b 16 out.wav
```
## Post #3
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T09:25:12+00:00
- Post Title: Voxware Headerless Interleave

It works like a charm. Thank you.
## Post #4
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T09:47:27+00:00
- Post Title: Voxware Headerless Interleave

Is there a command line to make denibble creates folders for each outL and outR by each filename? Thank you.
## Post #5
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T14:30:48+00:00
- Post Title: Voxware Headerless Interleave

Try

```

```

I think that should give you 469_44100_4_001.sfc_vxt_L, 469_44100_4_001.sfc_vxt_R, etc
## Post #6
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T14:55:04+00:00
- Post Title: Voxware Headerless Interleave

Yes, it works perfectly. Now I don't think if it's possible, but is there a way to reassemble L and R for each file with a sox command please? Thank you.
## Post #7
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T15:34:08+00:00
- Post Title: Voxware Headerless Interleave

Think about how you would run it one at a time, and how you might edit the command to move from one file to another; this will lead you to create an equivalent FOR loop.

I think this will work but I haven't tested it (nor did I test the denibble step I showed earlier):

```
FOR %A IN (*.sfc_vxt) DO sox --combine merge -t ima -r 44100 %A_L -t ima -r 44100 %A_R -e signed-integer -b 16 %A.wav
```
## Post #8
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T15:36:26+00:00
- Post Title: Voxware Headerless Interleave

Curiously, I tried to copy and paste this into a notepad, save as .BAT and launch, but it won't work.
## Post #9
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T15:38:36+00:00
- Post Title: Voxware Headerless Interleave

My bad, just noticed I had to use %%a instead of %a when using batch method.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T16:03:36+00:00
- Post Title: Voxware Headerless Interleave

Yeah, with a .bat file you need to use %%A instead of %A for the substitutions.

```
FOR %%A IN (*.sfc_vxt) DO sox --combine merge -t ima -r 44100 %%A_L -t ima -r 44100 %%A_R -e signed-integer -b 16 %%A.wav
```
## Post #11
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T16:08:52+00:00
- Post Title: Voxware Headerless Interleave

Still having an error though, don't know why.
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-08-03T16:43:35+00:00
- Post Title: Voxware Headerless Interleave

Actually every % needs to be %%, I corrected the last post.
## Post #13
- Username: vgripHE303
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Aug 11, 2014 7:41 pm
- Post datetime: 2016-08-03T16:47:18+00:00
- Post Title: Voxware Headerless Interleave

Thank you so much!
