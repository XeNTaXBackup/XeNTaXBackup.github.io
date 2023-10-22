## Post #1
- Username: binarybailey
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 02, 2016 11:35 am
- Post datetime: 2018-06-11T21:43:21+00:00
- Post Title: MechAssault [XBOX] .d1bank - some progress

Hello All,

Hoping one of you guys with superior tech skills can see if you can resolve this mystery! Have been trying to extract the sound effects from the XBOX game MechAssault however have got so far and don't know where to go next 

The files are stored as .d1bank files, which I haven't been able to find any information on from anyone else.  Someone else has uploaded the pertinent files to the internet as SFX.d1Bank and SFX_English.d1Bank .

I opened them up in watto game extractor which did managed to extract files but with no file extension and just as file.  I tried renaming them to .wav but alas no avail  Someone in this post - [viewtopic.php?f=10&t=6037&start=0](http://forum.xentax.com/viewtopic.php?f=10&t=6037&start=0) says it is raw xbox adpcm data at 48khz stereo.

I found this information online - [http://www.watto.org/specs.html?specs=Archive_D1BANK](http://www.watto.org/specs.html?specs=Archive_D1BANK) and it says:

4 - Unknown
4 - null
4 - Number Of Files
4 - Directory Length (ie numFiles*48)
4 - First File Offset
4 - Archive Header Length (32)
4 - Padding Multiple (2048)
4 - null

// for each file (48-bytes per entry)
  4 - Hash?
  4 - File Offset
  4 - Unknown (1)
  4 - Hash?
  4 - File Length
  8 - null
  2 - Stereo/Mono? (1)
  2 - Unknown (6)
  4 - Sound Quality? (48000)
  4 - Unknown (576000)
  2 - Unknown (12)
  4 - Bit Rate? (16)
  2 - Unknown

0-2047 - null Padding to a multiple of 2048 bytes

// for each file
  X - File Data
  0-2047 - null Padding to a multiple of 2048 bytes

No idea what any of this means, anyone able to shed any light on this?

Cheers,

BB
