## Post #1
- Username: drunkenchipmunk
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Aug 24, 2009 4:05 pm
- Post datetime: 2010-08-13T23:59:16+00:00
- Post Title: [PS2] CRICMP file format

Hi

Someone has ever stumbled upon this file format?

Things I found:

identifier is 6 bytes "CRICMP"

immediately after that, there's a sequence of chunks of 34 bytes, where the last two bytes seem to be CRCs, this is consistent over all the file

Just after the header, there's a few bytes that can be read in ascii like "2.10" which looks to be a version number.... but they're part of the first 34byte chunk, so it seems odd that the version is encrypted, but readable.... it might be a coincidence, and they're the first bytes of the encrypted stream (all CRICMP's I've seen have the same values, so it's not that clear)

inside it, there seems to be a MRG file, for which I already have the format.... CRICMP seems to just wrap arround an MRG, pretty much like how GZ wraps TAR.

Any ideas?
[ENM_GLG.rar](https://xentaxbackup.github.io/file/3321_ENM_GLG.rar)
## Post #2
- Username: biggestsonicfan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Dec 27, 2018 9:31 am
- Post datetime: 2018-12-27T02:49:52+00:00
- Post Title: [PS2] CRICMP file format

I too have a need for the CRICMP 2.10 files to be decompressed, but I have something that may help the decompression.

In one game, compressed in a CPK were CRICMP files AND THEIR UNCOMPRESSED BINARY FILES! Using a comparison tool, I can draw a basic structure conclusion:

```
@0x00: 16 bytes header data as follows: "CRICMP..2.10...."
@0x10 : 4 byte code 32 [20000000]
@0x14: 4 Byte value of decompressed file size in hex in reverse order. 
@0x18: 4 byte code 32 [20000000]
@0x1C:4 byte code 0 [00000000]
@0x20 4 byte code 16 [10000000]
@0x24: 4 bytes unknown data
@0x28++: Compressed Data
}
```


It's horrible psucdocode but if this unknown 4-byte array can be understood, it may help in the decompression of this file format.
