## Post #1
- Username: ketec
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Aug 01, 2017 1:50 pm
- Post datetime: 2017-08-01T06:21:02+00:00
- Post Title: Converting to .obj format - problematic textures

Dealing with a older ~2000 era dx8 custom .BSP that has a standard FVF vertex blob:

```
        struct BSPD3DVertex
	{
		float vPosition[3];
		float vNormal[3];
		UBYTE color[4];
		float vTextureCoord[2]
		float vLightmapCoord[2];
	};

```


Is there anything specific to look for / keep in mind when converting texture coordinates to .obj? Currently textures are  a mess. Looking at UV in 3dsmax shows that even for a simple 4 face rectangle it's a rats nest - the triangles in uv map  are there but warped and connected in wrong order.

EX: [http://imgur.com/a/7z2NS](http://imgur.com/a/7z2NS)
Currently:

```
  v vPosition[0] vPosition[1] vPosition[2]
  vt vPosition[0] 1- vPosition[1] 0.0000
  vn vNormal[0] vNormal[1] vNormal[2]

```
