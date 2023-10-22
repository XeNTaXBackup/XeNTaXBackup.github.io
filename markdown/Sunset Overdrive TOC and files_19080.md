## Post #1
- Username: redspike474
- Rank: n00b
- Number of posts: 12
- Joined date: Fri Feb 05, 2016 2:24 am
- Post datetime: 2018-11-17T01:16:25+00:00
- Post Title: Sunset Overdrive TOC and files

Hello, does anyone have any information on how to unpack sunset overdrive (pc) ?
I can upload an example file if its helpful.

See image attached for what the archive folder looks like.
[sunset.PNG](https://xentaxbackup.github.io/file/15186_sunset.PNG)
## Post #2
- Username: emoose
- Rank: beginner
- Number of posts: 26
- Joined date: Fri Sep 11, 2015 4:06 am
- Post datetime: 2018-11-24T05:51:57+00:00
- Post Title: Sunset Overdrive TOC and files

It looks like the layout.csv file contains all the filenames/offsets/archive names etc, here's a sample of the contents:

```
"levels\sunset_city\area_1_lit_windows_hor_lgt_night.zone",win/0xc4/0xc421ad02.built,0,308583,zone,built,,Yes,Yes,0x00000000c421ad02,0,g00s000,0
"levels\sunset_city\area_1_lit_windows_lgt_horrornight.zone",win/0xa7/0xa7691319.built,0,309085,zone,built,,Yes,Yes,0x00000000a7691319,0,g00s000,308583
"levels\sunset_city\aud_mus_global.zone",win/0xa4/0xa4472d1e.built,0,110219,zone,built,,Yes,Yes,0x00000000a4472d1e,0,g00s000,617668
"levels\sunset_city\aud_sfx_global.zone",win/0xf0/0xf04c0c30.built,0,2516,zone,built,,Yes,Yes,0x00000000f04c0c30,0,g00s000,727887
"levels\sunset_city\aud_verb_global.zone",win/0x2c/0x2c612226.built,0,1496,zone,built,,Yes,Yes,0x000000002c612226,0,g00s000,730403
"levels\sunset_city\fx_global_zone.zone",win/0x86/0x86a62664.built,0,7419,zone,built,,Yes,Yes,0x0000000086a62664,0,g00s000,731899
"levels\sunset_city\global_dynamic_encounters.zone",win/0x8e/0x8edc1a61.built,0,58349,zone,built,,Yes,Yes,0x000000008edc1a61,0,g00s000,739318
"levels\sunset_city\global_gameplay.zone",win/0x6f/0x6f8f9225.built,0,17904,zone,built,,Yes,Yes,0x000000006f8f9225,0,g00s000,797667
"levels\sunset_city\riot_squad_global.zone",win/0x76/0x76334899.built,0,134,zone,built,,Yes,Yes,0x0000000076334899,0,g00s000,815571
"levels\sunset_city\global_nav.zone",win/0x2c/0x2ce51f8a.built,0,24081757,zone,built,,No,Yes,0x000000002ce51f8a,0,g00s000,815705

```


Going by the field names on the first line, it looks like the File Size / Archive File / Segment Offset are the important fields for extracting.
For "levels\sunset_city\fx_global_zone.zone" that is:

```
Archive File: g00s000
Segment Offset: 731899

```


Looking at offset 731899 in the g00s000 archive it does seem like the start of a file, with a 1TAD header etc... and going forward by "Size" bytes (so 731899 + 7419) puts us at the start of another 1TAD header, so it seems like the offsets/sizes in that CSV are correct.

Is it possible for QuickBMS to work with these files? Not sure if it has support for anything like CSV...
I would upload the layout.csv file but it's pretty much just exactly what I quoted above, but if anyone needs it just let me know.

Also about that 1TAD stuff, it seems that's the games format for compiled assets etc, every file I checked seemed to use that 1TAD header anyway (even savegames)
No idea how hard extracting useful data from those files will be though, I guess we'll find out once we get an extractor working.
## Post #3
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2019-12-25T17:14:00+00:00
- Post Title: Sunset Overdrive TOC and files

Found any extractor for the files? Looking for the files of the weapons.
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2019-12-26T00:40:58+00:00
- Post Title: Sunset Overdrive TOC and files

QuickBMS can read CSV-format lines of text.  If you can upload the full layout file, I can have a look at it.
## Post #5
- Username: theismarius
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Jan 14, 2017 8:11 am
- Post datetime: 2020-04-05T09:46:03+00:00
- Post Title: Sunset Overdrive TOC and files

Here I post de layout.csv file

[https://mega.nz/file/A0VQGQrQ#TNsRoSv59 ... OMKdUQUns8](https://mega.nz/file/A0VQGQrQ#TNsRoSv59cP5nsnBlnK6UCbwiT7VQcVF2OMKdUQUns8)

thanks for the help
## Post #6
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-13T21:03:20+00:00
- Post Title: Sunset Overdrive TOC and files

[](https://ibb.co/Wv9Mj26)
[](https://ibb.co/K5ZCdWD)

Drop .csv on tool to extract files. Then use max script to load meshes. Textures export with Noesis. 

Credit to revetix for the tool update.  
[ratchet_and_clank_ps4_csv.zip](https://xentaxbackup.github.io/file/21763_ratchet_and_clank_ps4_csv.zip)
## Post #7
- Username: Slappy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jul 17, 2012 5:28 pm
- Post datetime: 2022-02-27T06:08:42+00:00
- Post Title: Sunset Overdrive TOC and files

How to pack files back into the archive?
## Post #8
- Username: Admixon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 29, 2017 4:20 am
- Post datetime: 2022-03-29T22:08:30+00:00
- Post Title: Sunset Overdrive TOC and files

> Reply from Sharppy ↑Mon Feb 14, 2022 5:03 am at Mon Feb 14, 2022 5:03 am
>
> 
I'm new here and I was confused. Thanks for the tool but it doesn't work (not when I downloaded it at first). I did some research and found you need the whole ratched and clank tool to use this exe (I found it on the discord server). You also need a plugin for Noesis to open texture files and you also need to edit this plugin to fix the texture problem. You also need GR2reader plugin to open .model files or 3ds max plugin (you can also find it on the server) but I got some problems extracting the models: Noesis can't extract them because while extracting it says "Format not supported" and the 3ds max plugin is for 3ds max only so... I simply don't have 3ds max. Would it be possible to make such a plugin for Blender?
## Post #9
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-03-30T23:05:56+00:00
- Post Title: Sunset Overdrive TOC and files

We used a batch script for 3DS Max to convert all these. It was the only way. And yes I did  not include the original files to the tool I noticed. Sorry about that. 

For this to work change this part of the script to where Index.txt is located. Inside of Index.txt use a program like Everything to scan through folders to get the names/locations. Paste this info into Index.txt 
ex:
C:\Users\xxx\Desktop\New\clank.model
change to:
"C:\\Users\\xxx\\Desktop\\New\\clank.model"
Credits to Adam 
[Batcher.zip](https://xentaxbackup.github.io/file/22047_Batcher.zip)
