## Post #1
- Username: scizzer12
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 03, 2017 11:30 pm
- Post datetime: 2017-10-25T14:29:24+00:00
- Post Title: Weird PS2 .bin/.hd pair with headerless TIM2 graphics

Over the last week I've been working on a crappy Visual Novel released only in Japan. (Zero no Tsukaima: Shou-akuma to Harukaze no Concerto).
At first I just wanted audio and I was able to cut the files with VGMToolbox and convert the headerless ADPCM by guessing interleave/ sample rates. Now I've gotten the itch to rip textures from the game but have come across a roadblock. Here's what I have so far:

Files are structured in pairs e.g., SCENEDAT.bin/SCENEDAT.hd

The .hd (presumably header) file is just a list of 4 bytes which I'm guessing are relative offsets (or filesize. I don't know the proper terminology) because they're not sequential. 
They also don't seem to line up with any structures in the bin file as they are.
There are about 1180 entries in the header and 1100 TIM2 files in the bin.
.hd file


The .bin file is strange because it lacks anything obvious in the header of it. No tables, no offset values, no header size.

The TIM2 files (identified by magic word) scattered inside are even weirder because they're offset from a sensible position by 9 bytes.
[They also don't seem to have any of the proper header except for the version number and the first byte of the image count](http://wiki.xentax.com/index.php?title=TM2_TIM2)
I also don't think the image is uncompressed because it's basically random noise when viewed with something like TextureFinder.
It's definitely .tm2 though since there are a bunch of plaintext error messages inside the elf file (SLPS_257.09).
TIM2 inside .bin file


Any help would be appreciated, even just encouragement.

Here's a download link to the elf, bin and hd. (70MB packed)
Here's the file structure of the entire disc:

```
		11/09/2006  01:07 AM            33,521 CDVDSTM.IRX
		11/09/2006  01:07 AM            15,653 DBCMAN.IRX
		11/09/2006  01:07 AM            12,149 DS2U_D.IRX
		11/09/2006  01:07 AM           278,353 IOPRP310.IMG
		11/09/2006  01:07 AM            30,085 LIBSD.IRX
		11/09/2006  01:07 AM            28,037 MC2_D.IRX
		11/09/2006  01:07 AM            63,005 MODHSYN.IRX
		11/09/2006  01:07 AM            21,941 MODMIDI.IRX
		11/09/2006  01:07 AM             9,161 SDRDRV.IRX
		11/09/2006  01:07 AM            11,289 SIO2D.IRX
		11/09/2006  01:07 AM             5,217 SIO2MAN.IRX
		11/09/2006  01:07 AM             9,601 SKHSYNTH.IRX
		11/09/2006  01:07 AM            12,973 SKMIDI.IRX
		11/09/2006  01:07 AM             9,717 SKSOUND.IRX
		11/09/2006  01:07 AM            35,009 USBD.IRX
					  15 File(s)        575,711 bytes
10/25/2017  09:16 AM    <DIR>          MOVIE
		12/24/2006  11:50 AM         5,275,652 BTLMOV00.PSS
		12/24/2006  11:50 AM         5,275,652 BTLMOV01.PSS
		12/24/2006  11:50 AM         4,603,908 BTLMOV02.PSS
		12/24/2006  11:50 AM         4,603,908 BTLMOV03.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV04.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV05.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV06.PSS
		12/24/2006  11:50 AM         3,145,732 BTLMOV07.PSS
		12/24/2006  11:50 AM         3,145,732 BTLMOV08.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV09.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV10.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV11.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV12.PSS
		12/24/2006  11:50 AM         4,046,852 BTLMOV13.PSS
		12/24/2006  11:50 AM         3,850,244 BTLMOV14.PSS
		12/24/2006  11:50 AM         3,883,012 BTLMOV15.PSS
		11/15/2006  11:48 PM         8,000,000 BTLMOV16.PSS
		11/15/2006  11:46 PM         8,000,000 BTLMOV17.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV18.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV19.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV20.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV21.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV22.PSS
		11/15/2006  11:47 PM         8,000,000 BTLMOV23.PSS
		12/19/2006  09:59 AM        69,795,844 ZERO.PSS
		12/19/2006  10:05 AM        94,568,452 ZEROED.PSS
					  26 File(s)    293,146,696 bytes
12/24/2006  10:47 PM         7,194,624 NORMAL.BIN
12/24/2006  10:47 PM             1,440 NORMAL.HD
10/25/2017  09:18 AM                 0 out.txt
12/24/2006  10:50 PM        95,215,616 SCENEDAT.bin
12/24/2006  10:50 PM             4,736 SCENEDAT.hd
12/24/2006  11:05 PM         6,492,160 SCENE_ID.bin
12/24/2006  11:05 PM             7,684 SCENE_ID.hd
12/24/2006  11:07 PM         1,386,560 SLPS_257.09
12/24/2006  10:47 PM       150,704,128 SOUND_ID.BIN
12/24/2006  10:47 PM               424 SOUND_ID.HD
12/21/2006  12:04 AM                57 SYSTEM.CNF
12/24/2006  10:44 PM       981,067,776 VOICE_ID.bin
12/24/2006  10:44 PM            64,768 VOICE_ID.HD
              13 File(s)  1,242,139,973 bytes

     Total Files Listed:
              54 File(s)  1,535,862,380 bytes
               8 Dir(s)  365,048,913,920 bytes free

```


Well it's been a week and I can't shadow bump in this forum so I'll reply with updates. If that isn't allowed I can just go back to having it all in one post again. Just delete this reply or message me.
I would have expected someone to at least go "Yeah that looks encrypted" or something at least.

> Reply from scizzer12
>
> 
Update 1: 
Looks like the header file (SCENEDAT.hd) does contain file sizes but in the container (SCENEDAT.bin) they're padded to 2kb (0x800). Still looking for the actual file headers but there seems to be two files before the list of TIM2 files begins with magic numbers seemingly of 54 00 30 21 and 54 04 00 00 (I'm assuming they're offset the same way the TIM2s are)
 
and


Update 2: 
Other files from different bin archives seem to be purposefully damaged in some way and may indicate some type of compression/ encryption. Probably not anything serious though as things are mostly visible. For instance, here's a snippet of what seems to be a Java file encoded in SHIFT-JIS. Notice the decently consistent replacement of garbage characters along beginning columns and similar replacements in words like "function".
## Post #2
- Username: num421337
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 06, 2010 6:46 am
- Post datetime: 2018-03-26T00:36:49+00:00
- Post Title: Weird PS2 .bin/.hd pair with headerless TIM2 graphics

I'm having similar issues with the game I'm trying to rip textures from, if I come across a solution I will try to let you know. I've seen some TIM2 files in the hex code of the GioGio ps2 game as well.
