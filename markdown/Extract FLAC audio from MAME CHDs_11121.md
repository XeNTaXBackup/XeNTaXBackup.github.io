## Post #1
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-01-10T01:41:39+00:00
- Post Title: Extract FLAC audio from MAME CHDs

Is it possible to extract audio from MAME CHDs? They are typically compressed in FLAC with the latest version (CHDv5). There are some CHDs that are CD image files and can be easily converted to bin/cue with CHDMAN, howeer the CHDs I'm trying to extract are hard disk image files. I tried decompressing them to raw .img files and mounting them, but nothing worked.
## Post #2
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-10T10:40:31+00:00
- Post Title: Extract FLAC audio from MAME CHDs

CHD harddisks are not compressed with FLAC. Only audio CDs and (maybe) Laserdiscs. FLAC wouldn't make sense on a harddisk now, would it?

It's however possible (if very unlikely) that the (uncompressed) harddisk image contains *.flac files, in that case you should be able to mount them (if it's a well-known filesystem) and copy the FLAC files off. I doubt any games use FLAC for audio though

Which chd in particular are you having trouble with?
## Post #3
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-01-10T10:49:34+00:00
- Post Title: Extract FLAC audio from MAME CHDs

> Reply from Darkstar
>
> CHD harddisks are not compressed with FLAC. Only audio CDs and (maybe) Laserdiscs. FLAC wouldn't make sense on a harddisk now, would it?

It's however possible (if very unlikely) that the (uncompressed) harddisk image contains *.flac files, in that case you should be able to mount them (if it's a well-known filesystem) and copy the FLAC files off. I doubt any games use FLAC for audio though

Which chd in particular are you having trouble with?

CarnEvil. The CHDMAN info command shows that the audio of the CHD has been compressed with FLAC. The FLAC codec was introduced to CHD compression when the CHD version 5 was released. More details [here](http://mamedev.emulab.it/haze/2012/02/16/chd-v5/).

I tried to mount the hard disk several times using virtual drives, and none of them worked. I read somewhere that I should try to mount it on an SD card, but I'm afraid to do that.
## Post #4
- Username: Darkstar
- Rank: advanced
- Number of posts: 67
- Joined date: Thu Jun 14, 2007 8:14 pm
- Post datetime: 2014-01-10T12:56:06+00:00
- Post Title: Extract FLAC audio from MAME CHDs

This is what I get:

```
chdman - MAME Compressed Hunks of Data (CHD) manager 0.152 (Dec 25 2013)
Input file:   carnevil.chd
File Version: 5
Logical size: 4,310,046,720 bytes
Hunk Size:    4,096 bytes
Total Hunks:  1,052,258
Unit Size:    512 bytes
Total Units:  8,418,060
Compression:  lzma (LZMA), zlib (Deflate), huff (Huffman), flac (FLAC)
CHD size:     1,465,496,818 bytes
Ratio:        34.0%
SHA1:         5cffb0de63ad36eb01c5951bab04d3f8a9e23e16
Data SHA1:    ba32b7ef9721d730ce58bd753d47fb947b6ae9b6
Metadata:     Tag='GDDD'  Index=0  Length=35 bytes
              CYLS:524,HEADS:255,SECS:63,BPS:512.

     Hunks  Percent  Name
----------  -------  ------------------------------------
     1,803     0.2%  Uncompressed
   318,771    30.3%  Copy from self
   682,769    64.9%  LZMA
    23,510     2.2%  Deflate
     1,752     0.2%  Huffman
    23,653     2.2%  FLAC

```

There's indeed some small percentage compressed with FLAC, but it's only 2.2%... So it seems when uncompressed there's at least a small bit of PCM wave data in the hard disk image, and opening the file as RAW in a sound editor shows that there are various musical parts splattered all over the file (you just have to find them):
[](http://imgbin.org/index.php?page=image&id=16270)

So your best bet is to either find someone who'll decipher the hard disk file system for you and writes an unpacker, or simply hunt for these fragments in Audacity or any other sound editor...
## Post #5
- Username: keystothemaxim
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Oct 21, 2013 6:19 pm
- Post datetime: 2014-01-10T22:52:06+00:00
- Post Title: Extract FLAC audio from MAME CHDs

Thank you very much!
