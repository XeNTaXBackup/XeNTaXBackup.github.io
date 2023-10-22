## Post #1
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-11T13:32:00+00:00
- Post Title: Starship Troopers TA pdo models

Hi,
so few days ago I get STTA game so I blah blah blah I'll skip that boring part.
In short way I yesterday created ms script to load meshes (PDO files), BUT I'm able to get only few blocks like animations, bones, etc.
And I cannot see any faces nor facecounts,vertexcounts, but it seems vertex data is here.
First I thought its not mesh file but after researching whole filestructure those must be ones coz there are only textures, terrain, script and those pdo files.
So Im asking for help becouse I have never seen anything like this before.
Thanks.

Packing script and some pdo files.
[MYScripts.zip](https://xentaxbackup.github.io/file/8244_MYScripts.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-16T20:18:40+00:00
- Post Title: Starship Troopers TA pdo models

for the bridge it's rather simple: from 0x5B6C you'll find 122 vertices, vertex block size: 36
and from 0x6CA8 DWord face indices f1, f2,f3 (also in 36 bytes blocks), 86 faces



bridge_pdo.JPG (96.96 KiB) Viewed 216 times



next submesh to be found at 0x78AC, H2O file:
0x9018 298
Vb1
36 28
0x78AC 166
040000
0x0 255
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-17T15:39:24+00:00
- Post Title: Starship Troopers TA pdo models

Thank you very much for info.
## Post #4
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-19T18:14:41+00:00
- Post Title: Starship Troopers TA pdo models

Becouse of nodes does not have parent id I have a big problem with hierarchy.
Hierarchy is stored in childcount tham mean any node have its own child count like
Node 1 have 3 childs
Node 2 have 2 childs
Node 3 have 0 childs
Node 4 -> 0
Node 5 -> 1
Node 6 -> 0
Node 7 -> 0

So it should look like

```
     Node 2 #numchilds 2
          Node 3 #numchilds 0
          Node 4 #numchilds 0
     Node 5 #numchilds 1 
          Node 6 #numchilds 0
     Node 7 #numchilds 0

```

its a little confusing but I cannot find a way to make propper hierarchy and tell nodes whos their parent.
Any help how should be looking function for that??
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-20T13:03:49+00:00
- Post Title: Starship Troopers TA pdo models

Hi

Sections:
1.header
2.animation info
3.animation data
4.lod info
5.lod data
5.1.skeleton
5.2.meshes

ad1.
int32
string20 from 20 bytes
int32 - animCount int
int32 - lodCount
int32 - boneCount
skip 32 bytes

ad2. repeat animCount
string20 - animation name
int32 - id
int32 - fps
int32 - unk
int32 - absolut offset to animation data

ad3.

ad4.repeat lodCount
int32 - boneCount
int32 - unk
int32 - unk
int32 - offset to lod data

ad5. repeat lodCount

ad5.1. repeat boneCount
int32 - unk
int32 - unk
int32 - unk
string24 - bone name
int32 - unk
int32 - unk
int32 - unk
int32 - parentID
int32 - vertCount for a mesh bind with this bone 
int32 - faceCount for a mesh bind with this bone
int32 - unk
int32 -unk
Vector f3 - bone position relativ to parent bone
Quaternion 4f - bone rotation relativ to parent bone
Vector f3
Quaternion 4f

ad.5.2.
mesh is parenting to bone 

Sorry. I can't explain good. Please look at python script for importing pdo.
[Blender249[SWSTTA][PC][pdo][2014-12-20].zip](https://xentaxbackup.github.io/file/8310_Blender249[SWSTTA][PC][pdo][2014-12-20].zip)
## Post #6
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-20T13:45:20+00:00
- Post Title: Starship Troopers TA pdo models

Well, I have already created MaxScript, it can load every mesh, Only problem is parenting possitions.
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-20T14:03:28+00:00
- Post Title: Starship Troopers TA pdo models

Hi

Good job with max script.

Maybe try build armature with relativ relations for bones. (from line 119)

Try this at line 123 . here is parent id:
msh.name = readschars f 40 <==>readschars f 24 + unk,unk,unk,bone.parentID=readlong,readlong,readlong,readlong

And after than get needed matrix(absolut) for mesh from bone with the same name.

Or try build matrix list with recursion function.

Edit:
at line 146:
msh.rot = (quat r21 r22 r23 r24)

please use:
msh.rot = (quat r14 r21 r22 r23)
## Post #8
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-20T14:15:18+00:00
- Post Title: Starship Troopers TA pdo models

Yes, I edited that, thanks for info in script. Now its working how it should be 

Also any tips for animation data?
## Post #9
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-20T14:22:35+00:00
- Post Title: Starship Troopers TA pdo models

I have no idea.

Maybe use bytes  for rotation key (example: 4/256,6/256,34/256 Euler ?) not shorts.
## Post #10
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2014-12-21T10:03:02+00:00
- Post Title: Starship Troopers TA pdo models

Okay, so here is my final version of script.
It can merge multimeshes to one so skinning operation is much faster.
Bones
Weights
LODs as Objects
UVs
Materials should be set manually, same for MATIDs.
I cannot understand animations so they are not in process.
Textures are in Portable Pixmap format (PPM), so they can be opened in every good editor/viewer.
[Starship Troopers TA Model (PDO).zip](https://xentaxbackup.github.io/file/8320_Starship Troopers TA Model (PDO).zip)
