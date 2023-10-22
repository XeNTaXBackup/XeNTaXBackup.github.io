## Post #1
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-21T20:49:10+00:00
- Post Title: Fate Grand Order Arcade

[https://arcade.fate-go.jp/](https://arcade.fate-go.jp/)

So the arcade file dump can be found around the web and the files don't look to be encrypted or even compressed but the format is kinda strange (to me anyways), the extension and header of the files seems to be FARC but it doesn't extract with the farc tools I was able to find around here.

Some samples here, as far as I can tell these are the files that include information about 1 character from the game (hopefully models, textures, etc), some sort of basic container with 15 different files (as far as I can see in the header):

[https://mega.nz/file/1Dh00J5A#sfDS_Hhp5 ... J14R9qvK34](https://mega.nz/file/1Dh00J5A#sfDS_Hhp5MsYfsleOTqbVrrLNtxIKYDQsJ14R9qvK34)

Anyone want to take a look? the in-game models look pretty good   

[https://www.youtube.com/watch?v=yEMULAYi6Ww](https://www.youtube.com/watch?v=yEMULAYi6Ww)
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-07-21T22:26:06+00:00
- Post Title: Fate Grand Order Arcade

FARc is slightly modified [Virtua Fighter 5](https://aluigi.altervista.org/bms/virtua_fighter_5.bms) format.

Update: Added script for extracting tex container into separate TXP files. For more info about this format and Project Diva format in general see [this topic](https://forum.xentax.com/viewtopic.php?t=5484).

Update 2: Added script for converting txp into dds (based on chrrox's script for first mips). Currently supported formats from used by the game: BC1 (DXT1), BC3 (DXT5), BC4 (ATI1), BC5 (ATI2), BC7.

Update 3: farc script simplified to handle other farc containers from the game.

Update 4: farc script updated to support zstd compression.

Update 5: txp script updated to support BC7 textures.



 FGO_arcade_farc+tex+txp.zip
(1.84 KiB) Downloaded 482 times
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-21T22:47:28+00:00
- Post Title: Fate Grand Order Arcade

Plain text and aligned data, probably the file is uncompressed, just combine together. 
And the header and A3DA looks like the file format used by SEGA games such as Project Diva.
The person who owns the file needs to make sure that those plugins are available.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-21T23:07:16+00:00
- Post Title: Fate Grand Order Arcade

In the end it looks like animation data:
.



a3d_SVT_0001-farc.png (5.91 KiB) Viewed 4429 times
## Post #5
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-21T23:35:27+00:00
- Post Title: Fate Grand Order Arcade

Seems I was looking in the wrong folder, THESE look like they contain the 3D data:

[https://mega.nz/file/4PhRRY7C#2jbuOdIqV ... _4rBbhGuRs](https://mega.nz/file/4PhRRY7C#2jbuOdIqVcvNalmQdsicprv1Dqzj2EqZ9_4rBbhGuRs)

I was able to decompress the first file of each with 7zip and after that it showed me some model data similar to the VF5/Diva Project ones:

```
0010h: 34 00 00 00 00 00 00 00 34 00 00 00 00 00 00 00  4.......4....... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 5F  ....<.......svt_ 
0040h: 30 30 30 31 5F 73 30 31 5F 6D 6F 64 65 6C 00 00  0001_s01_model.. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 13 00 00 00 00 00 00 00 0A 00 00 00 00 00 00 00  ................ 
0070h: 10 1C 00 00 00 00 00 00 18 00 00 00 00 00 00 00  ................ 

```


```
0010h: 34 00 00 00 00 00 00 00 13 00 00 00 00 00 00 00  4............... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 67  ....<.......svtg 
0040h: 5F 30 30 30 34 5F 77 69 6B 5F 6D 6F 64 65 6C 00  _0004_wik_model. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 11 00 00 00 00 00 00 00 4B 00 00 00 00 00 00 00  ........K....... 
0070h: D0 43 00 00 00 00 00 00 4B 00 00 00 00 00 00 00  ÐC......K....... 
0080h: E0 06 00 00 00 00 00 00 40 40 23 00 00 00 00 00  à.......@@#..... 
0090h: E8 5B 00 00 00 00 00 00 18 2B 04 00 00 00 00 00  è[.......+...... 
00A0h: 28 9C 23 00 00 00 00 00 28 02 00 00 00 00 00 00  (œ#.....(....... 
00B0h: 08 04 00 00 00 00 00 00 40 5B 00 00 00 00 00 00  ........@[...... 
00C0h: D8 5B 00 00 00 00 00 00 03 00 00 00 00 00 00 00  Ø[.............. 
00D0h: 40 C7 27 00 00 00 00 00 18 00 00 00 00 00 00 00  @Ç'............. 
00E0h: 68 C9 27 00 00 00 00 00 09 00 00 00 00 00 00 00  hÉ'............. 
00F0h: A8 CE 27 00 00 00 00 00 60 CF 27 00 00 00 00 00  ¨Î'.....`Ï'..... 
0100h: 98 EE 27 00 00 00 00 00 30 EF 27 00 00 00 00 00  ˜î'.....0ï'..... 
0110h: D0 F1 27 00 00 00 00 00 70 25 28 00 00 00 00 00  Ðñ'.....p%(..... 
0120h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0130h: 00 00 00 00 00 00 00 00 E8 F4 27 00 00 00 00 00  ........èô'..... 
0140h: 00 00 00 00 00 00 00 00 E8 F4 27 00 00 00 00 00  ........èô'..... 
0150h: 00 00 00 00 00 00 00 00 E8 F4 27 00 00 00 00 00  ........èô'..... 
0160h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0170h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0180h: 13 01 00 00 00 00 00 00 E8 F4 27 00 00 00 00 00  ........èô'..... 
0190h: D0 10 28 00 00 00 00 00 18 00 00 00 00 00 00 00  Ð.(............. 
01A0h: 60 64 28 00 00 00 00 00 A0 66 28 00 00 00 00 00  `d(..... f(..... 
01B0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
01C0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
01D0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
01E0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
01F0h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0200h: 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00  ................ 
0210h: 00 00 00 00 D8 38 A0 40 C0 6B C2 3C EF 1B D9 40  ....Ø8 @ÀkÂ<ï.Ù@ 
0220h: 00 00 00 00 D8 38 A0 40 C0 6B C2 3C D3 4B BA 40  ....Ø8 @ÀkÂ<ÓKº@ 
0230h: 0A C9 A0 40 7B 88 A6 3F 00 00 00 00 E2 91 B3 C0  .É @{ˆ¦?....â‘³À 
0240h: AB 41 7F 3F FC C8 2F BF 00 00 00 00 E5 DF 8E 3F  «A?üÈ/¿....åßŽ? 
0250h: 61 68 A0 40 BB 57 9F 40 7B 88 A6 3F 00 00 00 00  ah @»WŸ@{ˆ¦?.... 
0260h: 00 00 00 00 C0 6B C2 3C 28 02 00 00 00 00 00 00  ....ÀkÂ<(....... 
0270h: 00 00 00 00 00 00 00 00 1E 00 1F 00 20 00 00 00  ............ ... 
0280h: 1E 00 1F 00 1F 00 20 00 09 00 0A 00 0B 00 00 00  ...... ......... 
0290h: 09 00 0A 00 0A 00 17 00 18 00 14 00 0D 00 0C 00  ................ 
02A0h: 11 00 10 00 1B 00 1A 00 0B 00 00 00 1E 00 1F 00  ................ 
02B0h: 20 00 00 00 09 00 0A 00 17 00 18 00 14 00 15 00   ............... 
02C0h: 0D 00 0E 00 0C 00 11 00 12 00 10 00 1B 00 1A 00  ................ 
02D0h: 0B 00 00 00 03 00 00 00 00 00 00 00 03 00 00 00  ................ 
02E0h: 02 00 00 00 03 00 00 00 03 00 00 00 02 00 00 00  ................ 
02F0h: 00 00 00 00 03 00 00 00 01 00 02 00 03 00 00 00  ................ 
0300h: 03 00 00 00 01 00 02 00 2C 00 2D 00 2E 00 20 00  ........,.-... . 
0310h: 17 00 18 00 19 00 0B 00 29 00 2A 00 2B 00 20 00  ........).*.+. . 

```
## Post #6
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-07-22T01:24:31+00:00
- Post Title: Fate Grand Order Arcade

The gzip magic of this game file seems to be
1F 8B 08 08 00 00 00 00 00,
but there seems to be another delimiter because the number of files don't match the header map.
## Post #7
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-07-22T03:35:11+00:00
- Post Title: Fate Grand Order Arcade

I've updated the script, it can now handle chunked gzip files in farc container as well. Texture file is actually collection of textures (seems like DXT1).
## Post #8
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-22T05:13:31+00:00
- Post Title: Fate Grand Order Arcade

They managed to get the data?!!
I really thought it was another impossible.

Who ever know were to find it PM
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-07-22T07:47:21+00:00
- Post Title: Fate Grand Order Arcade

Some sub mesh:
.



svt_0001_s01_obj-bin.png (121.3 KiB) Viewed 4395 times
## Post #10
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-07-22T13:20:03+00:00
- Post Title: Fate Grand Order Arcade

Added script for extracting tex container into separate TXP files to the same package. Those filenames though >_>
## Post #11
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-22T13:21:59+00:00
- Post Title: Fate Grand Order Arcade

> Reply from shakotay2 ↑Thu Jul 22, 2021 3:47 pm at Thu Jul 22, 2021 3:47 pm
>
> 
Some sub mesh:
.
svt_0001_s01_obj-bin.png

So, internally looks like they are numbered the same as in the character page from the official website then, since I grabbed the first "servant" file and the first "weapon" file as a sample in my previous post:
## Post #12
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-22T13:41:38+00:00
- Post Title: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Thu Jul 22, 2021 1:13 pm at Thu Jul 22, 2021 1:13 pm
>
> 
They managed to get the data?!!
I really thought it was another impossible.

Who ever know were to find it PM

Just google "[Arcade PC] Fate/Grand Order Arcade (Sega ALLS UX)"
## Post #13
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-22T14:08:50+00:00
- Post Title: Fate Grand Order Arcade

> Reply from Spiritovod ↑Thu Jul 22, 2021 9:20 pm at Thu Jul 22, 2021 9:20 pm
>
> 
Added script for extracting tex container into separate TXP files to the same package. Those filenames though >_>

Yup, looks to be DXT# files:



face.jpg (149.14 KiB) Viewed 4369 times
## Post #14
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-22T14:28:43+00:00
- Post Title: Fate Grand Order Arcade

> Reply from Spiritovod ↑Thu Jul 22, 2021 11:35 am at Thu Jul 22, 2021 11:35 am
>
> 
I've updated the script, it can now handle chunked gzip files in farc container as well. Texture file is actually collection of textures (seems like DXT1).

The voice seem to be contained inside a slightly different kind of farc, just a bunch of ogg files (not even compressed):

[https://mega.nz/file/kL5jBCoT#9qa4Tdb_b ... rAtEcJiHXg](https://mega.nz/file/kL5jBCoT#9qa4Tdb_bqrQ2N6BWDxhNdt2TLM4bsrfWrAtEcJiHXg)
## Post #15
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-07-22T15:06:22+00:00
- Post Title: Fate Grand Order Arcade

I've updated farc script (actually simplified as it seems all farc containers are the same here) and added script for converting txp to dds (if possible).
## Post #16
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2021-07-22T18:46:37+00:00
- Post Title: Re: Fate Grand Order Arcade

Figure I'll throw what I've done in here as well (since apparently some people got a hold of some files before this full dump).

[https://github.com/Silvris/RandomScript ... O%20Arcade](https://github.com/Silvris/RandomScriptsAndTemplates/tree/main/FGO%20Arcade)

Python scripts for unpacking FARC and the tex-bins, and a Noesis script for viewing the resulting .txp. 

From what I can tell, the overall file structure mimics those of the Project DIVA games, so anyone looking into the models further should probably start with those.
[https://github.com/blueskythlikesclouds/MikuMikuLibrary](https://github.com/blueskythlikesclouds/MikuMikuLibrary)
## Post #17
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-24T04:33:17+00:00
- Post Title: Re: Fate Grand Order Arcade

The Miku Miku Model tool gives "Failed to Open svt_0022_s04_obj.bin  Reason: Invalid signature (expected TXP with 3)".
## Post #18
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-07-24T17:11:10+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Sat Jul 24, 2021 12:33 pm at Sat Jul 24, 2021 12:33 pm
>
> 
The Miku Miku Model tool gives "Failed to Open svt_0022_s04_obj.bin  Reason: Invalid signature (expected TXP with 3)".
They are read when they put txp file in the file same as obj.bin, but the contents are empty
## Post #19
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-24T18:00:53+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Sun Jul 25, 2021 1:11 am at Sun Jul 25, 2021 1:11 am
>
> 
They are read when they put txp file in the file same as obj.bin, but the contents are empty

Ok but those are the model file. Even opening on Hex shows model data.

I only use the bms for unpack the farc, because Silvris tool they only open/close if you move a farc on the bat.
## Post #20
- Username: Silvris
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Jul 16, 2019 5:44 am
- Post datetime: 2021-07-24T18:25:11+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Sat Jul 24, 2021 12:33 pm at Sat Jul 24, 2021 12:33 pm
>
> 
The Miku Miku Model tool gives "Failed to Open svt_0022_s04_obj.bin  Reason: Invalid signature (expected TXP with 3)".

IIRC that's because it's trying to read it as a texture, but even still the formats are not identical, so they shouldn't work in MML at all.
## Post #21
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-24T19:15:03+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Silvris ↑Sun Jul 25, 2021 2:25 am at Sun Jul 25, 2021 2:25 am
>
> 
IIRC that's because it's trying to read it as a texture, but even still the formats are not identical, so they shouldn't work in MML at all.
Then how one can open the model data?

And I notice that the bms doesn't unpack every farc.
I have try to unpack other Servants models and gives me the error "can't read 4 bytes  from offset 000000000019ca2c".
## Post #22
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2021-07-24T21:15:53+00:00
- Post Title: Re: Fate Grand Order Arcade

I've updated farc script with support for zstd compression, which is used in some archives.
## Post #23
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2021-07-25T01:49:46+00:00
- Post Title: Re: Fate Grand Order Arcade

This isn't done but I can't look at it anymore right now. This noesis script should load most models. But without bones, weights, and sometimes the UV's are scaled wrong(?!). Also, the vertex normals are encoded somehow and I haven't figured out how. If someone wants to spring off this and finish it that would be great, otherwise I'll come back to this later.
[fmt_FGOA_bin.zip](https://xentaxbackup.github.io/file/20504_fmt_FGOA_bin.zip)
## Post #24
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-25T02:06:57+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Sun Jul 25, 2021 5:15 am at Sun Jul 25, 2021 5:15 am
>
> 
I've updated farc script with support for zstd compression, which is used in some archives.

Yes this help! It unpack the ones that cause bms to crash



> Reply from Simguy ↑Sun Jul 25, 2021 9:49 am at Sun Jul 25, 2021 9:49 am
>
> 
This isn't done but I can't look at it anymore right now. This noesis script should load most models. But without bones, weights, and sometimes the UV's are scaled wrong(?!). Also, the vertex normals are encoded somehow and I haven't figured out how. If someone wants to spring off this and finish it that would be great, otherwise I'll come back to this later.

Cool, this will help for quickly find what each model as it is not truth what the first post say:
Servants order are different compared to the Japanese web, I found the number 09 being the 46 of the web.
## Post #25
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-25T03:56:01+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Sun Jul 25, 2021 9:49 am at Sun Jul 25, 2021 9:49 am
>
> 
This isn't done but I can't look at it anymore right now. This noesis script should load most models. But without bones, weights, and sometimes the UV's are scaled wrong(?!). Also, the vertex normals are encoded somehow and I haven't figured out how. If someone wants to spring off this and finish it that would be great, otherwise I'll come back to this later.

For these kind of models all the skeleton info seems to be in a separate folder, this one matches the sample from before:
[skl_svt_0001_s01.zip](https://xentaxbackup.github.io/file/20505_skl_svt_0001_s01.zip)
## Post #26
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-07-25T05:15:47+00:00
- Post Title: Re: Fate Grand Order Arcade

I just checked and only 4 servants model didn't load. Also the model order is the same one in which each servant was add and on the version 4.50.00 of the game ends on BB.

This video shows very similar order each servant model data is organize.

[https://youtu.be/6PsYFi9uNlc](https://youtu.be/6PsYFi9uNlc)
## Post #27
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-07-25T09:09:42+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Sun Jul 25, 2021 9:49 am at Sun Jul 25, 2021 9:49 am
>
> 
This isn't done but I can't look at it anymore right now. This noesis script should load most models. But without bones, weights, and sometimes the UV's are scaled wrong(?!). Also, the vertex normals are encoded somehow and I haven't figured out how. If someone wants to spring off this and finish it that would be great, otherwise I'll come back to this later.

I cannot read a model
## Post #28
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-07-25T21:03:28+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Sun Jul 25, 2021 5:09 pm at Sun Jul 25, 2021 5:09 pm
>
> 
Simguy wrote: ↑Sun Jul 25, 2021 9:49 am
This isn't done but I can't look at it anymore right now. This noesis script should load most models. But without bones, weights, and sometimes the UV's are scaled wrong(?!). Also, the vertex normals are encoded somehow and I haven't figured out how. If someone wants to spring off this and finish it that would be great, otherwise I'll come back to this later.


I cannot read a model

Remove other scripts/plugins that attempt to read .bin files first before trying this one.
## Post #29
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-07-26T10:30:01+00:00
- Post Title: Re: Fate Grand Order Arcade

Number of some characters
I was not able to read 0003, 0005, 0017, 0024, 0028

svt_0001 アルトリア・ペンドラゴン
svt_0002 ネロ・クラウディウス
svt_0003
svt_0004 クー・フーリン
svt_0005
svt_0006 メドゥーサ
svt_0007 アタランテ
svt_0008 エミヤ
svt_0009 武蔵坊弁慶
svt_0010 アルトリア・ペンドラゴン〔オルタ〕
svt_0011 マシュ・キリエライト
svt_0012 ランスロット
svt_0013 清姫
svt_0014 ジル・ド・レェ
svt_0015 ジークフリート
svt_0016 ゲオルギウス
svt_0017
svt_0018 ヴラド三世
svt_0019 カーミラ
svt_0020 エリザベート・バートリー
svt_0021 ヴォルフガング・アマデウス・モーツァルト
svt_0022 ジャンヌ・ダルク
svt_0023 ジャンヌ・ダルク〔オルタ〕
svt_0024
svt_0025 マリー・アントワネット
svt_0026 シュヴァリエ・デオン
svt_0027 マルタ
svt_0028
svt_0029 ガイウス・ユリウス・カエサル
svt_0030 諸葛孔明〔エルメロイⅡ世〕
## Post #30
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2021-07-27T00:11:47+00:00
- Post Title: Re: Fate Grand Order Arcade

Ok, I tackled this again. Now it should load most files. The skeleton is in the model files but the bone names don't match, so I don't assign names. Still no bone weights or normals, and UV's are still not scaled.
[fmt_FGOA_bin.zip](https://xentaxbackup.github.io/file/20517_fmt_FGOA_bin.zip)
## Post #31
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-07-27T15:48:32+00:00
- Post Title: Re: Fate Grand Order Arcade

the skin_param is what I guess it is either bone weights or the normals and I also included the .mot files too which they appear to be animations.


 skin_param and mot.zip
(60.33 KiB) Downloaded 107 times
## Post #32
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-07-31T00:41:43+00:00
- Post Title: Re: Fate Grand Order Arcade

texture and bone, a shape key are included in obj.bin
## Post #33
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-07-31T06:10:56+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from andree ↑Tue Jul 27, 2021 11:48 pm at Tue Jul 27, 2021 11:48 pm
>
> 
the skin_param is what I guess it is either bone weights or the normals and I also included the .mot files too which they appear to be animations.
skin_param and mot.zip

.mot is animation, skin param is what tells the game only how the mesh should behave physich wise, the shape, the movement and so on
## Post #34
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-08-05T14:32:02+00:00
- Post Title: Re: Fate Grand Order Arcade

Jehovah save us !
## Post #35
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2021-08-11T07:10:50+00:00
- Post Title: Re: Fate Grand Order Arcade

I'm sorry if I'm asking a dumb question but which download on this forum is the one where I can find the models for the game
## Post #36
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2021-08-11T07:11:56+00:00
- Post Title: Re: Fate Grand Order Arcade

I've never done anything like this before and I'm just trying to make sure I got everything I need to before I get started
## Post #37
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2021-08-11T08:28:48+00:00
- Post Title: Re: Fate Grand Order Arcade

I was wondering if anyone could let me borrow some of the game models please anyone private message me if you will let me
## Post #38
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-08-11T23:07:40+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Gamer1020 ↑Wed Aug 11, 2021 4:28 pm at Wed Aug 11, 2021 4:28 pm
>
> 
I was wondering if anyone could let me borrow some of the game models please anyone private message me if you will let me
[https://drive.google.com/file/d/1Jof78a ... sp=sharing](https://drive.google.com/file/d/1Jof78avpB2Navz7eBGhyEE9u14Cm9vZ6/view?usp=sharing)
## Post #39
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2021-08-11T23:34:22+00:00
- Post Title: Re: Fate Grand Order Arcade

Thanks.
## Post #40
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2021-08-12T05:56:03+00:00
- Post Title: Re: Fate Grand Order Arcade

Does anyone know how to put this in unity or if it even does I'm not sure what to use to actually see the models I'm not sure how to do it Someone please point me in the right direction
[https://drive.google.com/file/d/1v_TlA7 ... p=drivesdk](https://drive.google.com/file/d/1v_TlA7i1blfaM1XDqCTY6W9p6tYQ1rMH/view?usp=drivesdk)
## Post #41
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2021-08-16T13:07:30+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Thu Jul 22, 2021 6:26 am at Thu Jul 22, 2021 6:26 am
>
> 
FARc is slightly modified Virtua Fighter 5 format.

Update: Added script for extracting tex container into separate TXP files. For more info about this format and Project Diva format in general see this topic.

Update 2: Added script for converting txp into dds (based on chrrox's script for first mips). All "ramp" and other small textures with weird names are BC7 textures (32x32), which are not supported by current script due to different layout, but you can convert them with rawtex. Currently supported formats from used by the game: BC1 (DXT1), BC3 (DXT5), BC4 (ATI1) and BC5 (ATI2). For BC7 see above.

Update 3: farc script simplified to handle other farc containers from the game.

Update 4: farc script updated to support zstd compression.

the script you posted work great at converting them, both textures and models, like you said the textures aren’t all mapped correctly and the rigg isn’t applied , with some tweak in blender i could more or less make some texture fit, while some other are correctly mapped from the start like the hair, or almost correct, like the body

Those efforts and work are always really appreciated
I always wish I could be of some help
## Post #42
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-08-17T14:25:30+00:00
- Post Title: Re: Fate Grand Order Arcade

Is there the person who can finish the script of noesis?
I wait for a script to be completed
## Post #43
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-08-23T14:06:15+00:00
- Post Title: Re: Fate Grand Order Arcade

Any news regarding the Noesis plugin??
## Post #44
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2021-08-23T19:44:55+00:00
- Post Title: Re: Fate Grand Order Arcade

Sorry, been busy lately. I had to drop development of the Noesis script. This format is beyond me. This update should have bones parented correctly, but its kinda hard to tell since I can't figure out how bone names are assigned. There are skin weights now but they are parented to the wrong bones, possibly a connection to how bone names are setup. Still can't figure out how UV's or vertex normals work. 

To be clear, I wash my hands of this. I encourage anyone else to pick up where I left off and finish this. Just drop me a line and tell me how you figured it out.
[fmt_FGOA_bin.zip](https://xentaxbackup.github.io/file/20664_fmt_FGOA_bin.zip)
## Post #45
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-08-24T13:25:12+00:00
- Post Title: Re: Fate Grand Order Arcade

Oh Thanks.
## Post #46
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-08-26T19:59:32+00:00
- Post Title: Re: Fate Grand Order Arcade

Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.
## Post #47
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-08-27T01:14:33+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Fri Aug 27, 2021 3:59 am at Fri Aug 27, 2021 3:59 am
>
> 
Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.

check if you have other plugins that try to read bin files and remove them
## Post #48
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2021-08-27T18:34:54+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Fri Aug 27, 2021 9:14 am at Fri Aug 27, 2021 9:14 am
>
> 
Darko wrote: ↑Fri Aug 27, 2021 3:59 am
Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.


check if you have other plugins that try to read bin files and remove them

I used a clean version of Noesis to test the plugin.
## Post #49
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2021-08-27T20:15:30+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Fri Aug 27, 2021 3:59 am at Fri Aug 27, 2021 3:59 am
>
> 
Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.

It should just work. Which one are you trying to open?
## Post #50
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-08-27T20:18:40+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Sat Aug 28, 2021 2:34 am at Sat Aug 28, 2021 2:34 am
>
> 
GDL wrote: ↑Fri Aug 27, 2021 9:14 am
Darko wrote: ↑Fri Aug 27, 2021 3:59 am
Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.


check if you have other plugins that try to read bin files and remove them


I used a clean version of Noesis to test the plugin.

noesis now has a 32 and 64 bit version, some plugins dont work with the 64 bit version it seems
## Post #51
- Username: yorunikakeru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Aug 29, 2020 6:57 pm
- Post datetime: 2021-08-28T20:55:22+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Sat Aug 28, 2021 4:18 am at Sat Aug 28, 2021 4:18 am
>
> 
check if you have other plugins that try to read bin files and remove them

Within Noesis there are a bunch of built-in bin readers such as Bujingai or EB-Binary, sorry if this is an amateur question, but as i've searched/looked up Google and then systematically delete all the seemingly irrelevant plugins that came with a clean download of Noesis, how do you "remove" those plugins that's also trying to read the bin file for this to work

Thank you, again sorry if it's an amateur question
## Post #52
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2021-10-02T05:04:37+00:00
- Post Title: Re: Fate Grand Order Arcade

isit possible to load animation data ?
## Post #53
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-10-02T19:28:03+00:00
- Post Title: Re: Fate Grand Order Arcade

They barely made it possible to unpack models with weights and barely because not all is extracted right. Including UV Map.

So how it will be able to unpack animations?

Of course it cannot.
## Post #54
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-03T05:08:38+00:00
- Post Title: Re: Fate Grand Order Arcade

The engine itself is the same as Diva and VF5, and the model standards are similar, but bone_data, mot_db, etc. do not exist, and the animation type is completely different.
## Post #55
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-10-03T22:14:50+00:00
- Post Title: Re: Fate Grand Order Arcade

I remember they mentioned that on old posts, but for the lack of interest... I guess what we can get now is all we will get.
## Post #56
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2021-10-05T02:23:46+00:00
- Post Title: Re: Fate Grand Order Arcade

I uploaded the useful folder to mega so those who come later don't need to download the whole game. Most of the models are inside "objset" folder (the character models are "obj_svt...")
(removed)

One question: Is there a workaround to unpack zstd compression without installing zstd? Mine required installing zstd using "pip install zstd", but it says I need to install Microsoft Visual C++ 14, which I don't intend to do because I'm using portable python.
## Post #57
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-10-05T02:38:46+00:00
- Post Title: Re: Fate Grand Order Arcade

The UV is something others model have, not just on the head.

I didn't need to install it. Just following how they explained it
## Post #58
- Username: JalterLover
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 16, 2021 10:14 am
- Post datetime: 2021-11-10T01:17:42+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Fri Aug 27, 2021 3:59 am at Fri Aug 27, 2021 3:59 am
>
> 
Stupid question, do i need to do something with the obj.bin?? because Noesis says: file could not be previewed.
I think I found the solution to your problem
(error that I also had)(a stupid question with a stupid answer)
the fmt_FGOA_bin script
should be put in the \plugins\python folder
if you put it in \plugins it won't let you open the .bin
(Considering we are talking about the .bin that you extracted from the farc with quickbms)

-a clean installation of noesis will not bring you any problem with the script
## Post #59
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2021-11-11T14:42:46+00:00
- Post Title: Re: Fate Grand Order Arcade

How do I extract the texture from the tex.bin? I was able to check the model with noesis and export it as obj.
## Post #60
- Username: JalterLover
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 16, 2021 10:14 am
- Post datetime: 2021-11-12T02:20:51+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Thu Nov 11, 2021 10:42 pm at Thu Nov 11, 2021 10:42 pm
>
> 
How do I extract the texture from the tex.bin? I was able to check the model with noesis and export it as obj.
the script guy said:


Update 2: Added a script to convert txp to dds (based on the chrrox script for the first mips). All the "ramps" and other small textures with strange names are BC7 (32x32) textures, which are not compatible with the current script due to a different layout, but you can convert them with rawtex. Formats currently supported by the game: BC1 (DXT1), BC3 (DXT5), BC4 (ATI1) and BC5 (ATI2). For BC7, see above.


so to extract the textures you have to use Rawtex (Raw texture previewer)
a guide:
[viewtopic.php?f=18&t=16461&hilit=rawtex](https://forum.xentax.com/viewtopic.php?f=18&t=16461&hilit=rawtex)
## Post #61
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2021-11-12T06:03:46+00:00
- Post Title: Re: Fate Grand Order Arcade

Could you tell me more about it if you want? 
I can now extract obj.bin and tex.bin by changing farc in the FGO_arcade_farc.bms script, but extracting from tex.bin in RawTexture is wrong, right? I don't know what file to input to FGO_arcade_tex.bms and FGO_arcade_txp.bms because I can't see the .tex or .txp.
## Post #62
- Username: JalterLover
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 16, 2021 10:14 am
- Post datetime: 2021-11-13T01:33:56+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Fri Nov 12, 2021 2:03 pm at Fri Nov 12, 2021 2:03 pm
>
> 
Could you tell me more about it if you want? 
I can now extract obj.bin and tex.bin by changing farc in the FGO_arcade_farc.bms script, but extracting from tex.bin in RawTexture is wrong, right? I don't know what file to input to FGO_arcade_tex.bms and FGO_arcade_txp.bms because I can't see the .tex or .txp.
we goooo
I finally know what the 3 scripts are for
so before around 12:00 am I put a message / post but it was wrong so I deleted it (in my defense I was in class so ..)
so here you have my guide
from noobs to noobs
## Post #63
- Username: JalterLover
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 16, 2021 10:14 am
- Post datetime: 2021-11-13T02:18:48+00:00
- Post Title: Re: Fate Grand Order Arcade

well this is about the textures
It is easier for me to explain it in an image so....
[https://imgur.com/a/Xmzj74v](https://imgur.com/a/Xmzj74v)
## Post #64
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-11-13T02:57:58+00:00
- Post Title: Re: Fate Grand Order Arcade

Using the tools is easy.
But fix the UV and rigging bugs with bones order is the hard part.
## Post #65
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2021-11-13T05:15:54+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Fri Nov 12, 2021 2:03 pm at Fri Nov 12, 2021 2:03 pm
>
> 
Could you tell me more about it if you want? 
I can now extract obj.bin and tex.bin by changing farc in the FGO_arcade_farc.bms script, but extracting from tex.bin in RawTexture is wrong, right? I don't know what file to input to FGO_arcade_tex.bms and FGO_arcade_txp.bms because I can't see the .tex or .txp.
Okay here is the workflow (you'll need [quickbms](http://aluigi.altervista.org/quickbms.htm) and the [quickbms script of FGOA](https://forum.xentax.com/viewtopic.php?p=176585#p176585). For [noesis](http://www.richwhitehouse.com/index.php?content=inc_projects.php&showproject=91), install the plugins by copying the *.py into \plugins\python\):
- Ignore the "_table.bin", you don't need it.
- Use the quickbms script "FGO_arcade_farc.bms" on the *.farc to get two *.bin files: "_obj.bin" and "_tex.bin".
- For the extracted "_obj.bin", use the noesis script "[fmt_FGOA_bin.py](https://forum.xentax.com/viewtopic.php?p=181634#p181634)" (Update2: The [noesis-project-diva](https://github.com/h-kidd/noesis-project-diva) can handle the *.bin files better) to view the model (and export to *.fbx).
Update1: The script can now read the textures in the "_tex.bin" file, simply put the bins in the same folder then export the "_obj.bin" into another 3D format and it will export the textures.

Now import the *.fbx into a 3D modeling program, then apply textures (actually you can skip this step by adding extension eg. ".png" at lines 237, 239, 241, 243, 248 of the the noesis script).
## Post #66
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2021-11-13T06:14:15+00:00
- Post Title: Re: Fate Grand Order Arcade

Thank you kindly for your help. 
I'm familiar with 3dcg so fixing uv and rig is not a problem.
## Post #67
- Username: JalterLover
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Oct 16, 2021 10:14 am
- Post datetime: 2021-11-14T19:42:31+00:00
- Post Title: Re: Fate Grand Order Arcade

what the hell are the ramps I just get a bunch of colored pixels
Ahhhhhhh
## Post #68
- Username: Skyguy1337
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 17, 2021 8:26 pm
- Post datetime: 2021-11-18T03:49:31+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from johnwithlenon ↑Sat Nov 13, 2021 1:15 pm at Sat Nov 13, 2021 1:15 pm
>
> 
Melvinnnn wrote: ↑Fri Nov 12, 2021 2:03 pm
Could you tell me more about it if you want? 
I can now extract obj.bin and tex.bin by changing farc in the FGO_arcade_farc.bms script, but extracting from tex.bin in RawTexture is wrong, right? I don't know what file to input to FGO_arcade_tex.bms and FGO_arcade_txp.bms because I can't see the .tex or .txp.

Ok here is the workflow (you'll need quickbms and the quickbms script of FGOA. For noesis, install the plugins by copying the *.py into \plugins\python\):
- Ignore the "_table.bin", you don't need it.
- Use the quickbms script "FGO_arcade_farc.bms" on the *.farc to get two *.bin files: "_obj.bin" and "_tex.bin".
- For the extracted "_obj.bin", use the noesis script "fmt_FGOA_bin.py" to view the model (and export to *.fbx).
- For the extracted "_tex.bin", use the quickbms script "FGO_arcade_tex.bms", you will get a bunch of unknown texture files (they are *.txp if you check the header).
- To convert these textures into *.dds, you can use the quickbms script "FGO_arcade_txp.bms", but the "__ramp" textures (which have tiny filesize) won't be converted, Spiritovod said that you can use Rawtex to convert them. Or you can use the noesis script "tex_FGOA_txp.py" (need to add the ".txp" extension to those files first).

Now import the *.fbx into a 3D modeling program, then apply textures and fix the UVs/rigging/bones.

Thank you for the guide. I've noticed that the extracted FBX (or Collada, etc) from Noesis doesnt appear to have the armature weighted to the character mesh, there's also no shape key data on the mesh itself, which is opposite to what someone else had posted earlier. Is this the case or did I miss a step someplace? I'm using Blender 2.93 just in case if that makes any difference.
## Post #69
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2021-11-18T06:17:14+00:00
- Post Title: Re: Fate Grand Order Arcade

there is no missing step,
the noesis script is incomplete, as of now, it can't import the models with the proper uv maps, weights, and shapekeys
## Post #70
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-11-18T06:43:29+00:00
- Post Title: Re: Fate Grand Order Arcade

Already mentioned that the tool doesn't unpack right the models, but they ignore what I write days ago and keep going with they "It can fully unpacked without errors!".

For what I had seeing: Nobody is interested in "fix" the python either.
Better keep to rest this thread.
## Post #71
- Username: Skyguy1337
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 17, 2021 8:26 pm
- Post datetime: 2021-11-18T14:55:03+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Thu Nov 18, 2021 2:43 pm at Thu Nov 18, 2021 2:43 pm
>
> 
Already mentioned that the tool doesn't unpack right the models, but they ignore what I write days ago and keep going with they "It can fully unpacked without errors!".

For what I had seeing: Nobody is interested in "fix" the python either.
Better keep to rest this thread.

Sorry to hear, that's definitely frustrating. It's the interwebs tho, people are only human and people can miss stuff.

On the topic of fixing the Noesis py script, I know a little bit of Python, but not enough for calls for 3D models/formats to the level of being able to help. On the Python side, a very wild stab might be to adjust the BoneClass class to add a variable for the bone weights that can save the weight values per armature/bone as a double, since weights go from 0 to 1 per vertex, and using a double to account for the decimal values between 0 and 1.
## Post #72
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-11-18T23:46:00+00:00
- Post Title: Re: Fate Grand Order Arcade

Not showing  model  it say file can,t show preview  try the  svt_0001_s01_obj.bin but nothing.
## Post #73
- Username: yukina
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 24, 2021 7:44 pm
- Post datetime: 2021-11-24T11:46:46+00:00
- Post Title: Re: Fate Grand Order Arcade

ROMDo you have
## Post #74
- Username: MonarchMonica
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 08, 2021 12:33 pm
- Post datetime: 2021-11-25T07:08:37+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Thu Jul 22, 2021 6:26 am at Thu Jul 22, 2021 6:26 am
>
> 
FARc is slightly modified Virtua Fighter 5 format.

Update: Added script for extracting tex container into separate TXP files. For more info about this format and Project Diva format in general see this topic.

Update 2: Added script for converting txp into dds (based on chrrox's script for first mips). All "ramp" and other small textures with weird names are BC7 textures (32x32), which are not supported by current script due to different layout, but you can convert them with rawtex. Currently supported formats from used by the game: BC1 (DXT1), BC3 (DXT5), BC4 (ATI1) and BC5 (ATI2). For BC7 see above.

Update 3: farc script simplified to handle other farc containers from the game.

Update 4: farc script updated to support zstd compression.
These scripts works really well, thanks a lot
## Post #75
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2021-12-11T05:55:16+00:00
- Post Title: Re: Fate Grand Order Arcade

can someone update the obj_svt files.
## Post #76
- Username: Giordyman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 19, 2021 3:05 pm
- Post datetime: 2021-12-16T15:32:44+00:00
- Post Title: Re: Fate Grand Order Arcade

Why not make a discord to discuss this better?
It would be really nice to get these models and their animations
## Post #77
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-12-16T23:14:16+00:00
- Post Title: Re: Fate Grand Order Arcade

Because they is not much interest on people with skills to begin with it.

Later is the fact that the data of the game that is around is only of Version 4.50.00, a version around 2 years or more old.

Is actually a real miracle they managed to get the data and they found a way (a bit broken) to unpack models & textures.
## Post #78
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2021-12-17T07:50:49+00:00
- Post Title: Re: Fate Grand Order Arcade

Interest has plummeted to 0 ever since the guy working on the script gave up on it and no one I'm aware of bothered to continue his work.

Until someone's willing to take up the mantle, we'll be stuck here with broken UVs and bones, heck the newest version of the script can't read Marie Antoinette's model anymore unlike the earlier version.
## Post #79
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2021-12-31T03:58:03+00:00
- Post Title: Re: Fate Grand Order Arcade

They updated the game version Data from the link on the first page.
The game data new version has add this Servants beside the already existent ones:

-Nero Bride
-The ones from Prisma
-And Nightingale.

The tool works as always with they errors, but still can load the models.
## Post #80
- Username: Enkidu115
- Rank: beginner
- Number of posts: 28
- Joined date: Sun Jan 05, 2020 5:45 pm
- Post datetime: 2022-01-01T05:50:26+00:00
- Post Title: Re: Fate Grand Order Arcade

i also found morderd, lancer artoria alter, jack the ripper, and arthur
## Post #81
- Username: fgoac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 17, 2021 5:32 pm
- Post datetime: 2022-01-01T05:54:34+00:00
- Post Title: Re: Fate Grand Order Arcade

Number of All Characters Before 2020/09/16(REVISION 47)(Ver5.51.00)

001	:	☆5	Saber	アルトリア・ペンドラゴン
002	:	☆4	Saber	ネロ・クラウディウス
003	:	☆4	Berserker	ヘラクレス
004	:	☆3	Caster	クー・フーリン
005	:	☆2	Assassin	呪腕のハサン
006	:	☆3	Rider	メドゥーサ
007	:	☆4	Archer	アタランテ
008	:	☆4	Archer	エミヤ
009	:	☆2	Lancer	武蔵坊弁慶
010	:	☆4	Saber	アルトリア・ペンドラゴン(オルタ)
011	:	☆3	Shielder	マシュ・キリエライト
012	:	☆4	Berserker	ランスロット
013	:	☆3	Berserker	清姫
014	:	☆3	Caster	ジル・ド・レェ
015	:	☆4	Saber	ジークフリート
016	:	☆2	Rider	ゲオルギウス
017	:	☆2	Assassin	ファントム・オブ・ジ・オペラ
018	:	☆5	Berserker	ヴラド三世
019	:	☆4	Assassin	カーミラ
020	:	☆4	Lancer	エリザベート・バートリー
021	:	☆1	Caster	ヴォルフガング・アマデウス・モーツァルト
022	:	☆5	Ruler	ジャンヌ・ダルク
023	:	☆5	Avenger	ジャンヌ・ダルク(オルタ)
024	:	☆2	Assassin	シャルル＝アンリ・サンソン
025	:	☆4	Rider	マリー・アントワネット
026	:	☆4	Saber	シュヴァリエ・デオン
027	:	☆4	Rider	マルタ
028	:	☆3	Rider	ブーディカ
029	:	☆3	Saber	ガイウス・ユリウス・カエサル
030	:	☆5	Caster	諸葛孔明
031	:	☆-	-	-
032	:	☆2	Berserker	カリギュラ
033	:	☆-	-	-
034	:	☆2	Lancer	レオニダス一世
035	:	☆5	Saber	アルテラ
036	:	☆-	-	-
037	:	☆-	-	-
038	:	☆-	-	-
039	:	☆1	Assassin	マタ・ハリ
040	:	☆3	Saber	ジル・ド・レェ
041	:	☆-	-	-
042	:	☆-	-	-
043	:	☆5	Archer	ギルガメッシュ
044	:	☆-	-	-
045	:	☆5	Berserker	坂田金時
046	:	☆5	Lancer	スカサハ
047	:	☆5	Caster	玉藻の前
048	:	☆-	-	-
049	:	☆5	Lancer	カルナ
050	:	☆5	Archer	アルジュナ
051	:	☆5	Saber	両儀式
052	:	☆4	Assassin	両儀式
053	:	☆4	Archer	浅上藤乃
054	:	☆5	Assassin	酒呑童子
055	:	☆4	Berserker	茨木童子
056	:	☆-	-	-
057	:	☆-	-	-
058	:	☆5	Archer	アルトリア・ペンドラゴン
059	:	☆-	-	-
060	:	☆5	Rider	フランシス・ドレイク
061	:	☆4	Caster	メディア(リリィ)
062	:	☆2	Rider	エドワード・ティーチ
063	:	☆-	-	-
064	:	☆-	-	-
065	:	☆-	-	-
066	:	☆-	-	-
067	:	☆-	-	-
068	:	☆5	Assassin	ジャック・ザ・リッパー
069	:	☆-	-	-
070	:	☆5	Saber	沖田総司
071	:	☆4	Archer	織田信長
072	:	☆5	Saber	モードレッド
073	:	☆-	-	-
074	:	☆-	-	-
075	:	☆5	Ruler	天草四郎
076	:	☆-	-	-
077	:	☆4	Rider	レオナルド・ダ・ヴィンチ
078	:	☆-	-	-
079	:	☆4	Rider	エレナ・ブラヴァツキー
080	:	☆4	Lancer	源頼光
081	:	☆4	Assassin	ニトクリス
082	:	☆-	-	-
083	:	☆5	Archer	イシュタル
084	:	☆5	Foreigner	葛飾北斎
085	:	☆4	Lancer	アルトリア・ペンドラゴン
086	:	☆-	-	-
087	:	☆3	Assassin	岡田以蔵
088	:	☆5	Saber	アーサー・ペンドラゴン
089	:	☆-	-	-
090	:	☆5	MoonCancer	BB
091	:	☆-	-	-
092	:	☆-	-	-
093	:	☆-	-	-
094	:	☆4	Berserker	ジャンヌ・ダルク(オルタ)
095	:	☆5	Saber	ネロ・クラウディウス(ブライド)
096	:	☆-	-	-
097	:	☆5	Caster	イリヤスフィール・フォン・アインツベルン
098	:	☆4	Caster	美遊・エーデルフェルト
099	:	☆4	Archer	クロエ・フォン・アインツベルン
100	:	☆5	Berserker	ナイチンゲール
## Post #82
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-01-02T12:04:51+00:00
- Post Title: Re: Fate Grand Order Arcade

I know it a dumb question  but where is the game version Data  at on the first  page.
## Post #83
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2022-01-08T09:24:08+00:00
- Post Title: Re: Fate Grand Order Arcade

I know it's probably stupid to ask but how do I go about ripping the models from the game is it anywhere on the pages and if so can someone simplify the instructions I'm kinda dumb
## Post #84
- Username: Makaboshi
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 11, 2021 3:07 pm
- Post datetime: 2022-01-08T09:25:10+00:00
- Post Title: Re: Fate Grand Order Arcade

I wanna rip the models and put them in a game called vrchat but I don't know how to rip the models nor do I know if they can go into unity
## Post #85
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-01-08T10:12:04+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Gamer1020 ↑Sat Jan 08, 2022 5:25 pm at Sat Jan 08, 2022 5:25 pm
>
> 
I wanna rip the models and put them in a game called vrchat but I don't know how to rip the models nor do I know if they can go into unity

1. No double post.

2. READ. THE. REST. OF. THE. POSTS.

Everything you ask has being answer, even how limit the unpacking is right now.
## Post #86
- Username: vergil3322
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 17, 2021 10:09 pm
- Post datetime: 2022-01-08T13:12:25+00:00
- Post Title: Re: Fate Grand Order Arcade

if you're too lazy to read just 6 pages, imagine fixing the models.
## Post #87
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-01-09T07:56:52+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from vergil3322 ↑Sat Jan 08, 2022 9:12 pm at Sat Jan 08, 2022 9:12 pm
>
> 
if you're too lazy to read just 6 pages, imagine fixing the models.

Yes  .
Because it is a nightmare to fix them!
## Post #88
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-01-10T03:14:22+00:00
- Post Title: Re: Fate Grand Order Arcade

Well, you could have the xentax discord server help you.
## Post #89
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2022-01-13T00:13:34+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Fri Dec 31, 2021 11:58 am at Fri Dec 31, 2021 11:58 am
>
> 
They updated the game version Data from the link on the first page.
The game data new version has add this Servants beside the already existent ones:

-Nero Bride
-The ones from Prisma
-And Nightingale.

The tool works as always with they errors, but still can load the models.

Other than those the newer version also has JTR, Mordred, Christmas Helena, Artoria Lancer Alter, and Proto Arthur
## Post #90
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2022-01-13T11:04:42+00:00
- Post Title: Re: Fate Grand Order Arcade

I uploaded the useful folder of version 5.51.00 to mega, the same as previous link.
I will delete version 4.50.00 soon.
## Post #91
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-01-21T22:03:27+00:00
- Post Title: Re: Fate Grand Order Arcade

Someone said that Mordred was in the new update so I bashed my head against this some more.
[https://github.com/LordDude/FGOA_objset ... GOA_bin.py](https://github.com/LordDude/FGOA_objset/blob/main/fmt_FGOA_bin.py)

Exports UV's, Normals, Vertex Colors, and Skin Bindings. Its kinda hard to test given all the characters and how everyone's skeletons are set up (IK stuff I don't understand). Don't panic if characters show up dark or they look like they're missing pieces in the viewport (Noesis displays vertex colors by default) There is a setting to change that somewhere in Data View.
## Post #92
- Username: vergil3322
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 17, 2021 10:09 pm
- Post datetime: 2022-01-21T22:37:11+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Sat Jan 22, 2022 6:03 am at Sat Jan 22, 2022 6:03 am
>
> 
Someone said that Mordred was in the new update so I bashed my head against this some more.
https://github.com/LordDude/FGOA_objset ... GOA_bin.py

Exports UV's, Normals, Vertex Colors, and Skin Bindings. Its kinda hard to test given all the characters and how everyone's skeletons are set up (IK stuff I don't understand). Don't panic if characters show up dark or they look like they're missing pieces in the viewport (Noesis displays vertex colors by default) There is a setting to change that somewhere in Data View.

I tested it on other models there are still some problems but nothing compared to before thank you.
## Post #93
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-01-21T23:01:22+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Sat Jan 22, 2022 6:03 am at Sat Jan 22, 2022 6:03 am
>
> 
Someone said that Mordred was in the new update so I bashed my head against this some more.
https://github.com/LordDude/FGOA_objset ... GOA_bin.py

Exports UV's, Normals, Vertex Colors, and Skin Bindings. Its kinda hard to test given all the characters and how everyone's skeletons are set up (IK stuff I don't understand). Don't panic if characters show up dark or they look like they're missing pieces in the viewport (Noesis displays vertex colors by default) There is a setting to change that somewhere in Data View.

a few model got errors 
and others are fine with UVs and WEIGHT
finally Jesus saved us
## Post #94
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2022-01-22T08:24:07+00:00
- Post Title: Re: Fate Grand Order Arcade

I  don't know what I'm doing wrong:



I mean, I put the script in the python script section, Noesis recognises the script but it simply doesnt load any model.
## Post #95
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-01-22T13:16:07+00:00
- Post Title: Re: Fate Grand Order Arcade

It usually required that the Noesis had to be the latest version, at least 2 months old version from today.
## Post #96
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2022-01-22T16:33:41+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Sat Jan 22, 2022 9:16 pm at Sat Jan 22, 2022 9:16 pm
>
> 
It usually required that the Noesis had to be the latest version, at least 2 months old version from today.

It´s a clean updated version downloaded from mr addult's site.
## Post #97
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-01-22T19:23:08+00:00
- Post Title: Re: Fate Grand Order Arcade

Then it is maybe because the model is incompatible.
## Post #98
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2022-01-22T19:32:29+00:00
- Post Title: Re: Fate Grand Order Arcade

Probably:

[https://www.youtube.com/watch?v=yrap6hzueI8](https://www.youtube.com/watch?v=yrap6hzueI8)
## Post #99
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2022-01-22T19:55:05+00:00
- Post Title: Re: Fate Grand Order Arcade

well from what I saw, your doing everything correct. I can't think of anything that would cause it to not load for ya, since it works fine for me.
## Post #100
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-01-22T20:03:14+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Sun Jan 23, 2022 3:32 am at Sun Jan 23, 2022 3:32 am
>
> 
Probably:

https://www.youtube.com/watch?v=yrap6hzueI8

Whats weird is it doesn't seem like its failing to read the file, its not even trying. DM me a few of those models and I'll take a look.
## Post #101
- Username: uyjulian
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Dec 10, 2015 9:04 pm
- Post datetime: 2022-01-22T21:18:17+00:00
- Post Title: Re: Fate Grand Order Arcade

The issue may be that there may be another plugin installed that conflicts with the .bin extension
## Post #102
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-01-23T01:04:08+00:00
- Post Title: Re: Fate Grand Order Arcade

Works perfectly, but there's UV problems with the "face morph" models
## Post #103
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-01-23T07:27:07+00:00
- Post Title: Re: Fate Grand Order Arcade

So far, I've seen Servants 0025 (Marie), 0054 (Shuten), 0084 (Hokusai) and 0090 (BB) cant be read by the new script
## Post #104
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-01-23T15:13:14+00:00
- Post Title: Re: Fate Grand Order Arcade

If I remember (I may it be wrong), but someone mentioned in one of the posts that each model have they own format and/or different way made. Making the plugin not being able to work always.
## Post #105
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-01-23T20:41:54+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Sun Jan 23, 2022 3:27 pm at Sun Jan 23, 2022 3:27 pm
>
> 
So far, I've seen Servants 0025 (Marie), 0054 (Shuten), 0084 (Hokusai) and 0090 (BB) cant be read by the new script

Updated: [https://github.com/LordDude/FGOA_objset ... GOA_bin.py](https://github.com/LordDude/FGOA_objset/blob/main/fmt_FGOA_bin.py)

Sorry for the "Whack-a-mole" approach to bug-fixing, That's just how I know how to do things. 

Apparently some files (Like BB) have more then one model inside.

> Reply from andree ↑Sun Jan 23, 2022 9:04 am at Sun Jan 23, 2022 9:04 am
>
> 
Works perfectly, but there's UV problems with the "face morph" models

That's intentional on my part. I know Noesis has a way to setup morph targets but the plugin is unwieldy enough so I just left them as separate models for people to set them up on their own.
## Post #106
- Username: fgoac
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 17, 2021 5:32 pm
- Post datetime: 2022-02-06T20:35:35+00:00
- Post Title: Re: Fate Grand Order Arcade

Done
## Post #107
- Username: LeArcanist
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 23, 2022 9:59 pm
- Post datetime: 2022-02-23T14:43:52+00:00
- Post Title: Re: Fate Grand Order Arcade

Guys I'm kinda a newbie here....

Which obj_svt belongs to eresh?
## Post #108
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-02-23T16:38:19+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from LeArcanist ↑Wed Feb 23, 2022 10:43 pm at Wed Feb 23, 2022 10:43 pm
>
> 
Guys I'm kinda a newbie here....

Which obj_svt belongs to eresh?

Sorry, you're wasting your time. Eresh isn't in the current file dump. Wait for them to dump a new version.
## Post #109
- Username: SecaProject
- Rank: beginner
- Number of posts: 31
- Joined date: Wed Apr 11, 2012 1:48 am
- Post datetime: 2022-03-08T23:01:33+00:00
- Post Title: Re: Fate Grand Order Arcade

Hi there!
I was working on a script for blender. I can load all the objects in the model files and bones are ordered right, but I can't load them in the right position due to how blender works.
Could I ask what state the latest available script is in and what it can do? Currently I can load everything except the textures, which I still don't know how they work, and the position of the bones. I haven't implemented the weights yet, but it's easy.
## Post #110
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-13T09:18:08+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from SecaProject ↑Wed Mar 09, 2022 7:01 am at Wed Mar 09, 2022 7:01 am
>
> 
Hi there!
I was working on a script for blender. I can load all the objects in the model files and bones are ordered right, but I can't load them in the right position due to how blender works.
Could I ask what state the latest available script is in and what it can do? Currently I can load everything except the textures, which I still don't know how they work, and the position of the bones. I haven't implemented the weights yet, but it's easy.

From my understanding, the latest script is able to get the uvs and models out fairly nicely. However, it struggles with bone order and weights. As for textures, they need to be applied in blender after using the current script, as they wont show up in noesis
## Post #111
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-13T14:01:55+00:00
- Post Title: Re: Fate Grand Order Arcade

Bones and weight are perfectly fine actually. 

it's just that each model has 2 skeletons, one is the common skeleton that contains the basic bones, the other skeleton handles the additional bones such as physics and adjustment bones.

The thing with the additional bones is that it's not parented to the common skeleton. For example, hair bones are parented to head_m (additional bone) instead of head (common bone).  head_m is a child bone to SUB SKEL (root bone for the additional skeleton) while head is a child to neck. 

[https://i.imgur.com/tb7EEie.png](https://i.imgur.com/tb7EEie.png)

But if you reorder the skeletons with the common skeleton on top of the additional skeleton and make head_m a child to head, then you get a perfectly working head bone and weights.

[https://i.imgur.com/Rzppvp0.png](https://i.imgur.com/Rzppvp0.png)

This is pretty much how I do it. Dunno about the others who already did their porting work like those available in GMOD.
## Post #112
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-13T16:28:29+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Sun Mar 13, 2022 10:01 pm at Sun Mar 13, 2022 10:01 pm
>
> 
Bones and weight are perfectly fine actually. 

it's just that each model has 2 skeletons, one is the common skeleton that contains the basic bones, the other skeleton handles the additional bones such as physics and adjustment bones.

The thing with the additional bones is that it's not parented to the common skeleton. For example, hair bones are parented to head_m (additional bone) instead of head (common bone).  head_m is a child bone to SUB SKEL (root bone for the additional skeleton) while head is a child to neck. 

https://i.imgur.com/tb7EEie.png

But if you reorder the skeletons with the common skeleton on top of the additional skeleton and make head_m a child to head, then you get a perfectly working head bone and weights.

https://i.imgur.com/Rzppvp0.png

This is pretty much how I do it. Dunno about the others who already did their porting work like those available in GMOD.

Alright sorry, I only discovered this yesterday. I'm currently using blender, would this be correct? Do note I have figured out a way to get the skeleton acting normally, but its a lot more complicated than what you've suggested.



adawd.PNG (25.7 KiB) Viewed 307 times
## Post #113
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-13T16:39:23+00:00
- Post Title: Re: Fate Grand Order Arcade

nvm I misunderstood. I understand what you mean now, thanks
## Post #114
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-14T16:09:23+00:00
- Post Title: Re: Fate Grand Order Arcade

I’d like to ask when 5.51 released? Also, is saber lancer within the game files?
## Post #115
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-03-14T16:55:52+00:00
- Post Title: Re: Fate Grand Order Arcade

The official updates are listed here:

[https://arcade.fate-go.jp/info/category/update/](https://arcade.fate-go.jp/info/category/update/)

However, as far as I can tell none of them mention version numbers.
## Post #116
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-15T03:38:39+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from cybertron231 ↑Tue Mar 15, 2022 12:09 am at Tue Mar 15, 2022 12:09 am
>
> 
I’d like to ask when 5.51 released? Also, is saber lancer within the game files?

5.51 is up to Nightingale's release so Artoria Alter Lancer is included but not the Non-Alter version
## Post #117
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-15T04:36:18+00:00
- Post Title: Re: Fate Grand Order Arcade

Mannn, apparently someone might've gotten 8.0 or something but its in a discord somewhere
## Post #118
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-03-15T07:53:11+00:00
- Post Title: Re: Fate Grand Order Arcade

I read that from the page source and apparently he/she retract and erase every clue he/she was on that page. Worst of all is that the data was encrypted with AES.
## Post #119
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-15T13:52:09+00:00
- Post Title: Re: Fate Grand Order Arcade

I actually think they might not have retracted, but they were banned, I commented on the thread a day ago and I’ve been banned for abusive behaviour by the owner of the thread. Btw all I did was say is I was disappointed by this
## Post #120
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-03-15T14:31:40+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Tue Mar 15, 2022 3:53 pm at Tue Mar 15, 2022 3:53 pm
>
> 
I read that from the page source and apparently he/she retract and erase every clue he/she was on that page. Worst of all is that the data was encrypted with AES.

I think that's been the case since the first unencrypted release, someone out there has the decryption tools and is not willing to share them, as for the 8.xx files I wish I had saved the pics of the files that user posted to try and "google" the filenames to see if I could fine them somewhere out there.
## Post #121
- Username: vergil3322
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 17, 2021 10:09 pm
- Post datetime: 2022-03-15T15:52:45+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from cybertron231 ↑Tue Mar 15, 2022 9:52 pm at Tue Mar 15, 2022 9:52 pm
>
> 
I actually think they might not have retracted, but they were banned, I commented on the thread a day ago and I’ve been banned for abusive behaviour by the owner of the thread. Btw all I did was say is I was disappointed by this

i got the same ban but without saying anything
## Post #122
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-03-15T16:09:11+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Tue Mar 15, 2022 10:31 pm at Tue Mar 15, 2022 10:31 pm
>
> 
I think that's been the case since the first unencrypted release, someone out there has the decryption tools and is not willing to share them, as for the 8.xx files I wish I had saved the pics of the files that user posted to try and "google" the filenames to see if I could fine them somewhere out there.

Yes. Specially when with the 8.xx they may it be more character that many here we want.

On my case now I want more the last one were Gramps is add, but for that I may have to wait years
## Post #123
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-15T17:31:15+00:00
- Post Title: Re: Fate Grand Order Arcade

i do want Setanta and Nagiko

So i'm hoping someone does upload the latest decrypted dump
## Post #124
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-15T18:00:57+00:00
- Post Title: Re: Fate Grand Order Arcade

From research, apparently someone might've bought discs of the game sometime last year.
## Post #125
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-03-15T19:12:11+00:00
- Post Title: Re: Fate Grand Order Arcade

This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.
[FGO_arcade_texbin.zip](https://xentaxbackup.github.io/file/21951_FGO_arcade_texbin.zip)
## Post #126
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-15T20:22:01+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Wed Mar 16, 2022 3:12 am at Wed Mar 16, 2022 3:12 am
>
> 
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.

While the bms script does work, Noesis can't seem to read the output .txp files? 

[https://i.imgur.com/hw2m0kM.png](https://i.imgur.com/hw2m0kM.png)
## Post #127
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-03-15T20:54:19+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Wed Mar 16, 2022 4:22 am at Wed Mar 16, 2022 4:22 am
>
> 
Simguy wrote: ↑Wed Mar 16, 2022 3:12 am
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.


While the bms script does work, Noesis can't seem to read the output .txp files? 

https://i.imgur.com/hw2m0kM.png

I forgot I modified the original tex_FGOA_txp script. My bad.
[tex_FGOA_txp.zip](https://xentaxbackup.github.io/file/21953_tex_FGOA_txp.zip)
## Post #128
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2022-03-15T21:12:53+00:00
- Post Title: Re: Fate Grand Order Arcade

edit
## Post #129
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-03-15T22:04:23+00:00
- Post Title: Re: Fate Grand Order Arcade

I've updated txp bms script for converting textures to dds in [my base post](https://forum.xentax.com/viewtopic.php?p=176585#p176585) with support for BC7 textures ("ramp"). I think that their names are color palettes for gradients, used in them, with probably transparency flag - for example, ramp01000000ffffff would be 256x4 black-to-white gradient.
## Post #130
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-03-16T04:02:59+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Tue Mar 15, 2022 10:31 pm at Tue Mar 15, 2022 10:31 pm
>
> 
I think that's been the case since the first unencrypted release, someone out there has the decryption tools and is not willing to share them, as for the 8.xx files I wish I had saved the pics of the files that user posted to try and "google" the filenames to see if I could fine them somewhere out there.

Oh I just notice that luckyly Chrome App "save" the image as everytime I load that page it load the image.
Here are the Data File name:

```
DISC_01_03 0 KB SDEJ_8.00.00_20210714154904_0_0_30170.app
SDEJ_ACA.icf
DISC_02_03 0 KB SDEJ_8.00.00_20210714154904_0_30170_31992.app
DISC_03_03 0 KB SDEJ_8.00.00_20210714154904_0_62162_14717.app
ACA_0071.52.01_20210728145518_0.pack
SDEJ_8.10.00_20210806112905_1_8.00.00.app
SDEJ_8.20.00_20210915153738_1_8.00.00.app
SDEJ_8.30.00_20211101132404_2_8.20.00.app
SDEJ_8.40.00_20211202173103_2_8.20.00.app

```

I did search them in both Google, Bing & Yandex and got absolutely NO result.
## Post #131
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-16T04:26:15+00:00
- Post Title: Re: Fate Grand Order Arcade

best course of action is to ask the guy who shared the screenshots to that site

though i'd rather leave him be,
## Post #132
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-16T04:41:02+00:00
- Post Title: Re: Fate Grand Order Arcade

Wait a sec. Guys, the guy who has 8.00 has already been on this forum. His username is stamley213, he's posted here twice. Yes, this is the same person who sent those images
## Post #133
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-16T06:06:56+00:00
- Post Title: Re: Fate Grand Order Arcade

Response:
"I will not upload any file before I decrypted it."
"And all the 8.00 app, I dump it myself, you can get it on the net"

It's poor translation, but from what I understand, they want to decrypt it first before uploading any files. If anyone has info on this process for him you can tell me and ill pass it onto him.
## Post #134
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-03-16T06:45:22+00:00
- Post Title: Re: Fate Grand Order Arcade

Uh, dude the info is on the internet. They are hundreds of tutorial how get an AES, the big problem is that it varied from game to game to actually get the AES of the game, making some completely impossible to get.

> Reply from cybertron231 ↑Wed Mar 16, 2022 12:41 pm at Wed Mar 16, 2022 12:41 pm
>
> 
Wait a sec. Guys, the guy who has 8.00 has already been on this forum. His username is stamley213, he's posted here twice. Yes, this is the same person who sent those images
Then why not ask here? This page is made for unpack stuff around for years.
## Post #135
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-16T07:03:17+00:00
- Post Title: Re: Fate Grand Order Arcade

He had a file he provided me with, it was a file from 6.21.0 apparently

As for why he didn’t ask here, I’m not sure. I asked him whether he had ever participated here but he never answered.
## Post #136
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-03-16T07:38:15+00:00
- Post Title: Re: Fate Grand Order Arcade

Not an expert but: I highly doubt an AES key would be inside an encrypted file (AES being the most secure encryption method that would be a rookie mistake), UE4 AES keys are inside the EXE for example which would theoretically be more secure(?). Also how does he know that the files are in fact encrypted with AES? Based on the file names in that screenshot he posted and the name of that sample I think these are delta patches (which may lead to the encryption confusion) which are (probably) useless on their own without the original file they are patching.
## Post #137
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-03-16T11:39:21+00:00
- Post Title: Re: Fate Grand Order Arcade

This kind of arcades stuff is done in around the same way as for consoles, which means you can't decrypt anything from outside (disk/HDD/whatever), only dump already decrypted files from the platform (which is actually PC with a few adjustments in this case). That's if you don't have all required platform specific up-to-date keys, obviously, and you can reverse them only from platform, not from data itself. A good example are encrypted eappx Windows packages or pkg for PS, which you can freely download from official servers, but you can do nothing with them unless you install them on respective platform, where they will be decrypted.

So please stop those speculations, it will not lead you anywhere. Also, if I remember correctly, posting files like that - encrypted or not - is prohibited by forum rules, unless you want Sega to send some dmca here.
## Post #138
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-16T13:04:33+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Wed Mar 16, 2022 7:39 pm at Wed Mar 16, 2022 7:39 pm
>
> 
This kind of arcades stuff is done in around the same way as for consoles, which means you can't decrypt anything from outside (disk/HDD/whatever), only dump already decrypted files from the platform (which is actually PC with a few adjustments in this case). That's if you don't have all required platform specific up-to-date keys, obviously, and you can reverse them only from platform, not from data itself. A good example are encrypted eappx Windows packages or pkg for PS, which you can freely download from official servers, but you can do nothing with them unless you install them on respective platform, where they will be decrypted.

So please stop those speculations, it will not lead you anywhere. Also, if I remember correctly, posting files like that - encrypted or not - is prohibited by forum rules, unless you want Sega to send some dmca here.

Alright, it’s gone
## Post #139
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2022-03-16T15:11:35+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Wed Mar 16, 2022 3:38 pm at Wed Mar 16, 2022 3:38 pm
>
> 
Not an expert but: I highly doubt an AES key would be inside an encrypted file (AES being the most secure encryption method that would be a rookie mistake), UE4 AES keys are inside the EXE for example which would theoretically be more secure(?). Also how does he know that the files are in fact encrypted with AES? Based on the file names in that screenshot he posted and the name of that sample I think these are delta patches (which may lead to the encryption confusion) which are (probably) useless on their own without the original file they are patching.

Are you able to parent the bones properly in the script? thats the only thing keeping this script from being perfect

I would also be willing to throw money at a kofi or some other kind of donation if you are succesful in doing so, not chump change either.
## Post #140
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-03-16T19:13:46+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from takoyaki111 ↑Wed Mar 16, 2022 11:11 pm at Wed Mar 16, 2022 11:11 pm
>
> 
Simguy wrote: ↑Wed Mar 16, 2022 3:38 pm
Not an expert but: I highly doubt an AES key would be inside an encrypted file (AES being the most secure encryption method that would be a rookie mistake), UE4 AES keys are inside the EXE for example which would theoretically be more secure(?). Also how does he know that the files are in fact encrypted with AES? Based on the file names in that screenshot he posted and the name of that sample I think these are delta patches (which may lead to the encryption confusion) which are (probably) useless on their own without the original file they are patching.


Are you able to parent the bones properly in the script? thats the only thing keeping this script from being perfect

I would also be willing to throw money at a kofi or some other kind of donation if you are succesful in doing so, not chump change either.

I appreciate the offer but I don't want donations or anything.
I'd rather the script load models the way they are and you do whatever you need to in blender or something. Its not that much more work but its accurate.
## Post #141
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-19T02:58:26+00:00
- Post Title: Re: Fate Grand Order Arcade

So for voice lines in this game, where are they located and how would i extract them?
## Post #142
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-19T05:01:37+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from cybertron231 ↑Sat Mar 19, 2022 10:58 am at Sat Mar 19, 2022 10:58 am
>
> 
So for voice lines in this game, where are they located and how would i extract them?

rom/sound/voice

they're in .ogg format, no need to convert them or anything. They're just there, already ready for use.
same with the music files.
## Post #143
- Username: cybertron231
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 26, 2022 7:43 am
- Post datetime: 2022-03-19T17:37:24+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Sat Mar 19, 2022 1:01 pm at Sat Mar 19, 2022 1:01 pm
>
> 
cybertron231 wrote: ↑Sat Mar 19, 2022 10:58 am
So for voice lines in this game, where are they located and how would i extract them?


rom/sound/voice

they're in .ogg format, no need to convert them or anything. They're just there, already ready for use.
same with the music files.
Oh that's really useful lol, thanks
## Post #144
- Username: Devsterman12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 15, 2018 5:06 am
- Post datetime: 2022-03-27T16:10:29+00:00
- Post Title: Re: Fate Grand Order Arcade

Just got finished ripping some of the models I want, stupid question but is there a decent guide on how to fix the UV's and rigging in Blender?
## Post #145
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-03-27T19:49:29+00:00
- Post Title: Re: Fate Grand Order Arcade

The UVs are already fixed with the latest Noesis script, so you dont have to worry about that one.
## Post #146
- Username: Devsterman12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 15, 2018 5:06 am
- Post datetime: 2022-03-27T19:58:33+00:00
- Post Title: Re: Fate Grand Order Arcade

That's a relief, now I just have to adjust all the bones for Proto Arthur and figure out what to do with the extra faces.
## Post #147
- Username: Devsterman12
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 15, 2018 5:06 am
- Post datetime: 2022-03-27T21:17:06+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Devsterman12 ↑Mon Mar 28, 2022 3:58 am at Mon Mar 28, 2022 3:58 am
>
> 
That's a relief, now I just have to adjust all the bones for Proto Arthur and figure out what to do with the extra faces.

Just tried using Cat's plugin for Blender, it set the bones perfectly from what I can tell.
## Post #148
- Username: gunerkayber
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 25, 2021 12:28 am
- Post datetime: 2022-04-17T14:54:26+00:00
- Post Title: Re: Fate Grand Order Arcade

I have a noob question. 

Who can i find out which textures goes where? For example which texture is for the specular,etc
## Post #149
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-04-25T21:00:10+00:00
- Post Title: Re: Fate Grand Order Arcade

I guess that's one way to do it. Releasing it so there can be more eyes on it and more people can try seems like a better idea. I wouldn't have even known about the game if this thread wasn't here.
## Post #150
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2022-04-26T13:29:32+00:00
- Post Title: Re: Fate Grand Order Arcade

Well, months ago I got a private message about my uploaded data files which I reuploaded from emuline (I'm good because he then blamed the guy on emuline and tried to contact them).
This could be the reason why there's no new files, I mean the guy on emuline stops updating it.
## Post #151
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-04-26T16:25:05+00:00
- Post Title: Re: Fate Grand Order Arcade

Geez that looks like if they were a mafia. The only it need for end it was "if you don't, you will end sleeping with the fish".

But that is how some of the rules here are kind weird: you cannot post data of games, but if the game is from a source that is almost impossible to get and either buy?

Still, we can send the data on DM without saying anything: after all the original data was from Discord, not from emuline. hell, from a Chinese Discord.
## Post #152
- Username: mark12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 02, 2018 4:44 pm
- Post datetime: 2022-04-27T06:05:15+00:00
- Post Title: Re: Fate Grand Order Arcade

they can't sell/trade the assets if the files are publicly available
## Post #153
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-04-27T08:18:53+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Wed Apr 27, 2022 12:25 am at Wed Apr 27, 2022 12:25 am
>
> 
Geez that looks like if they were a mafia. The only it need for end it was "if you don't, you will end sleeping with the fish".

But that is how some of the rules here are kind weird: you cannot post data of games, but if the game is from a source that is almost impossible to get and either buy?

Still, we can send the data on DM without saying anything: after all the original data was from Discord, not from emuline. hell, from a Chinese Discord.

Like I said, we can wait for the game's service to finish first.

After all, if SEGA finds out about the leak, they would possibly make all future update files harder for these dataminers to obtain and decrypt.
Better be safe than sorry
## Post #154
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-04-27T09:12:29+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Wed Apr 27, 2022 4:18 pm at Wed Apr 27, 2022 4:18 pm
>
> 
Like I said, we can wait for the game's service to finish first.

After all, if SEGA finds out about the leak, they would possibly make all future update files harder for these dataminers to obtain and decrypt.
Better be safe than sorry

Right.
No.
They still and still leak the data in somewhere of the internet.
But people should learn not ask here for data and just spam were the source is.
As for this thread: back to be death. No data, no people care to keep fixing no nothing.
## Post #155
- Username: f2dr0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 15, 2022 5:12 am
- Post datetime: 2022-04-27T13:06:16+00:00
- Post Title: Re: Fate Grand Order Arcade

Could we even extract the files  (example get more models) of a newer fgo arcade version if someone has it? Or we need the key to do that?
## Post #156
- Username: Boeing747
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 19, 2022 9:01 am
- Post datetime: 2022-05-02T19:39:33+00:00
- Post Title: Re: Fate Grand Order Arcade

Does anyone know how to open the .mot files, I somehow got the mot_.farc files into .mot files.
## Post #157
- Username: Boeing747
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Apr 19, 2022 9:01 am
- Post datetime: 2022-05-02T19:59:32+00:00
- Post Title: Re: Fate Grand Order Arcade

Here is the file if it helps: [https://www.mediafire.com/file/xrkc2g8t ... 1.mot/file](https://www.mediafire.com/file/xrkc2g8t3wg7bfe/SVT_0001_S01_APL_1.mot/file)
## Post #158
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2022-05-24T04:43:55+00:00
- Post Title: Re: Fate Grand Order Arcade

Anything new? has anybody gotten hold of the new version
## Post #159
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2022-05-27T06:23:42+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Arielainthere ↑Tue May 24, 2022 12:43 pm at Tue May 24, 2022 12:43 pm
>
> 
Anything new? has anybody gotten hold of the new version

As far as I know, the people who might have the newer version are still keeping it private.
## Post #160
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-05-27T21:12:39+00:00
- Post Title: Re: Fate Grand Order Arcade

They wouldn't post on the page were it was. Now they're erasing comments there and anyone that have a question they actually make fun of it.

Seriously, how does that page roll? No one can say nothing and even if it is question with no offense the user get banned or comment erase?.

In my case I will wait. They just add Moriarty beside Iskandar. I can wait a year or two for get they models.

ADD:
They just update the data, but they add only the update in .APP format. And based on this [viewtopic.php?f=16&t=21673&p=183638&hilit=.app#p183638](https://forum.xentax.com/viewtopic.php?f=16&t=21673&p=183638&hilit=.app#p183638)  we're screw.
## Post #161
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-06-02T15:49:07+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Sat May 28, 2022 5:12 am at Sat May 28, 2022 5:12 am
>
> 
They wouldn't post on the page were it was. Now they're erasing comments there and anyone that have a question they actually make fun of it.

Seriously, how does that page roll? No one can say nothing and even if it is question with no offense the user get banned or comment erase?.

In my case I will wait. They just add Moriarty beside Iskandar. I can wait a year or two for get they models.

ADD:
They just update the data, but they add only the update in .APP format. And based on this viewtopic.php?f=16&t=21673&p=183638&hilit=.app#p183638  we're screw.

There's a lot of talented people around here, I'm sure someone will figure something out
## Post #162
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-06-02T16:31:05+00:00
- Post Title: Re: Fate Grand Order Arcade

@GDL: No, it's technically impossible, which was already explained on previous page.
## Post #163
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-06-02T16:52:06+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Fri Jun 03, 2022 12:31 am at Fri Jun 03, 2022 12:31 am
>
> 
@GDL: No, it's technically impossible, which was already explained on previous page.
## Post #164
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-06-02T16:53:17+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Thu Jun 02, 2022 11:49 pm at Thu Jun 02, 2022 11:49 pm
>
> 
There's a lot of talented people around here, I'm sure someone will figure something out
Did you took time for actually READ the post I link? Just like Spiritovod say it: it is IMPOSSIBLE to unpack. We will never get tools for unpack something that is clearly out of reach of anyone from here.

I mostly post the edit for clarify that will be impossible to get new updates forever.
## Post #165
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-06-03T02:08:29+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Thu Jun 02, 2022 11:49 pm at Thu Jun 02, 2022 11:49 pm
>
> 

There's a lot of talented people around here, I'm sure someone will figure something out

tldr; Unless someone here has the actual arcade machine, it's impossible to decrypt it.
## Post #166
- Username: Yun666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 10, 2022 5:07 pm
- Post datetime: 2022-07-10T09:43:09+00:00
- Post Title: Re: Fate Grand Order Arcade

Is there a new unpack file？
## Post #167
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-11T17:22:55+00:00
- Post Title: Re: Fate Grand Order Arcade

So it looks like a couple new files have been shared:

SDEJ_5.53.00_20200806201952_2_5.51.00.vhd
SDEJ_8.40.00_20211202173103_2_8.20.00.vhd

I'm not entirely sure but I think they are unencrypted, I can see the file structure and a bunch of *.farc files inside which means we could get the updates from both files.
## Post #168
- Username: f2dr0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 15, 2022 5:12 am
- Post datetime: 2022-07-11T21:46:56+00:00
- Post Title: Re: Fate Grand Order Arcade

You can open that 8.40 file?
## Post #169
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-11T23:07:56+00:00
- Post Title: Re: Fate Grand Order Arcade

I havent been able to mount it but I can see all the files using a hex editor
## Post #170
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2022-07-11T23:25:48+00:00
- Post Title: Re: Fate Grand Order Arcade

Differential Virtual Hard Disks. Semi-useless without the parent disk. You could probably manually pull out new files but that's it and it seems really hard.
## Post #171
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-13T14:46:18+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Tue Jul 12, 2022 7:25 am at Tue Jul 12, 2022 7:25 am
>
> 
Differential Virtual Hard Disks. Semi-useless without the parent disk. You could probably manually pull out new files but that's it and it seems really hard.

Probably, I was able to extract some files by just finding all the "FARc" headers and copy-pasting that chunk of data to a new file and use the scripts from spirit void in the first page of this thread to extract them, like I said, nothing seems to be encrypted and as far as I know the FARc files don't include the length of the file itself to be able to parse it without mounting the vhd, which I havent been able to do, but all the data is available, this is a list of some of the contents I found in the VHDs:

SDEJ_5.53.00_20200806201952_2_5.51.00.vhd

```
svt_action_event.bin
svt_exp.bin
svt_limit.bin
svt_asset.bin
svt_weapon.bin
svt_action.bin
svt_ascension_material.bin
svt_holo_stack_ratio.bin
svt_ascension_table.bin
svt_skill_synthesis_table.bin
svt_exceed_table.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_0099_obj.bin
svt_0099_tex.bin

```

SDEJ_8.40.00_20211202173103_2_8.20.00.vhd

```
svt_0129.bin
svt_0137.bin
svt_0144.bin
svt_8081.bin
svt_cutin_list.bin
svt_action_event.bin
svt_exp.bin
svt_limit.bin
svt_asset.bin
svt_weapon.bin
svt_action.bin
svt_ascension_material.bin
svt_holo_stack_ratio.bin
svt_ascension_table.bin
svt_skill_synthesis_table.bin
svt_exceed_table.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_cutin_list.bin
svt_action.bin
svt_asset.bin
svt_weapon.bin
svt_0120.bin
svt_win.bin
svt_ascension_material.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_exp.bin
svt_limit.bin
svt_action_event.bin
svt_ascension_table.bin
svt_exceed_table.bin
svt_skill_synthesis_table.bin
svt_0120_obj.bin
svt_0120_tex.bin
svt_0137_obj.bin
svt_0137_tex.bin
svt_0144_obj.bin
svt_0144_tex.bin
svt_8081_obj.bin
svt_8081_tex.bin
svt_0060_s07_obj.bin
svt_0060_s07_tex.bin
svt_0111_s01_obj.bin
svt_0111_s01_tex.bin
svt_0111_s02_obj.bin
svt_0111_s02_tex.bin
svt_0111_s03_obj.bin
svt_0111_s03_tex.bin
svt_0111_s99_obj.bin
svt_0111_s99_tex.bin
svt_0120_s01_obj.bin
svt_0120_s01_tex.bin
svt_0120_s02_obj.bin
svt_0120_s02_tex.bin
svt_0120_s03_obj.bin
svt_0120_s03_tex.bin
svt_0120_s04_obj.bin
svt_0120_s04_tex.bin
svt_0129_s01_obj.bin
svt_0129_s01_tex.bin
svt_0129_s02_obj.bin
svt_0129_s02_tex.bin
svt_0129_s03_obj.bin
svt_0129_s03_tex.bin
svt_0137_s01_obj.bin
svt_0137_s01_tex.bin
svt_0144_s01_obj.bin
svt_0144_s01_tex.bin
svt_0144_s02_obj.bin
svt_0144_s02_tex.bin
svt_0144_s03_obj.bin
svt_0144_s03_tex.bin
svt_8081_s01_obj.bin
svt_8081_s01_tex.bin
svt_8090_s01_obj.bin
svt_8090_s01_tex.bin
svt_8094_s01_obj.bin
svt_8094_s01_tex.bin
svt_8095_s01_obj.bin
svt_8095_s01_tex.bin
svt_8096_s01_obj.bin
svt_8096_s01_tex.bin

```

[farc.jpg](https://xentaxbackup.github.io/file/22480_farc.jpg)
## Post #172
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2022-07-13T17:39:46+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Wed Jul 13, 2022 10:46 pm at Wed Jul 13, 2022 10:46 pm
>
> 
Simguy wrote: ↑Tue Jul 12, 2022 7:25 am
Differential Virtual Hard Disks. Semi-useless without the parent disk. You could probably manually pull out new files but that's it and it seems really hard.


Probably, I was able to extract some files by just finding all the "FARc" headers and copy-pasting that chunk of data to a new file and use the scripts from spirit void in the first page of this thread to extract them, like I said, nothing seems to be encrypted and as far as I know the FARc files don't include the length of the file itself to be able to parse it without mounting the vhd, which I havent been able to do, but all the data is available, this is a list of some of the contents I found in the VHDs:

SDEJ_5.53.00_20200806201952_2_5.51.00.vhd
Code: Select allsvt_cutin_list.bin
svt_action_event.bin
svt_exp.bin
svt_limit.bin
svt_asset.bin
svt_weapon.bin
svt_action.bin
svt_ascension_material.bin
svt_holo_stack_ratio.bin
svt_ascension_table.bin
svt_skill_synthesis_table.bin
svt_exceed_table.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_0099_obj.bin
svt_0099_tex.bin

SDEJ_8.40.00_20211202173103_2_8.20.00.vhd
Code: Select allsvt_0111.bin
svt_0129.bin
svt_0137.bin
svt_0144.bin
svt_8081.bin
svt_cutin_list.bin
svt_action_event.bin
svt_exp.bin
svt_limit.bin
svt_asset.bin
svt_weapon.bin
svt_action.bin
svt_ascension_material.bin
svt_holo_stack_ratio.bin
svt_ascension_table.bin
svt_skill_synthesis_table.bin
svt_exceed_table.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_cutin_list.bin
svt_action.bin
svt_asset.bin
svt_weapon.bin
svt_0120.bin
svt_win.bin
svt_ascension_material.bin
svt_noble_phantasm.bin
svt_skill.bin
svt_support_skill.bin
svt_exp.bin
svt_limit.bin
svt_action_event.bin
svt_ascension_table.bin
svt_exceed_table.bin
svt_skill_synthesis_table.bin
svt_0120_obj.bin
svt_0120_tex.bin
svt_0137_obj.bin
svt_0137_tex.bin
svt_0144_obj.bin
svt_0144_tex.bin
svt_8081_obj.bin
svt_8081_tex.bin
svt_0060_s07_obj.bin
svt_0060_s07_tex.bin
svt_0111_s01_obj.bin
svt_0111_s01_tex.bin
svt_0111_s02_obj.bin
svt_0111_s02_tex.bin
svt_0111_s03_obj.bin
svt_0111_s03_tex.bin
svt_0111_s99_obj.bin
svt_0111_s99_tex.bin
svt_0120_s01_obj.bin
svt_0120_s01_tex.bin
svt_0120_s02_obj.bin
svt_0120_s02_tex.bin
svt_0120_s03_obj.bin
svt_0120_s03_tex.bin
svt_0120_s04_obj.bin
svt_0120_s04_tex.bin
svt_0129_s01_obj.bin
svt_0129_s01_tex.bin
svt_0129_s02_obj.bin
svt_0129_s02_tex.bin
svt_0129_s03_obj.bin
svt_0129_s03_tex.bin
svt_0137_s01_obj.bin
svt_0137_s01_tex.bin
svt_0144_s01_obj.bin
svt_0144_s01_tex.bin
svt_0144_s02_obj.bin
svt_0144_s02_tex.bin
svt_0144_s03_obj.bin
svt_0144_s03_tex.bin
svt_8081_s01_obj.bin
svt_8081_s01_tex.bin
svt_8090_s01_obj.bin
svt_8090_s01_tex.bin
svt_8094_s01_obj.bin
svt_8094_s01_tex.bin
svt_8095_s01_obj.bin
svt_8095_s01_tex.bin
svt_8096_s01_obj.bin
svt_8096_s01_tex.bin

can you upload the files or teach us how to extract from vhd ?
## Post #173
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-07-13T18:07:05+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Wed Jul 13, 2022 10:46 pm at Wed Jul 13, 2022 10:46 pm
>
> 

Probably, I was able to extract some files by just finding all the "FARc" headers and copy-pasting that chunk of data to a new file and use the scripts from spirit void in the first page of this thread to extract them, like I said, nothing seems to be encrypted and as far as I know the FARc files don't include the length of the file itself to be able to parse it without mounting the vhd, which I havent been able to do, but all the data is available, this is a list of some of the contents I found in the VHDs:

bruh I just did what you said and couldnt believe that a simple copy-pasting on a hex editor actually works
thank you for the tip
## Post #174
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-13T18:37:58+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Thu Jul 14, 2022 2:07 am at Thu Jul 14, 2022 2:07 am
>
> 
GDL wrote: ↑Wed Jul 13, 2022 10:46 pm

Probably, I was able to extract some files by just finding all the "FARc" headers and copy-pasting that chunk of data to a new file and use the scripts from spirit void in the first page of this thread to extract them, like I said, nothing seems to be encrypted and as far as I know the FARc files don't include the length of the file itself to be able to parse it without mounting the vhd, which I havent been able to do, but all the data is available, this is a list of some of the contents I found in the VHDs:


bruh I just did what you said and couldnt believe that a simple copy-pasting on a hex editor actually works
thank you for the tip

Maybe someone can come up with a script to parse all the farc files
## Post #175
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-07-13T18:52:26+00:00
- Post Title: Re: Fate Grand Order Arcade

Anyway I found a problem

The quickbms script cant seem to extract the tex.bin from the 8.40 servant farc files 
but no problems with the 5.53 weapon farc file

though granted I only did it to one file per version,



here's the sample file
[https://drive.google.com/file/d/1tRNfb6 ... sp=sharing](https://drive.google.com/file/d/1tRNfb6EpZpUVSQOikxUeK8IqWBux4Zmh/view?usp=sharing)
## Post #176
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-07-13T19:38:29+00:00
- Post Title: Re: Fate Grand Order Arcade

anyway if im reading this correctly, 8.40 should be the CCC collab update

svt_0060_s07 is drake's skin
while i can only guess svt_0137_s01 as welfare BB and then the two Alteregos
## Post #177
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-07-13T20:34:15+00:00
- Post Title: Re: Fate Grand Order Arcade

I can't check stuff and will not be able to do it in around two weeks, but if those vhd are differential disks, they contain only patch data - that means for totally new archives dataset will be complete, while for already existing archives there are only partial data, which should be merged within virtual file system first. Obviously, you can't fix existing script or create new one to parse incomplete data, except for implementing manual workarounds for each particular error, which doesn't worth it.
## Post #178
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-13T21:27:30+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Spiritovod ↑Thu Jul 14, 2022 4:34 am at Thu Jul 14, 2022 4:34 am
>
> 
I can't check stuff and will not be able to do it in around two weeks, but if those vhd are differential disks, they contain only patch data - that means for totally new archives dataset will be complete, while for already existing archives there are only partial data, which should be merged within virtual file system first. Obviously, you can't fix existing script or create new one to parse incomplete data, except for implementing manual workarounds for each particular error, which doesn't worth it.

Right, looks like we can use SDEJ_5.53.00_20200806201952_2_5.51.00.vhd to upgrade the files from 5.51 to 5.53 that are already shared in Fate Grand Order Arcade Ver.5.51.7z but the changes seem to be minimal, also, there is no base file v8.20 that can be upgraded with SDEJ_8.40.00_20211202173103_2_8.20.00.vhd from 8.20 to 8.40 , but as far as I can tell this last file was extracted from the SDEJ_8.40.00_20211202173103_2_8.20.00.app which was pointed out in a previous post as nearly impossible to be decrypted without the original hardware . . . well, looks like someone has it and is doing it, I hope we get more  

(I wonder if the .app and the .vhd can be used comparatively to figure out the decryption method )
## Post #179
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2022-07-14T06:50:20+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Thu Jul 14, 2022 3:38 am at Thu Jul 14, 2022 3:38 am
>
> 
anyway if im reading this correctly, 8.40 should be the CCC collab update

svt_0060_s07 is drake's skin
while i can only guess svt_0137_s01 as welfare BB and then the two Alteregos

111 : ☆5 Lancer ブラダマンテ
120 : ☆4 Caster ギルガメッシュ
129 : ☆5 Alterego ラーヴァ/ティアマト
137 : ☆5 Caster フランケンシュタイン(クリスマス)
144 : ☆5 Saber 宮本武蔵
## Post #180
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-07-14T08:05:40+00:00
- Post Title: Re: Fate Grand Order Arcade

i deadass forgot fran santa was a thing lmao
## Post #181
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2022-07-14T11:19:55+00:00
- Post Title: Re: Fate Grand Order Arcade

Darn, no Saber Astolfo, no Meltlilith!!!
## Post #182
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-07-14T13:23:18+00:00
- Post Title: Re: Fate Grand Order Arcade

I see. Neither Gray. But is the price from only getting a patch for 8.x version.
## Post #183
- Username: sopi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 17, 2022 11:30 am
- Post datetime: 2022-07-14T13:42:10+00:00
- Post Title: Re: Fate Grand Order Arcade

now to patiently watch for more exciting news
## Post #184
- Username: Yun666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 10, 2022 5:07 pm
- Post datetime: 2022-07-17T19:07:44+00:00
- Post Title: Re: Fate Grand Order Arcade

Hello,
## Post #185
- Username: Yun666
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 10, 2022 5:07 pm
- Post datetime: 2022-07-17T19:09:25+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Thu Jul 14, 2022 4:05 pm at Thu Jul 14, 2022 4:05 pm
>
> 
i deadass forgot fran santa was a thing lmao

Hello, could you share some new files?
## Post #186
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2022-07-23T21:29:24+00:00
- Post Title: Re: Fate Grand Order Arcade

Is this happening to everybody or the file is just updated that the bms can't be extracted? [https://imgur.com/28lMW8A](https://imgur.com/28lMW8A) Like i'm getting the Obj.bin but not the tex file and Noesis can't open the Obj.bin either
## Post #187
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-07-25T19:10:54+00:00
- Post Title: Re: Fate Grand Order Arcade

Finally got home and checked those vhd. My assumption from [previous post](https://forum.xentax.com/viewtopic.php?f=16&t=24274&start=165#p185835) was correct, some data is indeed just deltas.
TLDR: There is nothing to fix, because you can't extract or skip incomplete data (it's not properly structured).
## Post #188
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2022-08-04T10:09:48+00:00
- Post Title: Re: Fate Grand Order Arcade

A query so far the characters that are already available is the character "Passionlip".
## Post #189
- Username: LeArcanist
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 23, 2022 9:59 pm
- Post datetime: 2022-08-16T20:44:47+00:00
- Post Title: Re: Fate Grand Order Arcade

Hey all, is Eresh included in the newer(?) dumps? If so, could anyone share her files please?
## Post #190
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2022-09-29T14:55:38+00:00
- Post Title: Re: Fate Grand Order Arcade

Any new dumps?
## Post #191
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-10-01T02:42:59+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Arielainthere ↑Thu Sep 29, 2022 10:55 pm at Thu Sep 29, 2022 10:55 pm
>
> 
Any new dumps?

This is not the place for asking about dumps. If you want to ask, ask on the [page were they were dumping it](http://www.emuline.org/topic/2407-arcade-pc-fategrand-order-arcade-sega-alls-ux/). But expect to be banned there for just ask.
## Post #192
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2022-10-10T04:12:18+00:00
- Post Title: Re: Fate Grand Order Arcade

Hi everyone! Could someone run me through how I should go about either obtaining FGO AC models or at least how to port them myself? I've tried looking through the thread for awhile, however, I'm pretty confused. Any help would be greatly appreciated!
## Post #193
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2022-10-10T04:16:01+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Deckardddd ↑Mon Oct 10, 2022 12:12 pm at Mon Oct 10, 2022 12:12 pm
>
> 
Hi everyone! Could someone run me through how I should go about either obtaining FGO AC models or at least how to port them myself? I've tried looking through the thread for awhile, however, I'm pretty confused. Any help would be greatly appreciated!
I'm specifically attempting to get the models working in blender.
## Post #194
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2022-10-10T09:11:43+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Deckardddd ↑Mon Oct 10, 2022 12:12 pm at Mon Oct 10, 2022 12:12 pm
>
> how to port them myself
Check [this comment](https://forum.xentax.com/viewtopic.php?p=179577#p179577).
## Post #195
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2022-10-11T00:40:00+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from johnwithlenon ↑Mon Oct 10, 2022 5:11 pm at Mon Oct 10, 2022 5:11 pm
>
> 
Deckardddd wrote: ↑Mon Oct 10, 2022 12:12 pmhow to port them myself
Check this comment.
If you don't mind me asking, where could I get the dumped files to extract? Most megacloud links here seem to be dead. I know that there is a dump on emuline, however, the website is unable to load for me?
## Post #196
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2022-10-13T07:10:06+00:00
- Post Title: Re: Fate Grand Order Arcade

I've figured out how to export the fbx with textures to blender, however, I was wondering if anyone here has figured out how to export the shapekeys with the mesh from Noesis? Any help is greatly appreciated )
## Post #197
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-10-14T12:13:15+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Deckardddd ↑Thu Oct 13, 2022 3:10 pm at Thu Oct 13, 2022 3:10 pm
>
> 
I've figured out how to export the fbx with textures to blender, however, I was wondering if anyone here has figured out how to export the shapekeys with the mesh from Noesis? Any help is greatly appreciated )

I made a tutorial before for someone regarding shapekeys

so here

[https://www.tumblr.com/ailephi/67569125 ... -the-bones](https://www.tumblr.com/ailephi/675691256688558080/also-a-quick-observation-i-found-about-the-bones)
## Post #198
- Username: Deckardddd
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 10, 2022 11:54 am
- Post datetime: 2022-10-18T03:52:40+00:00
- Post Title: Re: Fate Grand Order Arcade

Ok, so while I have been able to get the model successfully ported to blender and fix the shape keys, I am still struggling to get a workable rig. I'm aware that the bone order is messed up, however, whenever I try to fix the issue via the "child of" function, I get this (picture below). Can anyone point me in the right direction on how I should go about reordering the bones?
[pic2.JPG](https://xentaxbackup.github.io/file/22928_pic2.JPG)
## Post #199
- Username: Temperance(Tempy)
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 13, 2021 10:54 am
- Post datetime: 2022-11-01T07:52:19+00:00
- Post Title: Re: Fate Grand Order Arcade

I'm very new to this ripping stuff, but if someone can keep me posted for if someone manages to get the data pack including Tiamat then that'd be great. I wish I could help more but I am a total noob when it comes to ripping from this game. I gotta read up on the thread.
## Post #200
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2022-11-01T17:44:55+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Temperance(Tempy) ↑Tue Nov 01, 2022 3:52 pm at Tue Nov 01, 2022 3:52 pm
>
> 
I'm very new to this ripping stuff, but if someone can keep me posted for if someone manages to get the data pack including Tiamat then that'd be great. I wish I could help more but I am a total noob when it comes to ripping from this game. I gotta read up on the thread.

Read. The. Last. Pages.
And you will understand the situation with the game files as I'm getting tired to repeat it: 

WE DO NOT CONTROL OR CAN GET THE GAME DATA. THEY LEAK IN OTHER PAGE WERE THEY ACTUALLY STOP LEAKING FOR MONTHS.
As I say before in one respond: Go ahead, go to that page and ask for an update of the files, but expect to get banned after just post one reply.
## Post #201
- Username: ddddcvlt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 29, 2022 9:23 am
- Post datetime: 2022-11-11T04:09:25+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Demonslayerx8 ↑Sun Jan 23, 2022 3:55 am at Sun Jan 23, 2022 3:55 am
>
> 
well from what I saw, your doing everything correct. I can't think of anything that would cause it to not load for ya, since it works fine for me.
can you give me 0051-0053 mods？please
## Post #202
- Username: Pepega
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 7:37 pm
- Post datetime: 2022-12-16T18:16:08+00:00
- Post Title: Re: Fate Grand Order Arcade

How dump even happened in the first place? Its not something common I believe




_________________________________________
*just ping me please if you will get Astolfo*
## Post #203
- Username: zarakaramara
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Dec 16, 2022 11:03 pm
- Post datetime: 2022-12-18T02:53:35+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from johnwithlenon ↑Tue Oct 05, 2021 10:23 am at Tue Oct 05, 2021 10:23 am
>
> 
I uploaded the useful folder to mega so those who come later don't need to download the whole game. Most of the models are inside "objset" folder (the character models are "obj_svt...")
https://mega.nz/folder/cIl1nCwT#gGbHR1eN71tg92KvL6IQvA

One question: Is there a workaround to unpack zstd compression without installing zstd? Mine required installing zstd using "pip install zstd", but it says I need to install Microsoft Visual C++ 14, which I don't intend to do because I'm using portable python.

I can not found svt files over 100. but I've seen several listings here.

by ATFE0123:
[viewtopic.php?p=185857#p185857](https://forum.xentax.com/viewtopic.php?p=185857#p185857)
111 : ☆5 Lancer ブラダマンテ
120 : ☆4 Caster ギルガメッシュ
129 : ☆5 Alterego ラーヴァ/ティアマト
137 : ☆5 Caster フランケンシュタイン(クリスマス)
144 : ☆5 Saber 宮本武蔵



I'm specifically looking for hair and weapon files for #111 and #144. Are these characters extracted from the vhd file in the link? Could you please tell me how to do that?
## Post #204
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2022-12-18T09:29:35+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from zarakaramara ↑Sun Dec 18, 2022 10:53 am at Sun Dec 18, 2022 10:53 am
>
> 
johnwithlenon wrote: ↑Tue Oct 05, 2021 10:23 am
I uploaded the useful folder to mega so those who come later don't need to download the whole game. Most of the models are inside "objset" folder (the character models are "obj_svt...")
https://mega.nz/folder/cIl1nCwT#gGbHR1eN71tg92KvL6IQvA

One question: Is there a workaround to unpack zstd compression without installing zstd? Mine required installing zstd using "pip install zstd", but it says I need to install Microsoft Visual C++ 14, which I don't intend to do because I'm using portable python.


I can not found svt files over 100. but I've seen several listings here.

by ATFE0123:
viewtopic.php?p=185857#p185857
111 : ☆5 Lancer ブラダマンテ
120 : ☆4 Caster ギルガメッシュ
129 : ☆5 Alterego ラーヴァ/ティアマト
137 : ☆5 Caster フランケンシュタイン(クリスマス)
144 : ☆5 Saber 宮本武蔵



I'm specifically looking for hair and weapon files for #111 and #144. Are these characters extracted from the vhd file in the link? Could you please tell me how to do that?

we only found the ID and names for those Servants but not the actual assets for them in the vhd because we dont have the base files
## Post #205
- Username: idkwhos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 03, 2023 11:10 am
- Post datetime: 2023-01-03T09:38:42+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Wed Mar 16, 2022 3:12 am at Wed Mar 16, 2022 3:12 am
>
> 
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.

Hi, Someone published the file dump recently for a game called Kancolle Arcade. I spent some time with it to see if I could extract the model from this game. It seems to use a file structure similar to Hatsune Miku Project DIVA and FGO Arcade, and I am able to extract obj.bin and tex.bin for the model with farc extractor for project DIVA. 

For the tex.bin, your script for FGO seems to work, and I am able to get most (if not all) of the texture files out.

However, obj.bin seems to be a bit different, and I have only been able to extract one of the many models in the file (in this case it's a turret lol):


Honeyview_Kancolle model.jpg (36.13 KiB) Viewed 228 times



From what I can tell, the problem is that Kancolle Arcade uses separate body/weapon models for a single character (in a single bin), while FGO Arcade uses one single model for each character:

Kncolle:

```
00E0: 30 31 5F 30 31 5F 62 5F 62 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 01_01_b_body_model�ch0201_01_b_g
0100: 65 61 72 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 65 61 72 30 34 5F 6D ear01_model�ch0201_01_b_gear04_m
0120: 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 odel�ch0201_01_b_wp02_model�ch02
0140: 30 31 5F 30 31 5F 62 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 62 01_01_b_wp05_model�ch0201_01_n_b
0160: 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 67 65 61 72 30 31 5F 6D 6F 64 ody_model�ch0201_01_n_gear01_mod
0180: 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 el�ch0201_01_n_wp01_model�ch0201
01A0: 5F 30 31 5F 6E 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 _01_n_wp02_model�ch0201_01_n_wp0
01C0: 33 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 00 3_model�ch0201_01_n_wp05_model

```

FGO:

```
0010h: 34 00 00 00 00 00 00 00 34 00 00 00 00 00 00 00  4.......4....... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 5F  ....<.......svt_ 
0040h: 30 30 30 31 5F 73 30 31 5F 6D 6F 64 65 6C 00 00  0001_s01_model.. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 13 00 00 00 00 00 00 00 0A 00 00 00 00 00 00 00  ................ 
0070h: 10 1C 00 00 00 00 00 00 18 00 00 00 00 00 00 00  ................ 

```


I tried to modify the script to make it work but failed...Could you help? Much appreciated!

Here's a link to the obj.bin and tex.bin that I extracted:
[https://mega.nz/folder/wG5GUYgT#rqjHXWWlb0M1p_7yiWcwew](https://mega.nz/folder/wG5GUYgT#rqjHXWWlb0M1p_7yiWcwew)
## Post #206
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-04T01:24:51+00:00
- Post Title: Re: Fate Grand Order Arcade

Simguy updated the import script to handle multiple models in one _obj.bin file here:

[viewtopic.php?p=181634#p181634](https://forum.xentax.com/viewtopic.php?p=181634#p181634)

however something seems to break it with these files:

Traceback (most recent call last):
  File "***\Noesis\plugins\python\fmt_FGOA_bin.py", line 609, in noepyLoadModel
    T, T2 = GetTextureList(bs, C.TextureList, ObjTables[M], S)
  File "***\Noesis\plugins\python\fmt_FGOA_bin.py", line 278, in GetTextureList
    T.Name = St[bs.readInt64()]
IndexError: list index out of range
## Post #207
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2023-01-04T01:46:15+00:00
- Post Title: Re: Fate Grand Order Arcade

Looks like there are some structural changes this game. Turns out the part it breaks on isn't actually used for anything (oops) and the bone weights are all jacked up. I'll look into it.
## Post #208
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-04T05:56:47+00:00
- Post Title: Re: Fate Grand Order Arcade

BTW, another newer version of the FGOA files leaked recently, version 9.00, around 20GB.
## Post #209
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-01-04T07:55:47+00:00
- Post Title: Re: Fate Grand Order Arcade

The data is not in the usual page nor on the link.
But as head ups: the old data were we could unpack models was of 12gb aprox. Meaning this one "could" be a more complete one, if it is not encrypted.
## Post #210
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-04T08:53:02+00:00
- Post Title: Re: Fate Grand Order Arcade

There are both versions out there, I got the one already decrypted and it includes servants fom 001 to 146 (with some exceptions inbetween).
## Post #211
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2023-01-04T08:57:26+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Wed Jan 04, 2023 1:56 pm at Wed Jan 04, 2023 1:56 pm
>
> 
BTW, another newer version of the FGOA files leaked recently, version 9.00, around 20GB.

now where did you come across that?
## Post #212
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2023-01-04T11:49:47+00:00
- Post Title: Re: Fate Grand Order Arcade

Did you got files from emuline?
## Post #213
- Username: f2dr0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 15, 2022 5:12 am
- Post datetime: 2023-01-04T12:51:33+00:00
- Post Title: Re: Fate Grand Order Arcade

Seems like emuline still has to update the page
## Post #214
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2023-01-04T12:52:54+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from idkwhos ↑Tue Jan 03, 2023 5:38 pm at Tue Jan 03, 2023 5:38 pm
>
> 
Simguy wrote: ↑Wed Mar 16, 2022 3:12 am
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.


Hi, Someone published the file dump recently for a game called Kancolle Arcade. I spent some time with it to see if I could extract the model from this game. It seems to use a file structure similar to Hatsune Miku Project DIVA and FGO Arcade, and I am able to extract obj.bin and tex.bin for the model with farc extractor for project DIVA. 

For the tex.bin, your script for FGO seems to work, and I am able to get most (if not all) of the texture files out.

However, obj.bin seems to be a bit different, and I have only been able to extract one of the many models in the file (in this case it's a turret lol):Honeyview_Kancolle model.jpg


From what I can tell, the problem is that Kancolle Arcade uses separate body/weapon models for a single character (in a single bin), while FGO Arcade uses one single model for each character:

Kncolle:
Code: Select all00C0: 00 00 00 00 9A 01 00 00 00 00 00 00 B1 01 00 00 00 00 00 00 C8 01 00 00 00 00 00 00 63 68 30 32 ����š������±������È������ch02
00E0: 30 31 5F 30 31 5F 62 5F 62 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 01_01_b_body_model�ch0201_01_b_g
0100: 65 61 72 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 65 61 72 30 34 5F 6D ear01_model�ch0201_01_b_gear04_m
0120: 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 odel�ch0201_01_b_wp02_model�ch02
0140: 30 31 5F 30 31 5F 62 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 62 01_01_b_wp05_model�ch0201_01_n_b
0160: 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 67 65 61 72 30 31 5F 6D 6F 64 ody_model�ch0201_01_n_gear01_mod
0180: 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 el�ch0201_01_n_wp01_model�ch0201
01A0: 5F 30 31 5F 6E 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 _01_n_wp02_model�ch0201_01_n_wp0
01C0: 33 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 00 3_model�ch0201_01_n_wp05_model

FGO:
Code: Select all0000h: 00 25 06 05 01 00 00 00 2C 00 00 00 00 00 00 00  .%......,....... 
0010h: 34 00 00 00 00 00 00 00 34 00 00 00 00 00 00 00  4.......4....... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 5F  ....<.......svt_ 
0040h: 30 30 30 31 5F 73 30 31 5F 6D 6F 64 65 6C 00 00  0001_s01_model.. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 13 00 00 00 00 00 00 00 0A 00 00 00 00 00 00 00  ................ 
0070h: 10 1C 00 00 00 00 00 00 18 00 00 00 00 00 00 00  ................ 


I tried to modify the script to make it work but failed...Could you help? Much appreciated!

Here's a link to the obj.bin and tex.bin that I extracted:
https://mega.nz/folder/wG5GUYgT#rqjHXWWlb0M1p_7yiWcwew
[https://github.com/LordDude/FGOA_objset](https://github.com/LordDude/FGOA_objset)

It works by changing a part of this script
[1.png](https://xentaxbackup.github.io/file/23254_1.png)
## Post #215
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2023-01-04T12:58:41+00:00
- Post Title: Re: Fate Grand Order Arcade

This model contains an LOD mesh
## Post #216
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2023-01-04T14:00:30+00:00
- Post Title: Re: Fate Grand Order Arcade

The problem this model has is that the vertex groups and bone names don't match
So the weights are going crazy
## Post #217
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2023-01-04T14:07:28+00:00
- Post Title: Re: Fate Grand Order Arcade

Do you need to modify the FGOA script or just use it instead of project diva's?
## Post #218
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-01-04T14:41:24+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Wed Jan 04, 2023 4:53 pm at Wed Jan 04, 2023 4:53 pm
>
> 
There are both versions out there, I got the one already decrypted and it includes servants fom 001 to 146 (with some exceptions inbetween).

A Yandex & Google search shows nothing so far.
I bet it is a Discord leak then.
## Post #219
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2023-01-04T15:01:09+00:00
- Post Title: Re: Fate Grand Order Arcade

Use script from project diva

Removed line: 2460 self.readTex(bs)
## Post #220
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-04T17:28:12+00:00
- Post Title: Re: Fate Grand Order Arcade

Looks like this script for noesis handles both the Kancolle AND Fate files better:

[https://github.com/h-kidd/noesis-project-diva](https://github.com/h-kidd/noesis-project-diva)




kancolle.jpg (225.72 KiB) Viewed 419 times
## Post #221
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2023-01-04T20:57:10+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Wed Jan 04, 2023 11:01 pm at Wed Jan 04, 2023 11:01 pm
>
> 
Use script from project diva

Removed line: 2460 self.readTex(bs)
I only managed find script for Virtua Fighter 5, where did you found quickbms script for Project Diva?
## Post #222
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2023-01-05T03:30:39+00:00
- Post Title: Re: Fate Grand Order Arcade

new character list

056 : ☆5 Lancer 玉藻の前
063 : ☆5 Avenger 巌窟王 エドモン・ダンテス
065 : ☆5 Caster レオナルド・ダ・ヴィンチ
078 : ☆5 Caster マーリン〔プロトタイプ〕
082 : ☆1 Berserker ポール・バニヤン
091 : ☆5 Lancer エレシュキガル
096 : ☆4 Saber セタンタ
101 : ☆5 Berserker クー・フーリン〔オルタ〕
102 : ☆4 Archer シータ
103 : ☆5 Berserker 宮本武蔵
104 : ☆4 Saber 葛飾北斎
107 : ☆5 Rider アルトリア・ペンドラゴン〔オルタ〕
108 : ☆4 Saber 女王メイヴ
109 : ☆5 Rider オジマンディアス
110 : ☆5 Saber ジャック・ド・モレー
111 : ☆5 Lancer ブラダマンテ
112 : ☆4 Lancer 鈴鹿御前〔サンタ〕
113 : ☆5 Lancer アルトリア・ペンドラゴン 
115 : ☆5 Foreigner 謎のヒロインXX 
117 : ☆5 Saber アストルフォ
118 : ☆5 Ruler シャーロック・ホームズ
119 : ☆5 Berserker 謎のヒロインX〔オルタ〕
120 : ☆4 Caster ギルガメッシュ
121 : ☆5 Lancer エルキドゥ 
129 : ☆5 Alterego ラーヴァ/ティアマト
133 : ☆5 Archer ジャンヌ・ダルク 
136 : ☆4 Lancer 虞美人
137 : ☆5 Caster フランケンシュタイン(クリスマス)
138 : ☆5 Rider 司馬懿〔ライネス〕
139 : ☆4 Ruler アストライア 
140 : ☆4 Assassin グレイ 
144 : ☆5 Saber 宮本武蔵
146 : ☆5 Archer 清少納言
## Post #223
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2023-01-05T04:45:09+00:00
- Post Title: Re: Fate Grand Order Arcade

While the update is only up to Babylonia
Queen Draco is in the files as an enemy servant/svt_8081, not as a playable

So no King Hassan and Draco's Beast form, even though Musashi Saber is there

Also svt_056/Tamamo Lancer cant be read with the script I'm using
## Post #224
- Username: idkwhos
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jan 03, 2023 11:10 am
- Post datetime: 2023-01-05T05:37:46+00:00
- Post Title: Re: Fate Grand Order Arcade

Fantastic. I am able to extract the mesh with this script [https://github.com/h-kidd/noesis-project-diva](https://github.com/h-kidd/noesis-project-diva):



Honeyview_Snipaste_2023-01-04_20-58-35.jpg (42.22 KiB) Viewed 334 times



It seems that the script is able to handle the mesh properly, but not the texture of some of the objects. The texture file itself looks ok and there are other objects in the model that use the same texture without any problem. Maybe there's something special about that object?
## Post #225
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-01-05T06:56:17+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Thu Jan 05, 2023 11:30 am at Thu Jan 05, 2023 11:30 am
>
> 
new character list

056 : ☆5 Lancer 玉藻の前
063 : ☆5 Avenger 巌窟王 エドモン・ダンテス
065 : ☆5 Caster レオナルド・ダ・ヴィンチ
078 : ☆5 Caster マーリン〔プロトタイプ〕
082 : ☆1 Berserker ポール・バニヤン
091 : ☆5 Lancer エレシュキガル
096 : ☆4 Saber セタンタ
101 : ☆5 Berserker クー・フーリン〔オルタ〕
102 : ☆4 Archer シータ
103 : ☆5 Berserker 宮本武蔵
104 : ☆4 Saber 葛飾北斎
107 : ☆5 Rider アルトリア・ペンドラゴン〔オルタ〕
108 : ☆4 Saber 女王メイヴ
109 : ☆5 Rider オジマンディアス
110 : ☆5 Saber ジャック・ド・モレー
111 : ☆5 Lancer ブラダマンテ
112 : ☆4 Lancer 鈴鹿御前〔サンタ〕
113 : ☆5 Lancer アルトリア・ペンドラゴン 
115 : ☆5 Foreigner 謎のヒロインXX 
117 : ☆5 Saber アストルフォ
118 : ☆5 Ruler シャーロック・ホームズ
119 : ☆5 Berserker 謎のヒロインX〔オルタ〕
120 : ☆4 Caster ギルガメッシュ
121 : ☆5 Lancer エルキドゥ 
129 : ☆5 Alterego ラーヴァ/ティアマト
133 : ☆5 Archer ジャンヌ・ダルク 
136 : ☆4 Lancer 虞美人
137 : ☆5 Caster フランケンシュタイン(クリスマス)
138 : ☆5 Rider 司馬懿〔ライネス〕
139 : ☆4 Ruler アストライア 
140 : ☆4 Assassin グレイ 
144 : ☆5 Saber 宮本武蔵
146 : ☆5 Archer 清少納言

No Iskandar or gramps Hassan, but Gray is there. Not exactly bad compared with what we had a year ago. Thanks.
## Post #226
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2023-01-05T07:05:24+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Thu Jan 05, 2023 11:30 am at Thu Jan 05, 2023 11:30 am
>
> 
new character list

056 : ☆5 Lancer 玉藻の前
063 : ☆5 Avenger 巌窟王 エドモン・ダンテス
065 : ☆5 Caster レオナルド・ダ・ヴィンチ
078 : ☆5 Caster マーリン〔プロトタイプ〕
082 : ☆1 Berserker ポール・バニヤン
091 : ☆5 Lancer エレシュキガル
096 : ☆4 Saber セタンタ
101 : ☆5 Berserker クー・フーリン〔オルタ〕
102 : ☆4 Archer シータ
103 : ☆5 Berserker 宮本武蔵
104 : ☆4 Saber 葛飾北斎
107 : ☆5 Rider アルトリア・ペンドラゴン〔オルタ〕
108 : ☆4 Saber 女王メイヴ
109 : ☆5 Rider オジマンディアス
110 : ☆5 Saber ジャック・ド・モレー
111 : ☆5 Lancer ブラダマンテ
112 : ☆4 Lancer 鈴鹿御前〔サンタ〕
113 : ☆5 Lancer アルトリア・ペンドラゴン 
115 : ☆5 Foreigner 謎のヒロインXX 
117 : ☆5 Saber アストルフォ
118 : ☆5 Ruler シャーロック・ホームズ
119 : ☆5 Berserker 謎のヒロインX〔オルタ〕
120 : ☆4 Caster ギルガメッシュ
121 : ☆5 Lancer エルキドゥ 
129 : ☆5 Alterego ラーヴァ/ティアマト
133 : ☆5 Archer ジャンヌ・ダルク 
136 : ☆4 Lancer 虞美人
137 : ☆5 Caster フランケンシュタイン(クリスマス)
138 : ☆5 Rider 司馬懿〔ライネス〕
139 : ☆4 Ruler アストライア 
140 : ☆4 Assassin グレイ 
144 : ☆5 Saber 宮本武蔵
146 : ☆5 Archer 清少納言

Is there a readily accessible batch of these yet or still within private download?
## Post #227
- Username: sopi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 17, 2022 11:30 am
- Post datetime: 2023-01-05T23:07:50+00:00
- Post Title: Re: Fate Grand Order Arcade

I can't wait to toss them in blender
## Post #228
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2023-01-06T08:17:30+00:00
- Post Title: Re: Fate Grand Order Arcade

Heads up, Emuline site released the new version 9.0 package files in Part 1 and Part 2

Question is, why are the file extensions .7z.001 and .7z.002? Failed to open the .002 and will see about the .001
## Post #229
- Username: sopi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jan 17, 2022 11:30 am
- Post datetime: 2023-01-06T10:10:45+00:00
- Post Title: Re: Fate Grand Order Arcade

anyone find 129/ tiamats noble phantasm model?
## Post #230
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2023-01-06T10:50:59+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from sopi ↑Fri Jan 06, 2023 6:10 pm at Fri Jan 06, 2023 6:10 pm
>
> 
anyone find 129/ tiamats noble phantasm model?

svtg_0129_obj.bin
## Post #231
- Username: Pepega
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 7:37 pm
- Post datetime: 2023-01-07T10:34:51+00:00
- Post Title: Re: Fate Grand Order Arcade

How I can extract all sub-models with Noesis "batch process" feature, there should be parameter for that

UPD: Sub-Models is pain in one place. There is no simple build it way to get all of them with one click even from one file, not to mention multiple ones. (if you asking what is submodels load svtg_0012_obj in noesis and press f2)

UPD2: with some pain but case resolved.
## Post #232
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2023-01-12T16:55:16+00:00
- Post Title: Re: Fate Grand Order Arcade

Can someone slide me a link to the new dump files. That would be appreciated
## Post #233
- Username: huehuehuynh
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Dec 18, 2021 2:17 pm
- Post datetime: 2023-01-15T05:06:56+00:00
- Post Title: Re: Fate Grand Order Arcade

So I've been wondering for a while, but for textures that have the endings of "_s" and "_bs" are they to be taken both as shadow maps like ambient occlusion or "_s" is specular mapping and "_bs" is AO mapping
## Post #234
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2023-01-16T22:11:50+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from huehuehuynh ↑Sun Jan 15, 2023 1:06 pm at Sun Jan 15, 2023 1:06 pm
>
> 
So I've been wondering for a while, but for textures that have the endings of "_s" and "_bs" are they to be taken both as shadow maps like ambient occlusion or "_s" is specular mapping and "_bs" is AO mapping

s is specular, bs is ao(baked shadow in this case). Ramps do a lot of the work
## Post #235
- Username: Pepega
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 7:37 pm
- Post datetime: 2023-01-17T04:39:09+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Makoto ↑Tue Jan 17, 2023 6:11 am at Tue Jan 17, 2023 6:11 am
>
> 
Ramps do a lot of the work

Well it is impossible to use them outside of the game because we can't tell how exactly they work with game shaders, so they can be deleted
## Post #236
- Username: f2dr0
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 15, 2022 5:12 am
- Post datetime: 2023-01-18T13:29:05+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ATFE0123 ↑Thu Jan 05, 2023 11:30 am at Thu Jan 05, 2023 11:30 am
>
> 
new character list

056 : ☆5 Lancer 玉藻の前
063 : ☆5 Avenger 巌窟王 エドモン・ダンテス
065 : ☆5 Caster レオナルド・ダ・ヴィンチ
078 : ☆5 Caster マーリン〔プロトタイプ〕
082 : ☆1 Berserker ポール・バニヤン
091 : ☆5 Lancer エレシュキガル
096 : ☆4 Saber セタンタ
101 : ☆5 Berserker クー・フーリン〔オルタ〕
102 : ☆4 Archer シータ
103 : ☆5 Berserker 宮本武蔵
104 : ☆4 Saber 葛飾北斎
107 : ☆5 Rider アルトリア・ペンドラゴン〔オルタ〕
108 : ☆4 Saber 女王メイヴ
109 : ☆5 Rider オジマンディアス
110 : ☆5 Saber ジャック・ド・モレー
111 : ☆5 Lancer ブラダマンテ
112 : ☆4 Lancer 鈴鹿御前〔サンタ〕
113 : ☆5 Lancer アルトリア・ペンドラゴン 
115 : ☆5 Foreigner 謎のヒロインXX 
117 : ☆5 Saber アストルフォ
118 : ☆5 Ruler シャーロック・ホームズ
119 : ☆5 Berserker 謎のヒロインX〔オルタ〕
120 : ☆4 Caster ギルガメッシュ
121 : ☆5 Lancer エルキドゥ 
129 : ☆5 Alterego ラーヴァ/ティアマト
133 : ☆5 Archer ジャンヌ・ダルク 
136 : ☆4 Lancer 虞美人
137 : ☆5 Caster フランケンシュタイン(クリスマス)
138 : ☆5 Rider 司馬懿〔ライネス〕
139 : ☆4 Ruler アストライア 
140 : ☆4 Assassin グレイ 
144 : ☆5 Saber 宮本武蔵
146 : ☆5 Archer 清少納言

Where can I see the character list? Is there a file?
## Post #237
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2023-01-22T13:57:10+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Pepega ↑Tue Jan 17, 2023 12:39 pm at Tue Jan 17, 2023 12:39 pm
>
> 
Makoto wrote: ↑Tue Jan 17, 2023 6:11 am
Ramps do a lot of the work


Well it is impossible to use them outside of the game because we can't tell how exactly they work with game shaders, so they can be deleted

some older programs such as MMD which is what i use can use them, they're kinda like normal toons
## Post #238
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2023-01-22T16:31:31+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Makoto ↑Sun Jan 22, 2023 9:57 pm at Sun Jan 22, 2023 9:57 pm
>
> 
Pepega wrote: ↑Tue Jan 17, 2023 12:39 pm
Makoto wrote: ↑Tue Jan 17, 2023 6:11 am
Ramps do a lot of the work


Well it is impossible to use them outside of the game because we can't tell how exactly they work with game shaders, so they can be deleted


some older programs such as MMD which is what i use can use them, they're kinda like normal toons

Are you still using toon ramps in mmd?? I don't even care when using raycast.
## Post #239
- Username: Pepega
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 7:37 pm
- Post datetime: 2023-01-23T06:23:13+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Makoto ↑Sun Jan 22, 2023 9:57 pm at Sun Jan 22, 2023 9:57 pm
>
> 
they're kinda like normal toons
Well, mmd tools material doesn't fit all those toons and I'm not good with making custom node groups so outside of mmd it is truly useless.
## Post #240
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2023-01-24T18:12:48+00:00
- Post Title: Re: Fate Grand Order Arcade

Can someone do a whole tutorial on how to extract the new files from VHD... Literally going into HxD without knowing a single thing..
## Post #241
- Username: Pepega
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jul 25, 2020 7:37 pm
- Post datetime: 2023-01-25T05:40:55+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Arielainthere ↑Wed Jan 25, 2023 2:12 am at Wed Jan 25, 2023 2:12 am
>
> 
Can someone do a whole tutorial on how to extract the new files from VHD... Literally going into HxD without knowing a single thing..

All you need to do is literally unzip it with 7zip.
## Post #242
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-01-26T12:24:13+00:00
- Post Title: Re: Fate Grand Order Arcade

Does the quickBms script method apply as well for blender or is it just noesis?
## Post #243
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2023-02-02T19:28:29+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from gakdta2 ↑Thu Jan 26, 2023 8:24 pm at Thu Jan 26, 2023 8:24 pm
>
> 
Does the quickBms script method apply as well for blender or is it just noesis?

quickbms is just to turn the farc files into a Obj. and Tex. files. and Noesis helps to open those files and export them as a file format that blender can open
## Post #244
- Username: gigna1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 05, 2020 8:36 pm
- Post datetime: 2023-02-05T09:55:28+00:00
- Post Title: Re: Fate Grand Order Arcade

Does anyone know what "bs" stands for in the textures?



image.png (42.33 KiB) Viewed 817 times
## Post #245
- Username: foulveins
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Apr 19, 2018 7:19 am
- Post datetime: 2023-02-05T20:09:24+00:00
- Post Title: Re: Fate Grand Order Arcade

not sure what 'bs' would mean here but that absolutely looks like an ao/shadow map
## Post #246
- Username: Modman69
- Rank: veteran
- Number of posts: 108
- Joined date: Wed Jun 17, 2009 11:33 pm
- Post datetime: 2023-02-06T23:49:43+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from gigna1 ↑Sun Feb 05, 2023 5:55 pm at Sun Feb 05, 2023 5:55 pm
>
> 
Does anyone know what "bs" stands for in the textures?
image.png

In FF7R the _B Maps are red like that and are for SSS , Not sure if it's the same here but looks like it could be
## Post #247
- Username: yourreason
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jul 16, 2020 4:15 pm
- Post datetime: 2023-02-13T19:49:54+00:00
- Post Title: Re: Fate Grand Order Arcade

Maybe,i disturb someone but i dont get, where located effects sounds and others sound tracks? Beside rom/sound/ folder.
## Post #248
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2023-02-14T15:52:08+00:00
- Post Title: Re: Fate Grand Order Arcade

Is there a wat to get morphs names in blender or 3ds max?? because every time I export a model to fbx and import it to blender or max studio the morphs tabs doe not show the names.
## Post #249
- Username: BossMob9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 27, 2019 5:43 am
- Post datetime: 2023-02-17T00:37:23+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darko ↑Tue Feb 14, 2023 11:52 pm at Tue Feb 14, 2023 11:52 pm
>
> 
Is there a wat to get morphs names in blender or 3ds max?? because every time I export a model to fbx and import it to blender or max studio the morphs tabs doe not show the names.

When you export from Noesis, it actually shows a list of all the morph names in the textbox from the export window. Ignoring the "(meshname)_base," is the names of the morphs in the correct order, so you can fill the names of them in 3dsmax.
## Post #250
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-02-22T03:10:34+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from johnwithlenon ↑Sat Nov 13, 2021 1:15 pm at Sat Nov 13, 2021 1:15 pm
>
> 
Melvinnnn wrote: ↑Fri Nov 12, 2021 2:03 pm
Could you tell me more about it if you want? 
I can now extract obj.bin and tex.bin by changing farc in the FGO_arcade_farc.bms script, but extracting from tex.bin in RawTexture is wrong, right? I don't know what file to input to FGO_arcade_tex.bms and FGO_arcade_txp.bms because I can't see the .tex or .txp.

Okay here is the workflow (you'll need quickbms and the quickbms script of FGOA. For noesis, install the plugins by copying the *.py into \plugins\python\):
- Ignore the "_table.bin", you don't need it.
- Use the quickbms script "FGO_arcade_farc.bms" on the *.farc to get two *.bin files: "_obj.bin" and "_tex.bin".
- For the extracted "_obj.bin", use the noesis script "fmt_FGOA_bin.py" (Update2: The noesis-project-diva can handle the *.bin files better) to view the model (and export to *.fbx).
Update1: The script can now read the textures in the "_tex.bin" file, simply put the bins in the same folder then export the "_obj.bin" into another 3D format and it will export the textures.

Now import the *.fbx into a 3D modeling program, then apply textures (actually you can skip this step by adding ".png" at lines 237, 239, 241, 243, 248 of the the noesis script).

How do you add the specific lines in the noesis script for the textures?
## Post #251
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2023-02-22T10:25:29+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from gakdta2 ↑Wed Feb 22, 2023 11:10 am at Wed Feb 22, 2023 11:10 am
>
> How do you add the specific lines in the noesis script for the textures?
Oh back then I was talking about the script from Simguy, it's just for my personal use (because I exported the textures from "_tex.bin" into *.png format), I added ".png" at those line then export the "_obj.bin" to *.fbx, therefore when I import the *.fbx into blender, the textures show up automatically without having to edit the textures slot. I haven't tried the project diva script yet.
## Post #252
- Username: Rider
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 23, 2023 7:35 pm
- Post datetime: 2023-02-23T11:39:11+00:00
- Post Title: Re: Fate Grand Order Arcade

Can anyone post the files for the models on this page I'm new here and I don't know how to get them myself any help would be very appreciated.
## Post #253
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-02-23T18:03:55+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Rider ↑Thu Feb 23, 2023 7:39 pm at Thu Feb 23, 2023 7:39 pm
>
> 
Can anyone post the files for the models on this page I'm new here and I don't know how to get them myself any help would be very appreciated.
Then go and read the rules because that is against the rules. This is not The Model Resources or pages like that. We only share sample files if the game data is unknown, but never the whole file data.
## Post #254
- Username: enochteo7
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Oct 02, 2021 12:32 pm
- Post datetime: 2023-03-23T07:05:54+00:00
- Post Title: Re: Fate Grand Order Arcade

Has anyone created a script to export the animation data from MOT files?
## Post #255
- Username: Arielainthere
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Apr 22, 2022 12:32 pm
- Post datetime: 2023-03-27T16:52:50+00:00
- Post Title: Re: Fate Grand Order Arcade

Anybody alse quickbms script just stop working after a while? like Command Prompt wont even open and just closes immediately after opening?
## Post #256
- Username: Melvinnnn
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Mar 14, 2019 5:06 am
- Post datetime: 2023-04-14T20:22:41+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from idkwhos ↑Tue Jan 03, 2023 5:38 pm at Tue Jan 03, 2023 5:38 pm
>
> 
Simguy wrote: ↑Wed Mar 16, 2022 3:12 am
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.


Hi, Someone published the file dump recently for a game called Kancolle Arcade. I spent some time with it to see if I could extract the model from this game. It seems to use a file structure similar to Hatsune Miku Project DIVA and FGO Arcade, and I am able to extract obj.bin and tex.bin for the model with farc extractor for project DIVA. 

For the tex.bin, your script for FGO seems to work, and I am able to get most (if not all) of the texture files out.

However, obj.bin seems to be a bit different, and I have only been able to extract one of the many models in the file (in this case it's a turret lol):Honeyview_Kancolle model.jpg


From what I can tell, the problem is that Kancolle Arcade uses separate body/weapon models for a single character (in a single bin), while FGO Arcade uses one single model for each character:

Kncolle:
Code: Select all00C0: 00 00 00 00 9A 01 00 00 00 00 00 00 B1 01 00 00 00 00 00 00 C8 01 00 00 00 00 00 00 63 68 30 32 ����š������±������È������ch02
00E0: 30 31 5F 30 31 5F 62 5F 62 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 01_01_b_body_model�ch0201_01_b_g
0100: 65 61 72 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 65 61 72 30 34 5F 6D ear01_model�ch0201_01_b_gear04_m
0120: 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 odel�ch0201_01_b_wp02_model�ch02
0140: 30 31 5F 30 31 5F 62 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 62 01_01_b_wp05_model�ch0201_01_n_b
0160: 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 67 65 61 72 30 31 5F 6D 6F 64 ody_model�ch0201_01_n_gear01_mod
0180: 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 el�ch0201_01_n_wp01_model�ch0201
01A0: 5F 30 31 5F 6E 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 _01_n_wp02_model�ch0201_01_n_wp0
01C0: 33 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 00 3_model�ch0201_01_n_wp05_model

FGO:
Code: Select all0000h: 00 25 06 05 01 00 00 00 2C 00 00 00 00 00 00 00  .%......,....... 
0010h: 34 00 00 00 00 00 00 00 34 00 00 00 00 00 00 00  4.......4....... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 5F  ....<.......svt_ 
0040h: 30 30 30 31 5F 73 30 31 5F 6D 6F 64 65 6C 00 00  0001_s01_model.. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 13 00 00 00 00 00 00 00 0A 00 00 00 00 00 00 00  ................ 
0070h: 10 1C 00 00 00 00 00 00 18 00 00 00 00 00 00 00  ................ 


I tried to modify the script to make it work but failed...Could you help? Much appreciated!

Here's a link to the obj.bin and tex.bin that I extracted:
https://mega.nz/folder/wG5GUYgT#rqjHXWWlb0M1p_7yiWcwew

This is a rudimentary question, but how can I get a farc extractor for project DIVA?
Also, can you tell me how to extract obj.bin and tex.bin from a kanncolle arcade dump?
## Post #257
- Username: BossMob9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 27, 2019 5:43 am
- Post datetime: 2023-04-15T06:09:50+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Sat Apr 15, 2023 4:22 am at Sat Apr 15, 2023 4:22 am
>
> 
This is a rudimentary question, but how can I get a farc extractor for project DIVA?
Also, can you tell me how to extract obj.bin and tex.bin from a kanncolle arcade dump?

You can use the virtua fighter 5 bms script for kancolle arcade. You should be able to find it with a quick google.
## Post #258
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2023-04-16T04:07:18+00:00
- Post Title: Re: Fate Grand Order Arcade

wait someone got a legit KC dump?
## Post #259
- Username: moonvoidd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2023 6:15 am
- Post datetime: 2023-04-16T19:15:10+00:00
- Post Title: Re: Fate Grand Order Arcade

Praying the next batch dump has Saber Shiki, Skadi, Melt, Osakabehime, Koyan & Morgan
## Post #260
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-04-16T19:57:08+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from moonvoidd ↑Mon Apr 17, 2023 3:15 am at Mon Apr 17, 2023 3:15 am
>
> 
Praying the next batch dump has Saber Shiki, Skadi, Melt, Osakabehime, Koyan & Morgan

As far as I know these are the "known" versions people have found in HDDs extracted from second hand arcade machines and only up to version 9.0 has ben decrypted and leaked (the decryption method/tools are known now the only issue is getting your hands on the .app files):

```
 3.00.00	26/03/2019
 3.60.01	04/07/2019
 4.00.00              2019
 4.50.00	16/12/2019
 5.31.00	26/03/2020
 5.51.00	06/07/2020
 6.10.00	18/08/2020
 6.11.00	08/09/2020
 6.20.01	11/09/2020
 6.21.00	25/09/2020
 6.31.00	23/10/2020
 6.51.00	23/12/2020
 7.20.00	22/03/2021
 7.60.01	09/07/2021
 8.00.00	26/08/2021
 8.11.00	27/08/2021
 8.30.00	18/11/2021
 8.40.00	16/12/2021
 9.00.00	09/12/2021
 9.10.00	03/02/2022
 9.31.00	26/04/2022
 9.50.00	23/06/2022
 9.61.00	01/08/2022
10.10.00	08/09/2022
10.30.00	01/11/2022
10.50.00	26/12/2022
10.60.00	
10.70.00	16/03/2023

```


If I remember correctly you can match these versions with the official release dates in the FGOA website to know which version includes which characters.
## Post #261
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-04-16T20:47:20+00:00
- Post Title: Re: Fate Grand Order Arcade

For what I read in one Discord page, the leaks we get normally are actually buy. Someone or people buy the leaks. This explain why they haven't being any new leaks or anything on the past months: they are not really easy to get or buy on this case.
## Post #262
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-04-17T00:44:39+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Mon Apr 17, 2023 4:47 am at Mon Apr 17, 2023 4:47 am
>
> 
For what I read in one Discord page, the leaks we get normally are actually buy. Someone or people buy the leaks. This explain why they haven't being any new leaks or anything on the past months: they are not really easy to get or buy on this case.

Yup, that makes sense, seeing how the models for this and a bunch of other games end up for sale in some obscure websites, similar on how once in a while requests pop up here and there for "help" to localize a game which will end up for sale in places where there was no localization for it.
## Post #263
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-04-17T05:37:34+00:00
- Post Title: Re: Fate Grand Order Arcade

China Discord servers, mostly.
In my case I'm only waiting for the patch were Gramps Hassan, Moriarty and Iskandar are for quitting on this game data hunt. After them, they is nothing interesting and for what I seeing on they Twitter account: They barely have add any new character in months.
## Post #264
- Username: BossMob9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 27, 2019 5:43 am
- Post datetime: 2023-04-18T07:44:15+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from moonvoidd ↑Mon Apr 17, 2023 3:15 am at Mon Apr 17, 2023 3:15 am
>
> 
Praying the next batch dump has Saber Shiki, Skadi, Melt, Osakabehime, Koyan & Morgan

Saber Shiki is already in the latest files. Her ID is 51.
## Post #265
- Username: lolololola
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 21, 2023 12:15 am
- Post datetime: 2023-04-20T16:20:29+00:00
- Post Title: Re: Fate Grand Order Arcade

the last version anyone will be able to obtain is 10.60 as 10.70 onwards changed to sega's internal network. you will have to buy decomissioned cabinets to obtain these updates in the future, or hack into an actual arcade's VPN. thanks idiot leakers on emuline for this
## Post #266
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2023-04-20T16:43:36+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from lolololola ↑Fri Apr 21, 2023 12:20 am at Fri Apr 21, 2023 12:20 am
>
> 
the last version anyone will be able to obtain is 10.60 as 10.70 onwards changed to sega's internal network. you will have to buy decomissioned cabinets to obtain these updates in the future, or hack into an actual arcade's VPN. thanks idiot leakers on emuline for this

well that's just fking great 
is 10.70 the one with Muramasa onwards? then that would mean the last servant we may be able to get is Koyan.
## Post #267
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2023-04-25T06:33:12+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from lolololola ↑Fri Apr 21, 2023 12:20 am at Fri Apr 21, 2023 12:20 am
>
> 
the last version anyone will be able to obtain is 10.60 as 10.70 onwards changed to sega's internal network. you will have to buy decomissioned cabinets to obtain these updates in the future, or hack into an actual arcade's VPN. thanks idiot leakers on emuline for this

great can u pm me for 10.60
## Post #268
- Username: BrawlBroHalo
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 06, 2022 8:57 pm
- Post datetime: 2023-04-27T15:56:36+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from lolololola ↑Fri Apr 21, 2023 12:20 am at Fri Apr 21, 2023 12:20 am
>
> 
the last version anyone will be able to obtain is 10.60 as 10.70 onwards changed to sega's internal network. you will have to buy decomissioned cabinets to obtain these updates in the future, or hack into an actual arcade's VPN. thanks idiot leakers on emuline for this

I'm gonna cry, I have been praying for Muramasa to be added to the Arcade so we could get his model, now I'm hit with this news. :c
## Post #269
- Username: kuzon1
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 08, 2018 4:23 pm
- Post datetime: 2023-04-29T05:11:57+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from BrawlBroHalo ↑Thu Apr 27, 2023 11:56 pm at Thu Apr 27, 2023 11:56 pm
>
> 
lolololola wrote: ↑Fri Apr 21, 2023 12:20 am
the last version anyone will be able to obtain is 10.60 as 10.70 onwards changed to sega's internal network. you will have to buy decomissioned cabinets to obtain these updates in the future, or hack into an actual arcade's VPN. thanks idiot leakers on emuline for this 


I'm gonna cry, I have been praying for Muramasa to be added to the Arcade so we could get his model, now I'm hit with this news. :c

Well, let's hope we get new versions anyway. i dont know what happened, but wasn't the way to get the data exactly the same? in any case, the data was obtained from obsolete machines, as far as I understand, which is why new versions appeared so rarely.
## Post #270
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2023-05-25T05:34:40+00:00
- Post Title: Re: Fate Grand Order Arcade

Sega hs announced that they will stop adding new servants into the game so Muramasa will be the last servant the file dump will ever get

anything beyond 10.70.00 would most likely just have new costume dresses and accessories for existing servants
## Post #271
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2023-05-25T16:05:38+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Thu May 25, 2023 1:34 pm at Thu May 25, 2023 1:34 pm
>
> 
Sega hs announced that they will stop adding new servants into the game so Muramasa will be the last servant the file dump will ever get

anything beyond 10.70.00 would most likely just have new costume dresses and accessories for existing servants

That's sad, i hope someday we atleast will get our hand on 10+ version of the game.
## Post #272
- Username: kuzon1
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 08, 2018 4:23 pm
- Post datetime: 2023-05-31T09:14:01+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Thu May 25, 2023 1:34 pm at Thu May 25, 2023 1:34 pm
>
> 
Sega hs announced that they will stop adding new servants into the game so Muramasa will be the last servant the file dump will ever get

anything beyond 10.70.00 would most likely just have new costume dresses and accessories for existing servants

Considering that Arcada's story is finished, and partially carried over into the original, it's no wonder there won't be any new servants. But sad. I hope they release something like FGO PC ver in the future.
## Post #273
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-05-31T23:41:14+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from kuzon1 ↑Wed May 31, 2023 5:14 pm at Wed May 31, 2023 5:14 pm
>
> 
But sad. I hope they release something like FGO PC ver in the future.
I doubt it. Even FGO fans complained a lot every time someone mentioned of a PC/Console version of FGO Arcade or FGO. Giving excuses that they don't see him money maker enough for the company.
## Post #274
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-06-01T18:52:14+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Thu Jun 01, 2023 7:41 am at Thu Jun 01, 2023 7:41 am
>
> 
kuzon1 wrote: ↑Wed May 31, 2023 5:14 pm
But sad. I hope they release something like FGO PC ver in the future.

I doubt it. Even FGO fans complained a lot every time someone mentioned of a PC/Console version of FGO Arcade or FGO. Giving excuses that they don't see him money maker enough for the company.

They said they were going to port Gunslinger Stratos to PC too but it never happened, arcade style games dont do well outside arcades coughDissidiaNTcough
## Post #275
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-06-01T19:35:01+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Fri Jun 02, 2023 2:52 am at Fri Jun 02, 2023 2:52 am
>
> 
Arcade style games dont do well outside arcades coughDissidiaNTcough

Best example on the marked. And it is a 3 vs 3 game too.
But neither Stratos nor FGO will ever get a PC or PvE version. They will be lost forever on the Arcade unless they emu, which is not easy to do.
## Post #276
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2023-06-01T23:05:26+00:00
- Post Title: Re: Fate Grand Order Arcade

A PC version of GUNSLINGER STRATOS existed. Was it only in Japan? It did not become very popular and the service was soon terminated.
## Post #277
- Username: kuzon1
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Mar 08, 2018 4:23 pm
- Post datetime: 2023-06-03T01:17:39+00:00
- Post Title: Re: Fate Grand Order Arcade

i mean, what they can make new FGO game for PC, maybe with using Models from FGO Arcade
## Post #278
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-06-09T02:01:39+00:00
- Post Title: Re: Fate Grand Order Arcade

i hope someone dumps the rest of the characters that aren't in the latest zip, like quetzalcoatl and morgan
## Post #279
- Username: ailephi
- Rank: beginner
- Number of posts: 31
- Joined date: Sun Jun 05, 2016 10:14 pm
- Post datetime: 2023-06-09T02:21:45+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from gakdta2 ↑Fri Jun 09, 2023 10:01 am at Fri Jun 09, 2023 10:01 am
>
> 
i hope someone dumps the rest of the characters that aren't in the latest zip, like quetzalcoatl and morgan

Quetz isn't in Arcade

The ones missing are

-Adult Beast Draco
-BB
-Meltryllis
-Passionlip
-King Hassan
-Iskandar
-Moriarty
-Abigail Summer
-Noah
-Merlin
-Artoria Ruler
-Osakabehime
-Skadi
-Morgan
-Kama Mistake
-Koyan Light
-Muramasa
## Post #280
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-06-09T05:55:15+00:00
- Post Title: Re: Fate Grand Order Arcade

For anyone wondering: Apparently, they is data or at least someone manage to get. I may have read it wrong too. But that was weeks ago and with a promise to upload on they page which it hadn't happen for nearly a month I believe.

Negative point is the data will come without being decrypted. It will be raw game data and on top they will not upload as a full game patched, but only the next patchs.

Good point: The game will not get more update so it is just a few more data to be add.

That is the only I know but it is as the rest: broken info.

I gotta confess, but I really want they update the data for finally put an end to care for the Arcade version and quiet finally of FGO & Type-Moon in general. They will keep forever with the gacha game and never made an actual 3D game not gacha involve like back on the day when they made PSP games and even multiple consoles games for anyone to play.
## Post #281
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-06-19T13:15:53+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from ailephi ↑Fri Jun 09, 2023 10:21 am at Fri Jun 09, 2023 10:21 am
>
> 
gakdta2 wrote: ↑Fri Jun 09, 2023 10:01 am
i hope someone dumps the rest of the characters that aren't in the latest zip, like quetzalcoatl and morgan


Quetz isn't in Arcade

The ones missing are

-Adult Beast Draco
-BB
-Meltryllis
-Passionlip
-King Hassan
-Iskandar
-Moriarty
-Abigail Summer
-Noah
-Merlin
-Artoria Ruler
-Osakabehime
-Skadi
-Morgan
-Kama Mistake
-Koyan Light
-Muramasa

strongest fucking Mandela effect hit me i could have sworn she was in the game lmaoo
## Post #282
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-06-19T13:50:38+00:00
- Post Title: Re: Fate Grand Order Arcade

did you guys figure out the shader type that the models use in game?

i assume its an mmd shader, but there are some weird stuff whenever i try to set it up in blender, so maybe its something else?
## Post #283
- Username: Simguy
- Rank: advanced
- Number of posts: 43
- Joined date: Tue Jul 24, 2007 2:11 am
- Post datetime: 2023-06-19T20:57:25+00:00
- Post Title: Re: Fate Grand Order Arcade

The raw glsl files are shipped with the game (for some reason). The problem is finding out which one is the the character shader, which textures slot in where and what the settings are. At least you don't have to guess how the shader works, you just have to find it. Personally I chose "uber_npr". Whether its based on an MMD shader or not I can't even guess.
## Post #284
- Username: gakdta2
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Thu Jan 26, 2023 8:22 pm
- Post datetime: 2023-06-21T13:19:18+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Simguy ↑Tue Jun 20, 2023 4:57 am at Tue Jun 20, 2023 4:57 am
>
> 
The raw glsl files are shipped with the game (for some reason). The problem is finding out which one is the the character shader, which textures slot in where and what the settings are. At least you don't have to guess how the shader works, you just have to find it. Personally I chose "uber_npr". Whether its based on an MMD shader or not I can't even guess.
oh so the shaders are already in the game files raw??? i see. i guess that can allow for alot of freedom when it comes to building the character back up in blender when it comes to looks?
## Post #285
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-07-14T21:38:37+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Thu Jan 05, 2023 1:28 am at Thu Jan 05, 2023 1:28 am
>
> 
Looks like this script for noesis handles both the Kancolle AND Fate files better:

https://github.com/h-kidd/noesis-project-diva


kancolle.jpg

New versions of Kancolle leaked out recently, last time it was up to v6.91.00:

6.91.00	2022/11/29	1.58GB
6.92.00	2023/03/08	1.83GB
7.00.00	2023/03/09	9.05GB
7.10.00	2023/05/29	121MB

I think they are not cumulative, or at least from this source, last time I saw 6.91.00 it was 9.3GB
## Post #286
- Username: BossMob9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 27, 2019 5:43 am
- Post datetime: 2023-07-14T22:55:10+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Sat Jul 15, 2023 5:38 am at Sat Jul 15, 2023 5:38 am
>
> 
GDL wrote: ↑Thu Jan 05, 2023 1:28 am
Looks like this script for noesis handles both the Kancolle AND Fate files better:

https://github.com/h-kidd/noesis-project-diva


kancolle.jpg


New versions of Kancolle leaked out recently, last time it was up to v6.91.00:

6.91.00	2022/11/29	1.58GB
6.92.00	2023/03/08	1.83GB
7.00.00	2023/03/09	9.05GB
7.10.00	2023/05/29	121MB

I think they are not cumulative, or at least from this source, last time I saw 6.91.00 it was 9.3GB

Mind sending a link?
## Post #287
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2023-07-16T15:28:48+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Sat Jul 15, 2023 5:38 am at Sat Jul 15, 2023 5:38 am
>
> 
GDL wrote: ↑Thu Jan 05, 2023 1:28 am
Looks like this script for noesis handles both the Kancolle AND Fate files better:

https://github.com/h-kidd/noesis-project-diva


kancolle.jpg


New versions of Kancolle leaked out recently, last time it was up to v6.91.00:

6.91.00	2022/11/29	1.58GB
6.92.00	2023/03/08	1.83GB
7.00.00	2023/03/09	9.05GB
7.10.00	2023/05/29	121MB

I think they are not cumulative, or at least from this source, last time I saw 6.91.00 it was 9.3GB

It breaks shape keys names
## Post #288
- Username: moonvoidd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 12, 2023 6:15 am
- Post datetime: 2023-07-24T00:59:46+00:00
- Post Title: Re: Fate Grand Order Arcade

any updates or news when the last batch is dropping? i want koyan and morgan
## Post #289
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-07-24T09:51:48+00:00
- Post Title: Re: Fate Grand Order Arcade

Nada so far. Which I really want it for close up the book with Arcade too.
## Post #290
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-07-25T16:25:51+00:00
- Post Title: Re: Fate Grand Order Arcade

what the situation with the game now ?
## Post #291
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-07-25T20:57:21+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from GDL ↑Mon Apr 17, 2023 3:57 am at Mon Apr 17, 2023 3:57 am
>
> 
moonvoidd wrote: ↑Mon Apr 17, 2023 3:15 am
Praying the next batch dump has Saber Shiki, Skadi, Melt, Osakabehime, Koyan & Morgan


As far as I know these are the "known" versions people have found in HDDs extracted from second hand arcade machines and only up to version 9.0 has ben decrypted and leaked (the decryption method/tools are known now the only issue is getting your hands on the .app files):
Code: Select all 2.06.00	11/01/2019
 3.00.00	26/03/2019
 3.60.01	04/07/2019
 4.00.00              2019
 4.50.00	16/12/2019
 5.31.00	26/03/2020
 5.51.00	06/07/2020
 6.10.00	18/08/2020
 6.11.00	08/09/2020
 6.20.01	11/09/2020
 6.21.00	25/09/2020
 6.31.00	23/10/2020
 6.51.00	23/12/2020
 7.20.00	22/03/2021
 7.60.01	09/07/2021
 8.00.00	26/08/2021
 8.11.00	27/08/2021
 8.30.00	18/11/2021
 8.40.00	16/12/2021
 9.00.00	09/12/2021
 9.10.00	03/02/2022
 9.31.00	26/04/2022
 9.50.00	23/06/2022
 9.61.00	01/08/2022
10.10.00	08/09/2022
10.30.00	01/11/2022
10.50.00	26/12/2022
10.60.00	
10.70.00	16/03/2023


If I remember correctly you can match these versions with the official release dates in the FGOA website to know which version includes which characters.

are you telling me i need to download the whole thing from the base version up to 9 to get all characters ???
## Post #292
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-07-25T21:26:53+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Mon Apr 17, 2023 1:37 pm at Mon Apr 17, 2023 1:37 pm
>
> 
China Discord servers, mostly.
In my case I'm only waiting for the patch were Gramps Hassan, Moriarty and Iskandar are for quitting on this game data hunt. After them, they is nothing interesting and for what I seeing on they Twitter account: They barely have add any new character in months.
[https://livedoor.blogimg.jp/gamemeister ... 950fb1.jpg](https://livedoor.blogimg.jp/gamemeister/imgs/2/5/25950fb1.jpg)
[https://livedoor.blogimg.jp/gamemeister ... befdcf.jpg](https://livedoor.blogimg.jp/gamemeister/imgs/4/f/4fbefdcf.jpg)
## Post #293
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2023-07-25T23:58:02+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from richardphone ↑Wed Jul 26, 2023 5:26 am at Wed Jul 26, 2023 5:26 am
>
> 
https://livedoor.blogimg.jp/gamemeister ... 950fb1.jpg
https://livedoor.blogimg.jp/gamemeister ... befdcf.jpg

Why are you doing spam? Anyone know the character if they had playing the game.
Please don't do spam as it will not change anything about unpacking what is left to unpack.
If you want to spam, go ahead and spam the page where they leak Arcade stuff and most likely get banned before a day.
## Post #294
- Username: richardphone
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jan 04, 2023 8:31 pm
- Post datetime: 2023-07-26T05:28:43+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Darkhowlings ↑Wed Jul 26, 2023 7:58 am at Wed Jul 26, 2023 7:58 am
>
> 
richardphone wrote: ↑Wed Jul 26, 2023 5:26 am
https://livedoor.blogimg.jp/gamemeister ... 950fb1.jpg
https://livedoor.blogimg.jp/gamemeister ... befdcf.jpg


Why are you doing spam? Anyone know the character if they had playing the game.
Please don't do spam as it will not change anything about unpacking what is left to unpack.
If you want to spam, go ahead and spam the page where they leak Arcade stuff and most likely get banned before a day.

not spamming , my mistake for making multiple replays
## Post #295
- Username: NineLivesBladeWorks
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 18, 2022 1:50 am
- Post datetime: 2023-07-27T21:20:19+00:00
- Post Title: Re: Fate Grand Order Arcade

Waiting for the day version with morgan gets uploaded
## Post #296
- Username: Gnomoed
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Mar 05, 2022 10:47 pm
- Post datetime: 2023-08-01T01:19:05+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Sat Apr 15, 2023 4:22 am at Sat Apr 15, 2023 4:22 am
>
> 
You can use the virtua fighter 5 bms script for kancolle arcade. You should be able to find it with a quick google.
This one? - [viewtopic.php?f=10&t=5462](https://forum.xentax.com/viewtopic.php?f=10&t=5462)
It does not work.
## Post #297
- Username: domonrain
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 05, 2023 10:35 pm
- Post datetime: 2023-08-05T17:07:04+00:00
- Post Title: Re: Fate Grand Order Arcade

hi, I am trying to export fbx file to the blender but it got no texture, is this something we have to setup manually or do we have a script to take care of that?
## Post #298
- Username: Gustav0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 06, 2022 9:20 am
- Post datetime: 2023-08-29T22:25:44+00:00
- Post Title: Re: Fate Grand Order Arcade

Anyone have Noah F/A art without the boards ?
## Post #299
- Username: NekoPrism04
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 30, 2023 9:11 pm
- Post datetime: 2023-09-06T06:21:59+00:00
- Post Title: Re: Fate Grand Order Arcade

Not sure if any other characters have this issue, but Mysterious Heroine X Alter (ID 119) has a broken armature. For all three of her steps her armature's always look like this. I'm unsure of how I would go about fixing this.
[armatureissue.png](https://xentaxbackup.github.io/file/24314_armatureissue.png)
## Post #300
- Username: NghtmrSrph
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 19, 2017 10:37 am
- Post datetime: 2023-09-13T18:18:41+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from johnwithlenon ↑Wed Feb 22, 2023 6:25 pm at Wed Feb 22, 2023 6:25 pm
>
> 
gakdta2 wrote: ↑Wed Feb 22, 2023 11:10 amHow do you add the specific lines in the noesis script for the textures?

Oh back then I was talking about the script from Simguy, it's just for my personal use (because I exported the textures from "_tex.bin" into *.png format), I added ".png" at those line then export the "_obj.bin" to *.fbx, therefore when I import the *.fbx into blender, the textures show up automatically without having to edit the textures slot. I haven't tried the project diva script yet.

Do you have an example of how those lines are supposed to look with the .png added? I tried adding it at the end of the lines but then got a bunch of errors when trying to load the objs in Noesis. Thanks!
## Post #301
- Username: johnwithlenon
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Oct 05, 2021 9:22 am
- Post datetime: 2023-09-16T12:00:16+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from NghtmrSrph ↑Thu Sep 14, 2023 2:18 am at Thu Sep 14, 2023 2:18 am
>
> Do you have an example of how those lines are supposed to look with the .png added? I tried adding it at the end of the lines but then got a bunch of errors when trying to load the objs in Noesis. Thanks!
This (I don't embed the image to save space for disscusion): [https://i.imgur.com/hfjBbor.png](https://i.imgur.com/hfjBbor.png)
But like I said before, it was for my personal use only because I exported the textures as *.png images, and idk if Simguy's script still works with newer dumps or not. You can try the [noesis-project-diva](https://github.com/h-kidd/noesis-project-diva) instead.
## Post #302
- Username: Qoying
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 20, 2023 2:49 am
- Post datetime: 2023-09-19T19:08:37+00:00
- Post Title: Re: Fate Grand Order Arcade

> Reply from Melvinnnn ↑Sat Apr 15, 2023 4:22 am at Sat Apr 15, 2023 4:22 am
>
> 
idkwhos wrote: ↑Tue Jan 03, 2023 5:38 pm
Simguy wrote: ↑Wed Mar 16, 2022 3:12 am
This should extract sprite texture.bins. There are no file names.
I was looking into character animations but I hit a wall (parsing the file and encoded rotation keys) and I guess its not that worthwhile since the game uses so much physics simulation and such.


Hi, Someone published the file dump recently for a game called Kancolle Arcade. I spent some time with it to see if I could extract the model from this game. It seems to use a file structure similar to Hatsune Miku Project DIVA and FGO Arcade, and I am able to extract obj.bin and tex.bin for the model with farc extractor for project DIVA. 

For the tex.bin, your script for FGO seems to work, and I am able to get most (if not all) of the texture files out.

However, obj.bin seems to be a bit different, and I have only been able to extract one of the many models in the file (in this case it's a turret lol):Honeyview_Kancolle model.jpg


From what I can tell, the problem is that Kancolle Arcade uses separate body/weapon models for a single character (in a single bin), while FGO Arcade uses one single model for each character:

Kncolle:
Code: Select all00C0: 00 00 00 00 9A 01 00 00 00 00 00 00 B1 01 00 00 00 00 00 00 C8 01 00 00 00 00 00 00 63 68 30 32 ����š������±������È������ch02
00E0: 30 31 5F 30 31 5F 62 5F 62 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 01_01_b_body_model�ch0201_01_b_g
0100: 65 61 72 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 67 65 61 72 30 34 5F 6D ear01_model�ch0201_01_b_gear04_m
0120: 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 62 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 odel�ch0201_01_b_wp02_model�ch02
0140: 30 31 5F 30 31 5F 62 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 62 01_01_b_wp05_model�ch0201_01_n_b
0160: 6F 64 79 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 67 65 61 72 30 31 5F 6D 6F 64 ody_model�ch0201_01_n_gear01_mod
0180: 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 31 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 el�ch0201_01_n_wp01_model�ch0201
01A0: 5F 30 31 5F 6E 5F 77 70 30 32 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 _01_n_wp02_model�ch0201_01_n_wp0
01C0: 33 5F 6D 6F 64 65 6C 00 63 68 30 32 30 31 5F 30 31 5F 6E 5F 77 70 30 35 5F 6D 6F 64 65 6C 00 00 3_model�ch0201_01_n_wp05_model

FGO:
Code: Select all0000h: 00 25 06 05 01 00 00 00 2C 00 00 00 00 00 00 00  .%......,....... 
0010h: 34 00 00 00 00 00 00 00 34 00 00 00 00 00 00 00  4.......4....... 
0020h: 00 00 00 00 00 00 00 00 00 00 00 00 50 00 00 00  ............P... 
0030h: 00 00 00 00 3C 00 00 00 00 00 00 00 73 76 74 5F  ....<.......svt_ 
0040h: 30 30 30 31 5F 73 30 31 5F 6D 6F 64 65 6C 00 00  0001_s01_model.. 
0050h: 06 00 02 00 00 00 00 00 C0 01 00 00 00 00 00 00  ........À....... 
0060h: 13 00 00 00 00 00 00 00 0A 00 00 00 00 00 00 00  ................ 
0070h: 10 1C 00 00 00 00 00 00 18 00 00 00 00 00 00 00  ................ 


I tried to modify the script to make it work but failed...Could you help? Much appreciated!




Here's a link to the obj.bin and tex.bin that I extracted:
https://mega.nz/folder/wG5GUYgT#rqjHXWWlb0M1p_7yiWcwew


This is a rudimentary question, but how can I get a farc extractor for project DIVA?
Also, can you tell me how to extract obj.bin and tex.bin from a kanncolle arcade dump?
To extract multi model"
[https://github.com/h-kidd/noesis-project-diva](https://github.com/h-kidd/noesis-project-diva)
a file  named "multi_model.bat" place this file in the folder which contains “Noesis.exe” 
launch the "multi_model.bat"
## Post #303
- Username: Insistent
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Apr 05, 2019 3:04 pm
- Post datetime: 2023-10-04T04:51:55+00:00
- Post Title: Re: Fate Grand Order Arcade

Has anyone managed to find or extract passionlip model yet?
## Post #304
- Username: BossMob9
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Sep 27, 2019 5:43 am
- Post datetime: 2023-10-18T19:43:47+00:00
- Post Title: Re: Fate Grand Order Arcade

Has anyone managed to figure out getting the character animations to load in Noesis?
