## Post #1
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-01-27T01:17:16+00:00
- Post Title: Amplitude Tracks (decrypting files)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: JaoSming
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jan 20, 2011 3:33 am
- Post datetime: 2011-01-28T05:10:21+00:00
- Post Title: Amplitude Tracks (decrypting files)

if you or someone gets this to work, let me know.  There are a bunch of mixes in that game I would love to have direct rips of.
## Post #3
- Username: Friedslick6
- Rank: advanced
- Number of posts: 61
- Joined date: Mon Sep 13, 2010 6:11 am
- Post datetime: 2011-01-28T05:14:38+00:00
- Post Title: Amplitude Tracks (decrypting files)

Perhaps you can let yourself know by subscribing to this topic...
## Post #4
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-01-28T19:29:59+00:00
- Post Title: Amplitude Tracks (decrypting files)

I never played that game... would it be possible to create a song, for example with only drums. Then I could record this with a device, then create a song with guitar only? Someone who can confirm this?
## Post #5
- Username: Tatsh
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jan 25, 2011 10:50 am
- Post datetime: 2011-01-29T00:30:46+00:00
- Post Title: Amplitude Tracks (decrypting files)

I decrypted these files a long time ago but I really do not remember the tool (this was a very long time ago). But I know I did not get the separate tracks. I got the songs as a whole, I just wanted them to listen to as no OST ever came out. I have them in 48 KHz MP3 after the conversion to WAV.

The songs (full tracks, no splitting of instruments) are in those files as a well-documented PS2 file format.
## Post #6
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-01-29T01:06:52+00:00
- Post Title: Amplitude Tracks (decrypting files)

> Reply from Tatsh
>
> I decrypted these files a long time ago but I really do not remember the tool (this was a very long time ago). But I know I did not get the separate tracks. I got the songs as a whole, I just wanted them to listen to as no OST ever came out. I have them in 48 KHz MP3 after the conversion to WAV.

The songs (full tracks, no splitting of instruments) are in those files as a well-documented PS2 file format.

If I get you right: you tried it too (I think with the programm called Jaeder Naub) and you also received only .wav files? I mean the seperate audio must be in the .str files, because there is no other folder which could contain them.
The songs must be in .ogg format and after Amplitude, people managed to hack other Harmonix games like Rock Band 1 and 2 which are much more safer. There must be a possibility.
## Post #7
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2011-01-29T12:20:21+00:00
- Post Title: Amplitude Tracks (decrypting files)

There is no ogg vorbis in example file from Amplitude, would be tad heavy for ps2 to handle anyways. Jaedernaub seems to give just 48khz mono and output size is half of str curiously, maybe missing the other channel or something. anyway doesn't have more than the single track in raw listening it seems.
## Post #8
- Username: kain34
- Rank: n00b
- Number of posts: 15
- Joined date: Thu Jan 27, 2011 9:07 am
- Post datetime: 2011-01-29T12:36:59+00:00
- Post Title: Amplitude Tracks (decrypting files)

> Reply from Apollo
>
> There is no ogg vorbis in example file from Amplitude, would be tad heavy for ps2 to handle anyways. Jaedernaub seems to give just 48khz mono and output size is half of str curiously, maybe missing the other channel or something. anyway doesn't have more than the single track in raw listening it seems.

Ok another format... it could be everything but I don't know how to open .str files. Hexeditor is nonsense and there is no other programm atm.
## Post #9
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2016-06-19T19:06:49+00:00
- Post Title: Amplitude Tracks (decrypting files)

The str files are 512-byte interleaved PCM, 16-bits @ 48000 Hz

Here's a bit of C code to turn that into regular interleaved stereo PCM.

```
#include <stdlib.h>
#include <string.h>

int main(int argc, char** argv)
{
  if(argc == 1) {
    printf("Usage: %s <path_to_file.str>\n", argv[0]);
    return -1;
  }
  FILE *fp = fopen(argv[1], "rb");
  int len = strlen(argv[1]);
  char * out_name = (char*)calloc(len + 5, 1);
  memcpy(out_name, argv[1], len);
  strncat(out_name, ".raw", 4);
  
  FILE *fo = fopen(out_name, "wb");
  free(out_name);
  
  if(!fp || !fo) {
    puts("Error opening input/output files");
    return -1;
  }
  
  const int INTERLEAVE = 512;
  int ctr = 0;
  char buffer[INTERLEAVE * 2];
  const int width = 2;
  while(!feof(fp)) {
    if(ctr < INTERLEAVE) {
      fread(buffer + ((ctr / width) << 2), width, 1, fp);
      ctr += width;
    }
    else if(ctr < (INTERLEAVE * 2)) {
      fread(buffer + (((ctr - INTERLEAVE) / width) << 2) + width, width, 1, fp);
      ctr += width;
    }
    else {
      fwrite(buffer, (INTERLEAVE * 2), 1, fo);
      ctr = 0;
      memset(buffer, 0, (INTERLEAVE * 2));
    }
  }
  fclose(fp);
  fclose(fo);
  return 0;
}

```


