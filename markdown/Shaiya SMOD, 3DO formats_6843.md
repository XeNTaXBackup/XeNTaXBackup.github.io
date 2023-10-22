## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-24T15:41:59+00:00
- Post Title: Shaiya SMOD, 3DO formats

fatduck posted up shaiya's 3DC format, but I couldn't find anything about the SMOD of 3DO format although they are already supported by various programs.

It doesn't look too complicated so I thought I would take a shot at it and try to figure out the format on my own.

Comparing a couple SMOD's, seems like

-starts with 40 bytes of ???
-followed by the number of meshes (4 bytes)
-followed by the struct for each mesh

For each mesh, we have
-the length of the texture name, null-terminated
-the texture name itself
-the number of vertices
-[a bunch of floats] with some padding I think, don't know the format
-the number of faces, followed by a list of face vertices

And then another 28 bytes after all meshes are done.

I don't know how to figure out the format for the floats, but I'm guessing there's padding here and there.

Here's a sample "door.SMOD"



Any techniques that would be useful? Tried looking for patterns, and found that

-it starts with 12 bytes before running into "00 00 80 3F"
-after "00 00 80 3F", there are 8 bytes (2 floats?)
-after "FF FF FF FF", there are 20 bytes (so 5 floats?)

This is consistent until we see the last FF FF FF FF, which is followed by 8 bytes before we get the number of faces.

But don't know if that can mean anything.
[Shaiya.rar](https://xentaxbackup.github.io/file/4374_Shaiya.rar)
## Post #2
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2011-06-25T10:13:07+00:00
- Post Title: Shaiya SMOD, 3DO formats

float_3  CoordXYZ
float_3  NormalXYZ
float     unknown
float_2  TexCoordUV

I note the V=1-Read_float
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-25T14:51:20+00:00
- Post Title: Shaiya SMOD, 3DO formats

ah, got it thanks.
