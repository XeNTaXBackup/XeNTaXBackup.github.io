## Post #1
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2023-09-26T11:11:21+00:00
- Post Title: Yet another NPK - Dragonheir

New game called Dragonheir just dropped. This one appears to not be NetEase, but it does use an .NPK resource archive.
Id code is "UnityFS" instead of "NXPK". Looking at the header also reveals a mention of CAB, however the regular tools won't load it, so that's probably not it.

The following tools were tried but do not work for this file:
Unity Editor
NXPK quickbms script: [http://aluigi.altervista.org/bms/nxpk.bms](http://aluigi.altervista.org/bms/nxpk.bms)
NPK LAUnpacker: [viewtopic.php?p=178322&hilit=npk#p178322](https://forum.xentax.com/viewtopic.php?p=178322&hilit=npk#p178322)
another NPK thread: [viewtopic.php?p=155648&hilit=npk#p155648](https://forum.xentax.com/viewtopic.php?p=155648&hilit=npk#p155648)
but flag does not seem to apply.

6GB File, too large to upload. Header screenshot attached. If this turns out to be something very weird/exotic, it might not be worth it.

edit: smaller npk file found, uploading that one instead
[https://mega.nz/file/4iJ2Ua7a#gOhgl1Zpr ... 2WOWOihBKI](https://mega.nz/file/4iJ2Ua7a#gOhgl1Zprh1KfXkWTqofzGadwpHshMLD42WOWOihBKI)
[DragonheirNPK.png](https://xentaxbackup.github.io/file/24386_DragonheirNPK.png)
## Post #2
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2023-09-28T19:56:55+00:00
- Post Title: Yet another NPK - Dragonheir

I'll quote the answer i gave in [this thread](https://forum.xentax.com/viewtopic.php?p=172369#p172369) and attach the file again.

> Reply from Allanoon ↑Thu Mar 18, 2021 12:51 am at Thu Mar 18, 2021 12:51 am
>
> 
Get VGMToolbox. Download the attached rar, extract the .xml into plugin-Advanced Cutter of VGMtoolbox folder.
Open VGM -> Misc tool -> Extraction tools -> Generic -> Advanced file cutter -> Preset "PKG CH Game" -> Load, drop file, it'll extract all the UnityFS header files. 
Res_0 also have lots of unity files inside.

You can use this ^ method for some other games too.

OT Note: Strange for netease to use unity, they usually go with their home engine.

Extranote: 
You can use asset ripper to extract everything BUT, there's some problem with the way the mesh is attached to the unity prefab so you won't be able to visualize the models (you'll have the mesh file/.obj tou). This problem is present even if you try to export them as fbx with Asset Studio.
[PKG CH game.rar](https://xentaxbackup.github.io/file/24389_PKG CH game.rar)
## Post #3
- Username: Jaw
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Jan 12, 2017 4:00 am
- Post datetime: 2023-09-30T16:50:42+00:00
- Post Title: Yet another NPK - Dragonheir

This worked, thank you very much!
