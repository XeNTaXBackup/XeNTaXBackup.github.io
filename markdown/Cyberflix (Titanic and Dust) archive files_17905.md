## Post #1
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-04-01T00:58:55+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

I was wondering, given their cult classic status and fanbase, some of you might be willing to help me extract and understand the files of the games Titanic: Adventure Out of Time and Dust: A Tale of the Wired West.

Here are the files from the Titanic demo if you want to study them: [https://drive.google.com/open?id=1a1FEG ... 08QOvKTJmA](https://drive.google.com/open?id=1a1FEG442cVNe8madItRr6K08QOvKTJmA)
## Post #2
- Username: Samuraid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 1:04 pm
- Post datetime: 2018-05-16T05:17:06+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

This is definitely not an easy request.

From some preliminary reverse engineering of Timelapse and Titanic I did a few years back, I figured out some about how the file formats worked.  But I only looked at the binary files themselves; I never really got the motivation or time to open it up in the disassembler and actually reverse engineer things properly.

In short, all the file types (MOV, TRK, STG) seem to have the same general container format.  I'm not even sure if there's enough metadata in each file to completely decode what is contained within.  In other words, I suspect you'd have to read the main metadata files for the game before you'd know how to completely decode each resource file.  This is only a guess, however.

If anyone wants to pick up the torch and give reverse engineering a shot, I'd be happy to post what I've figured out so far.  It will take a little time to collect and format into a coherent description, however, so I don't want to do the work unless there is interest.  If anyone is interested, let me know.
## Post #3
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-05-21T02:16:54+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

> Reply from Samuraid
>
> This is definitely not an easy request.

From some preliminary reverse engineering of Timelapse and Titanic I did a few years back, I figured out some about how the file formats worked.  But I only looked at the binary files themselves; I never really got the motivation or time to open it up in the disassembler and actually reverse engineer things properly.

In short, all the file types (MOV, TRK, STG) seem to have the same general container format.  I'm not even sure if there's enough metadata in each file to completely decode what is contained within.  In other words, I suspect you'd have to read the main metadata files for the game before you'd know how to completely decode each resource file.  This is only a guess, however.

If anyone wants to pick up the torch and give reverse engineering a shot, I'd be happy to post what I've figured out so far.  It will take a little time to collect and format into a coherent description, however, so I don't want to do the work unless there is interest.  If anyone is interested, let me know.

I am interested.
## Post #4
- Username: Samuraid
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 1:04 pm
- Post datetime: 2018-05-26T03:39:32+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

Thanks for your patience; I've had a crazy busy week but finally found time to write things down...

This is only a partial spec based on what I've figured out so far.  It's certainly missing a lot, so if you figure anything else out, please post it here.
These observations are purely based on looking at the binary data in the files.  I haven't stepped through any assembly yet...

The format seem to be the same for both Timelapse and Titanic; I don't own Dust, so I'm not sure about that one.

All numbers are in little-endian byte order.

Container Format
As far as I've seen, the major DreamFactory data files (TRK, STG, MOV, PUP, SET) are all based around a similar container format.

Each container file is divided into blocks, and each block can contain a wide variety of data.

Let's look at the Titanic file BOMBBLOW.MOV (In the GOG version, it's in the LOCAL directory; In the CD version, it's on Disc 1 in the BOMB directory.)

Header
The first 1024 bytes of the container comprise some metadata about the file:

```
[4-7]        int32   Length of the container file in bytes
[8-19]       ????
[20-23]      int32   Number of blocks in the container.  In the example below, there are 164 blocks in the container.
[24-1023]    ????

```


Here's an excerpt of the file header from BOMBBLOW.MOV:

```
0000010: 0100 0000 00a4 0000 0000 0000 0000 0000
0000020: 504c 4150 504c 4150 0000 0000 0000 0000
0000030: 0000 0000 0000 0000 0000 0000 0000 0000

```


Additional notes about the header:
Bytes 32-39 often spell out "LPPALPPA", but I'm not sure what that means.

There is additional data from 512-1023, and it may be compressed with some simple variant of LZ compression???  I'm really not sure, but I can sometimes see strange fragments of text.

Block Offset Table
There's a "block offset table" that starts at byte 1024.  It's basically an array of int32 offsets, one for each block in the container.
The number of entries in the table corresponds to the number of blocks specified in the header.  In this example, there are 164 entries.

Here's an excerpt of the block offset table, starting at byte 1024:

```
0000410: 1f80 0000 1800 0001 9f40 0001 a3c0 0001
0000420: a300 0002 a780 0002 dd40 0002 e1c0 0002
0000430: 1dc0 0003 2240 0003 5fc0 0003 6440 0003
0000440: a080 0003 a500 0003 e200 0003 e680 0003
0000450: 2380 0004 2800 0004 6540 0004 69c0 0004

```


In the example, the first block offset is 2048, the second is 7552, the third is 7872, and so on.

Blocks
To read each block, seek to the offset given in the block offset table, and read until you reach the start of the next block offset (or the end of the file).

Most blocks should be at least 8 bytes long, but I've occasionally seen some that are only 4 bytes long (and don't have a byte length number).

