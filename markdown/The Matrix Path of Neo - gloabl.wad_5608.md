## Post #1
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-22T16:12:29+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2010-12-24T05:25:25+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

Yes I second this request, as maybe this tool will also open the archives of THE GOLDEN COMPASS PC.
## Post #3
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2010-12-26T22:25:37+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

I've created a tool to extract the Sony ADPCM data from the *.WAD files for this game.  As above, I could not decipher the first 0x38000 bytes of the NSGLOB~1.WAD file.  However, I did figure out the small 0x40 byte header on each of the Sony ADPCM files.  Using this info, I made a tool to extract them.  It seems to work OK for all file except the last one in NSGLOB~1.WAD.  This header seems incorrect, since it spills over into a small footer.

I've attached both the tool and it's C# source.  I've also attached a .bat file to run the tool for all .WAD files on the disc (except NPGLOB~1.WAD and NSD_EN~1.WAD).  NPGLOB~1.WAD doesn't appear to have sound data, and NSD_EN~1.WAD uses a modified scheme.  Adding a GENH header to NSD_EN~1.WAD (@18000Hz, 1 channel, it appears to be a bunch of sfx).

Also, if you don't feel like running the tool, I attached a .bat file to extract all the files using a simple binary cutter, snakebite.exe.

The channel count for each file is at offset 4.
The frequency for each file is at offset 6.
2 channel files have a 0x6000 interleave.

If someone modifies the source to also unpack NSD_EN~1.WAD, please reply to this thread with the code.

EDIT: After a little listening, it almost sounds like the files in the IMS folder could be a blocked data format or some dynamic music engine.
[matrixext.7z](https://xentaxbackup.github.io/file/3721_matrixext.7z)
## Post #4
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-12-28T17:30:25+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

The extraction tool doesn't work properly with the NSGLOB~1.wad - it only extract 100 MB of 600 MB. I guess it's because of the four wad files that are inside that wad. all have exactly 4MB in between AND the file size of the file directly before it is wrong...
However I've split the file manually and cut out the wad files in between. Running the extractor at offset 0 gets all but the last files out of each split archive. Last one has to be extracted manually again (just search backwards for 16 bytes of zeros and you should see the beginning of the last file).
Here are the file sizes of the split archives (cut the first 0x38000): 0x63c8000, 0x6000000, 0x6000000, 0x6000000, 0x5228000. Each time there's that other wad in between with 0x400000 each. All in all I get 4643 files without the wads in between. Maybe that helps.
I'll now write a script that converts the *.bin files to playable vag and ss2 files.
## Post #5
- Username: snakemeat
- Rank: advanced
- Number of posts: 45
- Joined date: Wed Jan 28, 2009 12:00 am
- Post datetime: 2010-12-29T00:29:20+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

Nice work, I look forward to hearing the results.

Edit: Here's a snippet to cut the headerless WADs with according AlphaTwentyThrees tips

```
snakebite.exe "NSGLOB~1.WAD" "NSGLOB~1\NSGLOB~1_2.WAD" 0x06800000 0x0C7FFFFF
snakebite.exe "NSGLOB~1.WAD" "NSGLOB~1\NSGLOB~1_3.WAD" 0x0CC00000 0x12BFFFFF
snakebite.exe "NSGLOB~1.WAD" "NSGLOB~1\NSGLOB~1_4.WAD" 0x13000000 0x18FFFFFF
snakebite.exe "NSGLOB~1.WAD" "NSGLOB~1\NSGLOB~1_5.WAD" 0x19400000 0x1F3FFFFF
snakebite.exe "NSGLOB~1.WAD" "NSGLOB~1\NSGLOB~1_6.WAD" 0x1F800000 0x24A27FFF
```
## Post #6
- Username: Alex89
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 11, 2011 6:06 pm
- Post datetime: 2011-07-11T14:29:05+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

please, help me! I'm a lamer! how to play the resulting bin files?
## Post #7
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2012-12-16T02:46:12+00:00
- Post Title: The Matrix: Path of Neo - gloabl.wad

i have .bin result but how read them ?
