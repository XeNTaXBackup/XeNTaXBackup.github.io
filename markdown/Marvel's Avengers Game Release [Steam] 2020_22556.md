## Post #1
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-15T06:23:39+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

Hello everyone! 
Happy to create my first topic here because im really enjoy community for the long time. 
This topic is about Marvel's Avengers game and extracting files from it.
I have pre-ordered this game and have access to the files because beta open on weekends 14-16th August.
All i know right now: 
1.Game use same engine as Rise of Tomb Rider
2.Files comes in .tiger format (I have x6 files 4GB each)
3.Old tools from Rise of Tomb rider (dumper, unpacker) and any other like NinjaRipper doesn't work and have no results.

If anyone can help me with understanding how to unpack this files or maybe interested in this way feel free ask anything! 
I can upload any gamefiles from beta launch and maybe we will find workable solution  
Thank you for attention and keep well!

UPD: Open Beta 21-23 August

UPD1: Big thanks to Gh0stBlade and Ekey for decryption tool and Tiger Unpacker/DRM Dumper

UPD2: Release! Big thanks to Gh0stBlade for updated release decryption tool! Links in post updated. Kindly waiting for Ekey Unpacker/Dumper update!

Decryption tool : You can download it [here](https://forum.xentax.com/viewtopic.php?p=166510#p166510)

Tiger Unpacker : Tiger Unpacker - 0.0.2.33474
[DOWNLOAD](https://www58.zippyshare.com/v/4LEGfWDE/file.html)

```
    MAB.Tiger.Unpacker <m_TigerFile> <m_UnpackFolder>

    m_TigerFile - Source of Tiger file
    m_UnpackFolder - Destination directory

[Examples]
    MAB.Tiger.Unpacker D:\MAB\Decrypted\bigfile.000.tiger D:\Unpacked\bigfile

```


Note: m_TigerFile - Only following archives are allowed bigfile.000.tiger or bigfile.update1.000.000.tiger, orher files are parts.

DRM Dumper : DRM Dumper - 0.0.2.39914
[DOWNLOAD](https://www47.zippyshare.com/v/uXSPfnCT/file.html)

```
    MAB.DRM.Dumper <m_DRMFile> <m_UnpackFolder> <m_TigerFolder>

    m_DRMFile - Source of DRM file
    m_UnpackFolder - Destination directory
    m_TigerFolder - Folder with decrypted TIGER files
	
[Examples]
    MAB.DRM.Dumper
    m_DRMFile -> D:\MAB\bigfile\default\pcx64-w\hulk.drm
    m_UnpackFolder -> D:\Unpacked\DRM
    m_TigerFolder -> D:\MAB\Decrypted
	
    MAB.DRM.Dumper D:\Unpacked\bigfile\default\pcx64-w\hulk.drm D:\Unpacked\DRM D:\MAB\Decrypted

```

We still need .mamesh and .mapcd file format parser because all data (mesh and textures) inside this 2 fileformats .
## Post #2
- Username: AzothRaven
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-08-15T18:15:09+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

Can confirm the files are encrypted or compressed globally.
## Post #3
- Username: Joschka
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-08-17T22:25:18+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

Hey guys, I've managed to decrypt the Marvel's Avengers Beta .tiger files. Attached you will find the tool which can decrypt all the .tiger files with no problem.

Usage:
1. Extract the contents of the TigerDecrypt.zip to the root of where Marvel's Avengers Beta is installed (this means all files and folders.
2. Launch Decrypt.bat
3. The decrypted files are outputted to the /Decrypted/ folder.
Enjoy, the decrypted files! 

Note: We still need a bigfile unpacker.

Cheers.
[TigerDecrypt.zip](https://xentaxbackup.github.io/file/18622_TigerDecrypt.zip)
## Post #4
- Username: FGeeHD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 20, 2020 9:31 pm
- Post datetime: 2020-08-20T13:33:50+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

Open beta is available on Steam now, would love to see this one figured out
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-21T12:18:11+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Tue Aug 18, 2020 6:25 am at Tue Aug 18, 2020 6:25 am
>
> 
Hey guys, I've managed to decrypt the Marvel's Avengers Beta .tiger files. Attached you will find the tool which can decrypt all the .tiger files with no problem.

Usage:
1. Extract the contents of the TigerDecrypt.zip to the root of where Marvel's Avengers Beta is installed (this means all files and folders.
2. Launch Decrypt.bat
3. The decrypted files are outputted to the /Decrypted/ folder.
Enjoy, the decrypted files! 

Note: We still need a bigfile unpacker.

Cheers.
Woah, are they seriously encrypted?
## Post #6
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-22T11:56:19+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

In general, I made an unpacker, but there is one caveat, decryptor for some reason skips some encrypted data. For example, we have a next entry

```
   Offset: 0A2095B0
   Size: 116
   Part: bigfile.006.tiger
```


If you compare the original tiger with the decrypted one, the data will be almost identical, in fact, the block is skipped. Screens

Original TIGER


Decrypted TIGER


There are not so many such files, but if you plan to get all the available resources, then this should be fixed
## Post #7
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-22T12:51:39+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ekey ↑Sat Aug 22, 2020 7:56 pm at Sat Aug 22, 2020 7:56 pm
>
> 
In general, I made an unpacker, but there is one caveat, decryptor for some reason skips some encrypted data. For example, we have a next entry
Code: Select alldefault\__Unknown\2A95B0ADE124AA58
   Offset: 0A2095B0
   Size: 116
   Part: bigfile.006.tiger

If you compare the original tiger with the decrypted one, the data will be almost identical, in fact, the block is skipped. Screens

Original TIGER


Decrypted TIGER


There are not so many such files, but if you plan to get all the available resources, then this should be fixed

Great! Thank you ! Nice start btw  So with your unpacker what kind of models you can get? Heroes, levels etc? Or rest encrypted part of .tiger keep textures unpacked?
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-22T13:38:11+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

I we planning to make DRMDumper like in previous games on this engine, but first we need to resolve the problem with decryption
## Post #9
- Username: Ekey
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-08-22T13:44:33+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

Hey EKey, I managed to solve a bug with the decrypter a few days ago. Can you try the one I've attached?

Thanks.
[TigerDecrypt_v1_2.zip](https://xentaxbackup.github.io/file/18635_TigerDecrypt_v1_2.zip)
## Post #10
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-22T14:07:40+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Aug 22, 2020 9:44 pm at Sat Aug 22, 2020 9:44 pm
>
> 
Hey EKey, I managed to solve a bug with the decrypter a few days ago. Can you try the one I've attached?

Thanks.

Hey'a. Thanks, I'll check it later. I need to redownload all languages again
## Post #11
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-22T15:50:32+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

To make the wait not so boring, I suggest you help to collect as many file names as possible. I fixed the main executable file so that the file names are written to the main log 

You can found him in following path

```
C:\Users\USERNAME\Documents\Marvel's Avengers Beta\Marvel's Avengers Beta.log
```


In log you can see lines like this:

```
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\generalbank.drm
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\globalsoundinfo.drm
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\globalaniminfo.drm
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\globalstreamlayers.drm
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\globalbiometextureinfo.drm
18:46:57:973 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\checkpoint.drm
18:47:00:723 (00018808) > [ASSERT] Fatal error: Can't open file pcx64-w\fx_weather.drm
```

Please note that the log is overwritten if the game is restarted. Make copies

[DOWNLOAD](https://www34.zippyshare.com/v/YVa1L5sa/file.html)
## Post #12
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-22T22:23:46+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

...
## Post #13
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-23T01:08:16+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

This here filelist should make a good start. Contains 12,998 files including all currently released (and marketplace) hero appearances, alongside every file loaded during the first five or so missions.


[https://mega.nz/file/ZT4lkKgD#szQ2wQ_VY ... htJ7EnYEYc](https://mega.nz/file/ZT4lkKgD#szQ2wQ_VYBaUeB3RA6WlgENnK0k9uwsoZhtJ7EnYEYc)
## Post #14
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-23T02:34:12+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

> Reply from TrumpetPro ↑Sun Aug 23, 2020 9:08 am at Sun Aug 23, 2020 9:08 am
>
> 
This here filelist should make a good start. Contains 12,998 files including all currently released (and marketplace) hero appearances, alongside every file loaded during the first five or so missions. Unfortunately Thor and Cap only have their base appearances.


https://mega.nz/file/ZT4lkKgD#szQ2wQ_VY ... htJ7EnYEYc

Thanks, i will merge with my current list
## Post #15
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-23T16:08:03+00:00
- Post Title: Marvel's Avengers Game Release [Steam] 2020

I'm still digging DRM format, a lot of work has already been done, just a little bit left.

The format has changed slightly, but still remains similar to the previous version one from "Shadow of the Tomb Raider".
Here is one of the logs of working with the globaldialogueinfo.drm file:

```
[CDRM INFO]: Total Chunks: 1
[CDRM INFO]: Data Size: 1932
[CDRM INFO]: Compressed Data Size: 1932

[CDRM CHUNK INFO]: Offset: 00000020, ZSize: 1932, Size: 1932, Compressed: false

[RESOURCE INFO]: Total Resources: 34
[RESOURCE INFO]: [RESOURCE_1] -> Type: Dialogue, Offset: 46E5F590, Size: 456, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_2] -> Type: Dialogue, Offset: 9E9AF760, Size: 585, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_3] -> Type: Dialogue, Offset: 9E9AFBA0, Size: 475, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_4] -> Type: Dialogue, Offset: 9E9AFF80, Size: 677, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_5] -> Type: Dialogue, Offset: 9E9B0240, Size: 416, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_6] -> Type: Dialogue, Offset: 9E9B03F0, Size: 468, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_7] -> Type: Dialogue, Offset: 9E9B0A50, Size: 562, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_8] -> Type: Dialogue, Offset: 9F37EDC0, Size: 521, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_9] -> Type: Dialogue, Offset: 9F37EFE0, Size: 385, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_10] -> Type: Dialogue, Offset: 9F37F180, Size: 546, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_11] -> Type: Dialogue, Offset: 9F37F3C0, Size: 565, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_12] -> Type: Dialogue, Offset: 9F37F610, Size: 462, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_13] -> Type: Dialogue, Offset: 9F37F7F0, Size: 470, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_14] -> Type: Dialogue, Offset: 9F37F9E0, Size: 714, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_15] -> Type: Dialogue, Offset: 9F37FCC0, Size: 436, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_16] -> Type: Dialogue, Offset: 9F37FE90, Size: 337, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_17] -> Type: Object, Offset: 9F380000, Size: 120, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_18] -> Type: Dialogue, Offset: B8F66D80, Size: 477, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_19] -> Type: Dialogue, Offset: B8F66F70, Size: 552, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_20] -> Type: Dialogue, Offset: B8F671B0, Size: 378, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_21] -> Type: Dialogue, Offset: B8F67340, Size: 454, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_22] -> Type: Dialogue, Offset: B8F676F0, Size: 377, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_23] -> Type: Dialogue, Offset: F2E690F0, Size: 471, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_24] -> Type: Dialogue, Offset: 04F03920, Size: 445, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_25] -> Type: Dialogue, Offset: 04F32B60, Size: 436, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_26] -> Type: Dialogue, Offset: 04F32D30, Size: 837, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_27] -> Type: Dialogue, Offset: 04F5A180, Size: 402, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_28] -> Type: Dialogue, Offset: 05655920, Size: 647, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_29] -> Type: Dialogue, Offset: 05655E40, Size: 546, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_30] -> Type: Dialogue, Offset: 0D0B88A0, Size: 545, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_31] -> Type: Dialogue, Offset: 0D49C910, Size: 358, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_32] -> Type: Dialogue, Offset: 0D49CA90, Size: 347, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_33] -> Type: DTPData, Offset: 0D49CC00, Size: 14191, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_34] -> Type: DTPData, Offset: 0D4A0380, Size: 40, Archive: bigfile.003.tiger
[INFO]: DONE!

```


New resource types have been added, one of which is number 17. If you go through all the offsets, you can see lines with the names of the characters in the Marvel universe, like:

```
Hank Pym
Dr. Madame Curie "Maddy" Cho.Dr. Madame Curie
MODOK
Sidney "Gaffer" Levine
Alisande Morales.Alisande Moralesov
Monica Rappaccini
```


and etc.

I have temporarily set the type 17 as Dialogue. Not sure if this is correct, maybe this is a database of comics, I don't know for sure.
I also attached a log from the largest DRM > hulk.drm so that you can already start digging the resources by provided offsets 
[hulk_log.rar](https://xentaxbackup.github.io/file/18643_hulk_log.rar)
## Post #16
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-23T17:24:56+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Mon Aug 24, 2020 12:08 am at Mon Aug 24, 2020 12:08 am
>
> 
I'm still digging DRM format, a lot of work has already been done, just a little bit left.

The format has changed slightly, but still remains similar to the previous version one from "Shadow of the Tomb Raider".
Here is one of the logs of working with the globaldialogueinfo.drm file:
Code: Select all[CDRM INFO]: File: globaldialogueinfo.drm
[CDRM INFO]: Total Chunks: 1
[CDRM INFO]: Data Size: 1932
[CDRM INFO]: Compressed Data Size: 1932

[CDRM CHUNK INFO]: Offset: 00000020, ZSize: 1932, Size: 1932, Compressed: false

[RESOURCE INFO]: Total Resources: 34
[RESOURCE INFO]: [RESOURCE_1] -> Type: Dialogue, Offset: 46E5F590, Size: 456, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_2] -> Type: Dialogue, Offset: 9E9AF760, Size: 585, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_3] -> Type: Dialogue, Offset: 9E9AFBA0, Size: 475, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_4] -> Type: Dialogue, Offset: 9E9AFF80, Size: 677, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_5] -> Type: Dialogue, Offset: 9E9B0240, Size: 416, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_6] -> Type: Dialogue, Offset: 9E9B03F0, Size: 468, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_7] -> Type: Dialogue, Offset: 9E9B0A50, Size: 562, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_8] -> Type: Dialogue, Offset: 9F37EDC0, Size: 521, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_9] -> Type: Dialogue, Offset: 9F37EFE0, Size: 385, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_10] -> Type: Dialogue, Offset: 9F37F180, Size: 546, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_11] -> Type: Dialogue, Offset: 9F37F3C0, Size: 565, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_12] -> Type: Dialogue, Offset: 9F37F610, Size: 462, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_13] -> Type: Dialogue, Offset: 9F37F7F0, Size: 470, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_14] -> Type: Dialogue, Offset: 9F37F9E0, Size: 714, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_15] -> Type: Dialogue, Offset: 9F37FCC0, Size: 436, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_16] -> Type: Dialogue, Offset: 9F37FE90, Size: 337, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_17] -> Type: Object, Offset: 9F380000, Size: 120, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_18] -> Type: Dialogue, Offset: B8F66D80, Size: 477, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_19] -> Type: Dialogue, Offset: B8F66F70, Size: 552, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_20] -> Type: Dialogue, Offset: B8F671B0, Size: 378, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_21] -> Type: Dialogue, Offset: B8F67340, Size: 454, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_22] -> Type: Dialogue, Offset: B8F676F0, Size: 377, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_23] -> Type: Dialogue, Offset: F2E690F0, Size: 471, Archive: bigfile.000.tiger
[RESOURCE INFO]: [RESOURCE_24] -> Type: Dialogue, Offset: 04F03920, Size: 445, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_25] -> Type: Dialogue, Offset: 04F32B60, Size: 436, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_26] -> Type: Dialogue, Offset: 04F32D30, Size: 837, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_27] -> Type: Dialogue, Offset: 04F5A180, Size: 402, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_28] -> Type: Dialogue, Offset: 05655920, Size: 647, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_29] -> Type: Dialogue, Offset: 05655E40, Size: 546, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_30] -> Type: Dialogue, Offset: 0D0B88A0, Size: 545, Archive: bigfile.001.tiger
[RESOURCE INFO]: [RESOURCE_31] -> Type: Dialogue, Offset: 0D49C910, Size: 358, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_32] -> Type: Dialogue, Offset: 0D49CA90, Size: 347, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_33] -> Type: DTPData, Offset: 0D49CC00, Size: 14191, Archive: bigfile.003.tiger
[RESOURCE INFO]: [RESOURCE_34] -> Type: DTPData, Offset: 0D4A0380, Size: 40, Archive: bigfile.003.tiger
[INFO]: DONE!


New resource types have been added, one of which is number 17. If you go through all the offsets, you can see lines with the names of the characters in the Marvel universe, like:
Code: Select allJames Woo
Hank Pym
Dr. Madame Curie "Maddy" Cho.Dr. Madame Curie
MODOK
Sidney "Gaffer" Levine
Alisande Morales.Alisande Moralesov
Monica Rappaccini

and etc.

I have temporarily set the type 17 as Dialogue. Not sure if this is correct, maybe this is a database of comics, I don't know for sure.
I also attached a log from the largest DRM > hulk.drm so that you can already start digging the resources by provided offsets

Sounds really good! Thank you! Can't wait for exporter
## Post #17
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-23T20:54:44+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from bertonberton ↑Mon Aug 24, 2020 1:24 am at Mon Aug 24, 2020 1:24 am
>
> Sounds really good! Thank you! Can't wait for exporter
I wanted to make a release, but unexpectedly found out that several types of DRM are now used, one is an index for resources, and the second is a resource, so I need some more time to resolve the challenge
## Post #18
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-24T15:57:03+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Can someone take a look at this texture? I want to make sure that the data is unpacked correctly. According to the header, the size is correct

Image data size: 1398128
Width and height seems is 1024x1024

But texture data looks like are compressed or? 

