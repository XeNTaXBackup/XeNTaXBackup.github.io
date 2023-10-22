## Post #1
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-09T16:26:18+00:00
- Post Title: Leisure Suit Larry: Magna Cum Laude .WGG model

Hello there!
So, I am trying to extract some 3d models from the binary of the game. I know the purpose of most of the archives and I am positive that this one I'm about to show you, contains the 3D model of one of the women of the game.

My problem is that I don't understand the pattern of the archive. I was messing with the header and I was able to find some pieces of info there, but after that nothing makes sense to me. After the header there are a bunch of names and after that what seem to be a table of some sort:
[](https://ibb.co/nn7SHb1)
I have no idea of what are those bytes all around the table. Nothing.
But the thing doesn't stop there. After the table there are all the data for the vertices of the model followed by something I don't know the purpose of, and then the faces, wich are also pretty extrange because they seem to start again and again like there were more than one object (wich I think there are). And after the faces, an exact copy of the vertizes data (no idea why).

So, my conclusion is that, this 3D model is composed of different meshes and that table may be a way of differentiate the vertexes of the different meshes but i have no idea how to read it.

Thanks in advance and excuse me if there are some gramar mistakes.

EDIT: There are 45 entries in the table and I just discovered that the faces buffer contains chunks of indexes for 45 different object. Any clue of the data in the table?

EDIT: I've been taking the faces index chunks and deducing how many vertices per chunk i need to create something and with that i found out that the column of two bytes that starts with "2C 00" in the table are the vertices needed for each chunk (not in order) and the one that starts with "3E 00" are the cuantity of face indexes of every chunk (again, not in order) and that makes the forth entry the first chunk of the faces and the vertices.
## Post #2
- Username: Repeperilka
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Jun 09, 2018 5:36 am
- Post datetime: 2018-12-22T09:48:34+00:00
- Post Title: Leisure Suit Larry: Magna Cum Laude .WGG model

Okey, I've advanced a lot with this file and I will proceed to tell what I know about it. Why? you ask, well mainly because I am bored but also because I found out that the best way to overcome something you are stuck on, is to stop thinking about it (thats the first lesson this archive taught me)

So, first of, the structure of the file looks like this:

-Header (size of the file, pointers to the different sections, cuantity of objects...)
-Names of the different objects in the file
-The table I showed in the post
-1st chunk of vertices, normals, uv's (40 bytes)
-(optional) 2nd chunk of vertices...(36 bytes)
-(optional) 3rd chunk of vertices...(32 bytes)
-Faces Indexes
-An exact copy of the 1st vertex chunk

Header and Names
[](https://ibb.co/3SCBqvb)
All of the pointers work from the start position, wich is at the start of the field that holds the name of the objects

Table
[](https://ibb.co/YfhYv7q)
So, the yellow column of the table tells how many vertices are before the one that starts to build the mesh of the entry, therefore to find that vertex i had to do this:

[Start position of the vertex chunk] + [Yellow column number] * [Size of one vertex data (with normals, uv's etc)]

And the same goes for the face indexes.

Vertice chunks
Ok, the info of one vertex in the chunk is:
VertexPosition_float3
Unknown_float2/float1/float0
VertexNormal_float3
VertexUv's_float2
Why does every chunk have different sizes? And what is the extra info in them?

Faces
Nothing out of usual here

Copy of the main vertex chunk
I dont even know why do this exists.


And here is the link to the file: [https://mega.nz/#!d1BEDIYK!1IHSofZESe0a ... lD-2Aou2qw](https://mega.nz/#!d1BEDIYK!1IHSofZESe0agicz-qMG75wfn9LWVVCHglD-2Aou2qw)
