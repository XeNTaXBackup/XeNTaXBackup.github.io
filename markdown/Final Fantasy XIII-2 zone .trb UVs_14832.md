## Post #1
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2016-08-10T15:05:17+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

I've tried extracting the zone files from FFXIII-2, but they come without UV's. The FFXIII zones can be exported just fine though. Is there a way to fix this?I am ripping from the NA PS3 version. To extract the zone files, I first extract the main file in alba_data(which stored the pc,npc,monster etc models)and use the .bin files from the zone folders to extract the zone containers from the separate zone folder
Here's what I get while exporting from Noesis(the z0160e is Valhalla location):

```
.obj - WaveFront OBJ
Detected file type: FF13/FF13-2 Model
Processing TRB with 10 resources.
Parsing version 35 WRB.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because imgBundle is not accessible.
WARNING: Skipping uv's because they're in an external dependency.
WARNING: Skipping uv's because they're in an external dependency.
Expected main bundle size (D:\Ripping\Final Fantasy XIII\alba_data\zone\z0160e\filelist_imgu.ps3_files\bg\loc160\m030\bin\block030.ps3.trb): 4431148
Loaded 0 textures, 6 shaders, 17 meshes, 21 bones.
118245 triangles, 208205 vertices.
WARNING: Duplicate mesh names detected.
Renaming meshes.
Writing 'd:\ripping\final fantasy xiii\alba_data\zone\z0160e\filelist_imgu.ps3_files\bg\loc160\m030\bin\flatspec'.
Outputting to WaveFront obj.
Wrote file to D:\Ripping\Final Fantasy XIII\alba_data\zone\z0160e\filelist_imgu.ps3_files\bg\loc160\m030\bin\block030.ps3out.obj.

```
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-10T21:15:27+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

the uv's are stored with the texture file.
## Post #3
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2016-08-10T21:32:27+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

> Reply from chrrox
>
> the uv's are stored with the texture file.
Are there any ways to export them with the mesh?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-10T21:50:50+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

WARNING: Skipping uv's because imgBundle is not accessible.

you need to make the texture file for it available.
## Post #5
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2016-08-11T10:25:04+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

> Reply from chrrox
>
> WARNING: Skipping uv's because imgBundle is not accessible.

you need to make the texture file for it available.

But there is a corresponding .imgb file in the folder, it's just blank and the textures are stored in .imgb files which don't have any meshes owo
I've tried replacing a blank .imgb with the one which stores the textures but it didn't work
## Post #6
- Username: demolish1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 07, 2019 9:59 pm
- Post datetime: 2020-01-19T06:07:28+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

also getting the same issue using noesis despite copying all .trb and .imgb to the same dir (also no textures in noesis)

some zones (z0020e) seem to have some textures though they appear wrong

skyboxes appear to be fine though
[Noesis_eIO0yH2TMp.png](https://xentaxbackup.github.io/file/17380_Noesis_eIO0yH2TMp.png)
## Post #7
- Username: TheDude
- Rank: mega-veteran
- Number of posts: 239
- Joined date: Mon Mar 21, 2011 2:35 am
- Post datetime: 2020-01-21T15:24:18+00:00
- Post Title: Final Fantasy XIII-2 zone .trb UVs

If it's anything like the first game, those zones have a bunch of sub-directories and the image bundles are scattered all over the place.
You'll have to search through them all.
