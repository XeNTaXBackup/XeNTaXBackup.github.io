## Post #1
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-13T15:55:10+00:00
- Post Title: Demon's Souls (2020)

In case if someone wants to investigate meshes format in PS5 remake of Demon's Souls or compare with the original, it's pretty straightforward aside from skeleton related things. Sample is based on c1030_vanguard_mesh_lod0.cmsh from [those samples](https://mega.nz/file/fY4wwIDK#JyHGTwZwB_6na0uoP_Y-0UN2q6pJgjZp3PPsMSuUGO8).

After initial header and materials list it will be section with various mesh parameters, it usually starts with int64 = 7 value, as it's count for parameters blocks - and also it will be base offset for the block offsets. Blocks headers are combined together and placed before them - with prefix, identifier, some flags and two int64 values - offset to block (starting from base offset) and block size. Most blocks are usually separated by 8 0xFF bytes, but that's already considered in offsets/sizes. After all blocks there is block with indices and after it there is skeleton related info.




Clipboard01.jpg (239.68 KiB) Viewed 400 times
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-10-21T21:03:49+00:00
- Post Title: Demon's Souls (2020)

Interesting... Are there tools for unpack PS5 PKG's in the public?
## Post #3
- Username: Crazy31139
- Rank: veteran
- Number of posts: 121
- Joined date: Sat Dec 03, 2016 12:53 am
- Post datetime: 2022-10-22T11:56:55+00:00
- Post Title: Demon's Souls (2020)

Hi, people only can make fully dumped backup of disc game, right now. Can't find any info on PS5 FPKG
## Post #4
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2022-10-22T17:03:29+00:00
- Post Title: Demon's Souls (2020)

@Ekey: Only dumped files are avalilable for now (with eboot still encrypted). Since retail PKGs were mostly not extractable even on PS4 because of encryption, they were dumped and converted to FPKG - at the moment there is no such thing for PS5, because it would be useless anyway and dumped files are shared as-is. Interesting part is that apparently on PS5 native games doesn't use engine-level containers (compressed packages) and all files are already extracted, not sure if it's because of SSD or internal file system / memory management.
## Post #5
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2022-10-22T22:58:08+00:00
- Post Title: Demon's Souls (2020)

> Reply from Spiritovod ↑Sun Oct 23, 2022 1:03 am at Sun Oct 23, 2022 1:03 am
>
> 
@Ekey: Only dumped files are avalilable for now (with eboot still encrypted). Since retail PKGs were mostly not extractable even on PS4 because of encryption, they were dumped and converted to FPKG - at the moment there is no such thing for PS5, because it would be useless anyway and dumped files are shared as-is. Interesting part is that apparently on PS5 native games doesn't use engine-level containers (compressed packages) and all files are already extracted, not sure if it's because of SSD or internal file system / memory management.

Okay, thanks for info
## Post #6
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-10-29T14:01:14+00:00
- Post Title: Demon's Souls (2020)

The PSO2 Aqua Library has a function to convert the cmdl/cmsh to fbx with rigs/skeletons, weights and UVs.
Rawtex can convert the textures, with some work.

Game fake PKG [https://www.psxhax.com/forums/__/](https://www.psxhax.com/forums/__/)
PSO2 Aqua Library model tool [https://github.com/Shadowth117/PSO2-Aqua-Library](https://github.com/Shadowth117/PSO2-Aqua-Library)
Rawtex Texture tool [viewtopic.php?t=16461](https://forum.xentax.com/viewtopic.php?t=16461)

Process:
1. Download fake pkg from PSXHax.
2. Unpack the rar
3. Use PSO2 Aqua tool to convert the cmdl/cmsh to fbx.
4. Use Rawtex with the PS5 swizzle to convert the ctxc texture to dds.

Texture notes (most of it is from spiritvod):
chunk0 is raw data for biggest mip for any texture.
You can simply drop it on rawtex and choose correct size + format + ps5 option. 
Sometimes rawtex can't auto-detect sizes properly, but that's not an issue and clearly visible on result.
Some formats: 
col BC1(DXT1)
ems BC1(DXT1)
msk BC1(DXT1) or BC7
nml BC7
rgh BC3(DXT5)
alpha BC4(ATI1)
Auto detection for size does not work.
2048 offset works for most textures, but not all.
