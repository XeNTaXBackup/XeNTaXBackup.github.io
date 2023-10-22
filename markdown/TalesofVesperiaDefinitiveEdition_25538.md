## Post #1
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-16T22:09:33+00:00
- Post Title: TalesofVesperiaDefinitiveEdition

Need help opening  2  files [https://www.mediafire.com/folder/xjzx0j4hsjrce/Tales](https://www.mediafire.com/folder/xjzx0j4hsjrce/Tales)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-17T11:30:48+00:00
- Post Title: TalesofVesperiaDefinitiveEdition

> Reply from blacknight411 ↑Fri Jun 17, 2022 6:09 am at Fri Jun 17, 2022 6:09 am
>
> 
Need help opening  2  files

files are compressed:

```
-file_size    INT
-unpack_size  INT

```

i made 2 plugin for noesis:
-'fmt_UNPACK_DAT.py' for unpack *.DAT, (after unpacking, an FPS4 file will appear next to the original)
-'fmt_UNPACK_DDS.py' unpack all .DDS file from FPS4

FPS4 contains dds textures and meshes.
example 'EP_1420_010.FPS4'
vertex offset 0x50D60
indices offset 0x57B14 (tri strip?)

vbuf is divided into submesh (vertices first, then normals)
I don't have time now to look for submesh and information about them.
here is part of the vertex cloud of the head

look at [this](https://zenhax.com/viewtopic.php?f=17&t=7018&hilit=FPS4) topic, maybe there is something there.
[plugins.zip](https://xentaxbackup.github.io/file/22380_plugins.zip)
## Post #3
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2022-06-17T16:52:20+00:00
- Post Title: TalesofVesperiaDefinitiveEdition

[viewtopic.php?f=16&t=18844&hilit=Tales+ ... ia#p148260](https://forum.xentax.com/viewtopic.php?f=16&t=18844&hilit=Tales+of+vesperia#p148260)
We already have a model importer here.
## Post #4
- Username: blacknight411
- Rank: veteran
- Number of posts: 120
- Joined date: Fri Jun 22, 2018 8:39 pm
- Post datetime: 2022-06-18T01:19:13+00:00
- Post Title: TalesofVesperiaDefinitiveEdition

In the Blender249[TalesOfVesperia][PC][svo][dat][dec][2019-02-03] did anyone figure out how to fix  the no hair problems.
