## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-03-16T18:43:22+00:00
- Post Title: 3D map models from Black Box Need for Speed games

[https://mega.nz/file/hXg3BSbb#k3IzVidxp ... cz4RmXvRXk](https://mega.nz/file/hXg3BSbb#k3IzVidxpBFXPII9Q7GCpIiLFC53aryGncz4RmXvRXk)
[https://mega.nz/file/gHg2EbwD#l-WVecxkN ... p2UsO4K_rY](https://mega.nz/file/gHg2EbwD#l-WVecxkNKkojbvqJkIJga5gCdjNBoyy9p2UsO4K_rY)

I'm viewing Need for Speed Underground map models with hex2obj:
[https://i.ibb.co/9c2fFj6/bandicam-2022- ... 34-411.jpg](https://i.ibb.co/9c2fFj6/bandicam-2022-03-16-11-27-34-411.jpg)
[https://i.ibb.co/DbBktRB/bandicam-2022- ... 14-463.jpg](https://i.ibb.co/DbBktRB/bandicam-2022-03-16-11-32-14-463.jpg)

I tried NFSUGeomBin2Ase and Car Toolkit, but it won't support them.
According to STREAML1RA.bun, there are models named TRSCDE_TERRAINA_NRND_CHOP11.
I would have to batch convert them all from STREAML1RA.bun if possible.
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-27T22:51:38+00:00
- Post Title: 3D map models from Black Box Need for Speed games

> Reply from mrmaller1905 ↑Thu Mar 17, 2022 2:43 am at Thu Mar 17, 2022 2:43 am
>
> 
I'm viewing Need for Speed Underground map models with hex2obj
i made plugin for  opens *.geo.bin   

(so far without a mesh position and have uv only if stride over 24)
example 'STREAML1RA.BUN.000154.geo.bin' has 1322 meshes and they are all centered.
[fmt_geo.zip](https://xentaxbackup.github.io/file/22033_fmt_geo.zip)
## Post #3
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2022-03-28T20:31:59+00:00
- Post Title: 3D map models from Black Box Need for Speed games

Not sure what is exactly you are trying to achieve, but, there’s already a tool, in alpha stage at the moment called AssetDumper 2.0.0, this tool happens to support FULL maps as you see in-game, the 7 supported games from Black Box era are:


Need for Speed Underground
Need for Speed Underground 2
Need for Speed Most wanted
Need for Speed Carbon
Need for Speed ProStreet
Need for Speed Undercover
Need for Speed World


As far as I know the developer/reverser heyitsleo never posted about this tool here or if he even has an account here for that matter, so I think it’s important this tool to be mentioned here, so others won’t start this all over from scratch, as over the years many have made various attempts to reverse these games, yet not many fully succeeded, we all know the apparently abandoned project by nfsu360 MapToolKit, but this new version of the tool AssetDumper has support for mentioned games above, extraction/conversion of the map, textures included, keep in mind, no map editing or any of the sort or reimport or repacking, etc.
More info about it:
This is initial version 1, where it would export the assets as individual objects at 0,0,0 no sections as seen in-game or transforms.
[https://nfsmods.xyz/mod/684](https://nfsmods.xyz/mod/684)
And here is his GitHub, as for version 2.0.0 that supports full coordinates of the object sections as you see in game not sure if an official link exist, but I will ask and post here if there is.
[https://github.com/LeoCodes21](https://github.com/LeoCodes21)
## Post #4
- Username: Erik The Born
- Rank: n00b
- Number of posts: 14
- Joined date: Wed Jun 10, 2015 11:01 pm
- Post datetime: 2023-09-11T17:33:43+00:00
- Post Title: 3D map models from Black Box Need for Speed games

Im interested in that 2.0.0 version, where can I get it? I do not see it on that github.
## Post #5
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2023-09-11T21:56:13+00:00
- Post Title: 3D map models from Black Box Need for Speed games

> Reply from Erik The Born ↑Tue Sep 12, 2023 1:33 am at Tue Sep 12, 2023 1:33 am
>
> 
Im interested in that 2.0.0 version, where can I get it? I do not see it on that github.
If there where a public link of some sort, i would have posted it myself long ago, i did contacted him long time ago, i never got an answer, you might want to go to his GitHub and contact him yourself, maybe you'll have more luck, never knows.
