## Post #1
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-15T05:14:37+00:00
- Post Title: Death Stranding

Game just came out, it's protected with Denuvo so it can be a bit of a pain picking through a runtime dump of the executable.

Format seems to be a different version of the Decima engine than Horizon Zero Dawn and the file format looks quite different

0x20304050 for Horizon Zero Dawn
0x21304050 for Death Stranding

Here's one of the more smaller .bin files
[https://mega.nz/file/GOwSUYpK#tIASi5h1E ... Hv1t4XkWaQ](https://mega.nz/file/GOwSUYpK#tIASi5h1ERQypdtYUvXQ5fmSkUwLx3X8hHv1t4XkWaQ)

File IO seems to take advantage of the Murmur3 hash function utilizing seeds like `0x0FA3A9443,0x0F41CAB62,0x0F376811C, 0x0D2A89E3E` and some precursing SIMD code at the call site. After that, likely lots of oo2core via (oo2core _7_ win64.dll) for compression.
## Post #2
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-07-15T23:35:31+00:00
- Post Title: Death Stranding

Try this [viewtopic.php?f=16&t=21829](https://forum.xentax.com/viewtopic.php?f=16&t=21829)
## Post #3
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-16T03:58:44+00:00
- Post Title: Death Stranding

I think it deserves its own thread, rather than relying on one persons proprietary and obfuscated tools that don't even work on the PC version of the game. This is generally for interfacing with the game archive format rather than just interest in the 2d/3d assets.
## Post #4
- Username: wunk
- Rank: advanced
- Number of posts: 44
- Joined date: Thu Dec 23, 2010 4:49 pm
- Post datetime: 2020-07-16T14:18:36+00:00
- Post Title: Death Stranding

Murmur3 seed is "answer to everything" number "42" and it seems to just use a chain of salted(`0x0FA3A9443,0x0F41CAB62,0x0F376811C, 0x0D2A89E3E` interleaves with an input int) murmur3 hashes xored with the next 16 bytes.
The Murmur3 implementation is basically the one found here, where "seed" is always 42.
[https://github.com/PeterScott/murmur3/b ... ur3.c#L234](https://github.com/PeterScott/murmur3/blob/dae94be0c0f54a399d23ea6cbe54bca5a4e93ce4/murmur3.c#L234)

I'll post the some notes here and formalize some code on my [github
](https://github.com/Wunkolo/DecimaTools) while I make a basic dumper

Here is the header/filetable/chunktable of the 138969409f16e44df28d7fbcb87a5909.bin file posted in the OP. Structures are ultimately the same as Horizon Zero Dawn on the PS4 but with the added layer of encryption. The Header/FileTable/ChunkTable entries are encrypted somewhat differently.


```
Version:                 6DD02CEF
FileSize:                 2004617
DataSize:                 2131705
FileTableCount:                 4
ChunkTableCount:                9
MaxChunkSize:              262144
        ---------------------------------------
        EntryID:                      797099076
        Unknown04:                   1833628696
        Unknown08:             3F821535414ED8FD
        Offset:                               0
        Size:                           1354751
        Unknown1C:                     7496F6C2
        ---------------------------------------
        EntryID:                     4172398392
        Unknown04:                   2136868349
        Unknown08:             D3D19A0EB596F903
        Offset:                         1354751
        Size:                            145618
        Unknown1C:                     3D7F6668
        ---------------------------------------
        EntryID:                     3114963283
        Unknown04:                   4088237356
        Unknown08:             3E20BD7DB9BE7960
        Offset:                         1532501
        Size:                            599204
        Unknown1C:                     58D97D4F
        ---------------------------------------
        EntryID:                     1447133094
        Unknown04:                   3705277707
        Unknown08:             130EA489D652BD55
        Offset:                         1500369
        Size:                             32132
        Unknown1C:                     00176D49
        ---------------------------------------------
        OffsetUncompressed:                          
        SizeUncompresed:                       262144
        Unknown0C:                           030DFD13
        OffsetCompressed:                         456
        SizeCompressed:                        213931
        Unknown1C:                           5859112B
        ---------------------------------------------
        OffsetUncompressed:                    262144
        SizeUncompresed:                       262144
        Unknown0C:                           AE3F6A60
        OffsetCompressed:                      214387
        SizeCompressed:                        258608
        Unknown1C:                           DF45ABE1
        ---------------------------------------------
        OffsetUncompressed:                    524288
        SizeUncompresed:                       262144
        Unknown0C:                           D9A5F8E8
        OffsetCompressed:                      472995
        SizeCompressed:                        259270
        Unknown1C:                           9D9AC56C
        ---------------------------------------------
        OffsetUncompressed:                    786432
        SizeUncompresed:                       262144
        Unknown0C:                           CCE42AAC
        OffsetCompressed:                      732265
        SizeCompressed:                        258467
        Unknown1C:                           9015E633
        ---------------------------------------------
        OffsetUncompressed:                   1048576
        SizeUncompresed:                       262144
        Unknown0C:                           E52D54EF
        OffsetCompressed:                      990732
        SizeCompressed:                        254252
        Unknown1C:                           8A3465A0
        ---------------------------------------------
        OffsetUncompressed:                   1310720
        SizeUncompresed:                       262144
        Unknown0C:                           FE5724A2
        OffsetCompressed:                     1244984
        SizeCompressed:                        213497
        Unknown1C:                           EFFCE6F5
        ---------------------------------------------
        OffsetUncompressed:                   1572864
        SizeUncompresed:                       262144
        Unknown0C:                           DBCB4E32
        OffsetCompressed:                     1458481
        SizeCompressed:                        257844
        Unknown1C:                           D961FE10
        ---------------------------------------------
        OffsetUncompressed:                   1835008
        SizeUncompresed:                       262144
        Unknown0C:                           A7CD7DB2
        OffsetCompressed:                     1716325
        SizeCompressed:                        254539
        Unknown1C:                           DF590A89
        ---------------------------------------------
        OffsetUncompressed:                   2097152
        SizeUncompresed:                        34553
        Unknown0C:                           A5DAA534
        OffsetCompressed:                     1970864
        SizeCompressed:                         33753
        Unknown1C:                           5D58BE0F

```
## Post #5
- Username: PatrickJr
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 28, 2017 11:11 am
- Post datetime: 2020-07-20T05:11:56+00:00
- Post Title: Death Stranding

Looking forward to what you make Wunk!
## Post #6
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2020-07-21T15:07:03+00:00
- Post Title: Death Stranding

Any idea if the shaders in DeathStranding will be dumpable?
## Post #7
- Username: Dizcordum
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 01, 2019 10:32 am
- Post datetime: 2020-09-28T13:38:14+00:00
- Post Title: Death Stranding

any update Wunk?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-28T14:44:09+00:00
- Post Title: Death Stranding

[https://github.com/Jayveer/Decima-Explo ... ses/latest](https://github.com/Jayveer/Decima-Explorer/releases/latest)
## Post #9
- Username: BaynanaSlug
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 15, 2021 7:10 am
- Post datetime: 2021-07-14T23:17:06+00:00
- Post Title: Death Stranding

Can someone please help me understand how to extract the fonts from the PC version of the game? I have no idea what I'm doing and was hoping there was a way to derive .ttf or .otf files from the .core files I extracted w/ Decima Explorer.