Block format:

```
[4-7]        int32   Length of the block in bytes
[8-end]      block data

```

Formats of each type of block
I haven't yet figured out where the type of each block is stored, but I have been able to figure out some parts of some of the blocks just by observation and patterns.

For video files, there tend to be one or two metadata blocks near the beginning.

Then a little later (if the movie has audio), there's 1 or more blocks of audio data, probably to fill the audio buffer when the movie starts playing.

Then you'll see a list of alternating blocks.
The larger ones are video frames, and the smaller ones most likely contain pallete information (since these games use 8-bit color).

Here's a listing of the first 20 blocks in the BOMBBLOW.MOV file:

```
ID=1     Offset=7552     Size=270     ???
ID=2     Offset=7872     Size=92      ???
ID=3     Offset=8000     Size=4       ???
ID=4     Offset=8064     Size=63574   Audio block
ID=5     Offset=71680    Size=34603   Audio block
ID=6     Offset=106304   Size=1094    Pallete?
ID=7     Offset=107456   Size=65312   Frame
ID=8     Offset=172800   Size=1094    Pallete?
ID=9     Offset=173952   Size=13728   Frame
ID=10    Offset=187712   Size=1094    Pallete?
ID=11    Offset=188864   Size=15332   Frame
ID=12    Offset=204224   Size=1094    Pallete?
ID=13    Offset=205376   Size=15725   Frame
ID=14    Offset=221120   Size=1094    Pallete?
ID=15    Offset=222272   Size=15381   Frame
ID=16    Offset=237696   Size=1094    Pallete?
ID=17    Offset=238848   Size=15595   Frame
ID=18    Offset=254464   Size=1094    Pallete?
ID=19    Offset=255616   Size=15576   Frame

```

Metadata blocks
I really don't know much about the structure of these yet; however, they do contain an index of filenames or asset names.
So I'm guessing they also contain information about each block type.  I just haven't figured out how to decode them yet.

In the BOMBBLOW.MOV example, at file offset 4254, you'll see an 8-bit number indicating the length of the text string (0x6) followed by 6 characters of text "Frame1".

If you can figure out the structure of this metadata block, that would be wonderful!

Audio blocks
I've figured out the following about audio blocks:

```
[4-7]        int32   Length of the block in bytes
[8-11]       int32   Special FourCC, typically always 65536, indicating that this is an audio block.
[12-33]      ????
[34-35]      int16   Some flag, maybe to indicate stereo, or bit depth mode, or something??
[36-37]      int16   Audio sample rate, typically 22050 in the files I've looked at so far, which is a very normal audio sample rate.
[38-47]      ????
[48-51]      int32   Number of audio offset table entries

```


Byte 52 marks the start of an array of int32 values that appear to be offsets in the audio block.  The number of items in the table is the number stored in the block header at byte offset 48.
I'm not sure what they are for.  Maybe they are markers for when to display a frame as the audio plays???

After the offset table is the actual audio data.  The offset to the audio data appears to be: (number of audio offsets) * 4 + 56

The audio data itself, I am about 99% sure, is some form of ADPCM, in a 4:1 compression ratio (4-bit numbers that map to a delta lookup table, producing 16-bit audio).
I've tried decoding some of the data using common Microsoft ADPCM and IMA ADPCM algorithms, but it didn't produce anything normal sounding.  I might have messed up, though, so don't count those out without investigating further.
Finding out what delta encoding table Cyberflix uses might mean firing up the assembly debugger...

