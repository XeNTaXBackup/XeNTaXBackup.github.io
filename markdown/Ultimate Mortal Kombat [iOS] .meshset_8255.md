## Post #1
- Username: whoknows138
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 12, 2011 7:41 pm
- Post datetime: 2012-02-11T09:18:53+00:00
- Post Title: Ultimate Mortal Kombat [iOS] .meshset

Hello. I'm new here and i don't speak english, so please, be patient. 
There is a coolstory:
   I wanted make some models from the original Mortal Kombat 3 sprites, but then i found what that models is already done in iphone version of UMK. So, i decided to borrow them. I also found the same [topic](http://forum.xentax.com/viewtopic.php?f=21&t=5566) on this forum and free [tool](http://www.imgtec.com/powervr/insider/powervr-pvrtextool.asp) to view and convert textures from .pvr format. But the main question is about models in .meshset format.
   I know nothing about compression methods and so far i have tried only qbms(without any success ofc).I just can't understand what the .meshset actually is. Maybe it's an archive or some kind of collection of the meshes, can u help me with it? 
There is some reference about .fbx format inside the file, that maybe usefull i believe:

```
//=====================================================
MESHINFO *Mesh__ptrs[]={
	&MeshInfo__00,
};

//=====================================================
// Mesh set info block for this FBX file.
//=====================================================
MESHSETINFO MeshSet_= {
	1,	// Number of meshes in this set.
	&Mesh__ptrs[0]	// List of ptrs to each mesh.
};
```

[Example](http://rghost.ru/36458824)
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-11T22:47:11+00:00
- Post Title: Ultimate Mortal Kombat [iOS] .meshset

Well the format looks simple enough. It's just a mesh file.
Just can't figure out the vertex struct.

For anyone that wants to look into the vertex struct, here's a noesis plugin. Just fill in the parse_vertices method. Or, if you think the outline I wrote is wrong, just make the appropriate changes. There isn't too much info really.

[http://db.tt/gUAkrgAr](http://db.tt/gUAkrgAr)

```

struct Vertex {
	26 bytes
}

int32 numMesh
numMesh Mesh {
	char[64] meshName
	char[64] matName
	int32 numVerts
	int32 numFaces // numIdx = numFaces * 3
	float ?
	
	int16[numIdx] indices
	numVerts Vertex
}

#some ascii stuff at the end that does not seem important.

```


There's no material info. It might be stored in a separate file.

I can't figure out the vertex struct. They should be 26 bytes each since there's not a lot of information in this format (you can tell when I don't question marks all over my outlines), but nothing comes out right.

Upload more samples.
Also, find files related to the meshes.
## Post #3
- Username: whoknows138
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Oct 12, 2011 7:41 pm
- Post datetime: 2012-02-12T14:03:50+00:00
- Post Title: Ultimate Mortal Kombat [iOS] .meshset

Thanks for the help. 
I collected all related files and some of them maybe unnecessary, or I just don't known what they supposed to be. Looks like i can't attach it, so here is the link: [http://rghost.ru/36480984](http://rghost.ru/36480984)
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T16:36:54+00:00
- Post Title: Ultimate Mortal Kombat [iOS] .meshset

Hmm ya, unless there was something different about how the data is stored, you have 26 byte vertex structures.

There are a couple floats that seem to occur in the same positions for each vertex, but the output doesn't look like anything.

Might be some idea I'm not familiar with.
