## Post #1
- Username: biko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 29, 2013 2:12 pm
- Post datetime: 2013-09-29T13:13:41+00:00
- Post Title: Still Life 2 *.PFF Cutscenes

Hello there.

I'm having a little problem figuring out the cutscenes in Still Life 2 (demo is available [here](http://www.fileplanet.com/198863/190000/fileinfo/Still-Life-2-Demo)).
I was able to extract the files from the *.DAT archives thanks to [this post](http://forum.xentax.com/viewtopic.php?f=10&t=3414), however their format puzzles me.

All the file snippets below are taken from SPLASH_MICROIDS.PFF that is contained in Sl2cine.dat (freely available in the demo).
All values below are little endian.

Here's what I managed to learn so far:

File Structure

The files have the .PFF extension, yet they are neither PFF0 nor PFF3 archives.
Each file has the following header:
Code: Select all00000000 50 46 46 30 2E 30 00 56 49 44 45 4F 5F 44 44 53 00 53 4F 55 4E 44 5F 56 4F 52 42 49 53 00 45 4E 00 PFF0.0.VIDEO_DDS.SOUND_VORBIS.EN.
00000021 45 4E 44 48 45 41 44 45 52 00                                                                      ENDHEADER.
 Note the strings "VIDEO_DDS" and "SOUND_VORBIS".
The header can be represented as the following C structure:
Code: Select allstruct PFF_HEADER {
    char szFormat[7];
    char szVideo[10];
    char szAudio[13];
    char szLang[3];
    char szEndHeader[10];
};
Following the header is a sequence of frames (explained below).
The file ends with the following string:
Code: Select all001386CF 45 4E 44 46 49 4C 45 00                                                                            ENDFILE.
Frames
A standard frame has the following structure:

Frame header:
Code: Select allstruct FRAME_HEADER {
    char  szFrame[6];
    DWORD dwSize;
}; Note that the dwSize field specifies the length of the data after the field.
For example:
Code: Select all0000002B 46 52 41 4D 45 00 8A 5D 00 00                                                                      FRAME..]..
A sequence of 8-bytes. In the first frame of a cutscene these are all null bytes, however in consequent frames their values are different.
Therefore, it is unclear what their purpose is.
A VIDEO section (explained below).
A SOUND section (explained below).
A string signalling the end of a frame:
Code: Select all00005DB6 45 4E 44 46 52 41 4D 45 00                                                                         ENDFRAME.
Special Frames
Apart from the standard frame defined above, there also exist several other kinds of frames:

The first frame - Contains a special kind of the VIDEO section (see below).
Video-only frame - Does not contain a SOUND section.
Empty frame - Contains neither VIDEO nor SOUND sections. This is the last frame in the file.
VIDEO Section
A standard VIDEO section is defined as follows:

Header:
Code: Select allstruct VIDEO_HEADER {
    char  szVideo[6];
    DWORD dwSize;
}; Note that the dwSize field specifies the length of the data after the field.
For example: Code: Select all00005DD1 56 49 44 45 4F 00 FD 00 00 00                                                                      VIDEO.....
A sequence of bytes with the section's data. For a standard frame this should contain pixel information.

The first frame in a file has the following additional fields after the header:

A DWORD holding the value 0x80A90300 (decimal 240,000) in all files (!). See below for possible meaning.
A DDS_HEADER structure:
Code: Select all0000004B 44 44 53 20 7C 00 00 00 07 10 00 00 58 02 00 00 20 03 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 DDS |.......X... ................
0000006C 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 .................................
0000008D 00 00 00 00 00 00 00 00 00 00 20 00 00 00 04 00 00 00 44 58 54 31 00 00 00 00 00 00 00 00 00 00 00 .......... .......DXT1...........
000000AE 00 00 00 00 00 00 00 00 00 00 10 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00             .............................
 Given this, I reckon it is safe to assume that the video is represented by DDS textures.
Of particular interest are the dwHeight, dwWidth, dwPitchOrLinearSize and dwFourCC (inside the DDS_PIXELFORMAT sub-structure) fields.
The first two tell us that the video is 800x600 pixels, and the fourth one tells us that the textures are compressed using DXT1. However, the third field (dwPitchOrLinearSize) is empty.
According to the formula here, the texture size should be 240,000 bytes. This is precisely the value of the DWORD above, so it might actually hold this value instead of the DDS_HEADER.
SOUND Section

Header:
Code: Select allstruct SOUND_HEADER {
    char  szSound[6];
    DWORD dwSize;
};
 Note that the dwSize field specifies the length of the data after the field.
For example: Code: Select all00003DCC 53 4F 55 4E 44 00 E0 1F 00 00                                                                      SOUND.....
One null byte (probably padding).
A sequence of bytes with the section's data. For a standard frame this contains an Ogg stream with Vorbis audio.
(Deduced from the presence of "OggS" and "vorbis" strings.)
What Remains
What's the problem then, you might ask? Just extract the textures and be done with it.
Well, it turns out that the first frame doesn't have enough data (240,000 bytes), and neither do the rest of the frames.
It seems there is some compression involved, which is to be expected from a video stream, but I do not know what kind.

Also, there is the problem of framerate. I haven't found any indication what the framerate of the video might be in any of the game's files.
Maybe it is hardcoded somewhere in the executable, but I do not know where to look.

Finally, there are these 8 bytes following each frame's header.
They might represent a double, two DWORDs, a bitfield, or maybe they are just plain garbage.
It seems strange to put random bytes into a file (easier to use null bytes), so they must have some kind of meaning.

Please, if anyone has had experience with this kind of thing - do share.
Any form of help will be much appreciated.

P.S. [Here](https://gist.github.com/bikerm16/6752403) is a Hex Workshop structure library with a handy function to parse a .PFF file.
Be aware, though, that on big files it will consume a HUGE amount of memory (sorry  ).
