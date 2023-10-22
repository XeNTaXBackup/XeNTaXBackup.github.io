## Post #1
- Username: 3drussiangrabber
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 27, 2020 12:12 am
- Post datetime: 2021-02-23T14:58:27+00:00
- Post Title: Aquadelic *.ybo

game: Aquadelic
file: *.ybo
[https://dropmefiles.com/WMRU5](https://dropmefiles.com/WMRU5)



YagaBufferObject d   T2N3V3 e  Ш4ђ>lЁ{?’s-@.....

what soft ?????
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-23T19:44:30+00:00
- Post Title: Aquadelic *.ybo

Using hex2obj (view link in my sig):
.



file-ybo.png (35.28 KiB) Viewed 80 times

(Not sure about uv, best guess would be UV pos= 12 (tx at 12, ty at 16) but the displayed uvs have too many extra faces.)
## Post #3
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-02-23T20:06:48+00:00
- Post Title: Aquadelic *.ybo

The info at the start tells you the order of the values in the vertex table - "T2N3V3" - Texture: 2 floats, Normals: 3 floats, Vertex: 3 floats.  Unusually, the data starts at 0x20 with UV values instead of vertex coordinates.

I get this for the UVs, which doesn't look perfect, but I don't have a texture to test it with:
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-23T20:21:55+00:00
- Post Title: Aquadelic *.ybo

thx! To get better uvs for the example in my previous post one can set the start addr in step 3 to 0x14 (mesh displayed wrong/unvisible then, of course):
.



Rubber boat.png (39.2 KiB) Viewed 74 times
## Post #5
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2021-02-23T20:35:31+00:00
- Post Title: Aquadelic *.ybo

Yeah.  The reason it looks like there's duplicate lines is because there are exactly the same number of face index values as there are vertices, so a lot of vertices are stored more than once.  You can see in a hex editor that there are a lot of duplicate coordinate entries - you can see this if you look at the vertex list in Model Researcher.  But there's nothing else in the file to indicate things like LOD meshes, so I can only assume it's a very wasteful format!
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-02-25T14:11:30+00:00
- Post Title: Aquadelic *.ybo

There're about 14 submeshes in this file. That's why the UVs look such heavily chaotic. As the header indicates, this is just a buffer object with limited info. The actual submesh info must be stored somewhere else, most possibly in another file, which the author of this thread probably failed to mention or whatever.



ybo_split.png (151.21 KiB) Viewed 56 times
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-03-03T19:05:14+00:00
- Post Title: Aquadelic *.ybo

> Reply from Bigchillghost ↑Thu Feb 25, 2021 10:11 pm at Thu Feb 25, 2021 10:11 pm
>
> 
The actual submesh info must be stored somewhere else, most possibly in another file, which the author of this thread probably failed to mention or whatever.

The missing information are in the file.ent file.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2021-03-04T18:49:37+00:00
- Post Title: Aquadelic *.ybo

I have installed the Aquadelic GT game and I did find only one .ybo file called navnode.ybo.
I did find the 3d models in the *.bob files.

I have tested my Aquadelic GT *.bob/am loader module on about 200 different .bob/am files.
After it I have released the following programs as web updates:

- 3D Object Converter v7.044 (Windows)
- i3DConverter v3.903 (macOS)
- i3DConverter v1.903 (Linux)

How to get the 3D Object Converter v7.044:
Download the 3D Object Converter from [ http://3doc.i3dconverter.com](http://3doc.i3dconverter.com) and install it or download and use the portable version.
After it just use the Help/Check for updates... function to get the v7.044.

How to get the i3DConverter macOS v3.903:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v3.903.

How to get the i3DConverter Linux v1.903:
Download the i3DConverter from [ http://www.i3dconverter.com](http://www.i3dconverter.com) and install it.
After it just use the Help/Check for updates... function to get the v1.903.
