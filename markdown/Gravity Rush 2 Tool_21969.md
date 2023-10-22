## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-04T16:07:24+00:00
- Post Title: Gravity Rush 2 Tool

Returned to this format after quite some time. Supports geometry/skeleton/skinning. Only skinned models are supported atm (mostly character models). I might consider adding support for other stuff.

Tool overview and example exported model



Load

GFX : Loads skinned meshes inside gfx files.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
Note  : Models and textures will be exported into the folder Export.

Note on Normals / Tangents

I believe that I am loading the correct normal/tangent data in game files, but the meshes will look "weird" using that data. This game has a unique art style, and I guess the use of normals/tangents are not standard. Probably some shader work going on in the game engine.

So I have added the option to recalculate normals. It can also be done in most 3d software. You still have the option to disable it and load the original normal/tangent data. Incase you can put them to use somehow.

Download : [https://www.mediafire.com/file/b6u45og1 ... r.rar/file](https://www.mediafire.com/file/b6u45og1jzbdihg/GR2Viewer.rar/file)
## Post #2
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-04-06T12:45:01+00:00
- Post Title: Gravity Rush 2 Tool

> Reply from akderebur ↑Sun Apr 05, 2020 12:07 am at Sun Apr 05, 2020 12:07 am
>
> 
Returned to this format after quite some time. Supports geometry/skeleton/skinning. Only skinned models are supported atm (mostly character models). I might consider adding support for other stuff.

Tool overview and example exported model



Load

GFX : Loads skinned meshes inside gfx files.
Export

NEX : Exports the model in custom binary format (.nex), intended to be loaded by Noesis. Noesis script for this format : Nex Script
Note  : Models and textures will be exported into the folder Export.

Note on Normals / Tangents

I believe that I am loading the correct normal/tangent data in game files, but the meshes will look "weird" using that data. This game has a unique art style, and I guess the use of normals/tangents are not standard. Probably some shader work going on in the game engine.

So I have added the option to recalculate normals. It can also be done in most 3d software. You still have the option to disable it and load the original normal/tangent data. Incase you can put them to use somehow.

Download : https://www.mediafire.com/file/b6u45og1 ... r.rar/file

does it support models from the original game, both ps vita and ps3.
