## Post #1
- Username: PeterZ
- Rank: veteran
- Number of posts: 95
- Joined date: Sat Sep 17, 2016 11:07 am
- Post datetime: 2021-11-07T15:30:07+00:00
- Post Title: Ironsight .msh model Noesis script

Based on zaramot's maxscript
[viewtopic.php?f=16&t=17148&hilit=ironsight#p134670](https://forum.xentax.com/viewtopic.php?f=16&t=17148&hilit=ironsight#p134670)

I fix some issues ( uv, bone transform ) and rewrite this script for Noesis.


Unpack .wpg with d3v1l401's IronSightExtractor [https://github.com/d3v1l401/IronSightExtractor](https://github.com/d3v1l401/IronSightExtractor) or QuickBMS script [https://zenhax.com/viewtopic.php?f=9&t=5050#p27077](https://zenhax.com/viewtopic.php?f=9&t=5050#p27077)

For animation, check this topic:[viewtopic.php?f=16&t=25770](https://forum.xentax.com/viewtopic.php?f=16&t=25770)

```
v1.1 (2022.9.6) - Remove "addRootBone" feature. Use first bone instead.
v1.2 (2023.7.13) - Add ability to process Lods info

```

[fmt_Ironsight_msh_v1_2.zip](https://xentaxbackup.github.io/file/24066_fmt_Ironsight_msh_v1_2.zip)
## Post #2
- Username: stateeq
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 18, 2022 6:21 pm
- Post datetime: 2023-03-27T15:20:42+00:00
- Post Title: Ironsight .msh model Noesis script

Hey,

sorry for bumping such an old thread,
had some issues with the script (trying to export 2 models, one is foliage the other is some random antenna), it seems that wShift can have a value of 7 as well for foliage, and i have no idea what the issue with the antenna is

would be great if someone could take a look

[antenna01_v01](https://drive.google.com/file/d/1aqZOgLf0U0t9lTd85Cz--w6BLLsWNxYs/view?usp=share_link)


 grass02_v01_vege.zip
(32.65 KiB) Downloaded 16 times



EDIT:  seems that the grass_vege mesh is like a combination of multiple LODs or something, can't quite figure it out, so decided to use the same mesh without the _vege suffix (grass02_v01.msh, works fine). As to antennas not opening, there's something weird happening with material and mesh count offsets in those files, managed to fix it in a very hacky way by modifying the script, now all of the antennas open properly, [UPDATED SCRIPT DOWNLOAD LINK](https://drive.google.com/file/d/1f6SbONh_PKSK6Q6txNNlTpTsNlKMwR6E/view?usp=share_link)
