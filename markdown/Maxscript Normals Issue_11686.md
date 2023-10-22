## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-07-12T21:40:28+00:00
- Post Title: Maxscript Normals Issue

I`m building a mesh importer and I got a problem. When I apply a texture on the build mesh object it looks inverted(TEXT, numbers). Flipping normals don`t do any good. And I can`t seem to find an answer in the help files.

[https://www.dropbox.com/s/vhntho32z2kjs ... .03.29.png](https://www.dropbox.com/s/vhntho32z2kjss2/Screenshot%202014-07-10%2023.03.29.png)

So I suspect it has to be done before the mesh is build from vert and face arrays?
here`s the snip of my script

--Build Mesh From Arrays
mesh1 = mesh vertices:Vert_array faces:Face_array
mesh1.numTVerts = UV_array.count
buildTVFaces mesh1	
for j = 1 to nm_array.count do meshop.setMapVert mesh1 1 j nm_array[j] 
for j = 1 to Face_array.count do meshop.setMapFace mesh1 1 j Face_array[j] 

anyone has any clues?
## Post #2
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-07-12T22:00:40+00:00
- Post Title: Maxscript Normals Issue

It has nothing to do with normals, the mesh itself needs to be mirrored. Specifically, it looks like you need to load vertices as [-x, y, z].
You can also tell by the fact that the watch is on the right hand, whereas it should be on the left. 

Careful when doing this! Inverting or switching an odd number of vertex components will reverse the face winding. Activate backface cull on your mesh and see if it looks ok. If it doesn't, you'll need to flip face indices ([i3, i2, i1] instead of [i1, i2, i3]]
## Post #3
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-07-14T21:24:25+00:00
- Post Title: Maxscript Normals Issue

Your a star Chipicao. -Vpx does the job beautifully, thank you so much
