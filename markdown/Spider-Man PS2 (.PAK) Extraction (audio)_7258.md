## Post #1
- Username: FinalBlast
- Rank: advanced
- Number of posts: 52
- Joined date: Tue Dec 29, 2009 1:35 am
- Post datetime: 2011-08-29T19:02:02+00:00
- Post Title: Spider-Man PS2 (.PAK) Extraction (audio)

Begining of the file's hex.

```
0B 00 00 00 D6 03 00 00 33 03 00 00 97 01 00 00 00 00 00 00 30 00 00 00 00 18 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 EC CC AE 7B 00 00 00 00 90 12 00 00 FF FF 00 00 00 00 00 00 01 00 00 01 00 00 00 00 69 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 01 00 00 00 00 00 00 00 00 00 00 E3 E3 E3 E3 00 00 00 00 E3 E3 E3 E3 53 48 45 4E 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 19 00 00 00 00 00 70 01 00 43 49 54 59 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 19 00 70 01 00 00 40 13 00 53 48 45 4E 5F 45 4E 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
```

The file is "SOUNDS.PAK" is there a way to make a .bms script which can extract it's .wav's or whatever sound format they are in?
[http://img854.imageshack.us/img854/6180 ... sounds.jpg](http://img854.imageshack.us/img854/6180/somenamesshownhexsounds.jpg)
This picture I uploaded shows part of the hex where we see some names of files or folders, I have no idea, but maybe it would be useful?
## Post #2
- Username: distortedximage
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 29, 2011 8:30 am
- Post datetime: 2011-11-29T00:39:37+00:00
- Post Title: Spider-Man PS2 (.PAK) Extraction (audio)

I've managed to get the file to play almost right in MFaudio. If you import the file SOUNDS.PAK and set the offset to "33295820", (This is where the music starts) the interleave to "800" and the sample rate to 44100 It sounds ok but I just can't get the interleave quite right as theres still a small amount of crackling.

EDIT: Forget all that. If you use the FastElbJa ADPCM player it finds all the files. All the sounds and effects are in .mib format but the music has no file extension...... ? And the interleave is still messed up. Even though 0x800 is right it still crackles.
## Post #3
- Username: Infamous Star
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 01, 2016 8:01 am
- Post datetime: 2016-04-01T22:05:44+00:00
- Post Title: Spider-Man PS2 (.PAK) Extraction (audio)

I don't know this forum's policy on necroposting, but this is what I've found out about this format. Let me get this out of the way first:

> Reply from distortedximage
>
> set the offset to "33295820", (This is where the music starts) the interleave to "800" and the sample rate to 44100 It sounds ok but I just can't get the interleave quite right as theres still a small amount of crackling.
The offset should actually be 0x33296800. That'll fix the crackling. Now my analysis.

This information applies to SOUNDS.PAK and MOVIES.PAK. AMALGA.PAK and rmalga.pak seem to be in a different format (except for the 1st 24 bytes). They also seem to be the same file.

PAK archives store files in a directory-data format. They begin with:

```
0x0     24      0B 00 00 00 D6 03 00 00 33 03 00 00
                97 01 00 00 00 00 00 00 30 00 00 00
0x18    uint16  offset of 1st file
0x4C    uint8   number of files
0x258           directory
```


The directory consists of 40B entries, each one looking like this:

```
+0x0    31      file name
+0x1f   1       unknown (might indicate file type; 19 in SOUNDS, 1A in MOVIES)
+0x20   uint32  file offset (from start of 1st file)
+0x24   uint32  file length
```


The files in MOVIES.PAK start out with the signature 'ipum' and the rest, I assume, is compressed video. In SOUNDS.PAK, the files are archives themselves, each one storing a collection of related audio tracks. Because of their file signature, I call them 'wave blocks' or just 'blocks'. Blocks have a different format from PAKs, in which the directory is split up between track info, and names. Blocks can have one of two headers, but if you'll notice, everything needed to extract the audio is in the same place:

```
+0x0    8       file signature 'WAVEBK11'
+0x10   uint32  data offset (from start of block)
+0x14   uint32  data length (sans padding)
+0x18   uint32  block length
+0x1c   4       padding
+0x20   32      block name
+0x40   uint16  number of tracks
+0x44   32      unknown
+0x64   uint32  label offset
+0x68   156     unknown (padding?)
+0x104          track info
```


or

```
+0x0    8       file signature 'WAVEBK11'
+0x8    8       padding
+0x10   uint32  data offset (from start of block)
+0x14   4       padding
+0x18   uint32  data offset (again)
+0x1c   uint32  data length (w/ padding)
+0x20   32      block name
+0x40   uint32  number of tracks
+0x44   32      unknown
+0x64   uint32  label offset
+0x68   156     unknown (padding?)
+0x104          track info
```


In the info part of the directory, each track gets a 40B entry:

```
+0x0    4       unknown, starts with 0x04
+0x4    uint32  track length (in bytes obviously, not seconds)
+0x8    12      unknown
+0x14   4       FF FF FF FF (not sure why)
+0x18   uint32  track offset
+0x1c   uint32  sample rate
+0x20   8       unknown
```


The name part is a series of null-terminated strings. As best I can tell, there's always 1 more label than there are tracks, the 2nd label being a shorter version of the block's name. I don't know why. The tracks themselves are compressed ADPCM with an interleave of 0x800.

I've written a python script to extract sound and movies. For sound, it adds an SS2 header so you can play it with vgmstream. I have no idea how to play the movies, but the sound that goes with them is in the STREAMS_SCENE_EN wave block of SOUNDS.PAK (I assume EN stands for English, so it might be different if you have a different version of the game). You can find the script [here](https://github.com/InfamousStar/game-research/blob/master/spider-man-2/pak_extract.py) on GitHub.