[https://www67.zippyshare.com/v/4CyzqNUz/file.html](https://www67.zippyshare.com/v/4CyzqNUz/file.html)
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-24T16:25:39+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Mon Aug 24, 2020 11:57 pm at Mon Aug 24, 2020 11:57 pm
>
> 
But texture data looks like are compressed or?
Looks like a BC7 compressed normal map. Maybe for a particle or something? The data starts out with lower mipmaps and the largest mipmap is the last. It starts at 0x555C4 for this sample.
## Post #20
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-24T16:45:25+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Interesting, I tried this tool but it doesn't show the picture, even according to your settings



Maybe I have an outdated version, I don't know. Thanks anyway.
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-24T16:48:40+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Tue Aug 25, 2020 12:45 am at Tue Aug 25, 2020 12:45 am
>
> 
I tried this tool but it doesn't show the picture

Maybe you have a problem with the "texconv" setup. Better update that to latest version too.
## Post #22
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-24T16:54:43+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I solved this problem, there should be no spaces in the file name
## Post #23
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T01:17:30+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

So, I almost finished the dumper, here are the unpacked resources from hulk.drm for for analysis.
New type 17 is a localization strings, it's confirmed. Some mesh files have unusual data (example file is Resource_96202.mesh)

Resources extensions assigned as temporary before release.

Warninig: Packed size is 1,01GB and unpacked size is 2,75GB. [here](https://easyupload.io/h9omki)
## Post #24
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-25T14:01:18+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Tue Aug 25, 2020 9:17 am at Tue Aug 25, 2020 9:17 am
>
> 
So, I almost finished the dumper, here are the unpacked resources from hulk.drm for for analysis.
New type 17 is a localization strings, it's confirmed. Some mesh files have unusual data (example file is Resource_96202.mesh)

Resources extensions assigned as temporary before release.

Warninig: Packed size is 1,01GB and unpacked size is 2,75GB. here

Great! Thank you!! As i say previously can't wait for dumper release
## Post #25
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T16:26:11+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Well, I think it's time for release 

First, I want to say thanks to [Gh0stBlade](https://forum.xentax.com/memberlist.php?mode=viewprofile&u=29080) for the tool that decrypts archives. You can download it [here](https://forum.xentax.com/viewtopic.php?p=166510#p166510)

Additional thanks to TrumpetPro for log.

Since I do not have an decryption algorithm, you need to decrypt all archives (link above for download tool) that are, this is one of the conditions for using the tools. Here is my list of files that I have decrypted (Your list of files may be different because I we downloaded packages with other languages for tests). Also you can download packages with ultra textures.

```
bigfile.001.tiger
bigfile.002.tiger
bigfile.003.tiger
bigfile.004.tiger
bigfile.005.tiger
bigfile.006.tiger
bigfile.update1.000.000.tiger
bigfile.update1.000_arabic.000.tiger
bigfile.update1.000_english.000.tiger
bigfile.update1.000_french.000.tiger
bigfile.update1.000_german.000.tiger
bigfile.update1.000_iberspanish.000.tiger
bigfile.update1.000_italian.000.tiger
bigfile.update1.000_japanese.000.tiger
bigfile.update1.000_latamspanish.000.tiger
bigfile.update1.000_polish.000.tiger
bigfile.update1.000_portuguese.000.tiger
bigfile.update1.000_russian.000.tiger
bigfile.update1.000_simplechinese.000.tiger
bigfile.update1.000_ultra.000.tiger
bigfile_arabic.000.tiger
bigfile_english.000.tiger
bigfile_french.000.tiger
bigfile_german.000.tiger
bigfile_iberspanish.000.tiger
bigfile_italian.000.tiger
bigfile_japanese.000.tiger
bigfile_latamspanish.000.tiger
bigfile_polish.000.tiger
bigfile_portuguese.000.tiger
bigfile_russian.000.tiger
bigfile_simplechinese.000.tiger
bigfile_ultra.000.tiger
bigfile_ultra.001.tiger
bigfile_ultra.002.tiger
bigfile_ultra.003.tiger
bigfile_ultra.004.tiger

```


Tools are console with a simple batch usage. [Microsoft .NET Framework 4.7.2](https://support.microsoft.com/en-us/help/4054530/microsoft-net-framework-4-7-2-offline-installer-for-windows) are required!

Tools
[DOWNLOAD](https://forum.xentax.com/viewtopic.php?p=166524#p166524)

If you have troubles with unpacking DRM, be sure to indicate the file name and from which archive it is!
I think the tools will work on release game version, but I'm not sure. I didn't pre-order.

Happy digging
## Post #26
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-25T17:06:55+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Thank you Ekey ! Also can you share some information about the structure?
## Post #27
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T17:37:16+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from LazyCat2k3 ↑Wed Aug 26, 2020 1:06 am at Wed Aug 26, 2020 1:06 am
>
> 
Thank you Ekey ! Also can you share some information about the structure?
The structure from what? Tiger? DRM?
## Post #28
- Username: huitbgoiouythy
- Rank: beginner
- Number of posts: 20
- Joined date: Fri Nov 16, 2018 12:43 am
- Post datetime: 2020-08-25T17:49:06+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Thanks everyone
## Post #29
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-25T17:50:45+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Has anyone tested to see if Rise of the Tomb Raider's tools work on unpacked .DRM files yet?
## Post #30
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-25T17:57:32+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Thank you Ekey! Just trying unpack some DRM Files with MAB.DRM.Dumper  and got error that script can't find bigfile.000,tiger in decrypted directory 
Also script create folder with UnpackFolder name and drm file name which i choose. I've try unpack hulk.drm from bigfile.000.tiger
How to fix this?
## Post #31
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-25T18:04:54+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Wed Aug 26, 2020 1:37 am at Wed Aug 26, 2020 1:37 am
>
> 
LazyCat2k3 wrote: ↑Wed Aug 26, 2020 1:06 am
Thank you Ekey ! Also can you share some information about the structure? 

The structure from what? Tiger? DRM?

Both.   
I found out that it also uses fnv64 for namehash but can't figure out how it indexes other tiger files.
## Post #32
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-25T18:16:31+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Here few error messages from drm dumper 
[WARNING]: Archive bigfile.000.tiger not found in D:\CRY\SOFT\Decrypted directory! The current resource will be skipped

And last strings 

в System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   в System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   в System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   в System.IO.FileStream..ctor(String path, FileMode mode)
   в MAB.DRM.Dumper.Program.iSaveToFile(String m_FileName, Byte[] pBuffer)
   в MAB.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder)
   в MAB.DRM.Dumper.Program.Main(String[] args)
## Post #33
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T18:23:29+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

```
Int32 dwVersion; // 8
Int32 dwPartsCount;
Int32 dwTotalFiles;
Int32 dwPriority;
byte[] lpBasePath[32];
Int32 dwUnknown0; // 65535
Int32 dwTotalLanguages;

for (Int32 i = 0; i < dwTotalLanguages; i++)
{
    Int32 dwLanguageCode;
    Int32 dwFlag; // 0, 1
    byte[] lpLanguage[16];
}

for (Int32 i = 0; i < dwTotalFiles; i++)
{
    UInt64 dwHash;
    UInt32 dwLocale; // Language code
    Int32 dwSize;
    UInt32 dwOffset;
    UInt16 wPriorityID;
    UInt16 wTigerID;
}
```


About DRM, there is complicated structure with two types. First type is 0 - this is index of chunked resources, second type is 2 - resource data.
I've been digging this for 3 days
## Post #34
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T18:24:17+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from bertonberton ↑Wed Aug 26, 2020 2:16 am at Wed Aug 26, 2020 2:16 am
>
> 
Here few error messages from drm dumper 
[WARNING]: Archive bigfile.000.tiger not found in D:\CRY\SOFT\Decrypted directory! The current resource will be skipped

And last strings 

в System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   в System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   в System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   в System.IO.FileStream..ctor(String path, FileMode mode)
   в MAB.DRM.Dumper.Program.iSaveToFile(String m_FileName, Byte[] pBuffer)
   в MAB.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder)
   в MAB.DRM.Dumper.Program.Main(String[] args)

Fixed
## Post #35
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-25T18:25:25+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Just a couple notes:

A. I observed that you have to decrypt all .tiger files for the unpacker to work - with an NA English copy, this should be ten different .tiger files. Otherwise it simply spams the "skipped" message until you end up with an empty folder. Once again, if anybody is having that issue make sure you've unpacked *everything*.

B. For the .DRM unpacker - using the command 
```
MAB.DRM.Dumper.exe "F:\Game Dumps\MARVEL's Avengers Beta\Unpacked\default\pcx64-w\ironman.drm" "C:\Users\Solaris\Desktop\Avengers\output\ironman\" "F:\Game Dumps\MARVEL's Avengers Beta\Decrypted\"
```
 the tool does not display any errors and does not put any files in "C:\Users\Solaris\Desktop\Avengers\output\ironman\"  - however, it acts as though I never added any parameters in the first place with the output:

```
(c) 2020 Ekey (h4x0r) / v0.0.2.34539

Tool for decrypt TIGER files made by Gh0stBlade you can found by the link below!
https://forum.xentax.com/viewtopic.php?p=166049#p166049

[Usage]
    MAB.DRM.Dumper <m_DRMFile> <m_UnpackFolder> <m_TigerFolder>

    m_DRMFile - Source of DRM file
    m_UnpackFolder - Destination directory
    m_TigerFolder - Folder with decrypted TIGER files

[Examples]
    MAB.DRM.Dumper
    m_DRMFile -> D:\MAB\bigfile\default\pcx64-w\hulk.drm
    m_UnpackFolder -> D:\MAB\Unpacked
    m_TigerFolder -> D:\MAB\Decrypted
```
## Post #36
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T18:33:51+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

@TrumpetPro - Yes, I noticed this, for some reason they are ignored "" for path's with a spaces.
## Post #37
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T19:15:24+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Well, this is a [bug in .NET](https://www.mobzystems.com/code/bugingetcommandlineargs/). Fixed and  i hope it should work now.

Do not set in m_UnpackFolder and m_TigerFolder arguments -> "\" in the end.

[DOWNLOAD](https://www47.zippyshare.com/v/uXSPfnCT/file.html)
## Post #38
- Username: Kiekii922
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 12, 2020 4:50 am
- Post datetime: 2020-08-25T19:16:54+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

What can we use to open mamesh, and mapcd?
## Post #39
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-25T19:20:40+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from bertonberton ↑Wed Aug 26, 2020 1:57 am at Wed Aug 26, 2020 1:57 am
>
> 
Thank you Ekey! Just trying unpack some DRM Files with MAB.DRM.Dumper  and got error that script can't find bigfile.000,tiger in decrypted directory 
Also script create folder with UnpackFolder name and drm file name which i choose. I've try unpack hulk.drm from bigfile.000.tiger
How to fix this?
Show me the arguments what you used?

> Reply from Kiekii922 ↑Wed Aug 26, 2020 3:16 am at Wed Aug 26, 2020 3:16 am
>
> 
What can we use to open mamesh, and mapcd?

At least wait for the masters to parse these formats
## Post #40
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-26T14:25:05+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

DRM.Dumper is updated - fixed an insidious bug that is rare 
Tiger.Unpacker - updated project base, сurrent state is:

```
bigfile.update1.000.000.tiger -> 38434 of 42361 => [90%]
```


All links in [this post](https://forum.xentax.com/viewtopic.php?p=166156#p166156)
## Post #41
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-26T14:38:13+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Wed Aug 26, 2020 10:25 pm at Wed Aug 26, 2020 10:25 pm
>
> 
DRM.Dumper is updated - fixed an insidious bug that is rare 
Tiger.Unpacker - updated project base, surrent state is:
Code: Select allbigfile.000.tiger -> 211526 of 253476 => [83%]
bigfile.update1.000.000.tiger -> 38434 of 42361 => [90%]

All links in this post

Thank you for update  I've seen your message about .mamesh and .mapcd formats. So you have no idea how to parse this fileformats? I've checked ROTR threads and seems this format different compared with previous ROTR dumped formats.
## Post #42
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-26T15:04:53+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Wed Aug 26, 2020 10:25 pm at Wed Aug 26, 2020 10:25 pm
>
> Thank you for update  I've seen your message about .mamesh and .mapcd formats. So you have no idea how to parse this fileformats? I've checked ROTR threads and seems this format different compared with previous ROTR dumped formats.
Unfortunately no. Plugins for the latest games for Noesis as far as I remember made by Gh0stblade, I think you better ask him. I don't have much experience with 3D models and textures
## Post #43
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-26T23:22:14+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Wed Aug 26, 2020 2:23 am at Wed Aug 26, 2020 2:23 am
>
> 
About DRM, there is complicated structure with two types. First type is 0 - this is index of chunked resources, second type is 2 - resource data.
I've been digging this for 3 days

Thank you !
Can you explain more about the DRM type as 0
## Post #44
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-29T18:05:22+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I've been working on this for a while now and i've found paths to specific icons i would like to grab out like.. 

```
textures/HUD/Vault_Terminal.tga
```

Without adding them (full path) to the filelist and doing a full file extraction every time i find something new, is there a way to find those specific files? either by extracting one or converting the filename into a hash so i can pull it from the unknown files?
if the latter, would you be able to share what the crc (if its crc) is, i was assuming CRC_64 but no luck so far.
Thanks.
## Post #45
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-08-29T18:16:10+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Could someone please help me? I am getting this error:

[INFO]: Project File Loaded: 26209

[TIGER INFO]: Archive: bigfile.000.tiger
[TIGER INFO]: Version: 8
[TIGER INFO]: Parts: 7
[TIGER INFO]: Total files: 253476
[TIGER INFO]: Priority: 1
[TIGER INFO]: Base path: pcx64-w
[TIGER INFO]: Languages: 17
[TIGER INFO]:  >  00000001 = english
[TIGER INFO]:  >  00000002 = french
[TIGER INFO]:  >  00000004 = german
[TIGER INFO]:  >  00000008 = italian
[TIGER INFO]:  >  00000010 = latamspanish
[TIGER INFO]:  >  00000020 = iberspanish
[TIGER INFO]:  >  00000040 = japanese
[TIGER INFO]:  >  00000080 = portuguese
[TIGER INFO]:  >  00000100 = polish
[TIGER INFO]:  >  00000200 = russian
[TIGER INFO]:  >  00000400 = dutch
[TIGER INFO]:  >  00000800 = korean
[TIGER INFO]:  >  00001000 = chinese
[TIGER INFO]:  >  00002000 = simplechinese
[TIGER INFO]:  >  00004000 = arabic
[TIGER INFO]:  >  00008000 = czech
[TIGER INFO]:  >  20000000 = ultra

[INFO]: default\pcx64-w\audio\streams\ui\av1\gear_stinger_element_a_20.mul

Unhandled Exception: System.IO.IOException: The filename, directory name, or volume label syntax is incorrect.

   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at MAB.Tiger.Unpacker.Program.iSaveToFile(String m_FileName, Byte[] pBuffer)
   at MAB.Tiger.Unpacker.Program.iUnpackTigerFile(String m_TigerFile, String m_DstFolder, Boolean bSkipExist)
   at MAB.Tiger.Unpacker.Program.Main(String[] args)
## Post #46
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-08-29T18:34:17+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Puterboy1 ↑Sun Aug 30, 2020 2:16 am at Sun Aug 30, 2020 2:16 am
>
> 
Could someone please help me? I am getting this error:

[INFO]: Project File Loaded: 26209

[TIGER INFO]: Archive: bigfile.000.tiger
[TIGER INFO]: Version: 8
[TIGER INFO]: Parts: 7
[TIGER INFO]: Total files: 253476
[TIGER INFO]: Priority: 1
[TIGER INFO]: Base path: pcx64-w
[TIGER INFO]: Languages: 17
[TIGER INFO]:  >  00000001 = english
[TIGER INFO]:  >  00000002 = french
[TIGER INFO]:  >  00000004 = german
[TIGER INFO]:  >  00000008 = italian
[TIGER INFO]:  >  00000010 = latamspanish
[TIGER INFO]:  >  00000020 = iberspanish
[TIGER INFO]:  >  00000040 = japanese
[TIGER INFO]:  >  00000080 = portuguese
[TIGER INFO]:  >  00000100 = polish
[TIGER INFO]:  >  00000200 = russian
[TIGER INFO]:  >  00000400 = dutch
[TIGER INFO]:  >  00000800 = korean
[TIGER INFO]:  >  00001000 = chinese
[TIGER INFO]:  >  00002000 = simplechinese
[TIGER INFO]:  >  00004000 = arabic
[TIGER INFO]:  >  00008000 = czech
[TIGER INFO]:  >  20000000 = ultra

[INFO]: default\pcx64-w\audio\streams\ui\av1\gear_stinger_element_a_20.mul

Unhandled Exception: System.IO.IOException: The filename, directory name, or volume label syntax is incorrect.

   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at MAB.Tiger.Unpacker.Program.iSaveToFile(String m_FileName, Byte[] pBuffer)
   at MAB.Tiger.Unpacker.Program.iUnpackTigerFile(String m_TigerFile, String m_DstFolder, Boolean bSkipExist)
   at MAB.Tiger.Unpacker.Program.Main(String[] args)

What are your command-line arguments?
## Post #47
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-08-29T18:43:13+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from TrumpetPro ↑Sun Aug 30, 2020 2:34 am at Sun Aug 30, 2020 2:34 am
>
> 
Puterboy1 wrote: ↑Sun Aug 30, 2020 2:16 am
Could someone please help me? I am getting this error:

[INFO]: Project File Loaded: 26209

[TIGER INFO]: Archive: bigfile.000.tiger
[TIGER INFO]: Version: 8
[TIGER INFO]: Parts: 7
[TIGER INFO]: Total files: 253476
[TIGER INFO]: Priority: 1
[TIGER INFO]: Base path: pcx64-w
[TIGER INFO]: Languages: 17
[TIGER INFO]:  >  00000001 = english
[TIGER INFO]:  >  00000002 = french
[TIGER INFO]:  >  00000004 = german
[TIGER INFO]:  >  00000008 = italian
[TIGER INFO]:  >  00000010 = latamspanish
[TIGER INFO]:  >  00000020 = iberspanish
[TIGER INFO]:  >  00000040 = japanese
[TIGER INFO]:  >  00000080 = portuguese
[TIGER INFO]:  >  00000100 = polish
[TIGER INFO]:  >  00000200 = russian
[TIGER INFO]:  >  00000400 = dutch
[TIGER INFO]:  >  00000800 = korean
[TIGER INFO]:  >  00001000 = chinese
[TIGER INFO]:  >  00002000 = simplechinese
[TIGER INFO]:  >  00004000 = arabic
[TIGER INFO]:  >  00008000 = czech
[TIGER INFO]:  >  20000000 = ultra

[INFO]: default\pcx64-w\audio\streams\ui\av1\gear_stinger_element_a_20.mul

Unhandled Exception: System.IO.IOException: The filename, directory name, or volume label syntax is incorrect.

   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share, Int32 bufferSize, FileOptions options, String msgPath, Boolean bFromProxy)
   at System.IO.FileStream..ctor(String path, FileMode mode)
   at MAB.Tiger.Unpacker.Program.iSaveToFile(String m_FileName, Byte[] pBuffer)
   at MAB.Tiger.Unpacker.Program.iUnpackTigerFile(String m_TigerFile, String m_DstFolder, Boolean bSkipExist)
   at MAB.Tiger.Unpacker.Program.Main(String[] args)


What are your command-line arguments?
Actually, I have extracted the tiger files, right now, I would like an archive with all of the sound files converted, playable and ready for download.
## Post #48
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-08-29T18:44:02+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

These are the line arguments I am using for the DRM unpacker.

C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\MAB.DRM.Dumper.exe "C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Unpacked\default\pcx64-w\audio\dialogue sheets\missions\m101_van_vanilla_fpas.drm" C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Unpacked\ C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Decrypted\bigfile.000.tiger
## Post #49
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-08-29T19:20:00+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Guys i've add RenderMesh archive with .mamesh files. You can download it here [https://dropmefiles.com/rz1lZ](https://dropmefiles.com/rz1lZ)
Maybe someone who still do not get files can recognize parser script to transform it to .mesh or any acceptable format.
## Post #50
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-08-29T21:30:13+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

And I am getting this error with the DRM files.

Unhandled Exception: System.IO.IOException: Cannot create "C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\bigfile.000.tiger" because a file or directory with the same name already exists.
   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.Directory.InternalCreateDirectory(String fullPath, String path, Object dirSecurityObj, Boolean checkHost)
   at System.IO.Directory.InternalCreateDirectoryHelper(String path, Boolean checkHost)
   at System.IO.Directory.CreateDirectory(String path)
   at MAB.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder)
   at MAB.DRM.Dumper.Program.Main(String[] args)
## Post #51
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-29T21:34:39+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from LazyCat2k3 ↑Thu Aug 27, 2020 7:22 am at Thu Aug 27, 2020 7:22 am
>
> 
Thank you !
Can you explain more about the DRM type as 0

Maybe later. You are make a explorer for this files? What for you need this info?   

> Reply from IcarusTwine ↑Sun Aug 30, 2020 2:05 am at Sun Aug 30, 2020 2:05 am
>
> 
I've been working on this for a while now and i've found paths to specific icons i would like to grab out like.. 
Code: Select alltextures/icons/Ms_Marvel/White_Ms_Marvel.tga
textures/HUD/Vault_Terminal.tga
Without adding them (full path) to the filelist and doing a full file extraction every time i find something new, is there a way to find those specific files? either by extracting one or converting the filename into a hash so i can pull it from the unknown files?
if the latter, would you be able to share what the crc (if its crc) is, i was assuming CRC_64 but no luck so far.
Thanks.

These files are part of the Scaleform GFX resources. As far as I remember, their type was always DTPData, so look for GFX files there.

> Reply from Puterboy1 ↑Sun Aug 30, 2020 2:44 am at Sun Aug 30, 2020 2:44 am
>
> 
These are the line arguments I am using for the DRM unpacker.

C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\MAB.DRM.Dumper.exe "C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Unpacked\default\pcx64-w\audio\dialogue sheets\missions\m101_van_vanilla_fpas.drm" C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Unpacked\ C:\Users\Owner\Downloads\Marvels.Avengers.Beta\Content\Decrypted\bigfile.000.tiger

First - do not use "\" at the end of the path of arguments 2 and 3, and second - the last argument you have is not correct, for some reason you specified a tiger file and not a folder with them. In your case, it should be like this:

```

```


Some info about textures:

```
{
    //Texture type         //Flags that can be

    UNKNOWN_0 = 49,        //bFlag1 = 3, bFlag2 = 8
    BC1_DXT1 = 68,         //bFlag1 = 3, bFlag2 = 0 or 8
    BC1_DXT1A = 69,        //bFlag1 = 3 or 7, bFlag2 = 0
    BC3_DXT5 = 74,         //bFlag1 = 3 or 7, bFlag2 = 0
    UNKNOWN_1 = 75,        //bFlag1 = 7, bFlag2 = 2
    BC4_ATI1 = 77,         //bFlag1 = 3 or 7, bFlag2 = 0
    BC5_ATI2 = 80,         //bFlag1 = 3 or 7, bFlag2 = 0 or 8
    B8G8R8A8_DX10 = 84,    //bFlag1 = 3, bFlag2 = 0
    UNKNOWN_2 = 87,        //bFlag1 = 3, bFlag2 = 0
    BC6 = 91,              //bFlag1 = 7, bFlag2 = 0 
    BC7 = 94,              //bFlag1 = 3, bFlag2 = 0 or 8
    UNKNOWN_3 = 95,        //bFlag1 = 7, bFlag2 = 0
}

```


Header

```
Byte bFlag1; // 3, 7
Byte bFlag2; // 0, 2, 8
Int32 dwType;
UInt32 dwTextureSize;
UInt32 dwCompressedSize;

```


UNKNOWN 0,1,2 and 3 are compressed types (at least from those that I came across). Probably bFlag2 is a compression type (can someone confirm this?)
## Post #52
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-08-29T22:13:48+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Now about the .mul files. I'd like to extract them.
## Post #53
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-29T23:07:25+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Well, extract them, what's the problem?

As i know, nobody made converters for previous games like Tomb Raider (2013), Rise of the Tomb Raider, Shadow of the Tomb Raider and that's why hardly anyone will do it aslo for this game 

Note: Mul are raw audio data with a FSB4 chunks.
## Post #54
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-29T23:13:30+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I dont know if anyone has put any work into the locale files or DTP files (the ones which link to resources) 
but this is what i have for locale right now. 

```
    int type;
    ubyte header[24];
};


enum <int> Language
{
    English = 8,
	French = 16,
	German = 24,
	Spanish = 32,
	Portuguese = 40,
	Czech = 48,
	Italian = 56,
	unknownlang07 = 64,
	unknownlang08 = 72,
	unknownlang09 = 80,
	unknownlang10 = 88,
	unknownlang11 = 96,
	unknownlang12 = 104,
	unknownlang13 = 112,
	unknownlang14 = 120,
	unknownlang15 = 128

};
struct languagePointer {
    Language data;
    int pointer ;
};
struct paddingpointer {
    int startfrompointer;
};

```
## Post #55
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-29T23:18:35+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> UNKNOWN 0,1,2 and 3 are compressed types (at least from those that I came across). Probably bFlag2 is a compression type (can someone confirm this?)
do you have a path or an example file i can look at without me digging for a decade ?
## Post #56
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-29T23:39:08+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from IcarusTwine ↑Sun Aug 30, 2020 7:18 am at Sun Aug 30, 2020 7:18 am
>
> 
do you have a path or an example file i can look at without me digging for a decade ?

You can unpack for example a hulk.drm. There are no specific names, sorry, but they are the largest in size - 20MB +
## Post #57
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-30T03:33:56+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Sun Aug 30, 2020 5:34 am at Sun Aug 30, 2020 5:34 am
>
> 
LazyCat2k3 wrote: ↑Thu Aug 27, 2020 7:22 am
Thank you !
Can you explain more about the DRM type as 0 


Maybe later. You are make a explorer for this files? What for you need this info?

I'm focusing on localization for this game.
I want to extract the locale type from all DRM and get offset, size, TigerID then repack them with same size as original.
## Post #58
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-30T10:37:22+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from LazyCat2k3 ↑Sun Aug 30, 2020 11:33 am at Sun Aug 30, 2020 11:33 am
>
> 
I'm focusing on localization for this game.
I want to extract the locale type from all DRM and get offset, size, TigerID then repack them with same size as original.

```
Int32 dwDRMType; // 0
UInt32 dwChunks;
UInt32 dwPadding; // ???

for (Int32 i = 0; i < dwChunks; i++)
{
    UInt32 dwChunkSize;
    UInt32 dwChunkZSize;
	
    //Decompress it if chunks index data is compressed
}

//============
// INDEX TABLE
//============

Int32 dwVersion; // 22
Int32 dwStringLength1;
Int32 dwStringLength2;
Int64 dwReserved;
Int32 dwResChunks;
Int32 dwUnknown; // can be 0xFFFFFFFF

//Read the first block -> dwResChunks * 32
var lpFirstBlock;

//Read strings (dwStringLength1 + dwStringLength2 != 0)
Int32 dwStringsDataSize = dwStringLength1 + dwStringLength2;

//Read the second block -> dwResChunks * 24
var lpSecondBlock;

for (Int32 i = 0; i < dwResChunks; i++)
{
    //FirstBlock
    Int32 dwResChunkSize; //Uncompressed
    Int32 dwResType;
    Int64 dwResBlockHash;
    Int32 dwResChunkID;
    Int32 dwResUniqueID;
    UInt32 dwUnknown1; // 0xFFFFFFFF
    Int32 dwUnknown2; // 0
	
    //SecondBlock
    Int32 dwUnknown3; //ChunkSize + ResType ???
    Int32 dwUnknown4; // 0,1,2,3,4,5
    UInt32 dwResChunkOffset;
    UInt16 sResChunkPriority;
    UInt16 sResChunkTigerID;
    UInt32 dwResChunkZSize; // Compressed
    UInt32 dwResChunkHash;
}
```
## Post #59
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-30T15:38:20+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Sun Aug 30, 2020 7:39 am at Sun Aug 30, 2020 7:39 am
>
> 
IcarusTwine wrote: ↑Sun Aug 30, 2020 7:18 am
do you have a path or an example file i can look at without me digging for a decade ?


You can unpack for example a hulk.drm. There are no specific names, sorry, but they are the largest in size - 20MB +

I dont have any compression issues on it. This specific file 21,846 kb in size works fine with bc5_unorm, i can only guess that bFlag2 could be something to do with mipmap levels as this cuts perfectly at 8 different sizes.
## Post #60
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-30T15:52:12+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Thank you again Ekey !

I created a simple tool to get UniqueID, Offset, ZSize, TigerID, Priority for locale files from all DRM.
PS: Tested it with 85.000 DRM files. It'll take a decade to get all information (type locale) from 250.000+ DRM files.  
[https://www89.zippyshare.com/v/rOpqJ8Tt/file.html](https://www89.zippyshare.com/v/rOpqJ8Tt/file.html)
## Post #61
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-30T16:23:35+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

@IcarusTwine - Have you checked the types 49, 75, 87 and 95, right?
@LazyCat2k3 - Here the situation is such that each DRM can refer to 1 and the same resource, that's why all resources have a unique ID
## Post #62
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-30T17:02:14+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Mon Aug 31, 2020 12:23 am at Mon Aug 31, 2020 12:23 am
>
> 
@IcarusTwine - Have you checked the types 49, 75, 87 and 95, right?
@LazyCat2k3 - Here the situation is such that each DRM can refer to 1 and the same resource, that's why all resources have a unique ID

i will do when i'm back at pc. 
For now though  i can confirm that 

```
textures/icons/Ms_Marvel/White_Ms_Marvel,textures/icons/Ms_Marvel/White_Ms_Marvel.tga
textures/icons/Artifacts/Animation_files/VishantiAppendix_lettering.tga
textures/icons/Stats/Stat_Emblems_Heroic,textures/icons/Stats/Stat_Emblems_Heroic.tga
etc....
```

do not exist in .dtp files, 
these files are requested from the 
Resource_182592.dtp (actual file name is symbollibraryB.gfx or swf but it has a gfx header) from global_menus.drm
any more thoughts where those textures might be?
Update to this: the /Texture folder seems to have the .tga files i was looking for. just so many to go through manually so i didnt properly check.

Update: I got  UNKNOWN_3 = 95 to work with BC7, i'll check more though for any compression.
this was the header
```
00 00 00 00 01 01 FF 00
```
## Post #63
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-30T20:05:14+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from IcarusTwine ↑Mon Aug 31, 2020 1:02 am at Mon Aug 31, 2020 1:02 am
>
> 
i will do when i'm back at pc. 
For now though  i can confirm that 
Code: Select alltextures/icons/Thor/White_Thor.tga
textures/icons/Ms_Marvel/White_Ms_Marvel,textures/icons/Ms_Marvel/White_Ms_Marvel.tga
textures/icons/Artifacts/Animation_files/VishantiAppendix_lettering.tga
textures/icons/Stats/Stat_Emblems_Heroic,textures/icons/Stats/Stat_Emblems_Heroic.tga
etc....
Okay, probably this icons you can found in next path, but first we need to find all the drm real names that should be in this folder, since not all have been found. We still have 15,800 unknown DRMs. Sadly but only 1 person helped me with the log.  

```
pcx64-w\Design\Image Resources\scaleform\SharedTextures\
```
## Post #64
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-30T21:07:42+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

The only way i can think of doing it would be pulling strings from the xml/gfx/swf files but that only works on a small percentage for it. i'd imagine if we could hook it in memory to whatever resources is requested then we could probably produce a better list for you.
## Post #65
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-30T21:15:03+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

i did attempt the strings method and this is what i got. no filetype though but it's probably safe to assume all .drm besides the sheets/ or audio/
[https://filebin.net/j9qrbfsohzqzbjor](https://filebin.net/j9qrbfsohzqzbjor)
## Post #66
- Username: LazyCat2k3
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Aug 26, 2020 1:03 am
- Post datetime: 2020-08-30T22:12:43+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Has anyone found the file local\localization\voices\movies\1100_cin_005_aftermath_DARWIN_ONLY.sch ?
I looked for the F7FEC2D1BA0CD5FE hash code but couldn't find it.
## Post #67
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-08-30T22:39:38+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from LazyCat2k3 ↑Mon Aug 31, 2020 6:12 am at Mon Aug 31, 2020 6:12 am
>
> 
Has anyone found the file local\localization\voices\movies\1100_cin_005_aftermath_DARWIN_ONLY.sch ?
I looked for the F7FEC2D1BA0CD5FE hash code but couldn't find it.

this file is already extracted for me at 
```
\Unpacked\default\local\localization\voices\movies
```
## Post #68
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-08-31T02:18:25+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Tiger.Unpacker - updated project base, сurrent state is:

```
bigfile.update1.000.000.tiger -> 39515 of 42361 => [93%]
```


All links in [this post](https://forum.xentax.com/viewtopic.php?p=166156#p166156)
## Post #69
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-01T21:22:40+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Tools might need to be updated for the release. theres now 

```
->
bigfile.010.tiger
```

also theres a new update file (bigfile.update2.000.000)
## Post #70
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-01T21:38:05+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I'm pure sure that there is encryption also in the release version (maybe only the key will changed). Wait for Gh0stBlade
The unpacker and dumper will not work correctly, since, as I see new archives has been added in release version, like:

```
bigfile.008.tiger
bigfile.009.tiger
bigfile.010.tiger
bigfile.update1.000.001.tiger
bigfile.update1.000.002.tiger
bigfile.update2.000.000.tiger
bigfile_ultra.005.tiger
bigfile_ultra.006.tiger
```


As I said, I didn’t pre-order the game, and i can’t help, sorry.
## Post #71
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2020-09-01T22:12:41+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Any idea what's up with BIN files in bin folder? They have encrypted filenames and content as well.
## Post #72
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-01T22:41:06+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Espio ↑Wed Sep 02, 2020 6:12 am at Wed Sep 02, 2020 6:12 am
>
> 
Any idea what's up with BIN files in bin folder? They have encrypted filenames and content as well.

the bin files are encrypted or at least compressed. the filenames are named using a Caesar Cipher + 13
## Post #73
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2020-09-02T00:09:14+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

An no way to decrypt-unpack them yet, right?
## Post #74
- Username: Ekey
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T14:56:03+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I don't have the game yet. Will likely get it when the standard version releases though and update the decryption tool.
## Post #75
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-02T15:51:14+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Wed Sep 02, 2020 10:56 pm at Wed Sep 02, 2020 10:56 pm
>
> 
I don't have the game yet. Will likely get it when the standard version releases though and update the decryption tool.

I have binaries and one of small tiger archive as example from release game version. 

We have a BETA keys like:

[BETA]
K1 -> 0x27 ....
K2 -> 0xA0 ....

[RELEASE]
K1 - untouched, absolutely identical to the key from BETA
K2 - the situation here is more interesting, i found 2 places where 2 different keys are initialized. I'll tried to replace K2 with the current two keys in turn, but the result is always the same, it's a partially decrypted. It looks something like this:



Maybe that somewhere there is a function that mixes these 2 keys to get the final one for correct decrypt? Or I don't understand something 

I can upload to the file sharing if you interested (PM).
## Post #76
- Username: bertonberton
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T18:39:21+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

if you can upload the smallest tiger file and exe ill take a look more quickly.
## Post #77
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-02T21:28:12+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Do you guys know anything about these DTP Files, i've figured that the header contains the amount of pointers per section and the first section usually points to strings in the file its self but thats about it so far.
## Post #78
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-02T22:47:55+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

I noticed that in this version of the engine there are no resource types like:

```
Empty
Script
Object
CollisionMesh
StreamGroupList
TriggerData
```


My opinion: they are reassigned now into DTPData like: DTPGfx, DTPScript, DTPTrigger and etc. We need to find the parameters responsible for the DTP resource type. It is best way to do this with files from the release version of the game, since the structure may be different as it was in BETA.
I can give you an example - Hitman 2016 (RPKG). There was one structure in the beta version, and when the game is released the structure was very different from what it was
## Post #79
- Username: bertonberton
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T22:55:03+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from IcarusTwine ↑Thu Sep 03, 2020 5:28 am at Thu Sep 03, 2020 5:28 am
>
> 
Do you guys know anything about these DTP Files, i've figured that the header contains the amount of pointers per section and the first section usually points to strings in the file its self but thats about it so far.

I know all about DTP files.
## Post #80
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-02T22:57:11+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 6:55 am at Thu Sep 03, 2020 6:55 am
>
> I know all about DTP files.
In current game?
## Post #81
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T23:02:21+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Thu Sep 03, 2020 6:57 am at Thu Sep 03, 2020 6:57 am
>
> 
Gh0stBlade wrote: ↑Thu Sep 03, 2020 6:55 amI know all about DTP files.
In current game?

It is all the same I believe. Nothing different with this Engine.
## Post #82
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-02T23:10:46+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 7:02 am at Thu Sep 03, 2020 7:02 am
>
> 
It is all the same I believe. Nothing different with this Engine.

The current version of DRM is -> 22, exactly the same version as in Shadow of the Tomb Raider, but with a bunch of changes, idk why they were made - this is a complete mystery to me
## Post #83
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T23:24:01+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Thu Sep 03, 2020 7:10 am at Thu Sep 03, 2020 7:10 am
>
> 
Gh0stBlade wrote: ↑Thu Sep 03, 2020 7:02 am
It is all the same I believe. Nothing different with this Engine.


The current version of DRM is -> 22, exactly the same version as in Shadow of the Tomb Raider, but with a bunch of changes, idk why they were made - this is a complete mystery to me

I see. My Engine almost supports Marvel's Avengers Beta. I had some issues decompressing the CDRMs but I also noticed substantial changes to the DRM format etc. How complex is it?
## Post #84
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-02T23:52:25+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 7:24 am at Thu Sep 03, 2020 7:24 am
>
> 
I see. My Engine almost supports Marvel's Avengers Beta. I had some issues decompressing the CDRMs but I also noticed substantial changes to the DRM format etc.
Interesting.. Is this a public project or?

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 7:24 am at Thu Sep 03, 2020 7:24 am
>
> 
How complex is it?
The only thing that confused me is that in the first block, the ResUniqueID can be repeated several times, example from hawk.drm



It turned out that this resource is simply split into chunks 

Also, I do not know what kind of UInt64 after the resource type (temporarily set as a hash).
## Post #85
- Username: bertonberton
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-02T23:59:34+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Thu Sep 03, 2020 7:52 am at Thu Sep 03, 2020 7:52 am
>
> 
Gh0stBlade wrote: ↑Thu Sep 03, 2020 7:24 am
I see. My Engine almost supports Marvel's Avengers Beta. I had some issues decompressing the CDRMs but I also noticed substantial changes to the DRM format etc.
Interesting.. Is this a public project or?
Gh0stBlade wrote: ↑Thu Sep 03, 2020 7:24 am
How complex is it?

The only thing that confused me is that in the first block, the ResUniqueID can be repeated several times, example from hawk.drm



It turned out that this resource is simply split into chunks 

Also, I do not know what kind of UInt64 after the resource type (temporarily set as a hash).

Custom Engine and Editor project is closed source and private at this point in time.

About that resource being split into chunks. It is indeed strange as I've never seen this done in a Crystal Dynamics game. Its unfortunate that the Engine has changed so much. It only means it will take tons of refactoring of my Engine and Editor code to get things working properly which I really don't have the time to do unfortunately. 

The UInt64 after resource type is something I may have documented but i will check this once i have downloadrd the game off steam.
## Post #86
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-03T00:07:39+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 7:59 am at Thu Sep 03, 2020 7:59 am
>
> 
Custom Engine and Editor project is closed source and private at this point in time.
Oh, cool  

> Reply from Gh0stBlade ↑Thu Sep 03, 2020 7:59 am at Thu Sep 03, 2020 7:59 am
>
> 
The UInt64 after resource type is something I may have documented but i will check this once i have downloadrd the game off steam.
Maybe it's a chunk hash or symbol hash
## Post #87
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-04T19:45:47+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Do beta tools (decryptor/ unpacker / dumper)  work for final version, or they change keys?
## Post #88
- Username: Kiekii922
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-04T19:57:02+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Hey everyone!

Decryption tool for the retail game files is now available below.
[TigerDecrypt_v1_3.zip](https://xentaxbackup.github.io/file/18696_TigerDecrypt_v1_3.zip)
## Post #89
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-04T21:33:12+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Sat Sep 05, 2020 3:57 am at Sat Sep 05, 2020 3:57 am
>
> 
Hey everyone!

Decryption tool for the retail game files is now available below.

Thank you for update Gh0stBlade! Also do you know or maybe planning dig unpacked .mamesh and .mapcd formats and maybe you can create script for Noesis or any other program to parse this file formats and transform to .mesh or .obj? Thank you again
## Post #90
- Username: bertonberton
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-04T21:50:58+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from bertonberton ↑Sat Sep 05, 2020 5:33 am at Sat Sep 05, 2020 5:33 am
>
> 
Gh0stBlade wrote: ↑Sat Sep 05, 2020 3:57 am
Hey everyone!

Decryption tool for the retail game files is now available below.


Thank you for update Gh0stBlade! Also do you know or maybe planning dig unpacked .mamesh and .mapcd formats and maybe you can create script for Noesis or any other program to parse this file formats and transform to .mesh or .obj? Thank you again
I dont really have enough interest in this game to write a model importer for Noesis.
## Post #91
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-04T21:56:22+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Gh0stBlade ↑Sat Sep 05, 2020 5:50 am at Sat Sep 05, 2020 5:50 am
>
> 
bertonberton wrote: ↑Sat Sep 05, 2020 5:33 am
Gh0stBlade wrote: ↑Sat Sep 05, 2020 3:57 am
Hey everyone!

Decryption tool for the retail game files is now available below.


Thank you for update Gh0stBlade! Also do you know or maybe planning dig unpacked .mamesh and .mapcd formats and maybe you can create script for Noesis or any other program to parse this file formats and transform to .mesh or .obj? Thank you again 

I dont really have enough interest in this game to write a model importer for Noesis.

Sad to hear that ;( Anyway thank you for reply!
## Post #92
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-04T22:08:09+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Tools updated for release version files.

Tiger Unpacker - 0.0.3.1637 - [DOWNLOAD](https://www15.zippyshare.com/v/fAT7lQGe/file.html)

ProjectList - Update #3 (06.09.2020) - [DOWNLOAD](https://www69.zippyshare.com/v/5bSyQIOg/file.html)

```
bigfile.update1.000.000.tiger -> 218603 of 229839 => [95%]
bigfile.update2.000.000.tiger -> 268 of 299 => [89%]
```


```
    MA.Tiger.Unpacker <m_TigerFile> <m_UnpackFolder>

    m_TigerFile - Source of Tiger file
    m_UnpackFolder - Destination directory

[Examples]
    MA.Tiger.Unpacker D:\MA\Decrypted\bigfile.000.tiger D:\Unpacked\bigfile

```


Note: m_TigerFile - Only following archives are allowed:

*   bigfile.000.tiger
*   bigfile.update1.000.000.tiger
*   bigfile.update2.000.000.tiger

DRM Dumper - 0.0.3.1622 - [DOWNLOAD](https://www94.zippyshare.com/v/LlvKjbqw/file.html)

```
    MA.DRM.Dumper <m_DRMFile> <m_UnpackFolder> <m_TigerFolder>

    m_DRMFile - Source of DRM file
    m_UnpackFolder - Destination directory
    m_TigerFolder - Folder with decrypted TIGER files
	
[Examples]
    MA.DRM.Dumper
    m_DRMFile -> D:\MA\bigfile\default\pcx64-w\hulk.drm
    m_UnpackFolder -> D:\Unpacked\DRM
    m_TigerFolder -> D:\MA\Decrypted
	
    MA.DRM.Dumper D:\Unpacked\bigfile\default\pcx64-w\hulk.drm D:\Unpacked\DRM D:\MA\Decrypted

```
## Post #93
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-04T22:11:08+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Sat Sep 05, 2020 6:08 am at Sat Sep 05, 2020 6:08 am
>
> 
Tools updated for release version files.

Tiger Unpacker - 0.0.3.1637
DOWNLOAD

ProjectFile has not been updated, current state from BETA and i don't think there i will be make any updates.
Code: Select allbigfile.000.tiger -> 271783 of 450046 => [60%]
bigfile.update1.000.000.tiger -> 170378 of 229839 => [74%]
bigfile.update2.000.000.tiger -> 164 of 299 => [54%]
Code: Select all[Usage]
    MA.Tiger.Unpacker <m_TigerFile> <m_UnpackFolder>

    m_TigerFile - Source of Tiger file
    m_UnpackFolder - Destination directory

[Examples]
    MA.Tiger.Unpacker D:\MA\Decrypted\bigfile.000.tiger D:\Unpacked\bigfile


Note: m_TigerFile - Only following archives are allowed:

*   bigfile.000.tiger
*   bigfile.update1.000.000.tiger
*   bigfile.update2.000.000.tiger

DRM Dumper - 0.0.3.1622
DOWNLOAD
Code: Select all[Usage]
    MAB.DRM.Dumper <m_DRMFile> <m_UnpackFolder> <m_TigerFolder>

    m_DRMFile - Source of DRM file
    m_UnpackFolder - Destination directory
    m_TigerFolder - Folder with decrypted TIGER files
	
[Examples]
    MAB.DRM.Dumper
    m_DRMFile -> D:\MA\bigfile\default\pcx64-w\hulk.drm
    m_UnpackFolder -> D:\Unpacked\DRM
    m_TigerFolder -> D:\MA\Decrypted
	
    MAB.DRM.Dumper D:\Unpacked\bigfile\default\pcx64-w\hulk.drm D:\Unpacked\DRM D:\MA\Decrypted

what process did you use to produce the paths? i dont mind carrying it on as i'll be actively using it.
## Post #94
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-04T22:23:07+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from IcarusTwine ↑Sat Sep 05, 2020 6:11 am at Sat Sep 05, 2020 6:11 am
>
> 
what process did you use to produce the paths? i dont mind carrying it on as i'll be actively using it.

If you remember for the BETA version, I made a [modification](https://forum.xentax.com/viewtopic.php?p=166055#p166055) that allowed writing file names to the log, but this did not interest anyone and I while BETA it was is playable got more names my self.
## Post #95
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-04T22:51:49+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Sat Sep 05, 2020 6:23 am at Sat Sep 05, 2020 6:23 am
>
> 
If you remember for the BETA version, I made a modification that allowed writing file names to the log, but this did not interest anyone and I while BETA it was is playable got more names my self.

i dont mind running it if you could modify the exe the same way for release, or tell me what needs to be done so i can do it each patch. 
also i know it's a big ask but is there anyway i could selectively extract DRMs out or use the path to determine what unknown hash it is for new finds? 
saves me having to unpack over and over.
## Post #96
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-04T23:04:10+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from IcarusTwine ↑Sat Sep 05, 2020 6:51 am at Sat Sep 05, 2020 6:51 am
>
> 
i dont mind running it if you could modify the exe the same way for release,
I can't make the same mod for release because i don't have game and i don't want to waste money for this s***t, sorry. 

> Reply from IcarusTwine ↑Sat Sep 05, 2020 6:51 am at Sat Sep 05, 2020 6:51 am
>
> 
tell me what needs to be done so i can do it each patch. also i know it's a big ask but is there anyway i could selectively extract DRMs out or use the path to determine what unknown hash it is for new finds? saves me having to unpack over and over.
The unpacker does not overwrite files that are already unpacked. After update Project file you can remove all "__Unknown" folders and the unpacker will extract only unknown files and files that have been added to the list.
## Post #97
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-04T23:20:34+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Oh ? so it skips them, great. 
also new errors occurred 

```
   at MAB.DRM.Dumper.Program.iGetPackageNameFromID(UInt16 sTigerID, UInt16 sPriority)
   at MAB.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   at MAB.DRM.Dumper.Program.Main(String[] args)
```


also 

```
[WARNING]: Archive UNKNOWN (127-10) not found in 
```
## Post #98
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-04T23:42:47+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Are you sure you are using an updated version of DRMDumper from [this post](https://forum.xentax.com/viewtopic.php?p=166524#p166524)? I guess not
## Post #99
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-04T23:48:56+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from Ekey ↑Sat Sep 05, 2020 7:42 am at Sat Sep 05, 2020 7:42 am
>
> 
Are you sure you are using an updated version of DRMDumper from this post?

i am yes, zip version says "v0.0.3.1637" but internally when running it says v0.0.3.30949
## Post #100
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-04T23:50:28+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

my bad ! didnt know you changed it from MAB to MA
## Post #101
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-04T23:54:24+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Yup, I renamed them and also added missing archive IDs that are not in the tools version for BETA.
## Post #102
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-05T15:29:16+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Thank you for your tools!

How I can extract ultra graphics tiger( bigfile_ultra.[000...006].tiger)?
## Post #103
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-05T18:03:19+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

> Reply from erik945 ↑Sat Sep 05, 2020 11:29 pm at Sat Sep 05, 2020 11:29 pm
>
> 
Thank you for your tools!

How I can extract ultra graphics tiger( bigfile_ultra.[000...006].tiger)?

Files from these archives are can be extracted with DRMDumper.
## Post #104
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-07T19:25:05+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

Is there an easy way to explain how i can modify the exe to output to the log? i'm manually opening dtp files here and finding paths, bit slow
## Post #105
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-07T21:57:44+00:00
- Post Title: Re: Marvel's Avengers Open BETA [Steam] 2020

This game use very strange encoding of faces array for some parts (armor - normal, head -         )



In archive example of file and test maxscript for it.

[https://www.dropbox.com/s/etwxr9stfov371u/test.7z?dl=0](https://www.dropbox.com/s/etwxr9stfov371u/test.7z?dl=0)

If anyone understands how it works, let me know.
## Post #106
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-07T23:31:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from IcarusTwine ↑Tue Sep 08, 2020 3:25 am at Tue Sep 08, 2020 3:25 am
>
> 
Is there an easy way to explain how i can modify the exe to output to the log?
To do this, you need to have a reverse engineering skills.

> Reply from IcarusTwine ↑Tue Sep 08, 2020 3:25 am at Tue Sep 08, 2020 3:25 am
>
> 
i'm manually opening dtp files here and finding paths, bit slow
Yup, that's about what I was doing for update the filelist. Current state for clean release game files (without any patches):

```
bigfile.update1.000.000.tiger -> 218603 of 229839 => [95%]
bigfile.update2.000.000.tiger -> 268 of 299 => [89%]
```


~15000 in total still is unknown and ~5000 is unique names.

ProjectList - Update #3 (06.09.2020) - [DOWNLOAD](https://www69.zippyshare.com/v/5bSyQIOg/file.html)

> Reply from erik945 ↑Tue Sep 08, 2020 5:57 am at Tue Sep 08, 2020 5:57 am
>
> 
This game use very strange encoding of faces array for some parts (armor - normal, head -         )

Probably it's a template of head for body and model of hair + head in other DRM's? Like:

```
pcx64-w\charactermesh__av1_puppet_ambient_female_base__aim_scientist__head__head_01_acc_02__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__aim_scientist__head__head_01_acc_03__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__aim_scientist__head__head_01_acc_04__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__aim_scientist__head__head_01_acc_05__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head01__head_01_global_hat_07__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head01__head_01_global_hat_08__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head01__head_01_global_hat_09__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head02__head_02_global_hair_01__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head02__head_02_global_hair_02__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head02__head_02_global_hair_03__default.drm
pcx64-w\charactermesh__av1_puppet_ambient_female_base__resistance__head02__head_02_global_hair_04__default.drm

```


Good progress anyway, keep going!
## Post #107
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-08T04:35:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does not look like...
First, I don't see separate files for the heads of the main characters. I see hair, but no heads.
Secondly, the rest of the parts - eyes, teeth, etc. there is and work fine.
## Post #108
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-08T06:02:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Tue Sep 08, 2020 5:57 am at Tue Sep 08, 2020 5:57 am
>
> 
This game use very strange encoding of faces array for some parts (armor - normal, head -         )



In archive example of file and test maxscript for it.

https://www.dropbox.com/s/etwxr9stfov371u/test.7z?dl=0

If anyone understands how it works, let me know.

Thank you for script but i have this error when try to Run it. 

"MAXScript FileIn Exception
 Unable to convert: undefined to type: Float"

I have 3dsMax  2018. It's problem from my side?

UPD1: When i modify file path to mine then got this error

"MAXScript FileIn Exception
No ""+"" function for undefined"
## Post #109
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-08T06:19:04+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the script is a very very early test.
Works only with the attached file, the path to it is written manually in the body of the script.

Right now I'm just looking for arrays of vertices, polygons, basic structures.
## Post #110
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-08T21:42:48+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

hi how to extract,

all models.
I cannot extract the files

bigfile

the files are already decrypted with the file decrypt.bat

this is the complete game
[Decrypted.jpg](https://xentaxbackup.github.io/file/18716_Decrypted.jpg)
## Post #111
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-09T15:57:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Can anyone help I can't even extract
all files for the models of this game
## Post #112
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2020-09-09T21:51:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ransack ↑Wed Sep 09, 2020 11:57 pm at Wed Sep 09, 2020 11:57 pm
>
> ...
If no one answers you it's because the answers to your questions can be found in the previous comments...
## Post #113
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-09T23:29:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Just people do not read the post with examples of using the tools in the fact! This is so hard? Or what?

1) I don't even know why you have the "FileNames.list" project file located outside the "Projects" folder?
2) There are examples of use in [my post](https://forum.xentax.com/viewtopic.php?p=166524#p166524). Did you read them?

For all:
Why are there so many leehers here? If you are plannig to use the tools, why you can't even thank the author for at least the fact that he spent his time? I just see that decryptor was downloaded 30 times, and thanked 6 times, also 1 for my post with tools . It's so hard to push the "Thanks" button, seriously? 

If it weren't for Gh0st, I wouldn't even try to make any tools!
## Post #114
- Username: Defalt
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 10, 2020 7:48 am
- Post datetime: 2020-09-10T00:17:43+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I am new to the forum, but on behalf of everyone I want to thank @Ekey as well as @Gh0stBlade for the amazing work they have done for the community, and just remember they don't owe anything to any of us, it is because of people like them that this community stays so alive.
## Post #115
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-10T05:46:52+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ekey ↑Thu Sep 10, 2020 7:29 am at Thu Sep 10, 2020 7:29 am
>
> 
Just people do not read the post with examples of using the tools in the fact! This is so hard? Or what?

1) I don't even know why you have the "FileNames.list" project file located outside the "Projects" folder?
2) There are examples of use in my post. Did you read them?

For all:
Why are there so many leehers here? If you are plannig to use the tools, why you can't even thank the author for at least the fact that he spent his time? I just see that decryptor was downloaded 30 times, and thanked 6 times, also 1 for my post with tools . It's so hard to push the "Thanks" button, seriously? 

If it weren't for Gh0st, I wouldn't even try to make any tools!

Ekey thank you so much for your time and knowledge which you put in this tools and game! Idk why people don't mind press "thanks" button but if i had opportunity create 1000 accounts i'll say "Thank you" 1000 times. Also big thanks to Gh0stBlade who one of the first people start diggin in this game by my request. You guys awesome and don't pay attention about other members and forgive them. Many of them newbee and don't know how "thanks" button work and important for creator  Thank you again Ekey and Gh0stBlade  Live long!
## Post #116
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T11:38:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Noesis script for meshes and textures (beta version)



Works:
- geometry
- multiple UV channels
- skeletons/skin (test)
- textures
- multiple textures in single file (usually standart and HD)
- split LODs (use pugin versian 29, version 25 outdated, left just as archive. )

Does not work:
- some textures

update 16.09.2020
add:
- skeletons/skin (test)
- script for skeleton searching
- multiple textures in single file

update 19.09.2020
add:
- split LODs (use pugin version 29, version 25 outdated, left just as archive. )

update 01.10.2020
improved texture support

update 14.10.2020
add:
support LOD's number for submesh.
Now script load ONLY LOD1 (with max detalization).
You can load all LODs - edit script for it 
string 30

```
LoadOnlyLod1 = True
```

set to

```
LoadOnlyLod1 = False
```

hotfix14.10.2020#1
Some models has lod0, added its extraction to parametr LoadOnlyLod1 


Extracting characters with skeleton:
place skeleton file to folder with model,
skeleton name must be strictly "skeleton.maskl".
Skeleton be found in DTPData folder. It's just a renamed *.dtp file

You can use skeleton_finder.py tool for search "skeleton"'s file.
Just edit "search_dir = "D:\\marvel\\drm_unp"" to your path - script check dpd files, copy and renamed its to "skeleton_XXX.maskl" in same folder.
The script may not find all the files, or it may mistakenly recognize some of them. It doesn't fully parse the file structure - it just looks for similar ones.

For some models, skeletons need to be looked for in other "DRM" folders.
You can use noesis to view skeletons structure.

Thanks:  
Dazzy  -   for researching the skeleton structure
Based on Gh0stBlade's script for Tomb Raider
[fmt_MarvelsAvengers2020_31.7z](https://xentaxbackup.github.io/file/18824_fmt_MarvelsAvengers2020_31.7z)
## Post #117
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-10T12:09:59+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 7:38 pm at Thu Sep 10, 2020 7:38 pm
>
> 
Noesis script for meshes and textures (beta version)



Works:
-   geometry
-   multiple UV channels
-   textures

Does not work:
-   skeletons
-   skin

Based on Gh0stBlade's script for Tomb Raider

Insane! Working in my case  Thank you so much! Waiting for updates  Pog
## Post #118
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T12:53:32+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

sorry for not thanking anyone You did a great job can someone explain to me how to extract files with the tool
## Post #119
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-10T12:56:52+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ransack ↑Thu Sep 10, 2020 8:53 pm at Thu Sep 10, 2020 8:53 pm
>
> 
sorry for not thanking anyone You did a great job can someone explain to me how to extract files with the tool

I can suggest check all posts from start of thread because Ekey give ultra detailed guide how to extract files from .tiger
## Post #120
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T12:59:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from bertonberton ↑Thu Sep 10, 2020 8:56 pm at Thu Sep 10, 2020 8:56 pm
>
> 
Ransack wrote: ↑Thu Sep 10, 2020 8:53 pm
sorry for not thanking anyone You did a great job can someone explain to me how to extract files with the tool


I can suggest check all posts from start of thread because Ekey give ultra detailed guide how to extract files from .tiger

I did it but it doesn't extract the files

he told me every time  [Examples]
    MA.Tiger.Unpacker D: \ MA \ bigfile.000.tiger D: \ Unpacked \ bigfile
Press any key to continue ... 

Even though I'm the example

it's the same thing

I may be stupid but it would be good to explain
## Post #121
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T13:05:49+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Tiger decrypted?
## Post #122
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T13:23:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

yes already deciphered with TigerDecrypt_v1_3
## Post #123
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-10T13:28:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 7:38 pm at Thu Sep 10, 2020 7:38 pm
>
> 
Noesis script for meshes and textures (beta version)



Works:
-   geometry
-   multiple UV channels
-   textures

Does not work:
-   skeletons
-   skin

Based on Gh0stBlade's script for Tomb Raider

Also i have checked charactermesh files and some of meshes missing. For example from bigfile.000 i get default Captain America Mesh and default Thor. Other characters have more outfits but not all. This means we need provide Ekey log file from his modified .exe file to add missing folders with rest of outfits? Do you have the same list or rest of character mesh in another bigfile?
## Post #124
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T13:40:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ransack  
Just drag and drop to cmd window tool, tiger and folder to unpack.
Example:
D:\marvel\MA.Tiger.Unpacker_0.0.3.1637\MA.Tiger.Unpacker.exe D:\marvel\5665\bigfile.update1.000.000.tiger D:\marvel\6

bertonberton  I download tools from this thread. Try just search by drm files (*thor*) .
Many parts start with "charactermesh_" and "dbi_".
## Post #125
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T13:48:42+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ok because I have all the bigfile.tiger Decrypt file in the file

I just have to drag my Decrypted file into the tool
## Post #126
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T13:50:06+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

No, you need set destenation folder as thrid parametr.
See example in previous post.
## Post #127
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-10T13:52:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 9:40 pm at Thu Sep 10, 2020 9:40 pm
>
> 
Ransack  
Just drag and drop to cmd window tool, tiger and folder to unpack.
Example:
D:\marvel\MA.Tiger.Unpacker_0.0.3.1637\MA.Tiger.Unpacker.exe D:\marvel\5665\bigfile.update1.000.000.tiger D:\marvel\6

bertonberton  I download tools from this thread. Try just search by drm files (*thor*) .
Many parts start with "charactermesh_" and "dbi_".

Yeah i got this but some outfits missing i guess. Do you have more than  1 charactermesh file for Thor and Captain?I have only 1 body suit mesh and hair parts. Just want to know if i need unpack more bigfile. tiger
## Post #128
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T13:54:03+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 9:50 pm at Thu Sep 10, 2020 9:50 pm
>
> 
No, you need set destenation folder as thrid parametr.
See example in previous post.

I'll try to see Thanks
I don't know if I can extract the files
## Post #129
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T13:57:58+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I haven't unpacked all DRM - just no disk space.

Ransack 
look at the image
## Post #130
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-10T15:30:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

If you want extract more files with known names then just update the project file from [this post](https://forum.xentax.com/viewtopic.php?p=166605#p166605). At the moment about ~5000 unique names still is unknown.

Note: Before re-unpacking you will need to delete the "__Unknown" folders. The unpacker will skip files that are already on the disk and simply unpack only those that are missing (saving time ). Also, I do not recommend specifying long paths for the destination folder, as some file names are quite long and if the full path is longer than MAX_PATH (260 characters), there may be problems with saving files to disk. 

Just set a short paths, like:

```
D:\Unpacked\bigfile
```


About the "Thanks" button.
I said this because this situation is not only in this topic. This is also common in other topics with a contributing by other authors.. 

@Ransack - Show me args (you must edit a bat file) how you use the tool? Also - did you fix problem with project file? Otherwise, the file names will be as a simple hash.
## Post #131
- Username: TRDaz
- Rank: mega-veteran
- Number of posts: 215
- Joined date: Sun Sep 25, 2011 2:06 am
- Post datetime: 2020-09-10T18:05:42+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks for the big file tools! Also nice job on the Noesis script so far, though there is an issue with meshes, LODs are merging together with the main meshes when they should be all separate.
## Post #132
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T18:29:58+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

please Can you help me? I cannot extract all the files,

I followed what was marked
[Image.jpg](https://xentaxbackup.github.io/file/18722_Image.jpg)
## Post #133
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T19:05:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

You forgot set destenation folder for result. Look my screen.

And use simply exe, not bat
## Post #134
- Username: Ransack
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Sep 09, 2020 2:02 am
- Post datetime: 2020-09-10T19:38:19+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thank you very much this works all models are in which file  

I do not find
Where models are stored
## Post #135
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-10T20:12:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Next you need use DRM Dumper. 
DRM is something like a link to data in Tiger.

Carefully - one drm can give several gigabytes of unpacked files.
Pick one or two files and try dump them.
## Post #136
- Username: FGeeHD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 20, 2020 9:31 pm
- Post datetime: 2020-09-12T02:21:48+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Any clue about this one? Using the DRM dumper. I only have the DRM files from the beta if that's an issue.   

```

Unhandled Exception: System.Exception: [ERROR]: Invalid magic of DRM file!
   at MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   at MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   at MA.DRM.Dumper.Program.Main(String[] args)
Press any key to continue . . .
```
## Post #137
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-12T14:57:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Help me with this problem please.....


C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\MA.Tiger.Unpacker.exe C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\bigfile.000.tiger C:\Users\Owner\Downloads\Marvels.Avengers\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!
## Post #138
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-09-12T16:40:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Puterboy1 ↑Sat Sep 12, 2020 10:57 pm at Sat Sep 12, 2020 10:57 pm
>
> 
Help me with this problem please.....


C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\MA.Tiger.Unpacker.exe C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\bigfile.000.tiger C:\Users\Owner\Downloads\Marvels.Avengers\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!

What exactly did you type into CMD/PowerShell? 99% of the time the issue is with the launch arguments but nobody seems to post them.
## Post #139
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-12T16:42:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from TrumpetPro ↑Sun Sep 13, 2020 12:40 am at Sun Sep 13, 2020 12:40 am
>
> 
Puterboy1 wrote: ↑Sat Sep 12, 2020 10:57 pm
Help me with this problem please.....


C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\MA.Tiger.Unpacker.exe C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\bigfile.000.tiger C:\Users\Owner\Downloads\Marvels.Avengers\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!


What exactly did you type into CMD/PowerShell? 99% of the time the issue is with the launch arguments but nobody seems to post them.
This is what I typed: 
C:\Users\Owner>C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\MA.Tiger.Unpacker.exe C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted\bigfile.000.tiger C:\Users\Owner\Downloads\Marvels.Avengers\Decrypted

I followed the instructions on how to extract them carefully.
## Post #140
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-12T18:07:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

So can you please help me?
## Post #141
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-09-12T18:14:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Puterboy1 ↑Sun Sep 13, 2020 2:07 am at Sun Sep 13, 2020 2:07 am
>
> 
So can you please help me?

Are you using files from release or the beta?
## Post #142
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-12T19:38:19+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from TrumpetPro ↑Sun Sep 13, 2020 2:14 am at Sun Sep 13, 2020 2:14 am
>
> 
Puterboy1 wrote: ↑Sun Sep 13, 2020 2:07 am
So can you please help me?


Are you using files from release or the beta?

Release.
## Post #143
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-09-12T23:29:20+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Puterboy1 ↑Sun Sep 13, 2020 3:38 am at Sun Sep 13, 2020 3:38 am
>
> 
TrumpetPro wrote: ↑Sun Sep 13, 2020 2:14 am
Puterboy1 wrote: ↑Sun Sep 13, 2020 2:07 am
So can you please help me?


Are you using files from release or the beta?


Release.

Try this:

1. Open CMD
2. Type (or copy/paste) then press enter: cd "Downloads\Marvels.Avengers\Decrypted"
3. Type (or copy/paste) then press enter: MA.Tiger.Unpacker bigfile.000.tiger ..\Unpacked
## Post #144
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-12T23:45:45+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from TrumpetPro ↑Sun Sep 13, 2020 7:29 am at Sun Sep 13, 2020 7:29 am
>
> 
Puterboy1 wrote: ↑Sun Sep 13, 2020 3:38 am
TrumpetPro wrote: ↑Sun Sep 13, 2020 2:14 am


Are you using files from release or the beta?


Release.


Try this:

1. Open CMD
2. Type (or copy/paste) then press enter: cd "Downloads\Marvels.Avengers\Decrypted"
3. Type (or copy/paste) then press enter: MA.Tiger.Unpacker bigfile.000.tiger ..\Unpacked

This is what I got:

C:\Users\Owner>cd C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted

C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted> MA.Tiger.Unpacker.exe bigfile.000.tiger ..\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!
## Post #145
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2020-09-13T00:00:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Puterboy1 ↑Sun Sep 13, 2020 7:45 am at Sun Sep 13, 2020 7:45 am
>
> 
TrumpetPro wrote: ↑Sun Sep 13, 2020 7:29 am
Puterboy1 wrote: ↑Sun Sep 13, 2020 3:38 am


Release.


Try this:

1. Open CMD
2. Type (or copy/paste) then press enter: cd "Downloads\Marvels.Avengers\Decrypted"
3. Type (or copy/paste) then press enter: MA.Tiger.Unpacker bigfile.000.tiger ..\Unpacked


This is what I got:

C:\Users\Owner>cd C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted

C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted> MA.Tiger.Unpacker.exe bigfile.000.tiger ..\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!

Have you already run TigerDecrypt.exe or one of the associated .bat files (e.g. Decrypt_Bigfile.bat)?
## Post #146
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-13T01:05:39+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from TrumpetPro ↑Sun Sep 13, 2020 8:00 am at Sun Sep 13, 2020 8:00 am
>
> 
Puterboy1 wrote: ↑Sun Sep 13, 2020 7:45 am
TrumpetPro wrote: ↑Sun Sep 13, 2020 7:29 am


Try this:

1. Open CMD
2. Type (or copy/paste) then press enter: cd "Downloads\Marvels.Avengers\Decrypted"
3. Type (or copy/paste) then press enter: MA.Tiger.Unpacker bigfile.000.tiger ..\Unpacked


This is what I got:

C:\Users\Owner>cd C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted

C:\Users\Owner\Downloads\Marvels_Avengers\Decrypted> MA.Tiger.Unpacker.exe bigfile.000.tiger ..\Unpacked
Marvel's Avengers TIGER UnPacker
(c) 2020 Ekey (h4x0r) / v0.0.3.1637

[INFO]: Project File Loaded: 251035

[ERROR]: Invalid TIGER file!


Have you already run TigerDecrypt.exe or one of the associated .bat files (e.g. Decrypt_Bigfile.bat)?

Yes, I’ve already decrypted them.
## Post #147
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-09-13T07:47:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ekey write:Just set a short paths, like:
D:\bigfile
D:\Unpacked\bigfile 

use short path to folder
Example D:\big - your decrypted .tiger
D:\extract - where tool extract .tiger
D:\MA.Tiger.Unpacker_0.0.3.1637\MA.Tiger.Unpacker.exe

Win + r  and write cmd
Drag and drop MA.Tiger.Unpacker.exe on cmd, space button, drag an drop your .tiger file, space button, drag an drop you extract folder, hit enter
tool start extract .tiger to D:\extract
## Post #148
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-13T10:34:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

@Puterboy1 - I am pure sure that you have used a not the latest version of decryptor from [this post](https://forum.xentax.com/viewtopic.php?p=166510#p166510).
## Post #149
- Username: Puterboy1
- Rank: mega-veteran
- Number of posts: 204
- Joined date: Fri Mar 02, 2018 10:05 am
- Post datetime: 2020-09-13T13:41:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

But I have been using the latest decryptor. The one from Sep 4?
## Post #150
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-13T15:42:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Some posts have been removed. You want the files you buy the game. Do not resort to other means.
## Post #151
- Username: FGeeHD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 20, 2020 9:31 pm
- Post datetime: 2020-09-13T18:28:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Sorry to ask twice but any idea what's wrong with my issue above?^
## Post #152
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-13T21:01:18+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from FGeeHD ↑Mon Sep 14, 2020 2:28 am at Mon Sep 14, 2020 2:28 am
>
> 
Sorry to ask twice but any idea what's wrong with my issue above?^

I think you have not decrypted all files as required of my tools or you are using old version of decryptor.

1) You need a latest version of decryptor v1.3 from [this post](https://forum.xentax.com/viewtopic.php?p=166510#p166510).
2) You must decrypt absolutely ALL TIGER files > do it by the batch script below

```
TigerDecrypt bigfile.001.tiger 1
TigerDecrypt bigfile.002.tiger 2
TigerDecrypt bigfile.003.tiger 3
TigerDecrypt bigfile.004.tiger 4
TigerDecrypt bigfile.005.tiger 5
TigerDecrypt bigfile.006.tiger 6
TigerDecrypt bigfile.007.tiger 7
TigerDecrypt bigfile.008.tiger 8
TigerDecrypt bigfile.009.tiger 9
TigerDecrypt bigfile.010.tiger 10
TigerDecrypt bigfile.update1.000.000.tiger 0
TigerDecrypt bigfile.update1.000.001.tiger 1
TigerDecrypt bigfile.update1.000.002.tiger 2
TigerDecrypt bigfile.update2.000.000.tiger 0
TigerDecrypt bigfile.update1.000_ultra.000.tiger 0
TigerDecrypt bigfile_english.000.tiger 0
TigerDecrypt bigfile.update1.000_english.000.tiger 0
TigerDecrypt bigfile_ultra.000.tiger 0
TigerDecrypt bigfile_ultra.001.tiger 1
TigerDecrypt bigfile_ultra.002.tiger 2
TigerDecrypt bigfile_ultra.003.tiger 3
TigerDecrypt bigfile_ultra.004.tiger 4
TigerDecrypt bigfile_ultra.005.tiger 5
TigerDecrypt bigfile_ultra.006.tiger 6
```


3) Profit.
## Post #153
- Username: FGeeHD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Aug 20, 2020 9:31 pm
- Post datetime: 2020-09-13T21:18:32+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Is this no longer possible with just the beta files then?
## Post #154
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-14T16:18:20+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from FGeeHD ↑Mon Sep 14, 2020 5:18 am at Mon Sep 14, 2020 5:18 am
>
> 
Is this no longer possible with just the beta files then?
For beta files you shoud be use decryptor from [this post](https://forum.xentax.com/viewtopic.php?p=166049#p166049).
## Post #155
- Username: maryrangel
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 27, 2019 2:25 am
- Post datetime: 2020-09-14T16:54:06+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

You guys are always so helpful to the community and ahead of expectations! Thank you for everything you shared 

Two quick questions:
1) is modding with hex editing possible to swap characters meshes?
2) are there any plans for an injector for the files extracted?
## Post #156
- Username: maryrangel
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2020-09-14T17:37:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from maryrangel ↑Tue Sep 15, 2020 12:54 am at Tue Sep 15, 2020 12:54 am
>
> 
You guys are always so helpful to the community and ahead of expectations! Thank you for everything you shared 

Two quick questions:
1) is modding with hex editing possible to swap characters meshes?
2) are there any plans for an injector for the files extracted?

1. No.
2. Not from me.

You would need a file injector and an encrypter which im not working on either.
## Post #157
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-15T10:42:17+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Anyone find Captain America Stark outfit in charactermesh files? Same question for Black Widow, Kamala and Thor?
## Post #158
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-16T21:09:18+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the tool has been updated
[viewtopic.php?f=16&t=22556&p=166709#p166709](https://forum.xentax.com/viewtopic.php?f=16&t=22556&p=166709#p166709)
## Post #159
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-17T07:28:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 17, 2020 5:09 am at Thu Sep 17, 2020 5:09 am
>
> 
the tool has been updated
viewtopic.php?f=16&t=22556&p=166709#p166709

Thank you for update  Do you have any luck find charactermesh for Captain America/Thor/Widow/Kamala Stark outfit mesh? I guess we can't find them because guy who used Ekey modified .exe with attached log do not reach this mission and Engine do not load this names in log file ;( 
Ekey can you confirm that please?
## Post #160
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-17T08:45:29+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

charactermesh__XXX, charactermesh__dbi_XXX, e.t.c
As example:
 charactermesh__black_widow__infiltrator__body__body__03liberator charactermesh__captain_america__ultimate__body__body__version_04 charactermesh__dbi_widow_incognito_skirt__default__body__body__version_04

skeletons often  in dbi_XXX 
As example:
dbi_widow_incognito_skirt

just search by name.
I was not looking for specifically "Stark" outfit.

update: - it's found by *starktech* mask - charactermesh__thor__starktech__body__body__default, charactermesh__black_widow__starktech__body__body__default e.t.c
## Post #161
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-17T10:34:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from bertonberton ↑Thu Sep 17, 2020 3:28 pm at Thu Sep 17, 2020 3:28 pm
>
> 
Thank you for update  Do you have any luck find charactermesh for Captain America/Thor/Widow/Kamala Stark outfit mesh? I guess we can't find them because guy who used Ekey modified .exe with attached log do not reach this mission and Engine do not load this names in log file ;( 
Ekey can you confirm that please?

I don't know, sorry. I said that I don't have a game, but as for the beta, the files logged perfectly. On the 2nd update of the list, 99% of all files were found
## Post #162
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-17T12:26:06+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 17, 2020 4:45 pm at Thu Sep 17, 2020 4:45 pm
>
> 
charactermesh__XXX, charactermesh__dbi_XXX, e.t.c
As example:
 charactermesh__black_widow__infiltrator__body__body__03liberator charactermesh__captain_america__ultimate__body__body__version_04 charactermesh__dbi_widow_incognito_skirt__default__body__body__version_04

skeletons often  in dbi_XXX 
As example:
dbi_widow_incognito_skirt

just search by name.
I was not looking for specifically "Stark" outfit.

update: - it's found by *starktech* mask - charactermesh__thor__starktech__body__body__default, charactermesh__black_widow__starktech__body__body__default e.t.c
 Did you find this in unpacked bigfile.000 or in which one? I have extracted files from bigfile.000 and bigfile.update.1.000.000 in 2 different folders and found nothing with "starktech" outfit in pcx64-w folder.
## Post #163
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-17T12:58:30+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Dont't know i just extract all DRM from all bigfiles.
Do you use last ProjectList form here?
[viewtopic.php?f=16&t=22556&start=105#p166605](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=105#p166605)
## Post #164
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-09-17T16:32:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 7:38 pm at Thu Sep 10, 2020 7:38 pm
>
> 
Noesis script for meshes and textures (beta version)



Works:
- geometry
- multiple UV channels
- skeletons/skin (test)
- textures
- multiple textures in single file (usually standart and HD)


Does not work:
- split LODs

update 16.09.2020
add:
- skeletons/skin (test)
- script for skeleton searching
- multiple textures in single file

Extracting characters with skeleton:
place skeleton file to folder with model,
skeleton name must be strictly "skeleton.maskl".
Skeleton be found in DTPData folder. It's just a renamed *.dtp file

You can use skeleton_finder.py tool for search "skeleton"'s file.
Just edit "search_dir = "D:\\marvel\\drm_unp"" to your path - script check dpd files, copy and renamed its to "skeleton_XXX.maskl" in same folder.
The script may not find all the files, or it may mistakenly recognize some of them. It doesn't fully parse the file structure - it just looks for similar ones.

For some models, skeletons need to be looked for in other "DRM" folders.
You can use noesis to view skeletons structure.

Thanks:  
Dazzy  -   for researching the skeleton structure
Based on Gh0stBlade's script for Tomb Raider
Hi, first of all Thanks a lot guys for all the scripts and unpacker those are awesome but when trying to export textures from the mapcd files some worked but a lot of them gave me the RuntimeError: Tried to set offset beyond buffer size. error and iwas wondering if it had a simple fix or if it's the script not working could someone help me
## Post #165
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-17T17:37:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 17, 2020 8:58 pm at Thu Sep 17, 2020 8:58 pm
>
> 
Dont't know i just extract all DRM from all bigfiles.
Do you use last ProjectList form here?
viewtopic.php?f=16&t=22556&start=105#p166605

Yeah i've found problem just need to update last ProjectList  Thank you again!
## Post #166
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-17T21:54:50+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 17, 2020 5:09 am at Thu Sep 17, 2020 5:09 am
>
> 
the tool has been updated
viewtopic.php?f=16&t=22556&p=166709#p166709

Still got a few mapcd files with errors. for example

```
texture 0		offset 0x0
	uiMagic: 0x7c1cd
	uiPcdType: 0x5e
	uiPcdLength: 0x55000
	uiPcdUnk01: 0x5000
	uiPcdUnk02: 0x201
	uiPcdUnk03: 0xff0104
	uiPcdWidth: 0x200  /  512
	uiPcdHeight: 0x200  /  512
	uiPcdUnk04: 0x1
	uiPcdUnk05: 0x0
	uiPcdUnk06: 0x0
	Tex Header End: 0x28
Traceback (most recent call last):
  File "USER\Noesis\plugins\python\fmt_MarvelsAvengers2020_25.py", line 152, in pcdLoadDDS2
    bs.seek(uiPcdLength , NOESEEK_REL)
  File "USER\Noesis\plugins\python\inc_noesis.py", line 181, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "USER\Noesis\plugins\python\inc_noesis.py", line 177, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "USER\Noesis\plugins\python\inc_noesis.py", line 80, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (348200 > 86072)
```


File is BC7 (5E) 
offset is by 8 (Although displays multiple mipmaps)
## Post #167
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-18T15:11:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

@Ekey
I dont know if this is something you can do with your tool or if just best if we do it manually, i noticed files in update1 and update2 have updated versions of certain drms (like global_menu etc) but does not overwrite the old with the new (by design i know) 
Think it's best to not merge update1 and update2 into the same folder?

Also noteworthy, update 2 seems to output locale's weirdly, almost looks encrypted still.
## Post #168
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-19T12:32:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the tool has been updated
[viewtopic.php?f=16&t=22556&p=166709#p166709](https://forum.xentax.com/viewtopic.php?f=16&t=22556&p=166709#p166709)
## Post #169
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-19T14:29:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Sat Sep 19, 2020 8:32 pm at Sat Sep 19, 2020 8:32 pm
>
> 
the tool has been updated
viewtopic.php?f=16&t=22556&p=166709#p166709

Thank you for update! Works better than previous version! Meshes separated without glitches. 
I have little question abut texture: Some of models have black/white texture but with correct shape and details. Is there any way to find colored one or it depends from charactermesh files? Thank you again for your tool!
## Post #170
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-19T14:43:35+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I don’t know yet. My priority now is to improve texture support.
## Post #171
- Username: Ruisuu18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 16, 2019 3:03 am
- Post datetime: 2020-09-19T19:24:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Is anyone else unable to download Tiger Unpacker or DRM Dumper?

Both download links just give me a 403 Forbidden error.
## Post #172
- Username: bertonberton
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 15, 2020 2:05 pm
- Post datetime: 2020-09-19T19:31:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ruisuu18 ↑Sun Sep 20, 2020 3:24 am at Sun Sep 20, 2020 3:24 am
>
> 
Is anyone else unable to download Tiger Unpacker or DRM Dumper?

Both download links just give me a 403 Forbidden error.

Make sure you disable any vpn on your browser
## Post #173
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-09-19T19:38:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ruisuu18 ↑Sun Sep 20, 2020 3:24 am at Sun Sep 20, 2020 3:24 am
>
> 
Is anyone else unable to download Tiger Unpacker or DRM Dumper?

Both download links just give me a 403 Forbidden error.

Zippyshare is banned in places like UK and some others. use a vpn or proxy
## Post #174
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-09-20T18:05:14+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Big thanx to Gh0stBlade, Ekey, Erik945 with your help and support, I was able to extract model.
[Marvel's Avengers - Black Widow.jpg](https://xentaxbackup.github.io/file/18771_Marvel's Avengers - Black Widow.jpg)
## Post #175
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-20T20:23:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Nice job! Marmoset?
## Post #176
- Username: Kiekii922
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Mar 12, 2020 4:50 am
- Post datetime: 2020-09-21T00:36:12+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Sep 21, 2020 2:05 am at Mon Sep 21, 2020 2:05 am
>
> 
Big thanx to Gh0stBlade, Ekey, Erik945 with your help and support, I was able to extract model.

How did you get the textures? When I do it all of mine are errors and random sizes
## Post #177
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-09-21T03:09:39+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Sep 21, 2020 2:05 am at Mon Sep 21, 2020 2:05 am
>
> 
Big thanx to Gh0stBlade, Ekey, Erik945 with your help and support, I was able to extract model.
Really cool ! how did you manage to export the textures correctly ?
## Post #178
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-09-21T03:56:13+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Mon Sep 21, 2020 4:23 am at Mon Sep 21, 2020 4:23 am
>
> 
Nice job! Marmoset?
Yes, i using marmoset for render
## Post #179
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-09-21T03:58:57+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from ugo9p5 ↑Mon Sep 21, 2020 11:09 am at Mon Sep 21, 2020 11:09 am
>
> 
Crazy31139 wrote: ↑Mon Sep 21, 2020 2:05 am
Big thanx to Gh0stBlade, Ekey, Erik945 with your help and support, I was able to extract model.

Really cool ! how did you manage to export the textures correctly ?

Use latest Noesis and latest plugin Erik945
Open textures in Noesis and convert to interesting format
## Post #180
- Username: Ruisuu18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 16, 2019 3:03 am
- Post datetime: 2020-09-21T04:49:13+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

anyone know the cause of this error?
## Post #181
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-09-21T05:51:30+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Sep 21, 2020 11:58 am at Mon Sep 21, 2020 11:58 am
>
> 
ugo9p5 wrote: ↑Mon Sep 21, 2020 11:09 am
Crazy31139 wrote: ↑Mon Sep 21, 2020 2:05 am
Big thanx to Gh0stBlade, Ekey, Erik945 with your help and support, I was able to extract model.

Really cool ! how did you manage to export the textures correctly ?


Use latest Noesis and latest plugin Erik945
Open textures in Noesis and convert to interesting format
Weird got the latest version of everything but still got glitches
## Post #182
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2020-09-21T10:36:48+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ruisuu18 ↑Mon Sep 21, 2020 12:49 pm at Mon Sep 21, 2020 12:49 pm
>
> 



anyone know the cause of this error?

As I see you are trying to use tools for the BETA version that do not support the release version files =>> updated tools you can found in [this post](https://forum.xentax.com/viewtopic.php?p=166524#p166524)
## Post #183
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-09-21T13:25:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ekey, I wanted to ask - it cannot be such that DRM Dumper will cut files (does not write them to the end).
I parse textures - two files of the similar size. But looks like the headers describe different resolutions (2 x ushort, offset 0x18), first - 1024x1024, second - 4096x4096 and different size of byte arrays(uInt, offset 0x08) first - 0x00 15 55 70, second 0x01 55 55 70 . This is strange.

The archive contains these two files and a "debuging" script for noesis.
[https://www113.zippyshare.com/v/LV5zkRpi/file.html](https://www113.zippyshare.com/v/LV5zkRpi/file.html)

Thank you for tools.
## Post #184
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-09-24T14:54:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Wanted to thank again Gh0stBlade, Ekey, Erik945 for their awesome tools
it's just incredible that, this early after a release we got all these tools so
Thanks all of you for allow us to use them   

(Hope this image works lmao)
Now all i hope for is to the textures system to be figure out soon to be able to render some Hulk stills ! (wish i was a coder to help   )
Good luck !
## Post #185
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-01T07:43:57+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Any progress on thoses textures error ?
## Post #186
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-01T15:50:52+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the tool has been updated
[viewtopic.php?f=16&t=22556&p=166709#p166709](https://forum.xentax.com/viewtopic.php?f=16&t=22556&p=166709#p166709)
## Post #187
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-01T17:17:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Just tested the new update really cool for batch process that the error doesn't show up anymore !
Can't wait for you to find a way to fix the offset bug
## Post #188
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-01T18:27:15+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

What offset bug?
## Post #189
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-01T21:24:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

on some textures when i tried to export i get this error
BEGINNING JOB 0110 - D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted\drm\charactermesh__hulk__classic__body__body__02trackstar\Texture\Resource_90928.mapcd
Detected file type: Marvel's Avengers 2D Texture [PC]


#############################################


fsize: 0xaab10
texture 0		offset 0x0
	uiMagic: 0x7c1cd
	uiPcdType: 0x4d
	uiPcdLength: 0x2aaab8
	uiPcdUnk01: 0xaab8
	uiPcdUnk02: 0x901
	uiPcdUnk03: 0xff010c
	uiPcdWidth: 0x800  /  2048
	uiPcdHeight: 0x800  /  2048
	uiPcdUnk04: 0x1
	uiPcdUnk05: 0x0
	uiPcdUnk06: 0x0
	Tex Header End: 0x28
Traceback (most recent call last):
  File "D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted\Noesis\plugins\python\fmt_MarvelsAvengers2020_29.py", line 155, in pcdLoadDDS2
    bs.seek(uiPcdLength , NOESEEK_REL)
  File "D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted\Noesis\plugins\python\inc_noesis.py", line 181, in seek
    self.toUnpacker(); r = noeSuper(self).seek(addr, isRelative); self.fromUnpacker(); return r
  File "D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted\Noesis\plugins\python\inc_noesis.py", line 177, in fromUnpacker
    self.setOffset(self.byteOfs)
  File "D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted\Noesis\plugins\python\inc_noesis.py", line 80, in setOffset
    noesis.bsSetOfs(self.h, ofs)
RuntimeError: Tried to set offset beyond buffer size. (2796256 > 699152)


Which happens on most important textures and is kind of a bummer
## Post #190
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-01T22:14:27+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

It happens that some textures are not fully writen( fsize  <  uiPcdLength ). Take this resource from another DRM. look for a larger file .
As example:
d: \ marvel \ drm_unp2 \ New folder (2) \ enm_human_red_hulk \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ dbi_hulk_iconic_hair \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ dbi_hulk_broken_hair \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__joefixit__body__body__default \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__joefixit__body__body__05enforcer \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__joefixit__body__body__04pinstripe \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__joefixit__body__body__03suitandtie \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__joefixit__body__body__02justjoe \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__iconic01__body__body__version_05 \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__iconic01__body__body__version_04 \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__iconic01__body__body__version_03 \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__iconic01__body__body__version_02 \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__iconic01__body__body__default \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__classic__body__body__default \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__classic__body__body__05_version \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__classic__body__body__03workout \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__classic__body__body__02trackstar \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__hulk__classic__body__body__01gymrat \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__dbi_hulk_iconic_hair__default__body__body__default \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ charactermesh__dbi_hulk_broken_hair__default__body__body__default \ Texture \ Resource_90928.mapcd
d: \ marvel \ drm_unp2 \ New folder (2) \ av1_cine_only_morph_hulk_broken \ Texture \ Resource_90928.mapcd

this is specific map for the hair.
[453.jpg](https://xentaxbackup.github.io/file/18789_453.jpg)
## Post #191
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-01T23:34:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

oh so i just got to look into other drm for the textures ? i don't understand it fully
## Post #192
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-01T23:35:35+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

yes, search this texture in other drm
## Post #193
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-01T23:39:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks will update if this works
## Post #194
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T01:04:51+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Found a lot of textures but still can't seem to find a lot of them like iconic hulk skin
do i have to have the ultra bigfile cause i don't have them and it doesn't seem i can get them ?
## Post #195
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T19:48:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Fri Oct 02, 2020 7:35 am at Fri Oct 02, 2020 7:35 am
>
> 
yes, search this texture in other drm

Can you help me ? i want to know how to rewrite the offset of the fsize and uiPcdLength 
i just got what you meant and found the right fsize for a textures and i wanted to know how write to the other file
## Post #196
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T21:39:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

fsize - "physical" size of the file, how many bytes are actually present there. You can't rewrite it.
uiPcdLength is the size of the texture data buffer. If it is less than the specified one, the texture of the specified sizes will not fit there. If it larger then the file size, an error occurs (the file has already ended, but the buffer should be larger)
What is the problem?
You found Resource_90928 (2.7 Mb)?
## Post #197
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T22:23:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Sat Oct 03, 2020 5:39 am at Sat Oct 03, 2020 5:39 am
>
> 
fsize - "physical" size of the file, how many bytes are actually present there. You can't rewrite it.
uiPcdLength is the size of the texture data buffer. If it is less than the specified one, the texture of the specified sizes will not fit there. If it larger then the file size, an error occurs (the file has already ended, but the buffer should be larger)
What is the problem?
You found Resource_90928 (2.7 Mb)?

Yes i found it , but most of textures still do not work even in other drm, so i just don't fully understand what you advice me to do 
Just look in other drm if the same ressource is there and with a right sizes or took another file to help another export ?
i just don't get it cause most of the textures that i want to get for exemple iconic hulk do not seems to work and i cannot find them in another drm
## Post #198
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T22:54:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

these?
[1234.jpg](https://xentaxbackup.github.io/file/18793_1234.jpg)
## Post #199
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T23:05:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Yes these i can't seem to find the way to export those and the one that goes with them , i might bé missing some file or stuff like that
## Post #200
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T23:09:50+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

do you use fmt_MarvelsAvengers2020_29.py?
## Post #201
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T23:13:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Sat Oct 03, 2020 7:09 am at Sat Oct 03, 2020 7:09 am
>
> 
do you use fmt_MarvelsAvengers2020_29.py?

yes i do   
here a screenshot after the export of the iconic default drm
## Post #202
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T23:21:12+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

show me your noesis\plugins\python folder and version of noesis.
## Post #203
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T23:24:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

My noesis version is the latest normally it's version 4.433
and here is my python folder
## Post #204
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T23:33:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

send me Resource_87832.mapcd
## Post #205
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T23:38:35+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

there you go
[https://www36.zippyshare.com/v/kQ6qtGfl/file.html](https://www36.zippyshare.com/v/kQ6qtGfl/file.html)
Thanks a lot for the help
## Post #206
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-02T23:48:20+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

You have this file smaller. It should be 10.6 Mb. Did you get it from charactermesh__hulk__iconic01__body__body__default?
## Post #207
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2020-10-02T23:52:18+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

yep i did get it from there
but i think i know my problem
i don't have the big file ultra tiger
so when i export the drm some are not found or stuff like that so i suppose it's because of this 
how do i get those ? they we're not with my game
## Post #208
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-10-04T18:54:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi, someone can find bosses models or civil heroes models, like bruce banner
## Post #209
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-10-05T19:46:48+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I assume we still have an issue to overcome. this is for .Locale files. 
They extract fine for the base bigfiles (see: [https://imgur.com/a/xVMcO27](https://imgur.com/a/xVMcO27))

however for updates the extract like such ([https://imgur.com/a/5UfSegh](https://imgur.com/a/5UfSegh))

These are both the same file but different versions. 
1st is from 1.0
2nd is from update2
## Post #210
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-14T13:40:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the tool has been updated
[viewtopic.php?f=16&t=22556&p=166709#p166709](https://forum.xentax.com/viewtopic.php?f=16&t=22556&p=166709#p166709)
update 14.10.2020
add:
support LOD's number for submesh.
## Post #211
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-10-14T17:06:20+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Need help, cant find captain america skeleton, dont finding in my extracted files dbi_captain
Now try reextract all files, someone finding cap skeleton?
## Post #212
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-14T18:02:36+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

try this:
av1_cine_costume_captain_america
av1_puppet_ambient_captain
av1_puppet_captain_america
av1_puppet_captain_america_ada_speech
av1_puppet_captain_america_asl
av1_puppet_captain_america_modok_hostage
av1_puppet_wcap_captain_america
captain_america
## Post #213
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2020-10-14T18:16:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Oct 15, 2020 2:02 am at Thu Oct 15, 2020 2:02 am
>
> 
try this:
av1_cine_costume_captain_america
av1_puppet_ambient_captain
av1_puppet_captain_america
av1_puppet_captain_america_ada_speech
av1_puppet_captain_america_asl
av1_puppet_captain_america_modok_hostage
av1_puppet_wcap_captain_america
captain_america
Thanx for help i finded in captain_america.drm
## Post #214
- Username: erik945
- Rank: mega-veteran
- Number of posts: 257
- Joined date: Sat Jan 21, 2012 12:43 am
- Post datetime: 2020-10-14T19:03:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

the tool has been updated
[viewtopic.php?f=16&t=22556&p=166709#p166709](https://forum.xentax.com/viewtopic.php?f=16&t=22556&p=166709#p166709)
hotfix14.10.2020#1
Some models has lod0, added its extraction to parametr LoadOnlyLod1
## Post #215
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-10-23T01:51:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Sep 05, 2020 3:57 am at Sat Sep 05, 2020 3:57 am
>
> 
Hey everyone!

Decryption tool for the retail game files is now available below.

Thanks. Bro, this works with latest update version of game (1.3.3 build 141640) ?
## Post #216
- Username: Blackwolfe5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Oct 25, 2020 12:32 am
- Post datetime: 2020-10-24T16:45:45+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks for this. I'm trying to get the mission icons at the moment. Still trying to figure out the tools.

Only managed to exract.. mul files.. so far?
## Post #217
- Username: IcarusTwine
- Rank: beginner
- Number of posts: 22
- Joined date: Tue Aug 18, 2020 6:36 am
- Post datetime: 2020-10-30T19:17:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Oct 15, 2020 3:03 am at Thu Oct 15, 2020 3:03 am
>
> 
the tool has been updated
viewtopic.php?f=16&t=22556&p=166709#p166709
hotfix14.10.2020#1
Some models has lod0, added its extraction to parametr LoadOnlyLod1

Interesting about textures, have you come across any which seem to come out the wrong colours? blue skin for example.
fixed: type 0x54 is also used for `b8g8r8a8`
## Post #218
- Username: 2689081964
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 25, 2018 2:26 pm
- Post datetime: 2020-11-04T06:05:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Sep 05, 2020 3:57 am at Sat Sep 05, 2020 3:57 am
>
> 
Hey everyone!

Decryption tool for the retail game files is now available below.

I can't decrypt the "ultra--tiger" file.

Because my decryption tool has nothing to do with it.

This caused me to end up unpacking a file that was too small to properly export the texture

It seems there are other people who are having the same problem as me.
## Post #219
- Username: lujieshen
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 10, 2018 2:55 pm
- Post datetime: 2020-11-04T11:50:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Oct 15, 2020 3:03 am at Thu Oct 15, 2020 3:03 am
>
> 
the tool has been updated
viewtopic.php?f=16&t=22556&p=166709#p166709
hotfix14.10.2020#1
Some models has lod0, added its extraction to parametr LoadOnlyLod1

Thanks for great work. Just some improvements when I'm playing with mapcd: I found sometimes `uiPcdLength` is bigger than the file itself. After some investigation, it seems the texture data is just one mip downsized. So I added some lines here

```
print("	uiPcdUnk06: " + str(hex(uiPcdUnk06) ))
print("	Tex Header End: " + str(hex(bs.tell())))
# ============================
if ((uiPcdLength % 4 == 0) and (uiPcdLength > fsize * 3)):
	print("	maybe downsample one mip")
	uiPcdWidth = int(uiPcdWidth / 2)
	uiPcdHeight = int(uiPcdHeight / 2)
	uiPcdLength = int(uiPcdLength / 4)
# ============================
test_offset = bs.tell()
add_val = 0
bs.seek(uiPcdLength , NOESEEK_REL)

```




clipboard.jpg (97.12 KiB) Viewed 364 times
## Post #220
- Username: 2689081964
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 25, 2018 2:26 pm
- Post datetime: 2020-11-15T13:16:58+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from 2689081964 ↑Wed Nov 04, 2020 2:05 pm at Wed Nov 04, 2020 2:05 pm
>
> 
Gh0stBlade wrote: ↑Sat Sep 05, 2020 3:57 am
Hey everyone!

Decryption tool for the retail game files is now available below.


I can't decrypt the "ultra--tiger" file.

Because my decryption tool has nothing to do with it.

This caused me to end up unpacking a file that was too small to properly export the texture

It seems there are other people who are having the same problem as me.

我已经解决了这个问题，希望能帮助到后面想要提取的人。
首先我们要将“TigerDecrypt_v1_3”加些东西进行改造，使他可以将“urtla”文件进行解密。
之后使用“MA.Tiger.Unpacker_0.0.3.1637”将他支持的三个文件解包到同一个文件夹，大约得到8gb

最后使用“MA.DRM.Dumper_0.0.3.1622”将需要的资源文件进行转换。

重点在于“urtla”文件的解密，不解密的话就会像这里一样“[viewtopic.php?f=16&t=22556&start=195#p167314”只有2mb](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=195#p167314%E2%80%9D%E5%8F%AA%E6%9C%892mb)，解密后可以得到10mb

I've solved the problem and hope it will help those who want to extract it later.
First we have to modify "TigerDecrypt_v1_3" with something so that it can decrypt the "urtla" file.Just add the "ultra" manually.
Unpacker_0.0.3.1637" to unpack the three files he supports into one folder, and we get about 8gb!

Dumper_0.0.3.1622" is used to convert the required resource files.

The key point is to decrypt the "urtla" file, if you don't decrypt it, the "viewtopic.php?f=16&t=22556&start=195#p167314" will be only 2mb, like here. You get 10mb for decryption.

Translated with [www.DeepL.com/Translator](http://www.DeepL.com/Translator) (free version)
## Post #221
- Username: 2689081964
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 25, 2018 2:26 pm
- Post datetime: 2020-11-15T18:02:30+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from 2689081964 ↑Sun Nov 15, 2020 9:16 pm at Sun Nov 15, 2020 9:16 pm
>
> 
2689081964 wrote: ↑Wed Nov 04, 2020 2:05 pm
Gh0stBlade wrote: ↑Sat Sep 05, 2020 3:57 am
Hey everyone!

Decryption tool for the retail game files is now available below.


I can't decrypt the "ultra--tiger" file.

Because my decryption tool has nothing to do with it.

This caused me to end up unpacking a file that was too small to properly export the texture

It seems there are other people who are having the same problem as me.


我已经解决了这个问题，希望能帮助到后面想要提取的人。
首先我们要将“TigerDecrypt_v1_3”加些东西进行改造，使他可以将“urtla”文件进行解密。
之后使用“MA.Tiger.Unpacker_0.0.3.1637”将他支持的三个文件解包到同一个文件夹，大约得到8gb

最后使用“MA.DRM.Dumper_0.0.3.1622”将需要的资源文件进行转换。

重点在于“urtla”文件的解密，不解密的话就会像这里一样“viewtopic.php?f=16&t=22556&start=195#p167314”只有2mb，解密后可以得到10mb

I've solved the problem and hope it will help those who want to extract it later.
First we have to modify "TigerDecrypt_v1_3" with something so that it can decrypt the "urtla" file.Just add the "ultra" manually.
Unpacker_0.0.3.1637" to unpack the three files he supports into one folder, and we get about 8gb!

Dumper_0.0.3.1622" is used to convert the required resource files.

The key point is to decrypt the "urtla" file, if you don't decrypt it, the "viewtopic.php?f=16&t=22556&start=195#p167314" will be only 2mb, like here. You get 10mb for decryption.

Translated with www.DeepL.com/Translator (free version)

But I don't know how to attach bones yet.

Most importantly I don't know how to use "MA.DRM.Dumper_0.0.3.1622" for batch export. I have to convert them one by one, which is very tiring!
## Post #222
- Username: 2689081964
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Sep 25, 2018 2:26 pm
- Post datetime: 2020-12-11T09:19:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from 2689081964 ↑Mon Nov 16, 2020 2:02 am at Mon Nov 16, 2020 2:02 am
>
> 
2689081964 wrote: ↑Sun Nov 15, 2020 9:16 pm
2689081964 wrote: ↑Wed Nov 04, 2020 2:05 pm


I can't decrypt the "ultra--tiger" file.

Because my decryption tool has nothing to do with it.

This caused me to end up unpacking a file that was too small to properly export the texture

It seems there are other people who are having the same problem as me.


我已经解决了这个问题，希望能帮助到后面想要提取的人。
首先我们要将“TigerDecrypt_v1_3”加些东西进行改造，使他可以将“urtla”文件进行解密。
之后使用“MA.Tiger.Unpacker_0.0.3.1637”将他支持的三个文件解包到同一个文件夹，大约得到8gb

最后使用“MA.DRM.Dumper_0.0.3.1622”将需要的资源文件进行转换。

重点在于“urtla”文件的解密，不解密的话就会像这里一样“viewtopic.php?f=16&t=22556&start=195#p167314”只有2mb，解密后可以得到10mb

I've solved the problem and hope it will help those who want to extract it later.
First we have to modify "TigerDecrypt_v1_3" with something so that it can decrypt the "urtla" file.Just add the "ultra" manually.
Unpacker_0.0.3.1637" to unpack the three files he supports into one folder, and we get about 8gb!

Dumper_0.0.3.1622" is used to convert the required resource files.

The key point is to decrypt the "urtla" file, if you don't decrypt it, the "viewtopic.php?f=16&t=22556&start=195#p167314" will be only 2mb, like here. You get 10mb for decryption.

Translated with www.DeepL.com/Translator (free version)


But I don't know how to attach bones yet.

Most importantly I don't know how to use "MA.DRM.Dumper_0.0.3.1622" for batch export. I have to convert them one by one, which is very tiring!

@echo off
color a
for /f "delims=" %%a in ('dir /a-d/b *.drm') do D:\avengers\MA.DRM.Dumper_0.0.3.1622\MA.DRM.Dumper.exe "%%~a" "D:\avengers\5" "D:\avengers\Decrypted"

pause
## Post #223
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2020-12-22T16:17:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Greetings all.
I managed to decode the archives
I managed to unpack the archives

So far so good, but I never found anything useful, and I believe it is related to this error:
C:\avengers>MAB.DRM.Dumper.exe c:\avengers\default\pcx64-w\charactermesh__black_widow__default__body__body__06_version.drm c:\avengers\unpacked c:\avengers\decrypted
Marvel's Avengers (BETA) (C)DRM Dumper
(c) 2020 Ekey (h4x0r) / v0.0.2.39914

[CDRM INFO]: File: charactermesh__black_widow__default__body__body__06_version.drm
[DUMPING]: => [Material] -> Resource_2661134.material
[DUMPING]: => [Material] -> Resource_2660705.material
[DUMPING]: => [Material] -> Resource_2661163.material
[DUMPING]: => [Material] -> Resource_2661075.material
[DUMPING]: => [Material] -> Resource_2660803.material
[DUMPING]: => [Material] -> Resource_2661133.material
[DUMPING]: => [Material] -> Resource_2661164.material
[DUMPING]: => [Shader] -> Resource_74519.shader
[DUMPING]: => [Shader] -> Resource_74520.shader
[DUMPING]: => [Shader] -> Resource_74521.shader
[DUMPING]: => [Shader] -> Resource_74522.shader
[DUMPING]: => [Shader] -> Resource_75818.shader
[DUMPING]: => [Shader] -> Resource_75819.shader
[DUMPING]: => [Shader] -> Resource_75820.shader
[DUMPING]: => [Shader] -> Resource_75821.shader
[DUMPING]: => [Shader] -> Resource_76087.shader
[DUMPING]: => [Shader] -> Resource_76088.shader
[DUMPING]: => [Shader] -> Resource_76089.shader
[DUMPING]: => [Shader] -> Resource_76090.shader
[DUMPING]: => [Shader] -> Resource_77925.shader
[DUMPING]: => [Shader] -> Resource_77926.shader
[DUMPING]: => [Shader] -> Resource_77927.shader
[DUMPING]: => [Shader] -> Resource_77928.shader
[DUMPING]: => [Shader] -> Resource_77936.shader
[DUMPING]: => [Shader] -> Resource_77937.shader
[DUMPING]: => [Shader] -> Resource_77938.shader
[DUMPING]: => [Shader] -> Resource_77939.shader
[DUMPING]: => [Shader] -> Resource_82099.shader
[DUMPING]: => [Shader] -> Resource_82100.shader
[DUMPING]: => [Shader] -> Resource_82101.shader
[DUMPING]: => [Shader] -> Resource_82102.shader
[DUMPING]: => [Material] -> Resource_2661001.material

Unhandled Exception: System.Exception: [ERROR]: Unknown package ID 575 with 1 priority!
   at MAB.DRM.Dumper.Program.iGetPackageNameFromID(UInt16 sTigerID, UInt16 sPriority)
   at MAB.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder)
   at MAB.DRM.Dumper.Program.Main(String[] args)

Shaders, Materials. But no textures or meshes? What can it be?
## Post #224
- Username: snowboundmage
- Rank: advanced
- Number of posts: 40
- Joined date: Tue Dec 21, 2010 12:24 pm
- Post datetime: 2020-12-27T07:09:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Yo

I decrypted all the files, but when i pump the decrypted .tiger files into MAB.Tiger.Unpacker_0.0.2.33474, i only get .mul files in my unpack folder

Here's a little preview of the start of the log, with the rest just being a billion lines of "archive bigfile does not exist."

> marvels.PNG (93.77 KiB) Viewed 126 times

Also, update1.000.000.tiger isn't recognized

> J:\marvelsavengers\MAB.Tiger.Unpacker_0.0.2.33474> J:\marvelsavengers\MAB.Tiger.Unpacker_0.0.2.33474\MAB.Tiger.Unpacker.exe J:\madecrypted\bigfile.update1.000.000.tiger J:\MAunpack\
>
> Marvel's Avengers (BETA) TIGER UnPacker
>
> (c) 2020 Ekey (h4x0r) / v0.0.2.33474
>
> 
>
> Tool for decrypt TIGER files made by Gh0stBlade you can found by the link below!
>
> viewtopic.php?p=166049#p166049
>
> 
>
> [INFO]: Project File Loaded: 26209
>
> 
>
> [ERROR]: Invalid TIGER file!

Also, update 2 is just straight up not compatible

> J:\marvelsavengers\MAB.Tiger.Unpacker_0.0.2.33474> J:\marvelsavengers\MAB.Tiger.Unpacker_0.0.2.33474\MAB.Tiger.Unpacker.exe J:\madecrypted\bigfile.update2.000.000.tiger J:\MAunpack\
>
> Marvel's Avengers (BETA) TIGER UnPacker
>
> (c) 2020 Ekey (h4x0r) / v0.0.2.33474
>
> 
>
> Tool for decrypt TIGER files made by Gh0stBlade you can found by the link below!
>
> viewtopic.php?p=166049#p166049
>
> 
>
> [ERROR]: The file you are trying to unpack is part of the main archives!
>
> [ERROR]: Only following archives are allowed: bigfile.000.tiger, bigfile.update1.000.000.tiger

side note: the link for tigerdecrypt in the unpacker text links to 1_2, not 1_3
## Post #225
- Username: HAFEEZ1010
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 15, 2020 4:53 am
- Post datetime: 2020-12-29T18:43:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

HI GUYS I NEED A LITTLE HELP IN THE DRM DUMPING PROCESS I HAVE TRIED TO DUMP THE (charactermesh__ironman__classic__body__body__default.drm) after this a few lines in my cmd passed and a folder with the same name  (charactermesh__ironman__classic__body__body__default.drm) was created in my unpack folder but as i open it, it was empty!!! Please help me out!
## Post #226
- Username: HAFEEZ1010
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 15, 2020 4:53 am
- Post datetime: 2020-12-29T18:45:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

BY THE WAY I'M USING THE (fitgirl Repack) version of the game marvels avengers my repack also contain the ultra textures!
## Post #227
- Username: HAFEEZ1010
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 15, 2020 4:53 am
- Post datetime: 2021-01-02T12:39:36+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

HI GUYS I HAVE CRACK VERSION OF THE GAME SO I COULD NOT EXTRACT 3D MODELS FROM IT AS THE FILE SIZE IS COMPRESSED PLEASE HELP ME OUT BY SENDING ME ALL THE .TIGER FILES JUST ON GOOGLE DRIVE DOWNLOAD LINK I NEED THE ORIGINAL GAME ALL .TIGER FILES THANKS!
## Post #228
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2021-01-06T06:58:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Sep 05, 2020 3:57 am at Sat Sep 05, 2020 3:57 am
>
> 
Hey everyone!

Decryption tool for the retail game files is now available below.

Hey Gh0stBlade, just wondering if you could check the tool for some of the tiger files after the dlc update.
Some files do not decrypt properly.
Before the update the file decrypted properly

After the update its like this 


I'd really like to get the Kate Bishop model, but it seems I wont be able to right now.
Thanks for you efforts
## Post #229
- Username: befithalo
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 13, 2021 5:42 pm
- Post datetime: 2021-01-13T10:30:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from HAFEEZ1010 ↑Sat Jan 02, 2021 8:39 pm at Sat Jan 02, 2021 8:39 pm
>
> 
HI GUYS I HAVE CRACK VERSION OF THE GAME SO I COULD NOT EXTRACT 3D MODELS FROM IT AS THE FILE SIZE IS COMPRESSED PLEASE HELP ME OUT BY SENDING ME ALL THE .TIGER FILES JUST ON GOOGLE DRIVE DOWNLOAD LINK I NEED THE ORIGINAL GAME ALL .TIGER FILES THANKS!

If you're using FITGIRL, then you should has an installer for the game in the download folder, in which it installs all the proper .tiger files in the usual place, same as retail download.
## Post #230
- Username: abstrait
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Dec 05, 2016 12:33 am
- Post datetime: 2021-01-25T13:40:47+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Any idea where the Black Widow's room is located ?
I can't find it...
## Post #231
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-01-30T21:49:19+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from riccochet ↑Wed Jan 06, 2021 2:58 pm at Wed Jan 06, 2021 2:58 pm
>
> 
Hey Gh0stBlade, just wondering if you could check the tool for some of the tiger files after the dlc update.
Some files do not decrypt properly.
Before the update the file decrypted properly

After the update its like this 


I'd really like to get the Kate Bishop model, but it seems I wont be able to right now.
Thanks for you efforts

To me it looks like they linked the update files to the main bigfiles or something like that, because after decrypting the update1,2 and 3 I can see the internal filenames and other text that is not visible unencrypted, which would make the extraction an issue with the unpacker rather than with the decrypter:




example.jpg (240.16 KiB) Viewed 1223 times
## Post #232
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-01-31T21:48:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

GDL, а какой редактор вы используете?
По вашему скриншоту удалось извлечь некоторые костюмы Kate Bishop
In your screenshot managed to extract some costumes Kate Bishop
GDL and which editor do you use?
## Post #233
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-01-31T21:55:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I'ts called "010 Editor"
## Post #234
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-01T00:08:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Менял кодировки, но такого текста нет.
He changed encodings, but there is no such text.
## Post #235
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-02-01T00:24:00+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from micro777 ↑Mon Feb 01, 2021 8:08 am at Mon Feb 01, 2021 8:08 am
>
> 
Менял кодировки, но такого текста нет.
He changed encodings, but there is no such text.

That's weird, I had no problems decrypting it with just this:

TigerDecrypt.exe bigfile.update1.000.000.tiger 0

Are you using TygerDecrypt 1.3?
## Post #236
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-01T10:45:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from GDL ↑Mon Feb 01, 2021 8:24 am at Mon Feb 01, 2021 8:24 am
>
> 
micro777 wrote: ↑Mon Feb 01, 2021 8:08 am
Менял кодировки, но такого текста нет.
He changed encodings, but there is no such text.



That's weird, I had no problems decrypting it with just this:

TigerDecrypt.exe bigfile.update1.000.000.tiger 0

Are you using TygerDecrypt 1.3?
Yes, used TygerDecrypt 1.3
## Post #237
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-02T01:48:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020


## Post #238
- Username: anhbeto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 22, 2020 6:13 pm
- Post datetime: 2021-02-13T19:09:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hey! First of all thanks to the people who developed this tools. In the other hand, I would like to formulate various questions. First of all, I would like to know why return me this fail when i try to extract with the MA.DRM.DUMPER.
Result:
Excepción no controlada: System.IO.FileNotFoundException: No se puede cargar el archivo o ensamblado 'Ionic.Zlib, Version=1.9.1.8, Culture=neutral, PublicKeyToken=edbe51ad942a3f5c' ni una de sus dependencias. El sistema no puede encontrar el archivo especificado.
   en MA.DRM.Dumper.Program.iDecompress(Byte[] pScrBuffer, Int32 dwZSize)
   en MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   en MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   en MA.DRM.Dumper.Program.Main(String[] args)
Arguments: 
MA.DRM.Dumper.exe "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\default\pcx64-w\ada_elevator.drm" "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\Update" "F:\steam\steamapps\common\Marvels Avengers\Decrypted"

Other question, I'm starting in this world, in fact this is one of my first contact with reverse engineering, and I'm trying to understand with my previous knowledge about IT(I'm sysadmin), but there are some things that i cannot get. First, ¿how do i open these archives?. I mean, for example, the audio archives or the textures or whatever. I suppose i must use a hex editor read and trying to figure out some things, but how do i get to the result of extracting models and that?. Thanks for reading, sorry if i made mistakes writing this, but English is not my first language
## Post #239
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-13T20:18:09+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from eddyz115 ↑Sun Feb 14, 2021 3:09 am at Sun Feb 14, 2021 3:09 am
>
> 
Arguments: 
MA.DRM.Dumper.exe "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\default\pcx64-w\ada_elevator.drm" "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\Update" "F:\steam\steamapps\common\Marvels Avengers\Decrypted"

After the Unpacked folder, there must be a Bigfail folder.
For example,
 E :\Unpacked2\bigfile\default\pcx64-w\ada _ elevator.drm
Perhaps the paths should be as short as possible.
For example, 
MA.DRM.Dumper E:\Unpacked2\bigfile\default\pcx64-w\ada_elevator.drm E:\Unpacked\DRM E:\MA\Decrypted
## Post #240
- Username: anhbeto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 22, 2020 6:13 pm
- Post datetime: 2021-02-15T03:53:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks for the advice, but I still getting the same error. I mean, i think it's something with this error line:
'Ionic.Zlib, Version=1.9.1.8, Culture=neutral, PublicKeyToken=edbe51ad942a3f5c'
It says that he cannot load that archive. Any suggests? Thanks  

PS: Once I have some archives with the .mapcd extension, how can i open them?
## Post #241
- Username: anhbeto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 22, 2020 6:13 pm
- Post datetime: 2021-02-20T07:16:46+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from micro777 ↑Sun Feb 14, 2021 4:18 am at Sun Feb 14, 2021 4:18 am
>
> 
eddyz115 wrote: ↑Sun Feb 14, 2021 3:09 am
Arguments: 
MA.DRM.Dumper.exe "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\default\pcx64-w\ada_elevator.drm" "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\Update" "F:\steam\steamapps\common\Marvels Avengers\Decrypted"


After the Unpacked folder, there must be a Bigfail folder.
For example,
 E :\Unpacked2\bigfile\default\pcx64-w\ada _ elevator.drm
Perhaps the paths should be as short as possible.
For example, 
MA.DRM.Dumper E:\Unpacked2\bigfile\default\pcx64-w\ada_elevator.drm E:\Unpacked\DRM E:\MA\Decrypted

And Another question. There are DRM files that opens as a DTP File and i cannot convert to a valid format, there's a step im losing ? Also, there's .mapcd that i cannot import to a valid app to see textures and all that stuff. Thanks in advance again mate
## Post #242
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-20T10:07:57+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from eddyz115 ↑Sat Feb 20, 2021 3:16 pm at Sat Feb 20, 2021 3:16 pm
>
> 
micro777 wrote: ↑Sun Feb 14, 2021 4:18 am
eddyz115 wrote: ↑Sun Feb 14, 2021 3:09 am
Arguments: 
MA.DRM.Dumper.exe "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\default\pcx64-w\ada_elevator.drm" "F:\steam\steamapps\common\Marvels Avengers\cx\Unpacked\Update" "F:\steam\steamapps\common\Marvels Avengers\Decrypted"


After the Unpacked folder, there must be a Bigfail folder.
For example,
 E :\Unpacked2\bigfile\default\pcx64-w\ada _ elevator.drm
Perhaps the paths should be as short as possible.
For example, 
MA.DRM.Dumper E:\Unpacked2\bigfile\default\pcx64-w\ada_elevator.drm E:\Unpacked\DRM E:\MA\Decrypted


And Another question. There are DRM files that opens as a DTP File and i cannot convert to a valid format, there's a step im losing ? Also, there's .mapcd that i cannot import to a valid app to see textures and all that stuff. Thanks in advance again mate

DRM I convert only to .OBJ format
If converted to other formats, empty files are created.
I did not open or convert DTP files.
To open most files (99%) .mapcd files must be decrypted with ultra textures.
These are files TigerDecrypt bigfile_ultra.000.tiger 0, bigfile_ultra.000.tiger 1...bigfile_ultra.000.tiger 6.
Then unpack the files
1. bigfile.000.tiger
2. bigfile.update1.000.000.tiger
3. bigfile.update2.000.000.tiger
## Post #243
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-02-21T01:58:12+00:00
- Post Title: Re: I can't Extract these files and how to read it

I believe I have the same issue as the previous guy, I simply cant get all of the textures.
How do I decrypt bigfile_ultra.000 - bigfile_ultra.006? The tool seems to ignore those. And thanks for all the work that has been done for this game.
## Post #244
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-02-21T08:41:46+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from Vanillamilkshake ↑Sun Feb 21, 2021 9:58 am at Sun Feb 21, 2021 9:58 am
>
> 
I believe I have the same issue as the previous guy, I simply cant get all of the textures.
How do I decrypt bigfile_ultra.000 - bigfile_ultra.006? The tool seems to ignore those. And thanks for all the work that has been done for this game.

I spelled out the names of the files bigfile_ultra0-6, bigfile.update1-2.000_ultra.000.tiger in the tool TigerDecrypt_v1_3.
I did so:

The previous instrument has not been preserved. Now I have re-spelled the names.


 TigerDecrypt_v1_3.rar
(7.71 KiB) Downloaded 212 times
## Post #245
- Username: anhbeto
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Dec 22, 2020 6:13 pm
- Post datetime: 2021-02-22T10:40:30+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from micro777 ↑Sat Feb 20, 2021 6:07 pm at Sat Feb 20, 2021 6:07 pm
>
> 
eddyz115 wrote: ↑Sat Feb 20, 2021 3:16 pm
micro777 wrote: ↑Sun Feb 14, 2021 4:18 am


After the Unpacked folder, there must be a Bigfail folder.
For example,
 E :\Unpacked2\bigfile\default\pcx64-w\ada _ elevator.drm
Perhaps the paths should be as short as possible.
For example, 
MA.DRM.Dumper E:\Unpacked2\bigfile\default\pcx64-w\ada_elevator.drm E:\Unpacked\DRM E:\MA\Decrypted


And Another question. There are DRM files that opens as a DTP File and i cannot convert to a valid format, there's a step im losing ? Also, there's .mapcd that i cannot import to a valid app to see textures and all that stuff. Thanks in advance again mate  


DRM I convert only to .OBJ format
If converted to other formats, empty files are created.
I did not open or convert DTP files.
To open most files (99%) .mapcd files must be decrypted with ultra textures.
These are files TigerDecrypt bigfile_ultra.000.tiger 0, bigfile_ultra.000.tiger 1...bigfile_ultra.000.tiger 6.
Then unpack the files
1. bigfile.000.tiger
2. bigfile.update1.000.000.tiger
3. bigfile.update2.000.000.tiger
Okay, I understand the proccess and I thank you for being so clear. But I have some questions, I'm using the steam retail version, in my files there are no ultra files so i cannot decrypt them, are there in other side? The second thing is, you convert first the DRM to OBJ? Or you do the tigerdecrypt to ultra and with the result you try MA.DRM.DUMPER. Sorry If I have so many questions, but i'm still learning how to this things. If you can give me a little guide showing me the proccess you made for obtaining models and that, I would apreciate so much. Again, thanks for your time mate
## Post #246
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-03-10T12:07:11+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from eddyz115 ↑Mon Feb 22, 2021 6:40 pm at Mon Feb 22, 2021 6:40 pm
>
> 
Okay, I understand the proccess and I thank you for being so clear. But I have some questions, I'm using the steam retail version, in my files there are no ultra files so i cannot decrypt them, are there in other side? The second thing is, you convert first the DRM to OBJ? Or you do the tigerdecrypt to ultra and with the result you try MA.DRM.DUMPER. Sorry If I have so many questions, but i'm still learning how to this things. If you can give me a little guide showing me the proccess you made for obtaining models and that, I would apreciate so much. Again, thanks for your time mate

You need to right click the game inside the steam list -> properties -> DLC -> check the box that says ultra textures and steam will download the missing files.

One thing to point out is that it seem the decrypter is unable to properly decrypt the latest version of all the bigfile.update1.* files.
## Post #247
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-03-21T09:53:02+00:00
- Post Title: Re: I can't Extract these files and how to read it

New update adds Hawkeye, but I cant seem to find the model for him, Kate Bishop or any of the newer outfits for the base game heroes.
## Post #248
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2021-03-21T19:23:38+00:00
- Post Title: Re: I can't Extract these files and how to read it

I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.
## Post #249
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-03-21T22:58:16+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from Gh0stBlade ↑Mon Mar 22, 2021 3:23 am at Mon Mar 22, 2021 3:23 am
>
> 


I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.

Nice, I wonder why they decided to change the encryption in those files in particular instead of all of them.
## Post #250
- Username: sirgollum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 13, 2021 10:12 am
- Post datetime: 2021-03-23T10:33:08+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from GDL ↑Mon Mar 22, 2021 6:58 am at Mon Mar 22, 2021 6:58 am
>
> 
Gh0stBlade wrote: ↑Mon Mar 22, 2021 3:23 am


I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.


Nice, I wonder why they decided to change the encryption in those files in particular instead of all of them.

Because they don't want he new content being leaked, the old files there is nothing new in them
## Post #251
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-03-23T12:54:50+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from sirgollum ↑Tue Mar 23, 2021 6:33 pm at Tue Mar 23, 2021 6:33 pm
>
> 
GDL wrote: ↑Mon Mar 22, 2021 6:58 am
Gh0stBlade wrote: ↑Mon Mar 22, 2021 3:23 am


I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.


Nice, I wonder why they decided to change the encryption in those files in particular instead of all of them.


Because they don't want he new content being leaked, the old files there is nothing new in them

Guess will have to wait awhile, the only compareble game is Anthem, and its still up and going after 2 years since its release.
## Post #252
- Username: sirgollum
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 13, 2021 10:12 am
- Post datetime: 2021-03-23T14:09:33+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from Vanillamilkshake ↑Tue Mar 23, 2021 8:54 pm at Tue Mar 23, 2021 8:54 pm
>
> 
sirgollum wrote: ↑Tue Mar 23, 2021 6:33 pm
GDL wrote: ↑Mon Mar 22, 2021 6:58 am


Nice, I wonder why they decided to change the encryption in those files in particular instead of all of them.


Because they don't want he new content being leaked, the old files there is nothing new in them


Guess will have to wait awhile, the only compareble game is Anthem, and its still up and going after 2 years since its release.

Well or Destiny 1/Destiny 2 they are still going after 6 and 3 years respectively
## Post #253
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-03-23T17:40:24+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from sirgollum ↑Tue Mar 23, 2021 10:09 pm at Tue Mar 23, 2021 10:09 pm
>
> 
Vanillamilkshake wrote: ↑Tue Mar 23, 2021 8:54 pm
sirgollum wrote: ↑Tue Mar 23, 2021 6:33 pm


Because they don't want he new content being leaked, the old files there is nothing new in them


Guess will have to wait awhile, the only compareble game is Anthem, and its still up and going after 2 years since its release.


Well or Destiny 1/Destiny 2 they are still going after 6 and 3 years respectively

And they just announced Hawkeye and Black Panther
## Post #254
- Username: Lupacier
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 29, 2021 2:02 am
- Post datetime: 2021-03-28T18:39:16+00:00
- Post Title: Re: I can't Extract these files and how to read it

Priority, thank you very much, ekey, my problem is bigfile.000.tiger + Decrypt_Bigfile.bat together and D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted files of the same name occurred in this folder, but open them when I use it in MA.TigerUnpacker.bat nothing happens, I'm doing it wrong somewhere, but I understand, can you help me ? Update to the game advanced does this tool work in the latest version? You can reach me on discord Lupaceir#6627 It's so you want to open the game's language files Thanks ekey
## Post #255
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-03-31T02:45:11+00:00
- Post Title: Re: I can't Extract these files and how to read it

> Reply from Lupacier ↑Mon Mar 29, 2021 2:39 am at Mon Mar 29, 2021 2:39 am
>
> 
Priority, thank you very much, ekey, my problem is bigfile.000.tiger + Decrypt_Bigfile.bat together and D:\SteamLibrary\steamapps\common\Marvels Avengers\Decrypted files of the same name occurred in this folder, but open them when I use it in MA.TigerUnpacker.bat nothing happens, I'm doing it wrong somewhere, but I understand, can you help me ? Update to the game advanced does this tool work in the latest version? You can reach me on discord Lupaceir#6627 It's so you want to open the game's language files Thanks ekey

Did you let it fully decrypted? bigfile.000.tiger should be around 4GB in your Decrypted folder, all the other bigfiles are in similar size.

If it is, then open cmd, drag MA.unpacker into it, press space, drag the decrypted bigfile.000.tiger into it, space again, and then drag the folder where you want the unpacked files to go to into cmd, and then press enter. It should start unpacking.
## Post #256
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-04-01T16:44:41+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I was trying to grab the black Widow classic costume, it is the one named predator in the files for some unknown reason.

But I see some textures are not ripped. for example the normal map for the lower body. There is a map for a damaged version, but the clean one I can not find..

Any help to get?
## Post #257
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-04-02T16:10:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Ankhati ↑Fri Apr 02, 2021 12:44 am at Fri Apr 02, 2021 12:44 am
>
> 
I was trying to grab the black Widow classic costume, it is the one named predator in the files for some unknown reason.

But I see some textures are not ripped. for example the normal map for the lower body. There is a map for a damaged version, but the clean one I can not find..

Any help to get?



bwbottom.png (252.28 KiB) Viewed 352 times


This? its called Resource_87010 and its 21.846kb
## Post #258
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-04-03T08:21:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Sat Apr 03, 2021 12:10 am at Sat Apr 03, 2021 12:10 am
>
> 
Ankhati wrote: ↑Fri Apr 02, 2021 12:44 am
I was trying to grab the black Widow classic costume, it is the one named predator in the files for some unknown reason.

But I see some textures are not ripped. for example the normal map for the lower body. There is a map for a damaged version, but the clean one I can not find..

Any help to get?

bwbottom.png
This? its called Resource_87010 and its 21.846kb

thanks man!!! 

No idea why it was missing, I ripped another folder and there is was... weird stuff..
## Post #259
- Username: Ankhati
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Nov 09, 2020 7:34 pm
- Post datetime: 2021-04-03T08:32:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Found the reason.

My noesis plug in give this error.
RuntimeError: Tried to set offset beyond buffer size. (22369688 > 22304204)

intruguing
## Post #260
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2021-04-15T10:16:58+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

What's inside the Ultra.tiger? How do you extract them?
The Dumper is not working. Maybe I'm using the wrong paths?

Please help with an example, thanks.
## Post #261
- Username: beto200478rere
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 31, 2020 12:33 pm
- Post datetime: 2021-04-17T14:19:36+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

please!! can someone help me by telling how do i unpack the tiger files??? First of all i decrypted bigfile.004.tiger, now i know that i need to unpack it. The problem is that when i open the batch file, it says to press any key to continue. I tried draging the file on the batch and it doesn t work. What do i do wrong??
## Post #262
- Username: kloruklass
- Rank: beginner
- Number of posts: 21
- Joined date: Wed Jan 27, 2021 4:30 am
- Post datetime: 2021-04-19T02:52:57+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Please, can someone make a simple example of how to extract the bigfile_ultra.000-0006?
## Post #263
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-04-19T13:44:59+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from beto200478rere ↑Sat Apr 17, 2021 10:19 pm at Sat Apr 17, 2021 10:19 pm
>
> 
please!! can someone help me by telling how do i unpack the tiger files??? First of all i decrypted bigfile.004.tiger, now i know that i need to unpack it. The problem is that when i open the batch file, it says to press any key to continue. I tried draging the file on the batch and it doesn t work. What do i do wrong??

The unpacker only unpacks bigfile.000 and bigfile.update1.000.000.
all the other are just parts for bigfile.000 or bigfile.update1.000.000.
Currently with the latest update of the game only bigfile.000 can be unpacked, as bigfile.update1.000.000 has been changed with the new contents they added.

Have you decrypt all of the bigfiles?
## Post #264
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-04-19T13:51:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from kloruklass ↑Mon Apr 19, 2021 10:52 am at Mon Apr 19, 2021 10:52 am
>
> 
Please, can someone make a simple example of how to extract the bigfile_ultra.000-0006?

Its just HD textures for the other bigfiles. If you have already decrypt it, it should automatically pull the textures from them when you use the DRM.Dumper on a DRM file
## Post #265
- Username: Beto20047845
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 27, 2020 8:54 am
- Post datetime: 2021-04-20T08:42:00+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Mon Apr 19, 2021 9:44 pm at Mon Apr 19, 2021 9:44 pm
>
> 
beto200478rere wrote: ↑Sat Apr 17, 2021 10:19 pm
please!! can someone help me by telling how do i unpack the tiger files??? First of all i decrypted bigfile.004.tiger, now i know that i need to unpack it. The problem is that when i open the batch file, it says to press any key to continue. I tried draging the file on the batch and it doesn t work. What do i do wrong??


The unpacker only unpacks bigfile.000 and bigfile.update1.000.000.
all the other are just parts for bigfile.000 or bigfile.update1.000.000.
Currently with the latest update of the game only bigfile.000 can be unpacked, as bigfile.update1.000.000 has been changed with the new contents they added.

Have you decrypt all of the bigfiles?

Nope, i'm still downloading the game, thank you so much, and i have some questions about the drm dumper. After i unpack the tiger files, i open de drm exe from file explorer? Or in command prompt
## Post #266
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-04-21T10:11:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Beto20047845 ↑Tue Apr 20, 2021 4:42 pm at Tue Apr 20, 2021 4:42 pm
>
> 
Vanillamilkshake wrote: ↑Mon Apr 19, 2021 9:44 pm
beto200478rere wrote: ↑Sat Apr 17, 2021 10:19 pm
please!! can someone help me by telling how do i unpack the tiger files??? First of all i decrypted bigfile.004.tiger, now i know that i need to unpack it. The problem is that when i open the batch file, it says to press any key to continue. I tried draging the file on the batch and it doesn t work. What do i do wrong??


The unpacker only unpacks bigfile.000 and bigfile.update1.000.000.
all the other are just parts for bigfile.000 or bigfile.update1.000.000.
Currently with the latest update of the game only bigfile.000 can be unpacked, as bigfile.update1.000.000 has been changed with the new contents they added.

Have you decrypt all of the bigfiles?


Nope, i'm still downloading the game, thank you so much, and i have some questions about the drm dumper. After i unpack the tiger files, i open de drm exe from file explorer? Or in command prompt
Through command
Just drag and drop DRMdumper into it and then the drm file, the folder where you want it dump into, and for the last, the folder for the decrypted files and then you are set.

>MA.DRMdumper <DRMfile>  <Destination folder> <Decrypted files folder>
## Post #267
- Username: Beto20047845
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Nov 27, 2020 8:54 am
- Post datetime: 2021-04-21T15:23:00+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Wed Apr 21, 2021 6:11 pm at Wed Apr 21, 2021 6:11 pm
>
> 
Beto20047845 wrote: ↑Tue Apr 20, 2021 4:42 pm
Vanillamilkshake wrote: ↑Mon Apr 19, 2021 9:44 pm


The unpacker only unpacks bigfile.000 and bigfile.update1.000.000.
all the other are just parts for bigfile.000 or bigfile.update1.000.000.
Currently with the latest update of the game only bigfile.000 can be unpacked, as bigfile.update1.000.000 has been changed with the new contents they added.

Have you decrypt all of the bigfiles?


Nope, i'm still downloading the game, thank you so much, and i have some questions about the drm dumper. After i unpack the tiger files, i open de drm exe from file explorer? Or in command prompt

Through command
Just drag and drop DRMdumper into it and then the drm file, the folder where you want it dump into, and for the last, the folder for the decrypted files and then you are set.

>MA.DRMdumper <DRMfile>  <Destination folder> <Decrypted files folder>
Ok, and by decrypted files folder, you mean the decripted tiger files from the first place? Or the unpacked ones?
## Post #268
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-04-22T14:02:09+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Beto20047845 ↑Wed Apr 21, 2021 11:23 pm at Wed Apr 21, 2021 11:23 pm
>
> 
Vanillamilkshake wrote: ↑Wed Apr 21, 2021 6:11 pm
Beto20047845 wrote: ↑Tue Apr 20, 2021 4:42 pm


Nope, i'm still downloading the game, thank you so much, and i have some questions about the drm dumper. After i unpack the tiger files, i open de drm exe from file explorer? Or in command prompt

Through command
Just drag and drop DRMdumper into it and then the drm file, the folder where you want it dump into, and for the last, the folder for the decrypted files and then you are set.

>MA.DRMdumper <DRMfile>  <Destination folder> <Decrypted files folder>

Ok, and by decrypted files folder, you mean the decripted tiger files from the first place? Or the unpacked ones?

Not the unpacked ones no. Its the folder where all the decrypted files appear after you use the TigerDecrypt tool. It should be label as "Decrypted" or something similiar
## Post #269
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2021-04-25T23:11:16+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks a lot to all the people who worked on those tools haven't touched the files in a while and with the upcoming mcu suits i was wondering if it will ever be possible to get them i catchup on some of the thread and from what i gather they changed the encryption so we can't get them ? am i correct ? will it ever be possible or release to the public ? 
Thanks a lot to all of you again
## Post #270
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-29T07:59:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Thu Apr 22, 2021 10:02 pm at Thu Apr 22, 2021 10:02 pm
>
> 
Beto20047845 wrote: ↑Wed Apr 21, 2021 11:23 pm
Vanillamilkshake wrote: ↑Wed Apr 21, 2021 6:11 pm

Through command
Just drag and drop DRMdumper into it and then the drm file, the folder where you want it dump into, and for the last, the folder for the decrypted files and then you are set.

>MA.DRMdumper <DRMfile>  <Destination folder> <Decrypted files folder>

Ok, and by decrypted files folder, you mean the decripted tiger files from the first place? Or the unpacked ones?


Not the unpacked ones no. Its the folder where all the decrypted files appear after you use the TigerDecrypt tool. It should be label as "Decrypted" or something similiar
Why there is error when i attempt extracting characters with skeleton? There is 2 *dtp file inside dtpdata folder and I copy 0ne of the the *dtp file and rename it to "skeleton.maskl".Then extract the model and encounted error.I sucess to convert texture.Hope you can tell me,thanks.
[1.jpg](https://xentaxbackup.github.io/file/19987_1.jpg)
## Post #271
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-29T08:01:09+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

[2.jpg](https://xentaxbackup.github.io/file/19988_2.jpg)
## Post #272
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2021-04-29T18:44:41+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Has anyone been able to extract Unworthy Thor? Or is it not possible right now. I've been looking through the game files and can't find it.
## Post #273
- Username: cjdung
- Rank: beginner
- Number of posts: 24
- Joined date: Mon Apr 27, 2020 9:46 am
- Post datetime: 2021-04-30T02:28:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from VincentXyooj ↑Fri Apr 30, 2021 2:44 am at Fri Apr 30, 2021 2:44 am
>
> 
Has anyone been able to extract Unworthy Thor? Or is it not possible right now. I've been looking through the game files and can't find it.

Hey,man.Do you know how to extract character with skeleton?Hope you can tell me,plz.
## Post #274
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-04T00:01:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from VincentXyooj ↑Fri Apr 30, 2021 2:44 am at Fri Apr 30, 2021 2:44 am
>
> 
Has anyone been able to extract Unworthy Thor? Or is it not possible right now. I've been looking through the game files and can't find it.

Not possible atm as its in bigfile.updates1 (I assume atleast).
## Post #275
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-04T00:22:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from cjdung ↑Thu Apr 29, 2021 3:59 pm at Thu Apr 29, 2021 3:59 pm
>
> 
Vanillamilkshake wrote: ↑Thu Apr 22, 2021 10:02 pm
Beto20047845 wrote: ↑Wed Apr 21, 2021 11:23 pm

Ok, and by decrypted files folder, you mean the decripted tiger files from the first place? Or the unpacked ones?


Not the unpacked ones no. Its the folder where all the decrypted files appear after you use the TigerDecrypt tool. It should be label as "Decrypted" or something similiar

Why there is error when i attempt extracting characters with skeleton? There is 2 *dtp file inside dtpdata folder and I copy 0ne of the the *dtp file and rename it to "skeleton.maskl".Then extract the model and encounted error.I sucess to convert texture.Hope you can tell me,thanks.
The size is too small to be the skeleton, are you sure you placed the skeleton_finder.py in the correct folder? Also sometimes you need to look for other similar models for the skeleton as it doesnt work all the time (in my experience atleast). Try look in other Ironman DRM, extract the model with the skeleton and then just save that skeleton and add to the Bleeding edge Iron man model, all Iron man models use the same skeleton.
## Post #276
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2021-05-05T13:12:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

someone know whats causing this issue for me? I can't look at half the textures  



Also thank you Vanilla for the response ^^
## Post #277
- Username: bmosalt
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Feb 19, 2021 5:46 pm
- Post datetime: 2021-05-07T06:08:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thanks to everyone for developing these tools. Just bought the game yesterday, still unpacking it etc.

> Reply from VincentXyooj ↑Wed May 05, 2021 9:12 pm at Wed May 05, 2021 9:12 pm
>
> 
someone know whats causing this issue for me? I can't look at half the textures

I had this issue when doing some initial tests. For me, it's because there are two python files in erik945's noesis folder. I just dumped both in the noesis plugin folder, and it caused the error. I deleted the older .py file and am not getting the error message anymore.
## Post #278
- Username: drumguy560
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 20, 2021 7:32 am
- Post datetime: 2021-05-20T20:00:20+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi!

Hopefully someone can help me -

I got the tiger files to decrypt successfully, but when I use the TIGER unpacker, It only unpacks a few audio files, and not much else. I decrypted all of the tiger files for the NA version of the game. Of note - I do not have "ultra" tiger files, nor languages other than english. Are these a necessity? I'm working hard to understand so I can extract the Iron Man "Endgame" skin
## Post #279
- Username: KurtCobain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 03, 2016 7:36 pm
- Post datetime: 2021-05-21T21:24:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from drumguy560 ↑Fri May 21, 2021 4:00 am at Fri May 21, 2021 4:00 am
>
> 
Hi!

Hopefully someone can help me -

I got the tiger files to decrypt successfully, but when I use the TIGER unpacker, It only unpacks a few audio files, and not much else. I decrypted all of the tiger files for the NA version of the game. Of note - I do not have "ultra" tiger files, nor languages other than english. Are these a necessity? I'm working hard to understand so I can extract the Iron Man "Endgame" skin

I really want this Iron Man model too, please anyone ?
## Post #280
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-23T22:40:45+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from drumguy560 ↑Fri May 21, 2021 4:00 am at Fri May 21, 2021 4:00 am
>
> 
Hi!

Hopefully someone can help me -

I got the tiger files to decrypt successfully, but when I use the TIGER unpacker, It only unpacks a few audio files, and not much else. I decrypted all of the tiger files for the NA version of the game. Of note - I do not have "ultra" tiger files, nor languages other than english. Are these a necessity? I'm working hard to understand so I can extract the Iron Man "Endgame" skin

Ultra files are important if you want to extract models with all the textures, you go to your steam libary and then right click on the game and choose "properties" then go to dlc and install High resolution texture pack. No the other langauges are not important, do you have problem getting models in general or just Endgame Iron man? Endgame skins are part of the newer content and needs an updated decryption tool.
## Post #281
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-23T22:46:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from KurtCobain ↑Sat May 22, 2021 5:24 am at Sat May 22, 2021 5:24 am
>
> 
drumguy560 wrote: ↑Fri May 21, 2021 4:00 am
Hi!

Hopefully someone can help me -

I got the tiger files to decrypt successfully, but when I use the TIGER unpacker, It only unpacks a few audio files, and not much else. I decrypted all of the tiger files for the NA version of the game. Of note - I do not have "ultra" tiger files, nor languages other than english. Are these a necessity? I'm working hard to understand so I can extract the Iron Man "Endgame" skin


I really want this Iron Man model too, please anyone ?

I believe the Endgame skins are in bigfile.update1 or update2 which needs an updated decrypter. For every update a new version of the decrypter has to be made, and giving the game is constantly updating, you might have to wait until the game is dead before we get a new version of the tool
## Post #282
- Username: drumguy560
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu May 20, 2021 7:32 am
- Post datetime: 2021-05-25T15:11:43+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thank you all for the clarification!

I'm hoping I can figure out a way to get these newer files to unpack. The endgame Iron Man skin is my priority, since I want to 3d print a lifesize statue using the game model as modeling reference.
## Post #283
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-27T11:54:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi there! Thanks to everyone that has helped the process

Im trying to extract the models from Marvel Avengers, I manage to decrypt the files but not unpack them, i get this error, none the less the FileNames.list files its in the location it shows, did I miss a step after decrypting it? could anyone help?

[https://ibb.co/R9nt05Z](https://ibb.co/R9nt05Z)
## Post #284
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-27T12:08:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from AzothRaven ↑Thu May 27, 2021 7:54 pm at Thu May 27, 2021 7:54 pm
>
> 
Hi there! Thanks to everyone that has helped the process

Im trying to extract the models from Marvel Avengers, I manage to decrypt the files but not unpack them, i get this error, none the less the FileNames.list files its in the location it shows, did I miss a step after decrypting it? could anyone help?

https://ibb.co/R9nt05Z
 Now I get this error after updating the list:

[https://ibb.co/JcrML1f](https://ibb.co/JcrML1f)
## Post #285
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-27T13:49:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from AzothRaven ↑Thu May 27, 2021 8:08 pm at Thu May 27, 2021 8:08 pm
>
> 
AzothRaven wrote: ↑Thu May 27, 2021 7:54 pm
Hi there! Thanks to everyone that has helped the process

Im trying to extract the models from Marvel Avengers, I manage to decrypt the files but not unpack them, i get this error, none the less the FileNames.list files its in the location it shows, did I miss a step after decrypting it? could anyone help?

https://ibb.co/R9nt05Z

 Now I get this error after updating the list:

https://ibb.co/JcrML1f

looks like you are using the unpacker meant for the Marvel's Avengers BETA, try use the full release version.
## Post #286
- Username: AzothRaven
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Mar 09, 2021 7:23 pm
- Post datetime: 2021-05-27T19:17:35+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Thu May 27, 2021 9:49 pm at Thu May 27, 2021 9:49 pm
>
> 
AzothRaven wrote: ↑Thu May 27, 2021 8:08 pm
AzothRaven wrote: ↑Thu May 27, 2021 7:54 pm
Hi there! Thanks to everyone that has helped the process

Im trying to extract the models from Marvel Avengers, I manage to decrypt the files but not unpack them, i get this error, none the less the FileNames.list files its in the location it shows, did I miss a step after decrypting it? could anyone help?

https://ibb.co/R9nt05Z

 Now I get this error after updating the list:

https://ibb.co/JcrML1f


looks like you are using the unpacker meant for the Marvel's Avengers BETA, try use the full release version.

Thank you for answering!!! now I get the error in which I only get audio files, any idea why?

[https://ibb.co/NW2vM4v](https://ibb.co/NW2vM4v)
[https://ibb.co/qBBm4ym](https://ibb.co/qBBm4ym)
## Post #287
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-05-28T00:34:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ok since there are so many pages and tools I figured I'd give a quick tutorial on how to do this. 

***Make sure you have the "ultra" files installed from the game settings in steam***

1st thing. Download the V3 on page 17
[viewtopic.php?f=16&t=22556&start=240](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=240)

Once you got that you should have a "Projects" folder with a FileNames.list in it. Size around 30-31MB.

Now place the "Projects" folder and the tool into your .tiger directory.

Drop each 001.tiger onto the correct .bat file.

Once finished onto the unpack part. For that download the tools on page 7
[viewtopic.php?f=16&t=22556&start=90](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=90)

Run the tool as mentioned for the unpacker and it will unpack all the files. About an hour or two.

Once unpacked you should have a folder called pcx64w inside of the default folder with all the files.

Sort files by size. Now open CMD drop in MA.DRM (NOT MAB.DRM) drop in the drm, then drop in your export folder, THEN!! drop in your decrypted .tiger folder. I called mine D. And unpacked folder U.

Once you got that you will see the meshes process.

Noesis script found here on page 8
[viewtopic.php?f=16&t=22556&start=105](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=105)

Place the script into your "scripts" folder in Noesis. I used  fmt_MarvelsAvengers2020_31

Now you can click on your mesh and all is good. 

For bones paste in the correct folder to DTPData path in the skeleton.py. Be sure to put it as C://User// with the double / or it will fail. 

Once you go that load the bones. Load the mesh. Export as .FBX

Travel to the "Textures" for that you will need this on page 8
[viewtopic.php?f=16&t=22556&start=105](https://forum.xentax.com/viewtopic.php?f=16&t=22556&start=105)

Place the script into your "scripts" folder in Noesis. Turn the MAPCD into .dds or .png.

Done

[](https://ibb.co/JjJH0SQ)
## Post #288
- Username: KurtCobain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 03, 2016 7:36 pm
- Post datetime: 2021-05-28T02:22:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Sharppy ↑Fri May 28, 2021 8:34 am at Fri May 28, 2021 8:34 am
>
> 
Ok since there are so many pages and tools I figured I'd give a quick tutorial on how to do this. 

1st thing. Download the V3 on page 17
viewtopic.php?f=16&t=22556&start=240

Once you got that you should have a "Projects" folder with a FileNames.list in it. Size around 30-31MB.

Now place the "Projects" folder and the tool into your .tiger directory.

Drop each 001.tiger onto the correct .bat file.

Once finished onto the unpack part. For that download the tools on page 7
viewtopic.php?f=16&t=22556&start=90

Run the tool as mentioned for the unpacker and it will unpack all the files. About an hour or two.

Once unpacked you should have a folder called pcx64w inside of the default folder with all the files.

Sort files by size. Now open CMD drop in MA.DRM (NOT MAB.DRM) drop in the drm, then drop in your export folder, THEN!! drop in your decrypted .tiger folder. I called mine D. And unpacked folder U.

Once you got that you will see the meshes process.

Noesis script found here on page 11
viewtopic.php?f=16&t=22556&start=150

Place the script into your "scripts" folder in Noesis. I used  fmt_MarvelsAvengers2020_31

Now you can click on your mesh and all is good. 

For bones paste in the correct folder to DTPData path in the skeleton.py. Be sure to put it as C://User// with the double / or it will fail. 

Once you go that load the bones. Load the mesh. Export as .FBX

Travel to the "Textures" for that you will need this on page 8
viewtopic.php?f=16&t=22556&start=105

Place the script into your "scripts" folder in Noesis. Turn the MAPCD into .dds or .png.

Done

Great tutorial!

The only problem is tha the 'unpack' is out of date, cause can't unpack update 1 and 2 new files and give a error

=(
## Post #289
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-05-28T02:48:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I was able to dump all the assets so far no issues. Slowly going down the .DRM's from largest to smallest.
[](https://ibb.co/HKSLbfQ)
## Post #290
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-28T18:56:11+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Sharppy ↑Fri May 28, 2021 8:34 am at Fri May 28, 2021 8:34 am
>
> 
Ok since there are so many pages and tools I figured I'd give a quick tutorial on how to do this. 

***Make sure you have the "ultra" files installed from the game settings in steam***

1st thing. Download the V3 on page 17
viewtopic.php?f=16&t=22556&start=240

Once you got that you should have a "Projects" folder with a FileNames.list in it. Size around 30-31MB.

Now place the "Projects" folder and the tool into your .tiger directory.

Drop each 001.tiger onto the correct .bat file.

Once finished onto the unpack part. For that download the tools on page 7
viewtopic.php?f=16&t=22556&start=90

Run the tool as mentioned for the unpacker and it will unpack all the files. About an hour or two.

Once unpacked you should have a folder called pcx64w inside of the default folder with all the files.

Sort files by size. Now open CMD drop in MA.DRM (NOT MAB.DRM) drop in the drm, then drop in your export folder, THEN!! drop in your decrypted .tiger folder. I called mine D. And unpacked folder U.

Once you got that you will see the meshes process.

Noesis script found here on page 8
viewtopic.php?f=16&t=22556&start=105

Place the script into your "scripts" folder in Noesis. I used  fmt_MarvelsAvengers2020_31

Now you can click on your mesh and all is good. 

For bones paste in the correct folder to DTPData path in the skeleton.py. Be sure to put it as C://User// with the double / or it will fail. 

Once you go that load the bones. Load the mesh. Export as .FBX

Travel to the "Textures" for that you will need this on page 8
viewtopic.php?f=16&t=22556&start=105

Place the script into your "scripts" folder in Noesis. Turn the MAPCD into .dds or .png.

Done

never got the bones to work in blender I suspect I needed a different 3D software to have any uses of it
## Post #291
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-05-28T18:59:59+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from KurtCobain ↑Fri May 28, 2021 10:22 am at Fri May 28, 2021 10:22 am
>
> 


Great tutorial!

The only problem is tha the 'unpack' is out of date, cause can't unpack update 1 and 2 new files and give a error

=(

The new files needs to get decrypted by an updated decrypter, so its just the base game for now
## Post #292
- Username: KurtCobain
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 03, 2016 7:36 pm
- Post datetime: 2021-06-02T00:10:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Vanillamilkshake ↑Sat May 29, 2021 2:59 am at Sat May 29, 2021 2:59 am
>
> 
KurtCobain wrote: ↑Fri May 28, 2021 10:22 am


Great tutorial!

The only problem is tha the 'unpack' is out of date, cause can't unpack update 1 and 2 new files and give a error

=(


The new files needs to get decrypted by an updated decrypter, so its just the base game for now

Understand. And is there anyone updating the decrypter?
## Post #293
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2021-06-03T15:50:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from KurtCobain ↑Wed Jun 02, 2021 8:10 am at Wed Jun 02, 2021 8:10 am
>
> 
Vanillamilkshake wrote: ↑Sat May 29, 2021 2:59 am
KurtCobain wrote: ↑Fri May 28, 2021 10:22 am


Great tutorial!

The only problem is tha the 'unpack' is out of date, cause can't unpack update 1 and 2 new files and give a error

=(


The new files needs to get decrypted by an updated decrypter, so its just the base game for now


Understand. And is there anyone updating the decrypter?

Nope the creator said he would wait till the game is dead so unless you know reverse engineering and can comprend how is code works there is no way and even that option would be really disrespectful of his work so I would just suggest you to wait sadly
## Post #294
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2021-06-09T07:58:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi, how i can get latests filenames, many .DRM without names ( hawkeye, kate bishop etc)
Ekey need your help, thanx
## Post #295
- Username: 8fold
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 18, 2020 3:46 am
- Post datetime: 2021-06-11T02:05:30+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

hi there! trying to extract some of the base models so it should be fine with the current tools since they're not from the updates. i tried extracting the hulk in specific, but getting a weird problem complaining about... magic?

```
(c) 2020 Ekey (h4x0r) / v0.0.3.1622

[CDRM INFO]: File: charactermesh__hulk__iconic01__body__body__default.drm

Unhandled Exception: System.Exception: [ERROR]: Invalid magic of DRM file!
   at MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   at MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   at MA.DRM.Dumper.Program.Main(String[] args)
```
## Post #296
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2021-06-11T07:13:37+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020


## Post #297
- Username: gnilrad
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Sep 09, 2020 4:48 am
- Post datetime: 2021-06-13T15:13:39+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hello, thanks to everyone in the forum who helped and supplied the tools to give us the opportunity to work with these files. Much appreciated, was just looking to see if I could get some assistance so I am aware the tools may be out of date by now and could not quite be in their best condition but I have tried to export a few different DRMs. I exported kamala_room.drm and everything there was perfectly fine but anything else I always get these weird meshes that are like these splashes and scrap metal chunks. The textures I get are like smoke and like effect textures I guess. Yet none of the actual assets. Anyone else have this issue?
[splash.png](https://xentaxbackup.github.io/file/20300_splash.png)
## Post #298
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-06-13T15:25:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Yes the assests are in other files check the main ones or the character_ ones.

If you need further help or want the models check out my discord removed
## Post #299
- Username: gnilrad
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Sep 09, 2020 4:48 am
- Post datetime: 2021-06-13T16:22:28+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Sharppy ↑Sun Jun 13, 2021 11:25 pm at Sun Jun 13, 2021 11:25 pm
>
> 
Yes the assests are in other files check the main ones or the character_ ones.

If you need further help or want the models check out my discord removed

Thank you! I appreciate the help, I found what I was looking for
## Post #300
- Username: sergeykarpuhin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 01, 2021 3:40 am
- Post datetime: 2021-06-30T20:02:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hey! Has anyone pulled out a classic Hawkeye suit. I have not figured out how to extract the files, can someone help me with the file?
[icm_fullxfull.359326581_80hu2ybvpzgoo00c0gg0.jpg](https://xentaxbackup.github.io/file/20391_icm_fullxfull.359326581_80hu2ybvpzgoo00c0gg0.jpg)
## Post #301
- Username: ARRadiation
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 18, 2018 5:11 am
- Post datetime: 2021-07-02T18:36:04+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does the game use shaders for colour variants?
Some of the textures don't look like the right colour so I would like to check whether it's the shaders or I just need to find the right texture combo.

Black widows Predator and Infiltrator Diffuse Maps are completely black for example unless turned to non colour in blender.
## Post #302
- Username: WinterCanary5
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 23, 2021 7:05 am
- Post datetime: 2021-07-09T00:03:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

download for the models???
## Post #303
- Username: Calborian
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 08, 2020 7:32 pm
- Post datetime: 2021-07-31T16:22:59+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I want to make a language patch for the game. But I don't know where to start. I need to open the bigfile_english.000.tiger file. However, I couldn't open the file. Can you help?
## Post #304
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2021-08-08T02:20:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Any news on when the updated files will be posted for the DLC outfits and the new characters? Or do we still have to wait ... It would be great if whatever happened could be resolved so we can have the new files...
## Post #305
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2021-08-08T11:23:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from VincentXyooj ↑Sun Aug 08, 2021 10:20 am at Sun Aug 08, 2021 10:20 am
>
> 
Any news on when the updated files will be posted for the DLC outfits and the new characters? Or do we still have to wait ... It would be great if whatever happened could be resolved so we can have the new files...

That would be really cool hopefully it can be done
## Post #306
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2021-08-12T10:13:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi, need help, cant find skeleton for Hulkbuster, try extract av1_cine_only_hulkbuster.drm and hulkbuster.drm but in DTPData no skeleton file
Try use Hulk/Abomination/Red Hulk skeletons dont work.
I would be grateful for any help.
Thanx.
## Post #307
- Username: jettkerker
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 25, 2021 6:54 am
- Post datetime: 2021-08-25T17:50:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Has anyone pulled the MCU skins from the game? Only for the main six, So Iron Man, Captain America, Hawkeye, Hulk, Thor, and Black Widows MCU models. Or maybe someone just has a link with all the models from the game. I need them for a project. Or if you have the patience to walk me through how to do it myself, which you probably dont as I am not that smart.
## Post #308
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2021-08-25T22:27:13+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from jettkerker ↑Thu Aug 26, 2021 1:50 am at Thu Aug 26, 2021 1:50 am
>
> 
Has anyone pulled the MCU skins from the game? Only for the main six, So Iron Man, Captain America, Hawkeye, Hulk, Thor, and Black Widows MCU models. Or maybe someone just has a link with all the models from the game. I need them for a project. Or if you have the patience to walk me through how to do it myself, which you probably dont as I am not that smart.

As of right now nobody has access to the newer skins, only stuff from the base game. We will not be able to do anything more until the person who made the script releases the update.
## Post #309
- Username: digitalutopia1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2017 10:43 am
- Post datetime: 2021-08-31T00:22:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Not sure what's going on here - followed all instructions, even made the paths equal to the example. Decrypted and Extracted, but I get this when trying to do the DRM Dumper. 

```
Marvel's Avengers (C)DRM Dumper
(c) 2020 Ekey (h4x0r) / v0.0.3.1622

[CDRM INFO]: File: hulk.drm
[DRM INFO]: Linked Resource: pr_gearperk_proc_rocket
[DRM INFO]: Linked Resource: pr_gearperk_proc_rocket_explosion
[DRM INFO]: Linked Resource: pr_gearperk_proc_rocket_stunaoe
[DRM INFO]: Linked Resource: anchoredcamera
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_020_low_health
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_070_enemy_killed
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_120_objective_complete
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_160_enemy_spawn
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_170_enemy_spawn_large
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_200_waiting_for_team_up
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_280_coop_destination
[DRM INFO]: Linked Resource: audio\dialogue sheets\systemic\banter\b110_ban_player_banter\b110_ban_310_emotes
[DRM INFO]: Linked Resource: autobreadrepulsor
[DRM INFO]: Linked Resource: av1_ah_artifact_loot
[DRM INFO]: Linked Resource: av1_hulkbuster_aoe_indicator_ring
[DRM INFO]: Linked Resource: av1_loot_healthdrop_parent
[DRM INFO]: Linked Resource: av1_loot_heroicdrop_parent
[DRM INFO]: Linked Resource: av1_loot_intrinsicdrop_parent
[DRM INFO]: Linked Resource: av1_skillspawnables_whirlwind
[DRM INFO]: Linked Resource: av1_social_context_trigger
[DRM INFO]: Linked Resource: camera_bone_rig
[DRM INFO]: Linked Resource: combatproxy
[DRM INFO]: Linked Resource: dialogue_interact
[DRM INFO]: Linked Resource: fingerofgod_beam
[DRM INFO]: Linked Resource: fingerofgod_enmp_companion
[DRM INFO]: Linked Resource: fx_collection_bufffx_brute_hulk
[DRM INFO]: Linked Resource: fx_fire_vertical
[DRM INFO]: Linked Resource: fx_mp_gameplay_circle_revive_indicator
[DRM INFO]: Linked Resource: fx_mp_gameplay_circle_teamfinisher_indicator
[DRM INFO]: Linked Resource: fx_pickup_downedplayer
[DRM INFO]: Linked Resource: fx_resource_feed
[DRM INFO]: Linked Resource: fx_thor_overcharge_strike
[DRM INFO]: Linked Resource: gearperk_hazard_cosmic
[DRM INFO]: Linked Resource: gearperk_hazard_gamma
[DRM INFO]: Linked Resource: gearperk_hazard_shock
[DRM INFO]: Linked Resource: hulk_rock_multimesh
[DRM INFO]: Linked Resource: marker_object
[DRM INFO]: Linked Resource: marker_object_artifact_invisibility
[DRM INFO]: Linked Resource: marker_object_hulk_hazard
[DRM INFO]: Linked Resource: marker_object_hulk_hazard_assaultheroic
[DRM INFO]: Linked Resource: marker_object_hulk_ragemode_hazard
[DRM INFO]: Linked Resource: marker_object_invisibletarget
[DRM INFO]: Linked Resource: triggervolume
[DRM INFO]: Linked Resource: wp_hulk_charge
[DRM INFO]: Linked Resource: wp_hulk_rock_thrower

[DUMPING]: => [DTPData] -> Resource_1908357.dtp

Unhandled Exception: System.Exception: [ERROR]: Invalid magic of DRM file!
   at MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   at MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   at MA.DRM.Dumper.Program.Main(String[] args)
```


The only thing I got any messages regarding previously, was during decrypting - and that's only because I didn't install all the languages. Anybody got any ideas? Thanks in advance!
## Post #310
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-09-05T11:21:42+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Only following archives are allowed: bigfile.000.tiger, bigfile.update1.000.000.tiger

any idea about how extract SomeThinks about update 2.000

thank's
## Post #311
- Username: Espio
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jan 08, 2007 7:47 am
- Post datetime: 2021-10-14T17:49:17+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Mon Mar 22, 2021 3:23 am at Mon Mar 22, 2021 3:23 am
>
> 


I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.
The new update seems to be the last one plus game now has been released on Windows Store as a final move. May it be considered dead now? Would love to see the updated decryptor
## Post #312
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-10-14T20:51:16+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

wait Guardians of the Galaxy use the same engine maybie new here
## Post #313
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2021-10-17T13:06:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Espio ↑Fri Oct 15, 2021 1:49 am at Fri Oct 15, 2021 1:49 am
>
> 
Gh0stBlade wrote: ↑Mon Mar 22, 2021 3:23 am


I managed to decrypt the update files. Don't expect a tool to drop until the game is dead since y'all can't behave.

The new update seems to be the last one plus game now has been released on Windows Store as a final move. May it be considered dead now? Would love to see the updated decryptor

Hopefully very soon been waiting a long time get some of the update skins
## Post #314
- Username: Belghen
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 25, 2021 6:44 am
- Post datetime: 2021-10-24T22:58:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi guys, someone has extracted the models of the exo of the aim?
## Post #315
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2021-10-25T06:00:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Damn, I kinda wish they atleast add She-hulk and Captain Marvel into game before they pull the plug. The game is going down really fast.
## Post #316
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-10-25T18:38:02+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from kilik ↑Fri Oct 15, 2021 4:51 am at Fri Oct 15, 2021 4:51 am
>
> 
wait Guardians of the Galaxy use the same engine maybie new here
No, this game using Dawn Engine (Deus Ex: Mankind Divided) 

> Reply from 
>
> wrote:According to TheGamer, the developers behind Marvel’s Guardians Of The Galaxy were asked about the game crossing over with Marvel’s Avengers in the form of a future DLC on Twitter, with user All-Father Designs being under the impression that both titles used the same game engine and assets. Eidos quickly revealed that this wasn’t the case, as Marvel’s Avengers was made in the Foundation game engine (used for Crystal Dynamics’ Tomb Raider games), while Marvel’s Guardians Of The Galaxy is being built in Dawn Engine. Eidos Montreal previously used this engine to work on 2016’s Deus Ex: Mankind Divided.
## Post #317
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2021-10-25T18:46:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Good too know Thank's for info
## Post #318
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2021-11-25T19:47:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Mon Sep 21, 2020 9:25 pm at Mon Sep 21, 2020 9:25 pm
>
> 
Ekey, I wanted to ask - it cannot be such that DRM Dumper will cut files (does not write them to the end).
I parse textures - two files of the similar size. But looks like the headers describe different resolutions (2 x ushort, offset 0x18), first - 1024x1024, second - 4096x4096 and different size of byte arrays(uInt, offset 0x08) first - 0x00 15 55 70, second 0x01 55 55 70 . This is strange.
Most likely, it overwrites the same file. This happens when the updated resource chunks extracted from the patch archives. Absolutely ugly file system 
Anyway, I can't check cuz bigfile.update1.xxx files are not decrypted properly ¯\_(ツ)_/¯
## Post #319
- Username: coltman1000
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 24, 2021 11:05 am
- Post datetime: 2021-12-24T03:19:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi all, does anyone know if it's possible to decrypt an older outfit? Came out the same time Kate Bishop was dropped and I saw someone extracted her, I was hoping to grab the Iron Knight outfit for a Skyrim Mod I'm working on. I'm willing to drop the 15 to grab the game, just don't really want to waste the money if I don't have to
## Post #320
- Username: animationgentleman
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Jan 09, 2022 6:54 pm
- Post datetime: 2022-01-09T11:02:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hey you all, the links for the downloads are dead....for drm dumper and tiger extractor..could anybody maybe repost?
## Post #321
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2022-01-17T22:33:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

So there isnt currently a way to convert Mul voice files into anything useable is there?
## Post #322
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2022-02-03T22:04:14+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from animationgentleman ↑Sun Jan 09, 2022 7:02 pm at Sun Jan 09, 2022 7:02 pm
>
> 
Hey you all, the links for the downloads are dead....for drm dumper and tiger extractor..could anybody maybe repost?
found the rar files on my USB


 TigerDecrypt_v1_3.rar
(7.71 KiB) Downloaded 79 times
## Post #323
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2022-02-03T22:05:14+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

And heres the dumper


 MA.DRM.Dumper_0.0.3.1622.rar
(38.74 KiB) Downloaded 135 times
## Post #324
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2022-02-04T04:27:01+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

forgot the unpacker

[https://mega.nz/file/5EMExLBR#E-jIm2H4A ... 4UWSIdlKHE](https://mega.nz/file/5EMExLBR#E-jIm2H4Ai_sBgzMV0eA0seiHI6xzycCO4UWSIdlKHE)
## Post #325
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2022-02-10T07:17:18+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now (allegedly)...

Shame the models are going to waste since nobody can get any of them lol
## Post #326
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2022-02-12T12:30:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from VincentXyooj ↑Thu Feb 10, 2022 3:17 pm at Thu Feb 10, 2022 3:17 pm
>
> 
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol

If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.
## Post #327
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2022-02-16T18:12:11+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Need help finding the base color for Kamala Khan's student outfit, top and pants.
I have been looking in every single variations of her student01.drm with no luck just this weird looking map of it, not sure how its supposed to be used.
[khancolor.png](https://xentaxbackup.github.io/file/21794_khancolor.png)
## Post #328
- Username: VincentXyooj
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Jan 14, 2018 2:26 pm
- Post datetime: 2022-02-17T15:12:29+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Feb 12, 2022 8:30 pm at Sat Feb 12, 2022 8:30 pm
>
> 
VincentXyooj wrote: ↑Thu Feb 10, 2022 3:17 pm
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol


If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.

You do know I didn't intend to insult anyone right? I was literally just curious about updates...

If I offended you sorry   , I am rarely on this forum at all. I just come back from time to time to check, from what I was told the game would not be getting anymore DLC... My mistake.
## Post #329
- Username: sergeyi438
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 25, 2022 10:33 pm
- Post datetime: 2022-07-27T13:19:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Sup, any news?
## Post #330
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-07-28T21:05:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

[https://twitter.com/SquareEnix/status/1 ... 5232071680](https://twitter.com/SquareEnix/status/1552760875232071680)

Ok, I think this is a good time to release the updated extract tool
## Post #331
- Username: sh4dy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 18, 2022 8:26 am
- Post datetime: 2022-07-29T16:57:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hy and thanks for all the work on this tool,

I tried to unpack all the meshes and it only worked with the update2 tiger packages.
With the update1 packages it says "Invalid TIGER file"
And with bigfile.000.tiger it crashed:



Capture d’écran 2022-07-29 185026.png (77.82 KiB) Viewed 642 times



So after that, i tried to dump some files from update2 and with every .drm it crashed :

[CDRM INFO]: File: hulk.drm

Exception non gérée : System.Exception: [ERROR]: Invalid magic of DRM file!
   à MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   à MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   à MA.DRM.Dumper.Program.Main(String[] args)

Is it normal ? or did i make something wrong ?
## Post #332
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2023-01-22T00:50:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Feb 12, 2022 8:30 pm at Sat Feb 12, 2022 8:30 pm
>
> 
VincentXyooj wrote: ↑Thu Feb 10, 2022 3:17 pm
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol


If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.

Hey!  Game's dead now.

[https://avengers.crystald.com/en-us/fin ... -avengers/](https://avengers.crystald.com/en-us/final-update-on-the-future-of-marvels-avengers/)

Perhaps this is a silly question since I've never modded this game and I literally just bought it...

If once were to have PS4 patch files from a recent version of the game, would it be hypothetically possible or plausible to extract the Spider-man DLC and get it to integrate in the PC version?
## Post #333
- Username: soratrash
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 14, 2022 4:09 am
- Post datetime: 2023-01-22T02:37:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from TopSecretOfficial ↑Sun Jan 22, 2023 8:50 am at Sun Jan 22, 2023 8:50 am
>
> 
Gh0stBlade wrote: ↑Sat Feb 12, 2022 8:30 pm
VincentXyooj wrote: ↑Thu Feb 10, 2022 3:17 pm
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol


If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.


Hey!  Game's dead now.

https://avengers.crystald.com/en-us/fin ... -avengers/

Perhaps this is a silly question since I've never modded this game and I literally just bought it...

If once were to have PS4 patch files from a recent version of the game, would it be hypothetically possible or plausible to extract the Spider-man DLC and get it to integrate in the PC version?
Hey, already tried doing this months ago when Spider-Man PC released. So far I hit a brick-wall and can't seem to decrypt the contents to export the models :/ so unless OP upholds their word, I don't think we'll get much soon
## Post #334
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2023-01-22T04:02:09+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Also, I find it hilarious that the /bin/ directory for the PC version is literally just the movie files with obfuscated names.

The files and folder names look like a bunch of gibberish, but they are just a 13-character shift cypher for the file names.

CerivbhfylBaGurNiratref_1080C_ybatre.bin becomes PreviouslyOnTheAvengers_1080P_longer.webm

The PC movie files are .bin files, while the PS4 ones are .webm
## Post #335
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2023-01-22T04:08:27+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from IcarusTwine ↑Wed Sep 02, 2020 6:41 am at Wed Sep 02, 2020 6:41 am
>
> 
Espio wrote: ↑Wed Sep 02, 2020 6:12 am
Any idea what's up with BIN files in bin folder? They have encrypted filenames and content as well.


the bin files are encrypted or at least compressed. the filenames are named using a Caesar Cipher + 13

I've some PS4 patch files in front of me, alongside the files for my Steam version.

The /bin/ directory is the /movies/ directory in the PS4 patch.  On the PS4 side, they are unencrypted, uncompressed .webm video files.  You're correct about the Casear Cipher + 13 to get the file names.  I'm not sure if anyone here has found a way to decrypt the .bin files, but maybe having the decrypted files from the PS4 version would help to build a tool?
## Post #336
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-01-25T02:10:04+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

[https://avengers.crystald.com/en-us/fin ... -avengers/](https://avengers.crystald.com/en-us/final-update-on-the-future-of-marvels-avengers/)

The game is finally dead, is there a chance to get the updated decrypter/unpacker or do we have to wait a few months still?
## Post #337
- Username: kayhotic
- Rank: n00b
- Number of posts: 16
- Joined date: Sat May 16, 2020 12:50 pm
- Post datetime: 2023-03-02T11:28:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Feb 12, 2022 8:30 pm at Sat Feb 12, 2022 8:30 pm
>
> 
VincentXyooj wrote: ↑Thu Feb 10, 2022 3:17 pm
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol


If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.

so you're not gonna uphold your word. no reason for you to be flying off the handle like this. it wasn't needed. they ceased development of the game. they CONFIRMED the game is over with
## Post #338
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-03-28T02:30:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does anyone have MCU models? I would pay for them
## Post #339
- Username: MonsterSmashing
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Apr 02, 2023 11:38 pm
- Post datetime: 2023-04-02T15:47:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hey Everyone. I made an account here solely to respond to this thread. I'm an animator who has been looking for an MCU Black Widow skin for over 3 years. I've had some commissioned, but nothing comes close to what I wanted. I'd be willing to throw a decent amount of money to anyone who can extract the 2012 Black Widow MCU Skin. XPS Format, Textures Included. FBX and OBJ are also acceptable.

I heard the Code is being held hostage here....Not sure what that is about. I hope we can put our differences aside here for the common good. This is a desperate plea on the behalf of me and many others, who would love to have access to these assets. 

If anyone wants to Private Message me, I invite you to do so. 

Otherwise, I pray these models are able to be extracted and shared. 

Wishing Everyone here the absolute best!
## Post #340
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2023-04-02T18:50:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Feb 12, 2022 8:30 pm at Sat Feb 12, 2022 8:30 pm
>
> 
If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.

Hello!

The final content update has been released on Steam, and there is one more planned hotfix coming out on Tuesday.  Many of us would be thrilled if you'd be able to do one final update of your tooling so we can continue to mod the game.  If you'd prefer, could you please share your source code so someone can investigate and update the code for the latest build of the game?

Thanks!
## Post #341
- Username: elasticheart
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Oct 09, 2021 3:52 am
- Post datetime: 2023-04-03T23:14:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hello, sorry to barge in here with a question while people are waiting for an update, but I couldn't figure it out myself.
I've been trying to unpack my files, and there seems to be a slight confusion on my part. I have only used TigerDecrypt to Decrypt bigfiles excluding bigfileupdates and such.(decrypting some bigfileupdate files as I'm writing this) Do I have to unpack everything for unpacker to work? I am also not sure where to put my Decryted .tiger files and the unpacker so I just put them all in the same folder (will post a screenshot below). Any help would be appreciated as I'm fairly new when it comes to messing with the game files and unpacking stuff! 



download1.png (58.97 KiB) Viewed 297 times
## Post #342
- Username: robertsharp1981
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-05T10:03:06+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Thread temporarily locked since people cannot behave.

Expect a new decrypter soon i suppose since the game is now dead.
## Post #343
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-05T12:32:03+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from kayhotic ↑Thu Mar 02, 2023 7:28 pm at Thu Mar 02, 2023 7:28 pm
>
> 
Gh0stBlade wrote: ↑Sat Feb 12, 2022 8:30 pm
VincentXyooj wrote: ↑Thu Feb 10, 2022 3:17 pm
So is there actually any update on how to get the newer files? I am quite curious :/ the game is pretty much dead by now... No new DLC will come out for it so .. 

Shame the models are going to waste since nobody can get any of them lol


If there was a way to get the newer files it would have been posted already. Stop bumping this thread with useless information I'm sick to death of people saying the game is dead when it's still in development! Claims like no new DLC are stupid when they have a huge ass roadmap. Don't like the wait? Do it yourself.

Can people STOP chatting shit when it comes to the game being dead or not in attempt to finess a newer build of the decrypter. We're not stupid which is clearly what you think and it's highly insulting behavior.

Until i see official information that the game is dead. I won't be updating the decrypter unfortunately as I said already. And had you have been reading you'd have known this.

I am not going to keep repeating myself beyond this point. Continuing like this may result in posts being treated as spam and thus will be subject to Moderation.


so you're not gonna uphold your word. no reason for you to be flying off the handle like this. it wasn't needed. they ceased development of the game. they CONFIRMED the game is over with

What are you even talking about? I'm not obliged to write an updated tool if I don't want to (you're acting very entitled here). If you also look at when the message you quoted was posted, you'd know it was ages ago when they were still updating the game so at the time it was not "dead".

> Reply from MonsterSmashing ↑Sun Apr 02, 2023 11:47 pm at Sun Apr 02, 2023 11:47 pm
>
> 
Hey Everyone. I made an account here solely to respond to this thread. I'm an animator who has been looking for an MCU Black Widow skin for over 3 years. I've had some commissioned, but nothing comes close to what I wanted. I'd be willing to throw a decent amount of money to anyone who can extract the 2012 Black Widow MCU Skin. XPS Format, Textures Included. FBX and OBJ are also acceptable.

I heard the Code is being held hostage here....Not sure what that is about. I hope we can put our differences aside here for the common good. This is a desperate plea on the behalf of me and many others, who would love to have access to these assets. 

If anyone wants to Private Message me, I invite you to do so. 

Otherwise, I pray these models are able to be extracted and shared. 

Wishing Everyone here the absolute best!

Nobody is holding anything hostage, don't be so silly. Just because the code was not released doesn't mean anything is being "held hostage". These claims you are making are based upon the basis of "nothing" to stir things up quite clearly.
## Post #344
- Username: GDL
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-07T17:44:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

The good news is the final version of the decrypter is here!

The bad news is that the root decryption keys for update2 were not located and unfortunately I don't have time to look for them as I'm busy with other things.

This decrypter will allow you to decrypt the files for all base game bigfile.000.tiger and all of bigfile.update1.000.tiger files NO update2. If you want update2 find the keys for me
## Post #345
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-08T07:30:41+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Gh0stBlade huge thanks for latest Decrypter, and for your wasted time.
## Post #346
- Username: Harry2390850
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-08T13:19:43+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Ok so I gave it another shot and I found the root key for update2. Subsequently the tool has been updated below. You should now be able to decrypt the entire game.
[TigerDecrypt_v2_8_2_0.zip](https://xentaxbackup.github.io/file/23639_TigerDecrypt_v2_8_2_0.zip)
## Post #347
- Username: Harry2390850
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 12, 2023 11:09 pm
- Post datetime: 2023-04-08T13:27:59+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Apr 08, 2023 9:19 pm at Sat Apr 08, 2023 9:19 pm
>
> 
Ok so I gave it another shot and I found the root key for update2. Subsequently the tool has been updated below. You should now be able to decrypt the entire game. Thanks for your hard work Gh0st! We appreciate it
## Post #348
- Username: Darthshockwave
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 03, 2023 4:26 am
- Post datetime: 2023-04-08T14:15:30+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Sat Apr 08, 2023 9:19 pm at Sat Apr 08, 2023 9:19 pm
>
> 
Ok so I gave it another shot and I found the root key for update2. Subsequently the tool has been updated below. You should now be able to decrypt the entire game.

Thank you for the tool.

Do we need the DRM Dumper? cuz the last time I tried to download it the link is broken.
And is there a tutorial somewhere?
## Post #349
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-08T16:43:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Darthshockwave ↑Sat Apr 08, 2023 10:15 pm at Sat Apr 08, 2023 10:15 pm
>
> 
Gh0stBlade wrote: ↑Sat Apr 08, 2023 9:19 pm
Ok so I gave it another shot and I found the root key for update2. Subsequently the tool has been updated below. You should now be able to decrypt the entire game.


Thank you for the tool.

Do we need the DRM Dumper? cuz the last time I tried to download it the link is broken.
And is there a tutorial somewhere?

Hi, see page 22
But need fresh list with names
## Post #350
- Username: Harry2390850
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 12, 2023 11:09 pm
- Post datetime: 2023-04-08T18:02:52+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Could anybody possibly help me understand how to get started with all of this? I have decrypted all of the files with the updated decrypter (these are all now in the "Decrypted" folder) but am unsure on what next. Do the contents of the unpacker (the Projects folder, .exe and .bat file) go inside of the main directory or do these go into the Decrypted folder? Thanks in advance, quite new to this! Just wanting to grab some models.

Edit: Okay I actually think I'm on the right lines. Next step is to just figure out the DRM Dumper
## Post #351
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-08T18:53:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Harry2390850 ↑Sun Apr 09, 2023 2:02 am at Sun Apr 09, 2023 2:02 am
>
> 
Could anybody possibly help me understand how to get started with all of this? I have decrypted all of the files with the updated decrypter (these are all now in the "Decrypted" folder) but am unsure on what next. Do the contents of the unpacker (the Projects folder, .exe and .bat file) go inside of the main directory or do these go into the Decrypted folder? Thanks in advance, quite new to this! Just wanting to grab some models.

Friend, half the thread with explaining how to extract, this question has been repeatedly raised here
## Post #352
- Username: Harry2390850
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 12, 2023 11:09 pm
- Post datetime: 2023-04-08T19:01:08+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Sun Apr 09, 2023 2:53 am at Sun Apr 09, 2023 2:53 am
>
> 
Harry2390850 wrote: ↑Sun Apr 09, 2023 2:02 am
Could anybody possibly help me understand how to get started with all of this? I have decrypted all of the files with the updated decrypter (these are all now in the "Decrypted" folder) but am unsure on what next. Do the contents of the unpacker (the Projects folder, .exe and .bat file) go inside of the main directory or do these go into the Decrypted folder? Thanks in advance, quite new to this! Just wanting to grab some models.


Friend, half the thread with explaining how to extract, this question has been repeatedly raised here Yeah I appreciate that. A lot of it was still confusing to me but I've figured it out now with some help from a friend, and some trial and error. Overwhelming for a newbie hahah
## Post #353
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-09T07:10:43+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi, extract .tiger uising MA.Tiger.Unpacker_0.0.3.1637 all fine.
Extracted 124318 .drm without names, @Ekey need your help, need updated ProjectList
Big thanx to Gh0stBlade, Ekey, Erik945
## Post #354
- Username: Darkman234
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Feb 02, 2014 10:14 am
- Post datetime: 2023-04-09T08:50:40+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Sun Apr 09, 2023 3:10 pm at Sun Apr 09, 2023 3:10 pm
>
> 
Hi, extract .tiger uising MA.Tiger.Unpacker_0.0.3.1637 all fine.
Extracted 124318 .drm without names, @Ekey need your help, need updated ProjectList
Big thanx to Gh0stBlade, Ekey, Erik945

Does this tool unpack the ultra files? Thank you.
## Post #355
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-09T19:17:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Darkman234 ↑Sun Apr 09, 2023 4:50 pm at Sun Apr 09, 2023 4:50 pm
>
> 
Crazy31139 wrote: ↑Sun Apr 09, 2023 3:10 pm
Hi, extract .tiger uising MA.Tiger.Unpacker_0.0.3.1637 all fine.
Extracted 124318 .drm without names, @Ekey need your help, need updated ProjectList
Big thanx to Gh0stBlade, Ekey, Erik945


Does this tool unpack the ultra files? Thank you.

Yes need decrypt too, Ultra .tigers need when you be extract .tiger and .drm
## Post #356
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-09T22:01:06+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does anyone know why when I go to view the .MAMESH file in Noesis I get "File could not be previewed"?
## Post #357
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-10T10:33:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from hola83796 ↑Mon Apr 10, 2023 6:01 am at Mon Apr 10, 2023 6:01 am
>
> 
Does anyone know why when I go to view the .MAMESH file in Noesis I get "File could not be previewed"?

Need more info, name .DRM?
## Post #358
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-10T13:54:07+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

so, I have run the decryption tool but it skips the ultra files. is there a good explanation of how to get the tool to decrypt them? I have searched the forum but there is nothing that I can make sense of. I have run the tool several different times and it always skips the ultra files. maybe I'm just not able to understand the explanation. i have tried by dragging the ultra files to the tool I have tried running in cmd and dragging the files and dropping them in there and it only seems to decrypt the other files and not those. Would someone be kind enough to help me out without referring me to earlier posts. Like I said I have looked through every page on this thread and nothing I have found has been helpful for those files. Thank you all for all the work you have put into making this possible for everyone. I can not imagine the headache you all have had if I'm getting frustrated over this small issue I'm having.
## Post #359
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-10T14:38:56+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from robertsharp1981 ↑Mon Apr 10, 2023 9:54 pm at Mon Apr 10, 2023 9:54 pm
>
> 
so, I have run the decryption tool but it skips the ultra files. is there a good explanation of how to get the tool to decrypt them? I have searched the forum but there is nothing that I can make sense of. I have run the tool several different times and it always skips the ultra files. maybe I'm just not able to understand the explanation. i have tried by dragging the ultra files to the tool I have tried running in cmd and dragging the files and dropping them in there and it only seems to decrypt the other files and not those. Would someone be kind enough to help me out without referring me to earlier posts. Like I said I have looked through every page on this thread and nothing I have found has been helpful for those files. Thank you all for all the work you have put into making this possible for everyone. I can not imagine the headache you all have had if I'm getting frustrated over this small issue I'm having.

Edit .bat, add needed lines with names .tigers
## Post #360
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-10T15:16:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Apr 10, 2023 10:38 pm at Mon Apr 10, 2023 10:38 pm
>
> 
robertsharp1981 wrote: ↑Mon Apr 10, 2023 9:54 pm
so, I have run the decryption tool but it skips the ultra files. is there a good explanation of how to get the tool to decrypt them? I have searched the forum but there is nothing that I can make sense of. I have run the tool several different times and it always skips the ultra files. maybe I'm just not able to understand the explanation. i have tried by dragging the ultra files to the tool I have tried running in cmd and dragging the files and dropping them in there and it only seems to decrypt the other files and not those. Would someone be kind enough to help me out without referring me to earlier posts. Like I said I have looked through every page on this thread and nothing I have found has been helpful for those files. Thank you all for all the work you have put into making this possible for everyone. I can not imagine the headache you all have had if I'm getting frustrated over this small issue I'm having.


Edit .bat, add needed lines with names .tigers

Thank you for taking the time to answer my question. As soon as I return home I will attempt to edit the file.
## Post #361
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-10T15:20:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Use this, replace to your TigerDecrypt_v2_8_2_0 folder
## Post #362
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-10T15:36:58+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Do I need to also edit the unpacker because when I ran it is seems to have skipped bigfile.001-bigfile.010? Also bigfileupdate1 seems to have not unpacked anything.
## Post #363
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-10T15:50:39+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from robertsharp1981 ↑Mon Apr 10, 2023 11:36 pm at Mon Apr 10, 2023 11:36 pm
>
> 
Do I need to also edit the unpacker because when I ran it is seems to have skipped bigfile.001-bigfile.010? Also bigfileupdate1 seems to have not unpacked anything.

Copy in folder TigerDecrypt_v2_8_2_0 all .tigers and run Decrypt.bat
All decrypted .tiger be in TigerDecrypt_v2_8_2_0\Decrypted
## Post #364
- Username: Harry2390850
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 12, 2023 11:09 pm
- Post datetime: 2023-04-10T19:21:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does anybody know where we should be looking for specific skins like some of the MCU skins, Superior Iron Man etc? Are they just jumbled all over the place or can they all be found in \pcx64-w?
## Post #365
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-10T19:39:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Harry2390850 ↑Tue Apr 11, 2023 3:21 am at Tue Apr 11, 2023 3:21 am
>
> 
Does anybody know where we should be looking for specific skins like some of the MCU skins, Superior Iron Man etc? Are they just jumbled all over the place or can they all be found in \pcx64-w?

I've been wondering the same thing. If I manage to locate any i will share the info.
## Post #366
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-11T01:01:51+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

One question, when I drag the bigfile.000.tiger file to the Dumper to unpack, are the .update and .ultra files also unpacked?
## Post #367
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-11T02:13:50+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Has anyone else gotten this issue? I got it after replacing the decrypter files with the ones crazy31139 posted earlier. I get no .mamesh files but I also couldnt get the decrypter to decrypt bigfileupdate2_ultra files either the others seem to decrypt but it skipped those.

[CDRM INFO]: File: charactermesh__thor__default__body__body__default.drm
[DUMPING]: => [Shader] -> Resource_292530.shader
[DUMPING]: => [Shader] -> Resource_292231.shader
[DUMPING]: => [Shader] -> Resource_292233.shader
[DUMPING]: => [Shader] -> Resource_292225.shader
[DUMPING]: => [Shader] -> Resource_292230.shader
[DUMPING]: => [Texture] -> Resource_145342.mapcd
[DUMPING]: => [Texture] -> Resource_145341.mapcd
[DUMPING]: => [Material] -> Resource_339549.material
[DUMPING]: => [Shader] -> Resource_73782.shader
[DUMPING]: => [Shader] -> Resource_73783.shader
[DUMPING]: => [Shader] -> Resource_73784.shader
[DUMPING]: => [Shader] -> Resource_292219.shader
[DUMPING]: => [Shader] -> Resource_292216.shader
[DUMPING]: => [Shader] -> Resource_292220.shader
[DUMPING]: => [Shader] -> Resource_292215.shader
[DUMPING]: => [Shader] -> Resource_292206.shader
[DUMPING]: => [Shader] -> Resource_292221.shader
[DUMPING]: => [Shader] -> Resource_292361.shader
[DUMPING]: => [Material] -> Resource_2836308.material
[DUMPING]: => [Shader] -> Resource_72244.shader
[DUMPING]: => [Shader] -> Resource_72245.shader
[DUMPING]: => [Shader] -> Resource_74190.shader
[DUMPING]: => [Shader] -> Resource_74191.shader
[DUMPING]: => [Shader] -> Resource_74192.shader
[DUMPING]: => [Shader] -> Resource_74193.shader
[DUMPING]: => [Material] -> Resource_2503676.material
[DUMPING]: => [Material] -> Resource_2330937.material

Unhandled Exception: System.Exception: [ERROR]: Invalid magic of DRM file!
   at MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   at MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   at MA.DRM.Dumper.Program.Main(String[] args)
## Post #368
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-04-11T07:00:47+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from robertsharp1981 ↑Tue Apr 11, 2023 10:13 am at Tue Apr 11, 2023 10:13 am
>
> 
Has anyone else gotten this issue? I got it after replacing the decrypter files with the ones crazy31139 posted earlier. I get no .mamesh files but I also couldnt get the decrypter to decrypt bigfileupdate2_ultra files either the others seem to decrypt but it skipped those.

Read better discription Ghostblade
viewtopic.php?p=191058#p191058
Update2 dont support, need keys
## Post #369
- Username: robertsharp1981
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-11T12:06:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Apr 10, 2023 11:20 pm at Mon Apr 10, 2023 11:20 pm
>
> 
Use this, replace to your TigerDecrypt_v2_8_2_0 folder
These bat files are wrong and do not adhear to the decryption algorithm internal mechanisms. I suggest changing them or i'll have to delete them to prevent people getting corrupt files.
## Post #370
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-11T14:15:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

How can I decrypt bigfile.update2.000_ultra.001.tiger files?
## Post #371
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-11T14:17:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Tue Apr 11, 2023 8:06 pm at Tue Apr 11, 2023 8:06 pm
>
> 
Crazy31139 wrote: ↑Mon Apr 10, 2023 11:20 pm
Use this, replace to your TigerDecrypt_v2_8_2_0 folder

These bat files are wrong and do not adhear to the decryption algorithm internal mechanisms. I suggest changing them or i'll have to delete them to prevent people getting corrupt files.

So I only have to run "Decrypt.bat" and the others don't?
## Post #372
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-11T14:36:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Is it normal that the size of the decrypted bigfile.000.tiger file is 7.99 GB?
## Post #373
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-11T14:42:36+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from hola83796 ↑Tue Apr 11, 2023 10:36 pm at Tue Apr 11, 2023 10:36 pm
>
> 
Is it normal that the size of the decrypted bigfile.000.tiger file is 7.99 GB?

Read previous usage instructions it's all the same for the new tool.

And the decrypted size should match the encrypted bigfile size.
## Post #374
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-11T15:26:57+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from hola83796 ↑Tue Apr 11, 2023 10:36 pm at Tue Apr 11, 2023 10:36 pm
>
> 
Is it normal that the size of the decrypted bigfile.000.tiger file is 7.99 GB?
I had the same thing happen, turns out I decrypted the file twice and rather than overwriting the first one it just added to it. When I did it i dropped bigfile.000 into Decrypt_bigfile.bat and once it finished I then Dropped "bigfile.update1.000.000" into Decrypt.bat and that's what caused it.
## Post #375
- Username: robertsharp1981
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-11T15:28:03+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from robertsharp1981 ↑Tue Apr 11, 2023 11:26 pm at Tue Apr 11, 2023 11:26 pm
>
> 
hola83796 wrote: ↑Tue Apr 11, 2023 10:36 pm
Is it normal that the size of the decrypted bigfile.000.tiger file is 7.99 GB?

I had the same thing happen, turns out I decrypted the file twice and rather than overwriting the first one it just added to it. When I did it i dropped bigfile.000 into Decrypt_bigfile.bat and once it finished I then Dropped "bigfile.update1.000.000" into Decrypt.bat and that's what caused it.

Since the tool only appends and does not delete previous files. It expects /Decrypted/ to be empty before usage.
## Post #376
- Username: Darthshockwave
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Apr 03, 2023 4:26 am
- Post datetime: 2023-04-11T16:20:46+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Tue Apr 11, 2023 8:06 pm at Tue Apr 11, 2023 8:06 pm
>
> 
Crazy31139 wrote: ↑Mon Apr 10, 2023 11:20 pm
Use this, replace to your TigerDecrypt_v2_8_2_0 folder

These bat files are wrong and do not adhear to the decryption algorithm internal mechanisms. I suggest changing them or i'll have to delete them to prevent people getting corrupt files.

hey @Gh0stBlade
How can I then decrypt the .Ultra files if I shouldn't use the files from Crazy31139?
## Post #377
- Username: robertsharp1981
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-11T17:09:39+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Darthshockwave ↑Wed Apr 12, 2023 12:20 am at Wed Apr 12, 2023 12:20 am
>
> 
Gh0stBlade wrote: ↑Tue Apr 11, 2023 8:06 pm
Crazy31139 wrote: ↑Mon Apr 10, 2023 11:20 pm
Use this, replace to your TigerDecrypt_v2_8_2_0 folder

These bat files are wrong and do not adhear to the decryption algorithm internal mechanisms. I suggest changing them or i'll have to delete them to prevent people getting corrupt files.


hey @Gh0stBlade
How can I then decrypt the .Ultra files if I shouldn't use the files from Crazy31139?

I don't have the space to download them or figure out which keys to use. But the tool should support them, you just have to pass the right arguments to the tool.
## Post #378
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-11T23:48:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Does anyone know why when I go to use the Dumper I get this error?



Marvel's Avengers (C)DRM Dumper
(c) 2020 Ekey (h4x0r) / v0.0.3.1622

[CDRM INFO]: File: charactermesh__hulkbuster__gameplay__body__body__default.drm
[DUMPING]: => [Material] -> Resource_3116871.material
[DUMPING]: => [Material] -> Resource_3282194.material
[DUMPING]: => [Texture] -> Resource_100336.mapcd
[DUMPING]: => [Texture] -> Resource_100041.mapcd
[DUMPING]: => [Texture] -> Resource_100735.mapcd
[DUMPING]: => [Texture] -> Resource_100736.mapcd
[DUMPING]: => [Texture] -> Resource_100481.mapcd
[DUMPING]: => [Texture] -> Resource_100060.mapcd
[DUMPING]: => [Texture] -> Resource_100734.mapcd
[DUMPING]: => [Texture] -> Resource_100645.mapcd
[DUMPING]: => [Texture] -> Resource_107893.mapcd
[DUMPING]: => [Shader] -> Resource_83189.shader
[DUMPING]: => [Shader] -> Resource_83190.shader
[DUMPING]: => [Shader] -> Resource_83191.shader
[DUMPING]: => [Shader] -> Resource_83192.shader
[DUMPING]: => [Shader] -> Resource_83201.shader
[DUMPING]: => [Shader] -> Resource_83202.shader
[DUMPING]: => [Shader] -> Resource_83203.shader
[DUMPING]: => [Shader] -> Resource_83204.shader
[DUMPING]: => [Shader] -> Resource_141590.shader
[DUMPING]: => [Shader] -> Resource_141591.shader
[DUMPING]: => [Shader] -> Resource_141592.shader
[DUMPING]: => [Shader] -> Resource_141593.shader
[DUMPING]: => [Material] -> Resource_3200182.material
[DUMPING]: => [Texture] -> Resource_106544.mapcd
[DUMPING]: => [Texture] -> Resource_106740.mapcd
[DUMPING]: => [Texture] -> Resource_106556.mapcd
[DUMPING]: => [Texture] -> Resource_106543.mapcd
[DUMPING]: => [Texture] -> Resource_106563.mapcd
[DUMPING]: => [Texture] -> Resource_106540.mapcd
[DUMPING]: => [Texture] -> Resource_106830.mapcd
[DUMPING]: => [Texture] -> Resource_106549.mapcd
[DUMPING]: => [Shader] -> Resource_83197.shader
[DUMPING]: => [Shader] -> Resource_83198.shader
[DUMPING]: => [Shader] -> Resource_83199.shader
[DUMPING]: => [Shader] -> Resource_83200.shader

Unhandled Exception: Ionic.Zlib.ZlibException: Bad state (unknown compression method (0x33))
   en Ionic.Zlib.InflateManager.Inflate(FlushType flush)
   en Ionic.Zlib.ZlibCodec.Inflate(FlushType flush)
   en Ionic.Zlib.ZlibBaseStream.Read(Byte[] buffer, Int32 offset, Int32 count)
   en Ionic.Zlib.ZlibStream.Read(Byte[] buffer, Int32 offset, Int32 count)
   en System.IO.Stream.InternalCopyTo(Stream destination, Int32 bufferSize)
   en System.IO.Stream.CopyTo(Stream destination)
   en MA.DRM.Dumper.Program.iDecompress(Byte[] pScrBuffer, Int32 dwZSize)
   en MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   en MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   en MA.DRM.Dumper.Program.Main(String[] args)
## Post #379
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-12T00:41:51+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from hola83796 ↑Wed Apr 12, 2023 7:48 am at Wed Apr 12, 2023 7:48 am
>
> 
Does anyone know why when I go to use the Dumper I get this error?



Marvel's Avengers (C)DRM Dumper
(c) 2020 Ekey (h4x0r) / v0.0.3.1622

[CDRM INFO]: File: charactermesh__hulkbuster__gameplay__body__body__default.drm
[DUMPING]: => [Material] -> Resource_3116871.material
[DUMPING]: => [Material] -> Resource_3282194.material
[DUMPING]: => [Texture] -> Resource_100336.mapcd
[DUMPING]: => [Texture] -> Resource_100041.mapcd
[DUMPING]: => [Texture] -> Resource_100735.mapcd
[DUMPING]: => [Texture] -> Resource_100736.mapcd
[DUMPING]: => [Texture] -> Resource_100481.mapcd
[DUMPING]: => [Texture] -> Resource_100060.mapcd
[DUMPING]: => [Texture] -> Resource_100734.mapcd
[DUMPING]: => [Texture] -> Resource_100645.mapcd
[DUMPING]: => [Texture] -> Resource_107893.mapcd
[DUMPING]: => [Shader] -> Resource_83189.shader
[DUMPING]: => [Shader] -> Resource_83190.shader
[DUMPING]: => [Shader] -> Resource_83191.shader
[DUMPING]: => [Shader] -> Resource_83192.shader
[DUMPING]: => [Shader] -> Resource_83201.shader
[DUMPING]: => [Shader] -> Resource_83202.shader
[DUMPING]: => [Shader] -> Resource_83203.shader
[DUMPING]: => [Shader] -> Resource_83204.shader
[DUMPING]: => [Shader] -> Resource_141590.shader
[DUMPING]: => [Shader] -> Resource_141591.shader
[DUMPING]: => [Shader] -> Resource_141592.shader
[DUMPING]: => [Shader] -> Resource_141593.shader
[DUMPING]: => [Material] -> Resource_3200182.material
[DUMPING]: => [Texture] -> Resource_106544.mapcd
[DUMPING]: => [Texture] -> Resource_106740.mapcd
[DUMPING]: => [Texture] -> Resource_106556.mapcd
[DUMPING]: => [Texture] -> Resource_106543.mapcd
[DUMPING]: => [Texture] -> Resource_106563.mapcd
[DUMPING]: => [Texture] -> Resource_106540.mapcd
[DUMPING]: => [Texture] -> Resource_106830.mapcd
[DUMPING]: => [Texture] -> Resource_106549.mapcd
[DUMPING]: => [Shader] -> Resource_83197.shader
[DUMPING]: => [Shader] -> Resource_83198.shader
[DUMPING]: => [Shader] -> Resource_83199.shader
[DUMPING]: => [Shader] -> Resource_83200.shader

Unhandled Exception: Ionic.Zlib.ZlibException: Bad state (unknown compression method (0x33))
   en Ionic.Zlib.InflateManager.Inflate(FlushType flush)
   en Ionic.Zlib.ZlibCodec.Inflate(FlushType flush)
   en Ionic.Zlib.ZlibBaseStream.Read(Byte[] buffer, Int32 offset, Int32 count)
   en Ionic.Zlib.ZlibStream.Read(Byte[] buffer, Int32 offset, Int32 count)
   en System.IO.Stream.InternalCopyTo(Stream destination, Int32 bufferSize)
   en System.IO.Stream.CopyTo(Stream destination)
   en MA.DRM.Dumper.Program.iDecompress(Byte[] pScrBuffer, Int32 dwZSize)
   en MA.DRM.Dumper.Program.iReadCDRM(Stream TDRMReader, UInt32 dwTigerOffset)
   en MA.DRM.Dumper.Program.iReadDRMFile(String m_DRMFile, String m_DstFolder, String m_TigerFolder, Boolean bDumpFiles)
   en MA.DRM.Dumper.Program.Main(String[] args)

If you downloaded the replacement files for the Decrypter and replaced them, they are not correct I was getting the same error with those edited decrypter files also. use the Decrypter that Gh0stBlade posted a few days ago. I changed mine back to the original and have had no more errors. you will need to delete all decrypted.tiger files and run the decrypter again. I would leave the Ultra files for later when someone has had time to figure out the fix.
## Post #380
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-12T16:04:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Has anyone managed to figure out the Ultra decryption?
## Post #381
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2023-04-12T16:14:31+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I do not know if this adhere to the decryption algorithm internal mechanisms, because as far as I can tell, it's not documented anywhere. This is what I tried, and it seems to have worked. At least I can decrypt the files without error. I present this here as a 'Use at your own risk' kinda thing.

Edit the Decrypt_BigfileUpdate1.bat as follows,
----------------------------------------------------------
TigerDecrypt bigfile.update1.000.000.tiger 0 1
TigerDecrypt bigfile.update1.000.001.tiger 1 1
TigerDecrypt bigfile.update1.000.002.tiger 2 1
TigerDecrypt bigfile.update1.000.003.tiger 3 1
TigerDecrypt bigfile.update1.000.004.tiger 4 1
TigerDecrypt bigfile.update1.000.005.tiger 5 1
TigerDecrypt bigfile.update1.000.006.tiger 6 1
TigerDecrypt bigfile.update1.000.007.tiger 7 1
TigerDecrypt bigfile.update1.000_ultra.000.tiger 8 1
TigerDecrypt bigfile.update1.000_ultra.001.tiger 9 1
TigerDecrypt bigfile.update1.000_ultra.002.tiger 10 1
TigerDecrypt bigfile.update1.000_ultra.003.tiger 11 1
TigerDecrypt bigfile.update1.000_ultra.004.tiger 12 1
----------------------------------------------------------

Basically following the number sequence along the file name. The same principle should work with all the other ultra files. 
Would be nice if ghostblade can confirm or deny if this 'adhere to the decryption algorithm internal mechanisms'.

Edit:
Tested on a random Black Widow outfit, and the mesh and textures are extracted properly. Seems this works. If I can get the confirmation that this is the correct sequence (Not sure why it's not just included in the first place, to be honest...) I'll post the .bat files I used.

Edit 2:
Slight correction, there are a bunch of .mapcd in the texture folder of the extracted model that Noesis is unable to open. Unknown if it is because the noesis plugin need updating, or something is wrong with the extraction process, or if that's normal. Attempting a batch conversion of the textures result in those textures that failed with a "RuntimeError: Tried to set offset beyond buffer size."
## Post #382
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-12T16:29:57+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Also if anyone happens to find Thor's Cosmic Herald outfit please tell me what folder to look in so far in the Unknown drms I have managed to find several Hulkbuster and Ironman Models but they all look like the Bleeding Edge and stealth suit maybe even the Mark IV but I'm not sure.
## Post #383
- Username: TopSecretOfficial
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Sep 17, 2011 3:45 pm
- Post datetime: 2023-04-13T18:04:29+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I'm wanting to see if we can get the Spiderman DLC to work with the PC version.  I don't know enough about these tools, but I'd like to learn, if anyone is willing to help.

I think there is a possibility for us to identify the files that contain Spider-Man assets (done), decrypt them (done), then repackage them into a new "patch" for the PC version.

Is anyone able to give their thoughts about the feasibility of this concept, as well as a description of what steps we might need to try?

I'm not certain of the order of operations of what comes after decryption.  Simply putting the decrypted files + a modified NFO in the PC game directory doesn't work (error saying the game can't open the file).  Also, I don't know when I would or should run DRM Dumper or Unpacker.

Here's what I see so far:
- The PC version has a different naming sequence than the PS4 patches.
- On PC, we have:
      bigfile.001.tiger through bigfile.010.tiger
      bigfile.update1.000.000.tiger through bigfile.update1.000.007.tiger
      bigfile.update2.000.000.tiger through bigfile.update2.000.003.tiger
      The NFO files, the ultra files, and the english files.
- For PS4 cumulative patch (as of patch 1.55), we have:
      bigfile.patch00.001.000.tiger through bigfile.patch00.002.000.tiger  (patch00, chunk 00, version "5" in NFO)
      bigfile.patch01.001.000.tiger                                                           (patch01, chunk 00, version "6" in NFO)
      bigfile.patch00.002.000.tiger through bigfile.patch00.002.012.tiger  (patch00, chunk 20, version "5" in NFO - Adds Hawkeye, Kate Bishop, Black Panther)
      bigfile.patch01.002.000.tiger through bigfile.patch01.002.003.tiger  (patch01, chunk 20, version "6" in NFO) - Adds Spider-man


Is there anyone who would be willing to help me figure this out or work with me to do it?
## Post #384
- Username: Astasis210
- Rank: n00b
- Number of posts: 10
- Joined date: Sat Jun 14, 2014 12:05 am
- Post datetime: 2023-04-13T19:59:09+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Harry2390850 ↑Tue Apr 11, 2023 3:21 am at Tue Apr 11, 2023 3:21 am
>
> 
Does anybody know where we should be looking for specific skins like some of the MCU skins, Superior Iron Man etc? Are they just jumbled all over the place or can they all be found in \pcx64-w?
Trying looking in the Unknown folder. I found Hulks skin in there vs his drm file. I was trying to find Hulkbuster but no go. It seems some of the skin are not directly int he very drm files. Or at the least the file extractor can't detect them.

Some meshes won't load in Noesis sadly. I can't seem to get Hulkbuster skin which I want the most.
## Post #385
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-13T22:31:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Astasis210 ↑Fri Apr 14, 2023 3:59 am at Fri Apr 14, 2023 3:59 am
>
> 
Harry2390850 wrote: ↑Tue Apr 11, 2023 3:21 am
Does anybody know where we should be looking for specific skins like some of the MCU skins, Superior Iron Man etc? Are they just jumbled all over the place or can they all be found in \pcx64-w?

Trying looking in the Unknown folder. I found Hulks skin in there vs his drm file. I was trying to find Hulkbuster but no go. It seems some of the skin are not directly int he very drm files. Or at the least the file extractor can't detect them.

Some meshes won't load in Noesis sadly. I can't seem to get Hulkbuster skin which I want the most.

I found a bunch of hulkbuster skins in the unknown folder there are for sure a bunch of Ironman and Hulkbuster models in th 7 and 8 KB drm files.So far I have dumped several random files from each size group and that is where I found them. I dont remember exactly where but if I find them again I will update this reply
**UPDATE** here is one of the DRM files that has a Hulkbuster in it and there are several more in the Unknown folder throughout the 7 KB drm files 000EA05359497B31.drm
## Post #386
- Username: sergeyi438
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 25, 2022 10:33 pm
- Post datetime: 2023-04-14T06:00:25+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Is there anyone who located superior Iron Man model?
## Post #387
- Username: Harry2390850
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 12, 2023 11:09 pm
- Post datetime: 2023-04-14T10:32:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from robertsharp1981 ↑Fri Apr 14, 2023 6:31 am at Fri Apr 14, 2023 6:31 am
>
> 
Astasis210 wrote: ↑Fri Apr 14, 2023 3:59 am
Harry2390850 wrote: ↑Tue Apr 11, 2023 3:21 am
Does anybody know where we should be looking for specific skins like some of the MCU skins, Superior Iron Man etc? Are they just jumbled all over the place or can they all be found in \pcx64-w?

Trying looking in the Unknown folder. I found Hulks skin in there vs his drm file. I was trying to find Hulkbuster but no go. It seems some of the skin are not directly int he very drm files. Or at the least the file extractor can't detect them.

Some meshes won't load in Noesis sadly. I can't seem to get Hulkbuster skin which I want the most.


I found a bunch of hulkbuster skins in the unknown folder there are for sure a bunch of Ironman and Hulkbuster models in th 7 and 8 KB drm files.So far I have dumped several random files from each size group and that is where I found them. I dont remember exactly where but if I find them again I will update this reply
**UPDATE** here is one of the DRM files that has a Hulkbuster in it and there are several more in the Unknown folder throughout the 7 KB drm files 000EA05359497B31.drm 

Which ones are you looking in? I suppose I should be looking in Update1 and Update2 for anything relatively new. Is there a way to find out which update versions correlate with either the update1 or update2 files so we can attempt to narrow down the search?
## Post #388
- Username: Crazy31139
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2023-04-14T11:13:10+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

I made a discord server here: [https://discord.gg/DjfJxbPg](https://discord.gg/DjfJxbPg) for Modding Foundation Engine based games if anyone is interested in joining. You should join if you require additional support as such
## Post #389
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-14T15:39:50+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Shinteo ↑Thu Apr 13, 2023 12:14 am at Thu Apr 13, 2023 12:14 am
>
> 
I do not know if this adhere to the decryption algorithm internal mechanisms, because as far as I can tell, it's not documented anywhere. This is what I tried, and it seems to have worked. At least I can decrypt the files without error. I present this here as a 'Use at your own risk' kinda thing.

Edit the Decrypt_BigfileUpdate1.bat as follows,
----------------------------------------------------------
TigerDecrypt bigfile.update1.000.000.tiger 0 1
TigerDecrypt bigfile.update1.000.001.tiger 1 1
TigerDecrypt bigfile.update1.000.002.tiger 2 1
TigerDecrypt bigfile.update1.000.003.tiger 3 1
TigerDecrypt bigfile.update1.000.004.tiger 4 1
TigerDecrypt bigfile.update1.000.005.tiger 5 1
TigerDecrypt bigfile.update1.000.006.tiger 6 1
TigerDecrypt bigfile.update1.000.007.tiger 7 1
TigerDecrypt bigfile.update1.000_ultra.000.tiger 8 1
TigerDecrypt bigfile.update1.000_ultra.001.tiger 9 1
TigerDecrypt bigfile.update1.000_ultra.002.tiger 10 1
TigerDecrypt bigfile.update1.000_ultra.003.tiger 11 1
TigerDecrypt bigfile.update1.000_ultra.004.tiger 12 1
----------------------------------------------------------

Basically following the number sequence along the file name. The same principle should work with all the other ultra files. 
Would be nice if ghostblade can confirm or deny if this 'adhere to the decryption algorithm internal mechanisms'.

Edit:
Tested on a random Black Widow outfit, and the mesh and textures are extracted properly. Seems this works. If I can get the confirmation that this is the correct sequence (Not sure why it's not just included in the first place, to be honest...) I'll post the .bat files I used.

Edit 2:
Slight correction, there are a bunch of .mapcd in the texture folder of the extracted model that Noesis is unable to open. Unknown if it is because the noesis plugin need updating, or something is wrong with the extraction process, or if that's normal. Attempting a batch conversion of the textures result in those textures that failed with a "RuntimeError: Tried to set offset beyond buffer size."

Hi! Have you kept trying it? Has everything worked?
## Post #390
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-14T15:55:26+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Harry2390850 ↑Fri Apr 14, 2023 6:32 pm at Fri Apr 14, 2023 6:32 pm
>
> 
robertsharp1981 wrote: ↑Fri Apr 14, 2023 6:31 am
Astasis210 wrote: ↑Fri Apr 14, 2023 3:59 am

Trying looking in the Unknown folder. I found Hulks skin in there vs his drm file. I was trying to find Hulkbuster but no go. It seems some of the skin are not directly int he very drm files. Or at the least the file extractor can't detect them.

Some meshes won't load in Noesis sadly. I can't seem to get Hulkbuster skin which I want the most.


I found a bunch of hulkbuster skins in the unknown folder there are for sure a bunch of Ironman and Hulkbuster models in th 7 and 8 KB drm files.So far I have dumped several random files from each size group and that is where I found them. I dont remember exactly where but if I find them again I will update this reply
**UPDATE** here is one of the DRM files that has a Hulkbuster in it and there are several more in the Unknown folder throughout the 7 KB drm files 000EA05359497B31.drm
 

Which ones are you looking in? I suppose I should be looking in Update1 and Update2 for anything relatively new. Is there a way to find out which update versions correlate with either the update1 or update2 files so we can attempt to narrow down the search?
as far as I can tell, they are just random. I don't have any idea what folders are part of what update. I just sorted them into folders based on file size and started going through them one by one. I based my search on the size of the charactermesh files in the pcx64-w folder I looked at the File size for one of them before it was dumped to see how many KB the file was and then dump the files of the same size from the unknown folder. so far my search has been pretty good I have found Hawkeyes Age of Ultron top but I still havent found the rest of the body for him. I have also found about 7 or 8 Ironman suits and 1 thor outfit also still need to locate the body for him as well.
## Post #391
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-14T16:19:51+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from sergeyi438 ↑Fri Apr 14, 2023 2:00 pm at Fri Apr 14, 2023 2:00 pm
>
> 
Is there anyone who located superior Iron Man model?

I have not located it yet, but I have located about 7 or 8 other Ironman suits. If I locate it I will let you know.
## Post #392
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2023-04-14T18:46:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

anyone that could share the filename list file? most of the files here were hosted in zippyshare and they went out of business recently
## Post #393
- Username: hola83796
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jan 02, 2023 12:38 pm
- Post datetime: 2023-04-14T21:47:34+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi! I have a question, if at the time of unpacking I drag the file "bigfile.000.tiger" to Dumper, will update1 and update2 also be unpacked? Or do I have to drag them too?
## Post #394
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2023-04-15T00:56:55+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hi all!
How do I resolve a problem with models that do not appear in Noesis?
Do you have to open in ModelResearcher and manually search for vertices, faces, UV (where they are)?

[](https://ibb.co/3BKmgv9)
## Post #395
- Username: Shinteo
- Rank: beginner
- Number of posts: 28
- Joined date: Wed Apr 06, 2016 11:26 am
- Post datetime: 2023-04-18T04:02:44+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from hola83796 ↑Fri Apr 14, 2023 11:39 pm at Fri Apr 14, 2023 11:39 pm
>
> 
Shinteo wrote: ↑Thu Apr 13, 2023 12:14 am
I do not know if this adhere to the decryption algorithm internal mechanisms, because as far as I can tell, it's not documented anywhere. This is what I tried, and it seems to have worked. At least I can decrypt the files without error. I present this here as a 'Use at your own risk' kinda thing.

Edit the Decrypt_BigfileUpdate1.bat as follows,
----------------------------------------------------------
TigerDecrypt bigfile.update1.000.000.tiger 0 1
TigerDecrypt bigfile.update1.000.001.tiger 1 1
TigerDecrypt bigfile.update1.000.002.tiger 2 1
TigerDecrypt bigfile.update1.000.003.tiger 3 1
TigerDecrypt bigfile.update1.000.004.tiger 4 1
TigerDecrypt bigfile.update1.000.005.tiger 5 1
TigerDecrypt bigfile.update1.000.006.tiger 6 1
TigerDecrypt bigfile.update1.000.007.tiger 7 1
TigerDecrypt bigfile.update1.000_ultra.000.tiger 8 1
TigerDecrypt bigfile.update1.000_ultra.001.tiger 9 1
TigerDecrypt bigfile.update1.000_ultra.002.tiger 10 1
TigerDecrypt bigfile.update1.000_ultra.003.tiger 11 1
TigerDecrypt bigfile.update1.000_ultra.004.tiger 12 1
----------------------------------------------------------

Basically following the number sequence along the file name. The same principle should work with all the other ultra files. 
Would be nice if ghostblade can confirm or deny if this 'adhere to the decryption algorithm internal mechanisms'.

Edit:
Tested on a random Black Widow outfit, and the mesh and textures are extracted properly. Seems this works. If I can get the confirmation that this is the correct sequence (Not sure why it's not just included in the first place, to be honest...) I'll post the .bat files I used.

Edit 2:
Slight correction, there are a bunch of .mapcd in the texture folder of the extracted model that Noesis is unable to open. Unknown if it is because the noesis plugin need updating, or something is wrong with the extraction process, or if that's normal. Attempting a batch conversion of the textures result in those textures that failed with a "RuntimeError: Tried to set offset beyond buffer size."


Hi! Have you kept trying it? Has everything worked?

I am waiting for the updated name list, as would have to re-run the entire thing again after that anyway, so I did not test further.
## Post #396
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-04-21T20:42:22+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from sergeyi438 ↑Fri Apr 14, 2023 2:00 pm at Fri Apr 14, 2023 2:00 pm
>
> 
Is there anyone who located superior Iron Man model?

B1367C83B97F17B5.drm Superior Ironman or one of its variants.
## Post #397
- Username: PluckyParadise
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 01, 2023 6:55 am
- Post datetime: 2023-04-30T23:00:37+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Gh0stBlade ↑Fri Apr 14, 2023 7:13 pm at Fri Apr 14, 2023 7:13 pm
>
> 
I made a discord server here: https://discord.gg/DjfJxbPg for Modding Foundation Engine based games if anyone is interested in joining. You should join if you require additional support as such

the discord invite link expired. is there another way to join? another invite? thank you.
## Post #398
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-05-01T04:47:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from PluckyParadise ↑Mon May 01, 2023 7:00 am at Mon May 01, 2023 7:00 am
>
> 
Gh0stBlade wrote: ↑Fri Apr 14, 2023 7:13 pm
I made a discord server here: https://discord.gg/DjfJxbPg for Modding Foundation Engine based games if anyone is interested in joining. You should join if you require additional support as such 


the discord invite link expired. is there another way to join? another invite? thank you.
[https://discord.gg/BMMk6tNC](https://discord.gg/BMMk6tNC)
## Post #399
- Username: DHedge
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Sep 14, 2022 3:46 pm
- Post datetime: 2023-05-07T09:25:05+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Hello, did anybody manage to rip the Classic IronMan Armour?
[obraz_2023-05-07_112451254.png](https://xentaxbackup.github.io/file/23781_obraz_2023-05-07_112451254.png)
## Post #400
- Username: robertsharp1981
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jul 20, 2022 6:44 am
- Post datetime: 2023-05-18T15:41:51+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from DHedge ↑Sun May 07, 2023 5:25 pm at Sun May 07, 2023 5:25 pm
>
> 
Hello, did anybody manage to rip the Classic IronMan Armour? 
Yes
## Post #401
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-06-19T07:41:33+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon May 01, 2023 12:47 pm at Mon May 01, 2023 12:47 pm
>
> 
PluckyParadise wrote: ↑Mon May 01, 2023 7:00 am
Gh0stBlade wrote: ↑Fri Apr 14, 2023 7:13 pm
I made a discord server here: https://discord.gg/DjfJxbPg for Modding Foundation Engine based games if anyone is interested in joining. You should join if you require additional support as such 


the discord invite link expired. is there another way to join? another invite? thank you.

https://discord.gg/BMMk6tNC
can I have updated link? thank you
## Post #402
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2023-06-19T15:06:24+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Tosyk ↑Mon Jun 19, 2023 3:41 pm at Mon Jun 19, 2023 3:41 pm
>
> 
Crazy31139 wrote: ↑Mon May 01, 2023 12:47 pm
PluckyParadise wrote: ↑Mon May 01, 2023 7:00 am


the discord invite link expired. is there another way to join? another invite? thank you.

https://discord.gg/BMMk6tNC

can I have updated link? thank you
[https://discord.gg/am25mx9w](https://discord.gg/am25mx9w)
## Post #403
- Username: scientist223311
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 20, 2023 3:53 pm
- Post datetime: 2023-06-20T07:54:18+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

They absolutely will.

Marvel’s Avengers may have received a critical drubbing, but this game was never intended to be a one-and-done title - it's a live service game, and will receive additional content and updates for years.

The issue at hand is how long it will take. The additional content (specifically, extra characters) was meant to start arriving shortly after the game launched, but has been delayed so that the developers can prioritise essential fixes to the game.

This… sucks. No two ways about it. The game simply wasn't ready to be released, and the entire ‘roadmap’ of additional content has had be pushed back while they fix the game that itself should have been delayed to get right BEFORE it came out.

But regardless, they're not just going to throw up their hands and declare the game done - too much money has been invested in it and there's too much money yet to be made on it. This game will stick around, and hopefully down the line it'll be the improved experience we all hoped it would be.

pikashow
ppsspp emulator
## Post #404
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-06-25T09:17:23+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

hi, I appreciate for the hard work you guys did for the game! 
I have few questions tho:

1. most of the unknown files when dumped says:

```
A duplicate file name exists, or the file cannot be found.
```


I have no duplicate file names anywhere, so I wonder what that might be? I also feed DRM Dumper with any file from __Unknown folder even the ones without extension, but there are most of the files have no extension if not all.

2. I can't convert any texture from the dumped DRMs. Anytime I open MAPCD file with noesis I get this in the log:

```
Detected file type: Unknown
```

or

```
Detected file type: Unknown
```

or

```
Detected file type: Unknown
```


and so on.

for decrypting TIGER files with TigerDecrypt_v2_8_2_0 I used this batch:

```
TigerDecrypt bigfile.update1.000_ultra.001.tiger 1 1
TigerDecrypt bigfile.update1.000_ultra.002.tiger 2 1
TigerDecrypt bigfile.update1.000_ultra.003.tiger 3 1
TigerDecrypt bigfile.update1.000_ultra.004.tiger 4 1
```

and it gives me weird files if you look into HEX but their magic is 


but if I use this batch:

```
TigerDecrypt bigfile.update1.000_ultra.001.tiger 9 1
TigerDecrypt bigfile.update1.000_ultra.002.tiger 10 1
TigerDecrypt bigfile.update1.000_ultra.003.tiger 11 1
TigerDecrypt bigfile.update1.000_ultra.004.tiger 12 1
```

I get this kind of files:


which is not really far from encrypted one:


So, I can open models and skeletons are also seem fine but how to convert textures?
## Post #405
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2023-06-25T20:04:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from erik945 ↑Thu Sep 10, 2020 7:38 pm at Thu Sep 10, 2020 7:38 pm
>
> 
Noesis script for meshes and textures (beta version)

hi, can you update the script for the files such as
[https://drive.google.com/file/d/1z060ZD ... sp=sharing](https://drive.google.com/file/d/1z060ZDPNQJ7ZGj1XvXT2Y3NmOAnDVjSF/view?usp=sharing)
## Post #406
- Username: Andrei867
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jul 20, 2020 5:12 pm
- Post datetime: 2023-07-27T21:16:48+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Anyone got a working invite for the discord?
## Post #407
- Username: MichaelThe3rd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2023 10:38 pm
- Post datetime: 2023-08-25T09:48:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

anyone got the drm opening zip and projectlist?
## Post #408
- Username: MichaelThe3rd
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 22, 2023 10:38 pm
- Post datetime: 2023-08-25T09:56:53+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from bertonberton ↑Sat Aug 15, 2020 2:23 pm at Sat Aug 15, 2020 2:23 pm
>
> 
Hello everyone! 
Happy to create my first topic here because im really enjoy community for the long time. 
This topic is about Marvel's Avengers game and extracting files from it.
I have pre-ordered this game and have access to the files because beta open on weekends 14-16th August.
All i know right now: 
1.Game use same engine as Rise of Tomb Rider
2.Files comes in .tiger format (I have x6 files 4GB each)
3.Old tools from Rise of Tomb rider (dumper, unpacker) and any other like NinjaRipper doesn't work and have no results.

If anyone can help me with understanding how to unpack this files or maybe interested in this way feel free ask anything! 
I can upload any gamefiles from beta launch and maybe we will find workable solution  
Thank you for attention and keep well!

UPD: Open Beta 21-23 August

UPD1: Big thanks to Gh0stBlade and Ekey for decryption tool and Tiger Unpacker/DRM Dumper

UPD2: Release! Big thanks to Gh0stBlade for updated release decryption tool! Links in post updated. Kindly waiting for Ekey Unpacker/Dumper update!

Decryption tool : You can download it here

Tiger Unpacker : Tiger Unpacker - 0.0.2.33474
DOWNLOAD
Code: Select all[Usage]
    MAB.Tiger.Unpacker <m_TigerFile> <m_UnpackFolder>

    m_TigerFile - Source of Tiger file
    m_UnpackFolder - Destination directory

[Examples]
    MAB.Tiger.Unpacker D:\MAB\Decrypted\bigfile.000.tiger D:\Unpacked\bigfile


Note: m_TigerFile - Only following archives are allowed bigfile.000.tiger or bigfile.update1.000.000.tiger, orher files are parts.

DRM Dumper : DRM Dumper - 0.0.2.39914
DOWNLOAD
Code: Select all[Usage]
    MAB.DRM.Dumper <m_DRMFile> <m_UnpackFolder> <m_TigerFolder>

    m_DRMFile - Source of DRM file
    m_UnpackFolder - Destination directory
    m_TigerFolder - Folder with decrypted TIGER files
	
[Examples]
    MAB.DRM.Dumper
    m_DRMFile -> D:\MAB\bigfile\default\pcx64-w\hulk.drm
    m_UnpackFolder -> D:\Unpacked\DRM
    m_TigerFolder -> D:\MAB\Decrypted
	
    MAB.DRM.Dumper D:\Unpacked\bigfile\default\pcx64-w\hulk.drm D:\Unpacked\DRM D:\MAB\Decrypted

We still need .mamesh and .mapcd file format parser because all data (mesh and textures) inside this 2 fileformats .

alr so
I found an alt for the tiger unpacker
need links for drm and the projectlist one from later
## Post #409
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2023-09-09T05:23:54+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

been awhile since I posted here, but now the game is in its final month before it gets taken away from the store page, did anyone managed to decrypt the lastest update and get all the skins/models?
## Post #410
- Username: Vanillamilkshake
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Feb 20, 2021 11:43 pm
- Post datetime: 2023-09-10T23:10:21+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

Nvm found the new decrypt tool, the old unpacker and dumper should work fine right?
## Post #411
- Username: nahey42210
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 08, 2023 2:42 am
- Post datetime: 2023-09-24T21:37:38+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

> Reply from Crazy31139 ↑Mon Jun 19, 2023 11:06 pm at Mon Jun 19, 2023 11:06 pm
>
> 
Tosyk wrote: ↑Mon Jun 19, 2023 3:41 pm
Crazy31139 wrote: ↑Mon May 01, 2023 12:47 pm


https://discord.gg/BMMk6tNC

can I have updated link? thank you

https://discord.gg/am25mx9w

Can you send me the discord link?
## Post #412
- Username: HearthVader
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 07, 2016 3:32 pm
- Post datetime: 2023-09-30T03:47:52+00:00
- Post Title: Re: Marvel's Avengers Game Release [Steam] 2020

We gonna see mods now that the game is being delisted tomorrow? Also does anyone have a working discord link for the server? All the ones i see are invalid.
