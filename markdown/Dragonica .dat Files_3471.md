## Post #1
- Username: Intervene
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 10, 2009 10:06 am
- Post datetime: 2009-05-10T12:26:13+00:00
- Post Title: Dragonica .dat Files

Fairly new MMO currently in closed beta testing in a number of countries. I'm interested in extracting general game resources (music/sounds, models, textures and other graphic files) from a collection of .dat files the game uses as data archives. Rather than using a single .dat file, there seems to be a .dat file used for each aspect of the game engine (one for UI data, one for character data, one for Map data etc). The game is produced by Barunson Interactive (couldn't find any other titles they have produced).

File segment from 1_Cha.dat (1024k): [http://files.filefront.com/1+Chadatrar/ ... einfo.html](http://files.filefront.com/1+Chadatrar/;13735723;/fileinfo.html)

Any help would be greatly appreciated. Let me know if there is any info I've left out.

Cheers.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-05-11T01:32:28+00:00
- Post Title: Dragonica .dat Files

Encrypted index, followed by zlib compressed file data.

```
byte[4] unk2;
int encryptionDataSize; // 0x3F
byte[encryptionDataSize] encryptionData;
byte[4] unk3; // could be file count
int indexTableSize;
byte[indexTableSize] encryptedIndexTable;
(followed by zlib compressed blobs)
```


I havn't worked out the encryption yet though.
## Post #3
- Username: Intervene
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 10, 2009 10:06 am
- Post datetime: 2009-05-11T12:48:05+00:00
- Post Title: Dragonica .dat Files

Thanks for the fast response. 

There are a few questions I'd like to ask regarding how you went about extracting the information that you did. I have next to no knowledge or programming and very limited knowledge of hex editing, so the concept of reverse engineering the encryption on a file is well and truly out of my league. From what I understand (please correct me if I have this wrong) the game client decrypts each data file before using the zlib compression library to decompress the data files so they can be used by the game? Assuming the encryption can be cracked, what is needed to emulate the the way the game handles extracting data from the files? 

Regarding the information you presented in the code box, is there a particular program you used that gives that information, or is that derived from using a hex editor?

Thanks again.
## Post #4
- Username: Intervene
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-05-12T00:38:51+00:00
- Post Title: Dragonica .dat Files

Here is an exe scan of this game.

```
- 14811136 bytes allocated
- load signatures
- open file C:\signsrch\signsrch.sig
- 1294834 bytes allocated for the signatures
- 1869 signatures in the database
- WARNING:
  the file loaded in memory is very big so the scanning could take many time
- start signatures scanning:

  offset   num  description [bits.endian.size]
  --------------------------------------------
  00cdb998 31   Adler CRC32 (0x191b3141) [32.le.1024]
  00cdc998 32   Adler CRC32 (0x191b3141) [32.be.1024]
  00cdbd98 33   Adler CRC32 (0x01c26a37) [32.le.1024]
  00cdcd98 34   Adler CRC32 (0x01c26a37) [32.be.1024]
  00cdc198 35   Adler CRC32 (0xb8bc6765) [32.le.1024]
  00cdd198 36   Adler CRC32 (0xb8bc6765) [32.be.1024]
  00cdb598 83   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.le rev.1024]
  00cdc598 84   CRC-32-IEEE 802.3 poly 0x04C11DB7 [32.be rev.1024]
  00cda848 357  Zlib dist_code [..512]
  00cdaa48 358  Zlib length_code [..256]
  00cdab48 359  Zlib base_length [32.le.116]
  00cdabc0 361  Zlib base_dist [32.le.120]
  00cc4b08 383  Jpeg dct 14 bit aanscales [16.le.128]
  00cc4b88 387  Jpeg dct AA&N scale factor [double.le.64]
  00cdd890 556  __popcount_tab (compression?) [..256]
  00cdab48 1085 Rar29 LDecode [32.le.112]
  00cb5108 1244 rfc3548 Base 64 Encoding with URL and Filename Safe Alphabet [..62]
  00cb5108 1253 B64EncodeTable [..64]
  00cc55f8 1539 zinflate_lengthStarts [32.le.116]
  00cc5678 1541 zinflate_lengthExtraBits [32.le.116]
  00cc5675 1542 zinflate_lengthExtraBits [32.be.116]
  00cc5718 1543 zinflate_distanceStarts [32.le.120]
  00cc5790 1545 zinflate_distanceExtraBits [32.le.120]
  0017a0f1 1783 anti-debug: Dongle protection [..3]
  00e0dcd6 1784 anti-debug: IsDebuggerPresent [..17]

- 25 signatures found in the file

```
## Post #5
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2009-05-13T22:33:04+00:00
- Post Title: Dragonica .dat Files

Homebrew encryption, encrypted blocks can have various options that turn on and off encryption stages. Archives can have toggles on data for whether the data is encrypted, and compressed. Some .dats in Data have encryption off on some of the data in them. Archive index table is always encrypted.
## Post #6
- Username: hself
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 28, 2009 8:33 am
- Post datetime: 2009-05-28T11:11:03+00:00
- Post Title: Dragonica .dat Files

Hi,
First, sorry for my very bad grammar, i'm french.

I'm interresting in the encryption of .DAT files from Dragonica to extract items, textures, characters, etc. I actually use Dependency Walker ( [http://www.dependencywalker.com/](http://www.dependencywalker.com/) ) to find some functions in the DLLs. But it is very hard and hasardous :/
I want to create a DataBase to recence Dragonica items in a website. So if you have made avancements can you notify me here?

EDIT : or if you can give clues about how to start in the right way, thanks
## Post #7
- Username: xprince
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 29, 2009 1:34 pm
- Post datetime: 2009-05-30T01:37:23+00:00
- Post Title: Dragonica .dat Files

I need dragonica dat file exractor too
some1 make 1 plsss
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2009-06-01T18:05:54+00:00
- Post Title: Dragonica .dat Files

i need a lamborghini because i love speed, buy me one
## Post #9
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2009-06-01T20:10:02+00:00
- Post Title: Dragonica .dat Files

In otherwords, @xprince, don't 'simply' ask for something out of the blue...
## Post #10
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2010-07-30T16:33:15+00:00
- Post Title: Dragonica .dat Files

No one progress?
## Post #11
- Username: Rwd
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 13, 2010 10:51 pm
- Post datetime: 2010-08-17T13:52:55+00:00
- Post Title: Dragonica .dat Files

> Reply from Slozhny
>
> I've already extract dragonica .dat with "offzip" tool, and became many-many-many smallsize .dat files.
Then, I rename all to .nif, and open with "nifscope". But not all files is .nif, some have another format. 
Now it all.
thanks a lot! It really works!
Some words about "another formats". It could be:
.kf
.kfm
.dds
.lua
.gif
.tga
and even .xml

I have "offzipped" 5_effect.dat to edit the visual effects and make them easier to display on poor machines. But it's very difficult to find .nif file, containing a visual effect of a skill. So, please, if you find such .nif, post it's offset here.
