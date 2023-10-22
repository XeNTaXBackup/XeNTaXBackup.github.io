## Post #1
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-17T23:40:05+00:00
- Post Title: Soul Reverse Arcade (ソウルリバース) (.fpk)

The game files seem to be similar to the KanCole/FGOA files but are contained inside a .fpk file instead of a .farc and it seems inside are also 2 files (MDL and TEX headers), using 7zip to extract the fpk file I get part of the MDL file which means the compression is not custom, I'm not aware of any tools that can extract this (I looked around) and the FPK file extension seems to be used by other games but those have different formats, here are some samples in case anyone wants to take a look:

[https://mega.nz/folder/AK5yCDIA#yp9eRKXFuq6w20VPcMGCHw](https://mega.nz/folder/AK5yCDIA#yp9eRKXFuq6w20VPcMGCHw)


```
0010h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0020h: 60 00 00 00 00 00 00 00 42 14 00 00 01 00 00 00  `.......B....... 
0030h: B0 00 00 00 4D 44 4C 00 34 12 00 00 00 00 00 00  °...MDL.4....... 
0040h: 86 00 00 00 00 00 00 00 CA 00 00 00 01 00 00 00  †.......Ê....... 
0050h: F4 14 00 00 54 45 58 00 34 12 00 00 00 00 00 00  ô...TEX.4....... 
0060h: 6D 64 6C 2F 6D 64 6C 5F 70 63 68 5F 6D 61 6E 30  mdl/mdl_pch_man0 
0070h: 30 31 5F 61 72 63 68 65 72 30 30 31 5F 68 65 61  01_archer001_hea 
0080h: 64 2E 62 69 6E 00 74 65 78 2F 74 65 78 5F 70 63  d.bin.tex/tex_pc 
0090h: 68 5F 6D 61 6E 30 30 31 5F 61 72 63 68 65 72 30  h_man001_archer0 
00A0h: 30 31 5F 68 65 61 64 2E 62 69 6E 00 00 00 00 00  01_head.bin..... 
00B0h: 1F 8B 08 00 00 00 00 00 00 FF ED 5B 0B 78 4D D7  .‹.......ÿí[.xM× 
00C0h: B6 1E 3B B4 42 3C 22 5E A9 84 E0 48 50 B2 ED 48  ¶.;´B<"^©„àHP²íH 
00D0h: E4 B1 D7 DA 7B 0B 42 BC EA 59 5A 94 12 6E E9 39  ä±×Ú{.B¼êYZ”.né9 
00E0h: 8E 56 69 AB A7 74 47 AB 48 69 3D E3 5D 29 8A A8  ŽVi«§tG«Hi=ã])Š¨ 
00F0h: 6E 21 EF AC B9 8B 50 45 B5 3D 0D AD 47 0E 5A D4  n!ï¬¹‹PEµ=.­G.ZÔ 

```


Also, it seems the resulting model/tex files can be viewed with the kancole/fgoa plugin for noesis from h-kidd
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-18T00:00:56+00:00
- Post Title: Soul Reverse Arcade (ソウルリバース) (.fpk)

Something like this should work, tested only on provided samples.

Update: Script for extracting tex -> txp added to the attachment.
Update 2: Script for converting txp -> dds also added.



 soulreverse_fpk+tex+txp.zip
(1.64 KiB) Downloaded 22 times
## Post #3
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-18T00:12:29+00:00
- Post Title: Soul Reverse Arcade (ソウルリバース) (.fpk)

awesome, the resulting files seem to work with noesis:




soul.jpg (191.95 KiB) Viewed 77 times
