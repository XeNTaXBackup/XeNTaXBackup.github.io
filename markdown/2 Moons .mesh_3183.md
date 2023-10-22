## Post #1
- Username: ICON
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 12, 2008 2:51 am
- Post datetime: 2008-10-12T05:42:49+00:00
- Post Title: 2 Moons *.mesh

Been trying and trying to find something to convert the 2 Moons *.mesh file to *.Obj.

If any one have Luck on this it would be great.
What i tried the GH mesh tool did not work Scanned Google about 1000x. And looked into a few other tools with no luck at all. 

*.mesh to any usable format will be fine. .x .obj .3ds I can work with this Obj would be the best due to its the most versatile format.

[http://rapidshare.com/files/153166900/weapon.rar.html](http://rapidshare.com/files/153166900/weapon.rar.html)

This is the weapons folder all the *.mesh files for weapons. 

Thank you in advance.
## Post #2
- Username: ICON
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 12, 2008 2:51 am
- Post datetime: 2008-10-13T19:26:01+00:00
- Post Title: 2 Moons *.mesh

No Takers?
## Post #3
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2008-11-20T18:28:59+00:00
- Post Title: 2 Moons *.mesh

Started looking into it, this is what I got so far:

```
	DWORD unk1; //From the files I checked, it was always 0x20031117
	DWORD unk2; //From the files I checked, it was always 0x0
	DWORD unk3; //From the files I checked, it was always 0x0
	DWORD unk4; //From the files I checked, it was always 0x0
}

struct offsets[4] { //This section contains 4 sets of offsets (offset + size)
	DWORD offset;
	DWORD size;
}

//original source file, max of 64 bytes, path is padded by extra 0's to fill the space
char srcFile[64];

//offset 1 - files I looked at always had a size of 4 for the first offset
DWORD unknown1; 

//offset 2 - some kind of extra information for the mesh (will post later since I don't know the full structure)
//offset 2 section
//bone info perhaps?
DWORD count;
struct bone_info[count] {
	DWORD nameLen;
	char name[nameLen];
	DWORD index; //always seemed to be 1
	DWORD boneCount;
	struct Bone[boneCount] { //28 bytes, floatx7? floatx3+intx4?
		//from sampled data, the first 12 bytes were of float data, possibly a position?
		float pos[3];
		float rotation[4]; //quarterion? was always 0 in sample files
	}
	DWORD unknown; //always seemed to be 0
}

//offset 3 - was same as offset 1
DWORD unknown3;

//offset 4 - vertext/index data (and possibly more)
//offset 4 section
DWORD index; //or mesh count? could match up to bone_info[].index?
//rotation/translation or translation/rotation? or something else, 24 bytes (6 floats)
//EDIT: could also be a scale, my guess its rotation and scale
float rotation[3];
float translation[3];
DWORD unknown1[4]; //usally 1,0,1,0 or 1,1,1,0
DWORD count;

//index data
DWORD indexCount; 
WORD indices[indexCount];

//vertex data
DWORD vertexCount; //NOTE: same as count! so either could be the vertex count?
struct vertex[vertexCount] {
	float pos[3];		//position
	float normal[3];	//normal
	float uv[2][2]; 	//2 sets of UV coords
	float unknown[4];	//usually 0,0,0,0 or 0,0,1,0
				//could be a quarterion
}
DWORD nameCount; //usually 0
struct name[nameCount] {
	DWORD nameLen;
	char name[nameLen];
}
DWORD unknown2; //always 0?

```


Based on the files I looked at, this format works. Player model files may be different, but I do not have any to check.
## Post #4
- Username: ICON
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Sep 12, 2008 2:51 am
- Post datetime: 2008-11-23T21:26:38+00:00
- Post Title: 2 Moons *.mesh

thank you so very much ill have my dev start to code the tool.
## Post #5
- Username: Theran
- Rank: beginner
- Number of posts: 37
- Joined date: Thu Jun 12, 2008 1:49 am
- Post datetime: 2008-12-01T17:08:39+00:00
- Post Title: 2 Moons *.mesh

Np! Glad to help out. Let me now if it all works well, since there is a chance I may have missed something. Also if you can figure out any of the unknowns, let us know. 

Thanks.
