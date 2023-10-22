## Post #1
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2015-02-17T05:36:08+00:00
- Post Title: League of Legends WGeo

League of Legends World Geometry file as the name suggests contains all the world geometry.  Its a new format to take over the previous "NVR" format, its a baked terrain.

Currently this is how far I've gotten with the format, ideally would want to break it entirely down to be able to modify it as right now when you modify model vertex positions it ends up causing a weird error and some parts when I edit them causes crashes which will mention in the breakdown:

room.wgeo:
[https://mega.co.nz/#!8tlWUQza!tc-w5A--q ... SGn-0bJ0M4](https://mega.co.nz/#!8tlWUQza!tc-w5A--q42Cv4QivOajhNn6OLkCSs_ZFSGn-0bJ0M4)

4 Byte - Magic "WGEO"
4 Byte - Version - Latest is 5
4 Byte - Mesh Count
4 Byte - Total Tri Count

For Amount of Meshes

    260 Bytes - String, Texture Name
    64 Bytes - String, Material Name

    12 Bytes - Vector3<float>, Sphere Position
    4 Byte - float, Sphere Radius

    12 Bytes - Vector4<float>, min aabb
    12 bytes - Vector4 <float>, max aabb

    4 Bytes - Vertex Count
    4 Bytes - Index count

    For Vertex Count
        12 Bytes - Vector3<float>, Vertex
        8 Bytes - Vector2<float>, UV
    Loop

    For Index Count
        2 Byte - Index
    Loop

Loop

Note: Here comes the sketchy unsure area:

4 Bytes - Float, MinX?
4 Bytes - Float, MinZ?
4 Bytes - Float, MaxX?
4 Bytes - Float, MaxZ?
4 Bytes - Float, CenterX?
4 Bytes - Float, CenterZ?
4 Bytes - Float MinY?
4 Bytes - Float MaxY?

4 Bytes - Unknown
4 Bytes - UnkCount
4 Bytes - UnkCount2

For UnkCount
    12 Byte - Vector3<Float>, vertex? - NOTE: When Edited it crashes no idea what its meant to be.
Loop

Rest of data I'm unsure on.



Any help would be appreciated, currently this is all I've managed to work out from the format.  The main chunk of data to import it in is easy but exporting need to know this extra data.
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2015-02-18T01:31:56+00:00
- Post Title: League of Legends WGeo

[out]
## Post #3
- Username: Uli
- Rank: advanced
- Number of posts: 46
- Joined date: Sat Dec 12, 2009 2:42 am
- Post datetime: 2015-02-18T12:11:29+00:00
- Post Title: League of Legends WGeo

> Reply from Wobble
>
> I get the same.  

Last part:
Code: Select all[0] f: -713.382690	// paired values?
[1] f: -630.093384

[2] f: 14830.331055
[3] f: 14891.101563

[4] f: 2796.732910
[5] f: 2816.903320

[6] f: 121.435265
[7] f: 121.259338
[10764342]

  unk_count: 128
 vert_count: 220289
index_count: 627756   



List of vertices only - no UVs
List of indices - related to trigs?  count is evenly divisible by 3 (209252).

I would probably plot these unknown vertices around the meshes, and see what you get.  Probably has something to do with collision planes, boxes, octrees, etc...  All the mesh data has already been listed, so whatever it is, I would guess it's not visible geometry (no uvs, textures, or materials).

Yea good plan, its 100% non visible geometry.  What it handles is some particles are drawn onto the terrain rather then in physical space, no idea why some do it like this is very weird which aren't and are there is zero correlation, so any heavy or minor modification means these particles are no longer drawn.  A shift by -0.1 or 0.1 on the Y of all the vertices will completely break the particles drawn on the terrain.

Trying to adjust the unknown verts leads to a crash. (tried where I set it to 0 and loaded fine but using any form of abilities which tries to map the particles to the map lead to a crash)

Kind of feels easier to just convert it to the old NVR format to get around the issue.
