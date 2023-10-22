## Post #1
- Username: johnk
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jul 03, 2019 2:14 am
- Post datetime: 2020-02-27T16:45:40+00:00
- Post Title: PES2014 Head Models [PS3]

Hi,

I have been trying to decypher the head & hair models for WE2014 for PS3 but I'm struggling to obtain the faces/polygons and normals for 3 models (face_high_win32, face_edithair_win32 & hair_d_win32).

I have a topic setup in the 2d/3d models which bigchillghost has been really helpful but he thinks that the faces/polygons are compressed within the model files and wondered if anyone could help.

[viewtopic.php?f=16&t=21748&sid=fa9d812a ... b8c812e703](https://forum.xentax.com/viewtopic.php?f=16&t=21748&sid=fa9d812a84d63073e26432b8c812e703)

[https://easyupload.io/juztis](https://easyupload.io/juztis)

For example, I have found that there are 5 subparts within the face_high_win32.model in the WE2014 folder with verts and UVs as follows:

Verts:- 0x1950 - 0x47d0, 0x6810 - 0xcd94, 0x101c0 - 0x10808, 0x10f40 - 0x11120, 0x11970 - 0x136f8
UVs:- 0x7650 - 0x9550, 0xe330 - 0xf188, 0x10810 - 0x10a28, 0x11120 - 0x111c0, 0x15490 - 0x15368

I suspect the faces/polygons and normals are inbetween the verts and its associated UVs but if anyone can find any compressed data within the models, I would appreciate it.

There was one layer of zlib compression on the original files, which has been removed.
