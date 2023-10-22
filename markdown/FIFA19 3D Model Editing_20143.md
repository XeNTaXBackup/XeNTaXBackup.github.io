## Post #1
- Username: halilyc
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 27, 2016 4:56 pm
- Post datetime: 2019-04-30T00:05:43+00:00
- Post Title: FIFA19 3D Model Editing

Galaxyman released a tool(frosty editor) for edit frostbite games but we cant edit mesh files for now but he added chunk and res editor for manuel editing for it. He gave us an example on head of messi but he does not show any tutorial about it. I have chunk file and obj file of messi and I want to locate my edited obj(polygons same, only position changes) in that file. He wrote this but I dont have any idea how can do that. I researched it on google and I found here and something about hex2obj program. Can you help me ? Thanks in advance.

> but the simplest way to work with heads is, export the head as obj. Import into whatever 3d program, move ur verts around, dont add, break, remove any. Export as obj, ensuring that the vertex count is unaffected. Then convert that obj into a stream of Vector 3 values, locate the chunk, and replace the first N bytes with the bytes from the obj stream u created (FIFA19 stores each vertex element, positions, normals, etc. as separate streams)

I added below edited messi chunk file and original messi chunk file for comparison.

[https://www25.zippyshare.com/v/gHD1ulhy/file.html](https://www25.zippyshare.com/v/gHD1ulhy/file.html)
