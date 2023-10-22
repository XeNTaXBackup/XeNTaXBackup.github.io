## Post #1
- Username: fierce
- Rank: advanced
- Number of posts: 41
- Joined date: Mon Jul 16, 2012 7:18 pm
- Post datetime: 2012-11-15T18:45:09+00:00
- Post Title: [Noesis Plugin Question]  What are the "Indices" on NoeMesh

Hey,

I'm trying to build a Noesis plugin to extract data from a game (Meshes+UV+Textures) and display it and export it, and I have no idea what should I input as the first parameter on NoeMesh().
I've read the inc_noesis.py file but I still have no idea.

NoeMesh(triList, posList)
triList? Is that the faces values? Or just some ordered index?
The files I'm trying to extract don't have any index values associated with the vertex, should I just add those indexes myself? Like: 1,2,3,4... And how do I input that data? An array with those values?
I'm a bit new to game dev/3d design so I have no clue about most definitions.

Also the faces on the file I'm trying to export have 4 values (quads), should I convert them myself to triangles?
I've searched the forum and Mr. Adults told finale00 to use "rpgCommitTriangles" but I still havent figured out the difference between using the "rpg" thingy and the "NoeMesh/NoeModel". I'll probably have this figured out by tomorrow but would be helpful if someone just gave me some pointers.

Thank you in advance for any help.
## Post #2
- Username: fierce
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-11-18T19:52:40+00:00
- Post Title: [Noesis Plugin Question]  What are the "Indices" on NoeMesh

If you're going to fill in a NoeMesh, you must fill in the indices with a Python list of triangle indices. Only triangle-ordered indices are accepted. This is one of the many reasons you should be using the rpg interface instead. It automatically takes care of batching, data conversion, data optimization, and a variety of other tasks.