Pallete blocks
These most likely contain more than just pallete data, but I haven't figured out what yet.
They are always the same size within a given video file (>1024 bytes), but the size varies slightly between video files.
I would normally expect a full pallete table to be 768 bytes, so maybe these have alpha information as well, and maybe they have additional metadata used for decoding the frame.

Frame blocks
I don't know much about these except that the video codec itself is based on some form of vector quantization of 4x4 pixel blocks.

There's some block header info, though:

```
[4-7]        int32   Length of the block in bytes
[8-9]        int16   Video height, in pixels (ex: 384)
[10-11]      int16   Video width, in pixels (ex: 512)

```

Conclusion
That's what I have so far.  Let me know if there's anything else that would be helpful.
Hope this helps!
## Post #5
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-05-26T20:58:42+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

> Reply from Samuraid
>
> Thanks for your patience; I've had a crazy busy week but finally found time to write things down...

This is only a partial spec based on what I've figured out so far.  It's certainly missing a lot, so if you figure anything else out, please post it here.
These observations are purely based on looking at the binary data in the files.  I haven't stepped through any assembly yet...

The format seem to be the same for both Timelapse and Titanic; I don't own Dust, so I'm not sure about that one.

All numbers are in little-endian byte order.

Container Format
As far as I've seen, the major DreamFactory data files (TRK, STG, MOV, PUP, SET) are all based around a similar container format.

Each container file is divided into blocks, and each block can contain a wide variety of data.

Let's look at the Titanic file BOMBBLOW.MOV (In the GOG version, it's in the LOCAL directory; In the CD version, it's on Disc 1 in the BOMB directory.)

Header
The first 1024 bytes of the container comprise some metadata about the file:
Code: Select all[0-3]        int32   FourCC code, should be 65536 (0x00 0x00 0x00 0x01)
[4-7]        int32   Length of the container file in bytes
[8-19]       ????
[20-23]      int32   Number of blocks in the container.  In the example below, there are 164 blocks in the container.
[24-1023]    ????


Here's an excerpt of the file header from BOMBBLOW.MOV:
Code: Select all0000000: 0000 0001 1d80 0017 0000 0000 0000 0000
0000010: 0100 0000 00a4 0000 0000 0000 0000 0000
0000020: 504c 4150 504c 4150 0000 0000 0000 0000
0000030: 0000 0000 0000 0000 0000 0000 0000 0000


Additional notes about the header:
Bytes 32-39 often spell out "LPPALPPA", but I'm not sure what that means.

There is additional data from 512-1023, and it may be compressed with some simple variant of LZ compression???  I'm really not sure, but I can sometimes see strange fragments of text.

Block Offset Table
There's a "block offset table" that starts at byte 1024.  It's basically an array of int32 offsets, one for each block in the container.
The number of entries in the table corresponds to the number of blocks specified in the header.  In this example, there are 164 entries.

Here's an excerpt of the block offset table, starting at byte 1024:
Code: Select all0000400: 0800 0000 1d80 0000 1ec0 0000 1f40 0000
0000410: 1f80 0000 1800 0001 9f40 0001 a3c0 0001
0000420: a300 0002 a780 0002 dd40 0002 e1c0 0002
0000430: 1dc0 0003 2240 0003 5fc0 0003 6440 0003
0000440: a080 0003 a500 0003 e200 0003 e680 0003
0000450: 2380 0004 2800 0004 6540 0004 69c0 0004


In the example, the first block offset is 2048, the second is 7552, the third is 7872, and so on.

Blocks
To read each block, seek to the offset given in the block offset table, and read until you reach the start of the next block offset (or the end of the file).

Most blocks should be at least 8 bytes long, but I've occasionally seen some that are only 4 bytes long (and don't have a byte length number).

Block format:
Code: Select all[0-3]        int32   Block ID
[4-7]        int32   Length of the block in bytes
[8-end]      block data

Formats of each type of block
I haven't yet figured out where the type of each block is stored, but I have been able to figure out some parts of some of the blocks just by observation and patterns.

For video files, there tend to be one or two metadata blocks near the beginning.

Then a little later (if the movie has audio), there's 1 or more blocks of audio data, probably to fill the audio buffer when the movie starts playing.

Then you'll see a list of alternating blocks.
The larger ones are video frames, and the smaller ones most likely contain pallete information (since these games use 8-bit color).

