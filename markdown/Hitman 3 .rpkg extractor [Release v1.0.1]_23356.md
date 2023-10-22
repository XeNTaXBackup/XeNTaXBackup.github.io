## Post #1
- Username: LennardF1989
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 31, 2010 7:54 am
- Post datetime: 2021-01-23T01:56:05+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

[Update 24/1/2020] v1.0.1 released!

Initially created to help a guy on ZenHAX, but I guess it can be up here as well.

Source and compiled version can be found here: [https://github.com/LennardF1989/HitmanExtractor](https://github.com/LennardF1989/HitmanExtractor)

Format so far.

```
0x00 String - "2KPR"
Skip 9 bytes
0x0d UInt - File count
0x11 UInt - File table 1 size
0x15 UInt - File table 2 size

File table 1 immediately follows, loop "File count" times, each entry has:
0x00 UInt64 - Hash (Needs hash to filename mapping)
0x08 UInt - File offset
Skip 4 bytes
0x10 UInt - File size (Bit 31 determines if encrypted, if Bit 31 is set, exclude it, eg. using bitshifting with & 0x3fffffff)

Assert current offset position is total header size + file table 1 size

File table 2 immediately follows, loop "File count" times, each entry has:
0x00 String - Filetype (in reverse, eg. NOSJ is JSON)
0x04 UInt - Additional number of bytes for entry (total size is 0x18 + this value)
Skip 4 bytes
0x0C UInt - Decompressed size
Skip x bytes - Where x = 0x18 + (Additional bytes) - 0x10 (current offset into entry)

Assert current offset position is total header size + file table 1 size + file table 2 size

Extraction:
Loop through all entries, use File offset and File size (adjusted if encrypted!) from File table 1, use File type for file-extension and decompressed size from File table 2.

Compression:
If file is encrypted, XOR the bytes with key [0xDC, 0x45, 0xA6, 0x9C, 0xD3, 0x72, 0x4C, 0xAB], then decompress with LZ4.

```
## Post #2
- Username: YourImaginaryFriend
- Rank: n00b
- Number of posts: 16
- Joined date: Mon Mar 14, 2016 5:57 pm
- Post datetime: 2021-01-23T09:30:15+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

Awesome! Hopefully someone will make an extraction tool for meshes and textures
## Post #3
- Username: BoomBookTR
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Jun 03, 2019 6:36 am
- Post datetime: 2021-01-23T17:00:09+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

ty great job but i'm trying to find game text files for localization...
waiting some upgrades...
And i need rpkg import support too.
## Post #4
- Username: LennardF1989
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Dec 31, 2010 7:54 am
- Post datetime: 2021-01-24T12:05:14+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

Just pushed v1.0.1, fixing the issue with extracting non-compressed assets. 

[https://github.com/LennardF1989/HitmanE ... tag/v1.0.1](https://github.com/LennardF1989/HitmanExtractor/releases/tag/v1.0.1)
## Post #5
- Username: atomicool
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Jun 14, 2019 11:01 pm
- Post datetime: 2021-02-05T11:16:14+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

so how to packback?
## Post #6
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-02-05T16:40:29+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

@atomicool: [https://notex.app/rpkg/](https://notex.app/rpkg/)
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2021-02-07T16:49:08+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

> Reply from YourImaginaryFriend ↑Sat Jan 23, 2021 5:30 pm at Sat Jan 23, 2021 5:30 pm
>
> 
Awesome! Hopefully someone will make an extraction tool for meshes and textures
[viewtopic.php?p=171085#p171085](https://forum.xentax.com/viewtopic.php?p=171085#p171085)
## Post #8
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2021-02-08T16:02:15+00:00
- Post Title: Hitman 3 .rpkg extractor [Release v1.0.1]

Hi,
any hints to see how are savegame encrypted?
