## Post #1
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-11-21T08:39:28+00:00
- Post Title: Dead Rising 2 [pc] 3d model format

dead rising 2 uses .big or .tex archives for models and textuers.
With extractor (gibbed or bms script) I can extract npcs.big file and analyzed model formats.
They use simple float and integer array files and TRI-STRIP.

For example, cast_rebecca.big in npcs.big has files named "geo_blouseShape Indices 0" and "geo_blouseShape Vertices 0"

"geo_blouseShape Vertices 0" is a float array file and size is 122,920 bytes, So the number of floats are
122920/4 = 30730 (the size of a float is 4)
"geo_blouseShape Indices 0" is a integer array file and if you convert to text using utility like od2 ([http://www.gdargaud.net/Hack/BinToAscii.html](http://www.gdargaud.net/Hack/BinToAscii.html)), you see integers running from 0 to maximum 2194 which means it deals with 2195 points.

So you can guess 30730/2195 = 14 floats form a one point.

I found [0,1,2] modulo 14 forms a 3d mesh data.
[3, 4] modulo 14 forms a uv coordinates
[5, 6] modulo 14 always(?) zero
[7, 8, 9] modulo 14 forms a some normal
[10] modulo 14 always -1 but in other formats is seems like a weight
[11,12,13] modulo 14 forms a vertex normal which is used in obj like format

all points uses common uv and normal intex system that is the number of points for mesh, uv, normals are all equal.
To overcome the limits of this system, all part is divided to smaller parts.
So one tri-strip in "geo_blouseShape Indices 0" can handle all mesh, uv, normal in the same time.

With this analysis, I can convert all meshes in npcs.big into obj like format. (skeleton is not analyzed but it seems simple, there is only few float data in bone files, the problem is there is no suitable easy format which can contain mesh and bone data which i know of, texture information seems to be stored in another file "MatTextureInfoArray" in ordered method because each single part uses single texture.)

I tried to analyse zombies.big with this success.

But it seems use somewhat different system.

It has files something like "Combined Vertices 56" or "Combined Vertices 40"
I found 56 means 56 bytes per points that is 56/4=14 floats. 40 means 10 floats forms a point.
I thinks [7, 8, 9, 10] modulo 14 in 56-format is removed in 40-format. (with some repositioning, [5,6] modulo 14 has moved to [8,9] modulo 10.)
So vertex file structure for "Combined Vertices 56" is same with "geo_*Shape Vertices 0" type files.
But indices are very different.

For example, zombie_construction.big in zombies.bin has files "zombie_construction_2.big" "zombie_construction_3.big" "zombie_construction_4.big".

"zombie_construction_3.big" and "zombie_construction_4.big" seems like a more reduced polygon version of "zombie_construction_2.big"

each has single mesh file and it is named 
"Combined Vertices 56" for "zombie_construction_2.big" and has 41566 floats means 2969 points
"Combined Vertices 40" for "zombie_construction_3.big" and has 13120 floats means 1312 points
"Combined Vertices 40" for "zombie_construction_4.big" and has 3310 floats means 331 points

The corresponding Indices file name is same as "Combined Indices 2"
But strangely
"Combined Indices 2" for "zombie_construction_2.big" has indices running from 0 to 534 (required points are 2969!)
"Combined Indices 2" for "zombie_construction_2.big" has indices running from 0 to 210 (required points are 1312!)
"Combined Indices 2" for "zombie_construction_2.big" has indices running from 0 to 330 (well it has all points)

Also it seems use a multiple textures for a combined mesh. But one mesh must use one texture in this system otherwise it is complicated with other stuff.
So i guees it is really a combined files, then maximum indices need not to be large and each part can use single texture.
But i must know wheres is the position i must cut the file.
Any help will be welcome.

- The converter for npcs.big which converts geo* file pairs to obj is uploaded at [http://deadrising2mods.proboards.com/in ... thread=354](http://deadrising2mods.proboards.com/index.cgi?board=dr2tools&action=display&thread=354)
I also attached the converter.

But it only works in 32bit environment (but source is included)
[Geo2Obj.rar](https://xentaxbackup.github.io/file/3628_Geo2Obj.rar)
## Post #2
- Username: bluearms
- Rank: beginner
- Number of posts: 29
- Joined date: Wed Oct 13, 2010 4:48 am
- Post datetime: 2010-11-21T12:52:05+00:00
- Post Title: Dead Rising 2 [pc] 3d model format

Nevermind, I have found all new parts start with sequence 0, 1, 2 (seems obvious)
And file "SceneDescription" contains required part name.