Here's a listing of the first 20 blocks in the BOMBBLOW.MOV file:
Code: Select allID=0     Offset=2048     Size=5490    Metadata block
ID=1     Offset=7552     Size=270     ???
ID=2     Offset=7872     Size=92      ???
ID=3     Offset=8000     Size=4       ???
ID=4     Offset=8064     Size=63574   Audio block
ID=5     Offset=71680    Size=34603   Audio block
ID=6     Offset=106304   Size=1094    Pallete?
ID=7     Offset=107456   Size=65312   Frame
ID=8     Offset=172800   Size=1094    Pallete?
ID=9     Offset=173952   Size=13728   Frame
ID=10    Offset=187712   Size=1094    Pallete?
ID=11    Offset=188864   Size=15332   Frame
ID=12    Offset=204224   Size=1094    Pallete?
ID=13    Offset=205376   Size=15725   Frame
ID=14    Offset=221120   Size=1094    Pallete?
ID=15    Offset=222272   Size=15381   Frame
ID=16    Offset=237696   Size=1094    Pallete?
ID=17    Offset=238848   Size=15595   Frame
ID=18    Offset=254464   Size=1094    Pallete?
ID=19    Offset=255616   Size=15576   Frame

Metadata blocks
I really don't know much about the structure of these yet; however, they do contain an index of filenames or asset names.
So I'm guessing they also contain information about each block type.  I just haven't figured out how to decode them yet.

In the BOMBBLOW.MOV example, at file offset 4254, you'll see an 8-bit number indicating the length of the text string (0x6) followed by 6 characters of text "Frame1".

If you can figure out the structure of this metadata block, that would be wonderful!

Audio blocks
I've figured out the following about audio blocks:
Code: Select all[0-3]        int32   Block ID
[4-7]        int32   Length of the block in bytes
[8-11]       int32   Special FourCC, typically always 65536, indicating that this is an audio block.
[12-33]      ????
[34-35]      int16   Some flag, maybe to indicate stereo, or bit depth mode, or something??
[36-37]      int16   Audio sample rate, typically 22050 in the files I've looked at so far, which is a very normal audio sample rate.
[38-47]      ????
[48-51]      int32   Number of audio offset table entries


Byte 52 marks the start of an array of int32 values that appear to be offsets in the audio block.  The number of items in the table is the number stored in the block header at byte offset 48.
I'm not sure what they are for.  Maybe they are markers for when to display a frame as the audio plays???

After the offset table is the actual audio data.  The offset to the audio data appears to be: (number of audio offsets) * 4 + 56

The audio data itself, I am about 99% sure, is some form of ADPCM, in a 4:1 compression ratio (4-bit numbers that map to a delta lookup table, producing 16-bit audio).
I've tried decoding some of the data using common Microsoft ADPCM and IMA ADPCM algorithms, but it didn't produce anything normal sounding.  I might have messed up, though, so don't count those out without investigating further.
Finding out what delta encoding table Cyberflix uses might mean firing up the assembly debugger...

Pallete blocks
These most likely contain more than just pallete data, but I haven't figured out what yet.
They are always the same size within a given video file (>1024 bytes), but the size varies slightly between video files.
I would normally expect a full pallete table to be 768 bytes, so maybe these have alpha information as well, and maybe they have additional metadata used for decoding the frame.

Frame blocks
I don't know much about these except that the video codec itself is based on some form of vector quantization of 4x4 pixel blocks.

There's some block header info, though:
Code: Select all[0-3]        int32   Block ID
[4-7]        int32   Length of the block in bytes
[8-9]        int16   Video height, in pixels (ex: 384)
[10-11]      int16   Video width, in pixels (ex: 512)

Conclusion
That's what I have so far.  Let me know if there's anything else that would be helpful.
Hope this helps!

Yes. A QuickBMS script would be nice.
## Post #6
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2018-09-25T01:59:18+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

In the meantime, Aluigi has made an impromptu script available here: [https://zenhax.com/viewtopic.php?f=9&t=8515](https://zenhax.com/viewtopic.php?f=9&t=8515)

But don’t expect exact results though. If someone were to modify it with the research seen above, maybe the results will have a better delivery.
## Post #7
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2021-08-11T17:23:58+00:00
- Post Title: Cyberflix (Titanic and Dust) archive files

At last, someone else has managed to succeed where others fail. Check this tool out: [https://github.com/M3tox/DFET/releases/tag/0.71](https://github.com/M3tox/DFET/releases/tag/0.71)