Unfortunately there seems to be something else going on in there, as there is a lot of high-frequency content in the resulting file, as evidenced by this pretty picture from Audacity:


I would be interested to see if anyone else has some knowledge of the format.

edit: Fixed the code, it now decodes correctly.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-06-23T12:28:21+00:00
- Post Title: Amplitude Tracks (decrypting files)

I'd guess that you have to interleave 2 bytes at a time instead of 4 bytes as you're doing here, the interleave blocks being 512 bytes of left channel, then 512 bytes of right channel.
## Post #11
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2016-06-23T19:09:30+00:00
- Post Title: Amplitude Tracks (decrypting files)

Of course! I must have been thinking that the audio was 32-bit while I wrote that code. Seems fine now, thanks for the help! 

So every .str file in the game is the stereo mix of a song. The separate instruments are sliced up and put into sound banks which are sampled while you play. It seems to be an in-house format:

.bnk - the soundbank descriptor, contains the names of all the samples, their positions, as well as original file names (like "R:\FREQ2\FreQ2_Game Levels\Blink 182\Wav Slices\bass_sect 01&7&15 to 19\bass_sect 01 001.wav\") Apparently Amplitude's codename was Frequency 2.

It's made up of several chunks:

```
  char    chunk_id[4];
  uint32  chunk_size;
  byte    chunk_data[chunk_size];
} soundbank_chunk;

```

Chunk IDs:

SAMP - sample definitions
SANM - sample names
SAFN - sample original filenames
BANK - banks?
BKNM - bank names
INST - instrument definitions
INNM - instrument names
SDES - ??
SDNM - names for the previous section
.nse - the sample audio, unknown format. Data seems to be grouped into 16-byte fields and the first 2 bytes of every field don't change very much:

```
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
44 00 F0 10 FE F2 00 FF E0 F0 F1 12 D0 CD FD 30
24 00 35 13 B0 DB 2D 32 F2 0F F1 12 12 01 10 F2
24 00 CD 0D 55 C2 DD 01 21 13 D0 FE 00 DF ED 01
24 00 ED 1D 30 22 01 BB EA 52 35 D0 DE 1F 11 12
24 00 FF FF 2F 31 01 EF EE 52 24 21 20 33 30 12
25 00 01 E0 DC 41 76 16 BC 21 44 11 57 15 C1 AB
44 00 51 45 11 DE 30 22 F3 11 52 45 F1 0F 2F 32
44 00 43 04 FF FC 42 35 24 12 2F 34 03 12 23 12
24 00 0F 30 66 23 00 E0 F0 E1 FE F0 12 31 43 22
25 00 25 01 2E 42 33 10 20 21 21 33 13 13 23 24
24 00 10 21 13 10 31 44 33 E2 20 C2 20 32 22 02

```


If I import the .nse files into audacity as 8-bit, mono PCM at 22050 Hz, I can make out some musical audio and glitched vocals above the noise. Perhaps it's some sort of ADPCM, or simple compression algorithm? It's very close to PCM...

The histogram of byte values in the file looks like this:

Does anyone more experienced with audio formats recognize such a pattern?
## Post #12
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2016-06-24T02:15:04+00:00
- Post Title: Amplitude Tracks (decrypting files)

Looks like standard Playstation ADPCM, decodable with [FastElbja's ADPCM player](http://www.freewebs.com/snakemeat/tools/ADPCM_Player_v1.44h.zip) or similar.
## Post #13
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-06-24T02:42:03+00:00
- Post Title: Amplitude Tracks (decrypting files)

> Reply from hcs
>
> Looks like standard Playstation ADPCM
It actually is.
## Post #14
- Username: maxton
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Jun 13, 2011 12:29 am
- Post datetime: 2016-06-24T02:51:08+00:00
- Post Title: Amplitude Tracks (decrypting files)

Is there a specification for the format of Playstation ADPCM somewhere? I can't get that ADPCM Player to open the files - it thinks they are ~2^32 bytes long, which is definitely wrong.

edit - I added a header with GENH and some of the samples in the file are now clearly audible when I play them in vgmstream, I guess the interleave must be wrong.

edit 2 - it kind of works with a freqency of 24000 in mono, but I can't figure out the interleave for 2 channels. That's probably stored in the .bnk file
