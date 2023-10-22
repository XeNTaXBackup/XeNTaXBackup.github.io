## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-06-19T13:45:44+00:00
- Post Title: Alienbrain .es

This is a container format used by the Alienbrain engine, which is utilized in a few games by RTL. The format can store textures with EST header and models with ESM header. I tried to load one of the 3D models into 3ds max, but I'm having problems with loading the vertices correctly - I can only get a flat representation of the mesh (could be UV map) by reading some of the coordinates as int16 divided by factor.



In the provided .esm file, I expect the vertex block to start somewhere around offset 0x44. The model file should represent a globe. Any help is appreciated.
[0x4006C_74612.zip](https://xentaxbackup.github.io/file/7492_0x4006C_74612.zip)
