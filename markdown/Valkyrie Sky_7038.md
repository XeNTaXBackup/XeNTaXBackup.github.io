## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T20:10:50+00:00
- Post Title: Valkyrie Sky

Game is no longer running, but the client is still around.
MMO + shmup. Lol pretty cool. [http://www.youtube.com/watch?v=zfbQweYRzPA](http://www.youtube.com/watch?v=zfbQweYRzPA)
Oh well, plenty of touhou to keep enthusiasts busy.

```

char_80 header
dword_4 ???
dword numSections (??)
dword 4 ???

numSections unkSection {
   char_80 name
}

dword ???
IF numSections >2
   dword ??? 
ENDIF
float_9 ???
dword_5 ???
320 bytes ???
float_9 ???
dword_5 ???
char_80 texName
320 bytes ???
220 bytes ???
char_80 unkProperty
IF unkProperty == "Particle_View"
   220 bytes ???
   char_80 unkProperty2  ("editable mesh")
ENDIF

dword ???
184 bytes ???
dword numVertexCoords
dword numNormals
dword numUV
dword numFaces
dword numIndex
dword unkCount1 (0 with the samples I uploaded)
dword unkCount2 (some section after all the indices. 48 bytes per struct. Note, always numFaces * 3)
dword unkCount3

numVertexCoords coords {
   float_3 vert coords
}

numNormals normal {
   float_3 normals
}

numUV texCoords {
   float_2 u,v
}

numFace Face {
   dword one
   dword_3 indices
}

numIndex face UV {
   dword_3 indices
}

unkCount2 unkStruct2 {
   float_5 ???
   dword_7 padding
}
unkCount3 unkStruct3 {
   dword_3 indices?
}

```


Note that the "Particle_View" might appear after the editable_mesh section, so you need to check for that.
[Valkyrie Sky.rar](https://xentaxbackup.github.io/file/4527_Valkyrie Sky.rar)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-29T17:59:39+00:00
- Post Title: Valkyrie Sky

Updated the specs.

It occurred to me that it is also common to store all vertex coords, all normals, and all texcoords contiguously, so I put it to the test, and it worked.

The number of vertices is equal to the number of vertex normals, so presumably when you go through each group of vertices for each face, the same indices are used for the normals.

And then texcoords use the second set of indices, and the max indices for each section match.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T02:26:01+00:00
- Post Title: Valkyrie Sky

The UV's are stored with the faces      

My program can't handle that properly yet (it assumes UV stored with vertex)
I may have to create extra vertices...
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-12T10:30:46+00:00
- Post Title: Valkyrie Sky

I have worked with this before this is how you do it.

league of legends was just like this format.
[League of Legends.rar](https://xentaxbackup.github.io/file/4616_League of Legends.rar)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T12:48:16+00:00
- Post Title: Valkyrie Sky

My own issue here is that I have not found a good way to store the UV with the faces and export it to a format that stores them with the vertices lol

If they use indices to refer to vertices, then chances are the number of duplicate coords are minimized, but if I have to store UV with vertices then I will most likely end up with lots of duplicate coords, which wouldn't work well for the original format cause it bloats the filesize.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-12T19:12:55+00:00
- Post Title: Valkyrie Sky

I don't understand what the problem is in my script i convert the uv's so they are one uv per vert.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-12T20:16:40+00:00
- Post Title: Valkyrie Sky

Maybe I'm not reading the script correctly.

Two faces can share the same vertex but have different UV values.
I am not sure how those are handled. In this case there would be less vertices than there are UV values.
