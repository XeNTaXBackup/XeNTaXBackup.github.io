## Post #1
- Username: eri619
- Rank: veteran
- Number of posts: 81
- Joined date: Wed May 16, 2012 1:36 pm
- Post datetime: 2015-09-29T01:44:26+00:00
- Post Title: need help with Face Endian offset and such

Since Szkaradek123 is the creator of the Rumble Roses yobj Python(PS2) Script i thought i should ask for help here.
blender scripts are totally greek to me,could you please help me find the location of
U-V maps,draw offset and facetable offset from this model file?
i'm attaching the blender script Szkaradek123 created and a sample model file.The blender script has everything you need.You just need to help me find U-V maps offset,draw offset and facetable(endian)offset
since i dont understand blender scripts.it would be also appreciated if i could get info about the rigging method of bones.This script exports the mesh,uv and bones.It doesnt import the edits back.My friend has made an importer of vertices only.I need these info to make a complete importer.
[https://openload.io/f/Fjh9O4Fm_ag/Files.rar](https://openload.io/f/Fjh9O4Fm_ag/Files.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-09-29T15:33:50+00:00
- Post Title: need help with Face Endian offset and such

hi, seems you're not too lucky with your requests...

For this one I simply fail to download your uploaded rar file - all I get is nasty popup windows.
## Post #3
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-09-30T12:00:31+00:00
- Post Title: need help with Face Endian offset and such

As with a lot of ps2 formats, there is no face buffer explicitly stored in the file.
The GS is capable of generating a trilist or tristrip based on the vertex count on runtime.
Not sure what you mean by draw offset, draw calls are designated by XX YY ZZ 17 or XX YY ZZ 14 in ps2 vif packets
As far as the uvs, it seems there's 2 sets of buffers, one of which seems to vertex position & weight and the other normals & uvs maybe?

I also attached the download to this post.


 Files.rar
(180 KiB) Downloaded 29 times
