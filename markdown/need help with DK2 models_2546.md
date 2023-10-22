## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-21T08:53:57+00:00
- Post Title: need help with DK2 models

This is what I know so far:
The files are made up of chunks starting with a fourcc at the beginning followed by the size of the whole chunk.

```
	char fourcc[4];
	int size;
	byte data[size-8];
} CHUNK;
```


This is the structure of a file. There is either a MESH chunk or an ANIM chunk.

```
	int version; // 17
	HEAD
		int format; // ?? 1=mesh 2=anim
		int uk; // always 1 ?
	MATL
		int NumMaterials;
		MAT2* // Material Entry
			string uk;
			int uk;
			string Texturename; // file name
			...
	MESH
		HEAD
			string meshname;
			int NumSPRS;
			...
		CTRL
		SPRS
			SPHD*
			SPRS*
		GEOM
	ANIM
		HEAD
		CTRL
		SPRS
			SPHD*
			SPRS*
				POLY
				VERT
		ITAB
		GEOM
		VGEO

```


I uploaded the files for the bile demon as an example.
[http://uploaded.to/?id=6qjw59](http://uploaded.to/?id=6qjw59)

Any help appreciated.
Might even be of help if someone could guess what SPRS (HD could mean header and RS resource, but what is SP) ITAB or VGEO stands for.
## Post #2
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-03-22T07:33:06+00:00
- Post Title: need help with DK2 models

ITAB is the index table - how triangles are assembled 
and VGEO look like fixed point vertices or a picture lol

I am not sure but it looks like the game uses vertex animation and not skinning
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-22T11:53:13+00:00
- Post Title: need help with DK2 models

I don't think so. The ITAB has as much integers as the number of vertices in the mesh.
Besides there are also static meshes with no ANIM files, so the key to the problem seems to be the SPRS chunk.
I found out that the GEOM chunk in MESH files contains the vertices for that mesh (3 floats for each vertex)
The GEOM chunk in ANIM files consists of many structures consisting of an int and a byte.
VGEO consists of single byte data that seems to be an index that goes from 0 up to a value specified in the header.
The game's from 1997. I don't know what techniques they used at that time.

I attach my binary template for 010 Editor, so you can see what I have so far and some of the static meshes.
[Static Meshes.rar](https://xentaxbackup.github.io/file/1098_Static Meshes.rar)
## Post #4
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-03-22T18:11:21+00:00
- Post Title: need help with DK2 models

you are right.. the VGEO data seems to increase over as it goes.. but then again so does the poly data

I found what looks like vertex data in the VERT chunk :D

32 or 36 bytes per vertex dunno
{
int32
float nx
flaot ny
float nz
float x
float y
float z
int32
}

or with normals last I don't remember

without a doubt however itab seems to be the index table

are you sure that GEOM has floats? it looked like ints to me.. or fixed point floats but not ieee ### floats

1997 uhh software render was still popular and so was vertex animation
I said that because this one model is devided into many poses and the
files together are bigger than what is needed today for a single model
with a skeleton and its textures

I find that at this stage the only thing left to do is to visualize the file
so I suggest you grap your compiler and try to read vertices somewhere in the file to see if a shape comes up :)

I'm sorry I don't have 010 :(
Edit: oops forgot to add the vertex part
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-22T18:39:00+00:00
- Post Title: need help with DK2 models

You can grab a trial [here](http://www.sweetscape.com/010editor/). It's really worth a try.
Nevertheless those files are only text files with C-like structure definitions.

I can't say for sure, but GEOM (in MESH files!) seems to hold vertices. I imported the ones of an imp into 3ds Max and the vertices indeed made up something that looked like an imp, you could see the feet, arms, and the knapsack.
And if you look at those claimed_floor files you will also see that it fits (4 vertices there).
The only strange thing is that the values are very small, always 0,....

So those VERT data could be the vertex positions for the individual frames?

Currently I'm searching for the faces. As I said, those claimed_floor files don't have any ANIM files, so there must be some face definitions in there.

Edit:
The SPHD chunk contain 16 (mostly, this value is specified in the mesh header) ints at the beginning.
The SPRS subchunks contain an amount of bytes at the beginning that is equal to the sum of all the values in those 16 ints.
After that there are a number (specified in the header) of such structs:

```
		short uk1;
		dword uk2;
		dword uk3;
		dword uk4;
		dword uk5;
	} unknown;
```
## Post #6
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-03-22T19:45:41+00:00
- Post Title: need help with DK2 models

I'm so sorry I missed the part about the GEOM chunk in Mesh and anim files >.< I was looking at anim files hehe

likle you said, it is possible that the anim files have vertices composing a model or a morph target in them

it always seemed strange to me that vert and poly where inside the anim chunk and not the mesh one


as for the floor files... this can sound can kind of crazy and it is.. but maybe its the int8s from the sprs chunk >.<? because the model vertices never exceed 256 lol... uhh that just doesn't sound right but there are only 4 vertices in floor1_1 and I can't see anything else that could make sense

the sprs struct is more like

{
int16
float
float
float
float
}

it fails some times thought but I think they are matrices - positions, scene
graph, what ever
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-22T20:00:54+00:00
- Post Title: need help with DK2 models

Yeah I only know that they are dword sized, can be floats of course.
I forgot that there's still another int coming before those bytes in SPRS chunks.

Edit:
The number of bytes in SPRS is equal the described sum multiplied by 3! So this could indeed be some triangle definition.
The indices in those bytes range from 0 to the number of structs that follow those bytes.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-10T13:16:49+00:00
- Post Title: need help with DK2 models

So here the current binary template, maybe someone can help using this as a start.
Any help is appreciated, this format makes me go crazy 

P.S.: Are you still alive alera?  You aren't online in ICQ anymore.
[Keeper 2 KMF.rar](https://xentaxbackup.github.io/file/1115_Keeper 2 KMF.rar)
## Post #9
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-10T13:39:06+00:00
- Post Title: need help with DK2 models

Here another set of example files containing the files for the imp. The special thing about this one is that imp.kmf is a mesh file.
The archive also includes a maxscript I generated out of the imp.kmf. If you load it, you can see the contours of the imp. The faces aren't right, this was just a test.
[Imp.rar](https://xentaxbackup.github.io/file/1116_Imp.rar)
## Post #10
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-04-10T18:19:53+00:00
- Post Title: need help with DK2 models

I'm really sorry Rheini I was not able to access the internet for a month

I believe I figured out how to assemble the faces but I don't know how the coin is supposed to look like in the first place >.< everything in the screen shot you showed me is crooked and curvy

The file uses LOD and triplets, there dons't seem to be a distance setting anywhere so I guess the LOD is only used for the 'detail' setting in the game if there is any, if it don't have then it was just unimplemented but the mesh files do have LOD

2 polys for the floor and 2 levels of detail, one using only 1 triangle and the last level is 0 in most files, the extra vertex is there for the lower level of detail(floor had 3 vertices)

Summary for the mesh files:
Main LOD index - the 16 int32s
LOD index buffer - the array of char
extended vertex buffer - this one has the normals(fixed point)
simple Vertex buffer - at the end of the file

To assemble the model one must read from the LOD index buffer from the main LOD index to choose the correct level of detai, the LOD index buffer assemble the vertices stored in the extended vertex buffer that in turn use the vertices from the simple vertex buffer :D makes any sense?
## Post #11
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-10T18:44:11+00:00
- Post Title: need help with DK2 models

Trying hard to understand it 

Edit: Think I got it now.
But why are there so much "1" entries in the main index all having the same verts?
Makes no sense to me.
As well, why is there another entry for vertex 2 for the low detail version? 
The only difference in the entry is that uk that seems to be some kind of flag.
And why are there so many entries for LOD? You can't zoom out that much that the model has to be reduced in such a way.

Edit 2: Fuck this really works! Great job man!
Tested it with some models, now the faces are correct. Of course I couldn't test if the normals and all that stuff is correct 
Here the current v0.30 template and the script to output the maxscript file for loading a model.
[Keeper 2 KMF.rar](https://xentaxbackup.github.io/file/1118_Keeper 2 KMF.rar)
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-04-15T18:20:15+00:00
- Post Title: need help with DK2 models

Here a separate template for animation files, it reads them correctly though not all parts are figured out yet.
The SPRS part holds nearly the same data like the mesh files, so that must be the cause for some creatures having no static mesh files.
[Keeper 2 KMF ANIM.rar](https://xentaxbackup.github.io/file/1126_Keeper 2 KMF ANIM.rar)
## Post #13
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-07-02T11:32:22+00:00
- Post Title: need help with DK2 models

Any updates here? alera?
## Post #14
- Username: alera
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Oct 06, 2006 9:33 am
- Post datetime: 2007-07-21T18:49:49+00:00
- Post Title: need help with DK2 models

<-- Dead.

Life has been a little hectic lately and I can't seem to concentrate one on one thing very well hehe ^^(I had a terrible night yesterday trying to figure out how to sort 3 numbers bleh)

My computers video card is currently overheating so I am unable to use any
sort of hardware acceleration until I can fix it. In other word, I can't visualize anything :P

I'll see if I can get my software rasterizer working and look into the anim files
## Post #15
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-01-14T10:38:43+00:00
- Post Title: need help with DK2 models

Since I do not like this game/model. It is hard for me to look deep into it.

the only things I can found are:
Basic file structure

```
  HEAD
  MATL
  MESH/ANIM

```


MESH structure

```
  chr[]        Mesh_Name
  dword        SPRS_Count     //Faces data with different material
  dword        Vert_Count
  float X 4    ??             //bounding area??
  dword        Part_count     //each SPRS data sub-divided into part
                              //maybe for animation
}
CTRL           ??
SPHD {
  dword X Part_count   Face_Count
  dword                Index_count     //for index ref to vert
}
SPRS {
  dword       ??                    //always 00
  struct FaceIndex { 
    byte X 3                        //Reference to IndexData
  }
  struct IndexData {
    word       Vert_index           //Real ref to vert
    float        ??
    float        ??
    float        UV                 //Not sure??
  }
}
GEOM {
 float X 3     VertXYZ
}

```


So SPHD and SPRS must be in pair

Hope this help!
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-14T10:50:42+00:00
- Post Title: 

> Reply from fatduck
>
> Since I do not like this game/model. It is hard for me to look deep into it.
Thanks for still looking into this mate
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-06-19T15:09:28+00:00
- Post Title: 

any updates here?
## Post #18
- Username: alariq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 22, 2008 11:04 pm
- Post datetime: 2008-11-22T15:36:57+00:00
- Post Title: 

texture coordinates can be extraced as follows: 
x = (UV >>16)/float(1<<16);
y = (0x0000FFFF  & UV)/float(1<<16);

X and Y could be swapped, i cannot check what is correct because do not have texture
## Post #19
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-22T19:13:49+00:00
- Post Title: 

Unfortunately I can't provide you with texture samples cause they use an unknown compression: [viewtopic.php?f=18&t=2580](http://forum.xentax.com/viewtopic.php?f=18&t=2580)
## Post #20
- Username: alariq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 22, 2008 11:04 pm
- Post datetime: 2008-11-28T08:51:13+00:00
- Post Title: 

Yes i know, seems the only way to find out a compression algorithm is disassemble dkii.exe and trace it    any considerations?
## Post #21
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-28T09:52:34+00:00
- Post Title: 

Of course I already tried that, but it's hard to find the algorithm. Haven't had any luck yet.
Maybe I'll give it another try when I have my 2nd monitor (if I ever manage to buy a new one).
## Post #22
- Username: alariq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 22, 2008 11:04 pm
- Post datetime: 2008-11-28T10:22:15+00:00
- Post Title: 

Can you tell me from what did you started? Some gudelines  i also want to try, who knows
## Post #23
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-28T11:08:12+00:00
- Post Title: 

Not sure, but since there is no magic ID, I probably set a breakpoint on CreateFile and ReadFile trying to get to the memory address where the texture data resides. Then I set a "breakpoint on access" on the data.
But IIRC it didn't break. Maybe they pass the compressed texture to the graphics pipeline.
## Post #24
- Username: alariq
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Nov 22, 2008 11:04 pm
- Post datetime: 2008-11-28T12:11:03+00:00
- Post Title: 

aha same as i expected but you know if they pass it compressed to grafic pipeline this is even better  this way we can find out texture format, 

i'll try to see when i'll have some thime

btw, what debugger did you use?
## Post #25
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-28T12:19:03+00:00
- Post Title: 

Good old OllyDbg 
And sometimes I use IDA for disassembling, but I'm not very experienced in using this tool. Thus I only use basic functions, mainly the graphical view.
## Post #26
- Username: dedesite
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Apr 17, 2010 6:47 am
- Post datetime: 2010-04-26T18:02:32+00:00
- Post Title: 

Hi,

I try to load .kmf model into .mesh ogre3d files. I successfully manage to read the vertices and normals seems fine, but I don't know where are the uvs.
Fatduck says it's in Vertex Data struct but I think these structure is for Normals and faces index as Rheini found.

Does someone knows how to read uvs?

Greetings,
Andréas
