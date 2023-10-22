## Post #1
- Username: porimac
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-22T01:45:45+00:00
- Post Title: Shining Resonance (PS3) CPK

Ok this is a guide to extract large encrypted cpk's.
Here is the files you need for shining resonance .
using hxd paste these un encrypted tables over the encrypted tables at these offsets

table 1 - 0x10 offset 0x360 is the length
table 2  0x810 offset 0x41F20 is the length
table 3  0x49010 offset 0x13100 is the length
table 4 0x129686010 offset 0xCA68 is the length

Make sure you use the 64 bit quickbms as this file is over 4gb
[USRDIR.7z](https://xentaxbackup.github.io/file/8332_USRDIR.7z)
## Post #2
- Username: ativsp
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Sep 16, 2012 5:48 pm
- Post datetime: 2014-12-22T02:27:52+00:00
- Post Title: Shining Resonance (PS3) CPK

thanks!  
I will try it.
And the tool for convert extracted file to 3d model format is already exist?
## Post #3
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2014-12-22T04:53:23+00:00
- Post Title: Shining Resonance (PS3) CPK

You mean this offset

table1: offset start 000000010 length 000000360

table2: offset start 000000810 length 000041f20 

table3: offset start 000049010 length 000013100 

table4: offset start 129686010 length 00000CA68 

cpk file is DRG_0000.cpk



paste like this? 

and error  occurred when using bms



help!

and confirm bms file plz
[cpk.zip](https://xentaxbackup.github.io/file/8337_cpk.zip)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-22T10:56:37+00:00
- Post Title: Shining Resonance (PS3) CPK

Yes as long as you overwrite the data so the file size does not change.
I think i had to change the cpk.bms also try this one.
[cpk.bms.zip](https://xentaxbackup.github.io/file/8339_cpk.bms.zip)
## Post #5
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2014-12-22T12:43:04+00:00
- Post Title: Shining Resonance (PS3) CPK

still display error..
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-22T13:15:02+00:00
- Post Title: Shining Resonance (PS3) CPK

How much ram do you have?
Did you download the latest quickbms?
## Post #7
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2014-12-22T14:53:37+00:00
- Post Title: Shining Resonance (PS3) CPK

I' m using 16gb ram and
latest version quick bms (0.6.1c)

I think something wrong with my cpk file or bms setting
cpk file size was not change.. (4,876,369kb)
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-12-22T17:10:38+00:00
- Post Title: Shining Resonance (PS3) CPK

mabee you have a different version of the game.
I need to know the exact size of the cpk file in bytes using an hex editor.
I had someone else try this and it worked for them.
## Post #9
- Username: systembest
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Nov 14, 2012 10:37 am
- Post datetime: 2014-12-22T17:54:44+00:00
- Post Title: Shining Resonance (PS3) CPK

> size 4.65gb (4,993,401,472 byte)
>
> 
>
> nothing change file size when using HxD
>
> 
>
> And chrrox which version use for extract? 
>
> this game available two version 
>
> 
>
> chinese and japanese version exist
>
> 
>
> I have japanese version


I solve it !
the answer was chinese version 
thanks for help chrrox 

But stuck noesis to open mlx format 
related link has all dead
## Post #10
- Username: RangerRus
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Apr 19, 2011 1:17 am
- Post datetime: 2014-12-22T20:20:13+00:00
- Post Title: Shining Resonance (PS3) CPK

BLJM61156 -> DRG_0000.CPK

```

               1 = UpdateDateTime
		             FileSize
           5f800 = ContentOffset
       1299a8000 = ContentSize
             800 = TocOffset
           41f50 = TocSize
		             TocCrc
		             HtocOffset
		             HtocSize
       129a07800 = EtocOffset
            ca80 = EtocSize
		             ItocOffset
		             ItocSize
		             ItocCrc
           49000 = GtocOffset
           13118 = GtocSize
		             GtocCrc
		             HgtocOffset
		             HgtocSize
       2e659fcea = EnabledPackedSize
       29c6127ca = EnabledDataSize
		             TotalDataSize
		             Tocs
            1941 = Files
               1 = Groups
               1 = Attrs
		             TotalFiles
		             Directories
		             Updates
               7 = Version
               d = Revision
             800 = Align
               1 = Sorted
               1 = EnableFileName
		             EID
               3 = CpkMode
             1ba = Tvers
		             Comment
               0 = Codec
               0 = DpkItoc
               0 = EnableTocCrc
               0 = EnableFileCrc
               0 = CrcMode
               0 = CrcTable

Tvers   = CPKMC2.47.00, DLL3.17.00

Anticollision: OFF
Safename: OFF

Current cpk TOC record structure:

[OFF]			DirName
	  FileName
	  FileSize
	  ExtractSize
	  FileOffset
	  ID
[OFF]			UserString

TOC offset       800
TOC data offset  84b
TOC info offset  26663
TOC record size  18
TOC record size  18 (real)
TOC elements     7
TOC DynamicSize  2b
TOC DynamicSize  2b (real)

    1/ 6465: Size       90; ExtSize       90; Offset         e73e5000; [DRG_0000/AI_UNIT_00_000.NAD]
    2/ 6465: Size     1210; ExtSize     5fc0; Offset         e73e5800; [DRG_0000/AI_UNIT_00_010.NAD]
    3/ 6465: Size     1110; ExtSize     5d30; Offset         e73e7000; [DRG_0000/AI_UNIT_00_011.NAD]
    4/ 6465: Size     1108; ExtSize     5c80; Offset         e73e8800; [DRG_0000/AI_UNIT_00_012.NAD]
    5/ 6465: Size      588; ExtSize     1800; Offset         e73ea000; [DRG_0000/AI_UNIT_00_013.NAD]
    6/ 6465: Size     1a74; ExtSize     9900; Offset         e73ea800; [DRG_0000/AI_UNIT_00_020.NAD]
    7/ 6465: Size     18f0; ExtSize     93a0; Offset         e73ec800; [DRG_0000/AI_UNIT_00_021.NAD]
    8/ 6465: Size     1b34; ExtSize     9ef0; Offset         e73ee800; [DRG_0000/AI_UNIT_00_022.NAD]
    9/ 6465: Size      ca4; ExtSize     44a0; Offset         e73f0800; [DRG_0000/AI_UNIT_00_023.NAD]
   10/ 6465: Size     1754; ExtSize     7c00; Offset         e73f1800; [DRG_0000/AI_UNIT_00_030.NAD]
   11/ 6465: Size     13dc; ExtSize     6b50; Offset         e73f3000; [DRG_0000/AI_UNIT_00_031.NAD]
   12/ 6465: Size     165c; ExtSize     7920; Offset         e73f4800; [DRG_0000/AI_UNIT_00_032.NAD]
  ....

Necessity for anticollision = NO
Necessity for safename      = NO
```

Nothing interesting in those *.cpk samples.
## Post #11
- Username: lovemarin
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Sep 14, 2014 10:40 am
- Post datetime: 2015-03-07T03:14:53+00:00
- Post Title: Shining Resonance (PS3) CPK

> Reply from chrrox
>
> Ok this is a guide to extract large encrypted cpk's.
Here is the files you need for shining resonance .
using hxd paste these un encrypted tables over the encrypted tables at these offsets

table 1 - 0x10 offset 0x360 is the length
table 2  0x810 offset 0x41F20 is the length
table 3  0x49010 offset 0x13100 is the length
table 4 0x129686010 offset 0xCA68 is the length

Make sure you use the 64 bit quickbms as this file is over 4gb

I got MLX files, but don't know how to extrcat these files or load them within Noesis further. seems useful links and related tools are all invalid. Could you do me a favor please? [roll]maybe I need some kind of plugin. Thanks!
## Post #12
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-14T20:52:12+00:00
- Post Title: Shining Resonance (PS3) CPK

Can anyone tell me where to find this Asia .CPK file ?
