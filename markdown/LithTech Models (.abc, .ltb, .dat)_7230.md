## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-24T15:03:39+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

LTB script: [http://db.tt/WhaVroBD](http://db.tt/WhaVroBD)
ABC script: [http://db.tt/N8KeCn5o](http://db.tt/N8KeCn5o)
DAT script: [http://db.tt/ogpsoZNY](http://db.tt/ogpsoZNY) (maps and stuff, only for files with idstring 85 for now)
DTX script: [http://db.tt/jVR8Q8kr](http://db.tt/jVR8Q8kr) (does not work for many files. For me anyways)

Overview

Models are in .abc, .lta, or .ltb format.
lta probably stands for "lithtech ascii" while ltb stands for "lithtech binary"

I am not interested in the lta files. It is a text file and is a pain to parse. Good for reference, but that's it.

Info

Some info from Tron: [http://www.ldso.net/tronwiki/doku.php?i ... htechfiles](http://www.ldso.net/tronwiki/doku.php?id=wiki:article:tronfaq:editing:lithtechfiles)

I'm looking for any specs or tools that are already out there.

I know they have plenty of modding tools already for particular lithtech games (I think monolith even provided a set of tools themselves awhile ago).

Dtx format specs would be nice.
If not, a standalone dtx exporter would also be nice. I don't like how existing tools just rely on milkshape, photoshop, or dedit.

Samples and games

Aside from info, I'm also looking for samples from various games using LithTech engine (all versions)
So far the samples I have are from

Might and Magic 9: abc
Combat arms (LithTech jupiter)
Sudden Attack (LithTech jupiter)
Zu Online: ltb
Atlantis: Search for the Journal: abc
Crossfire Online: abc
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-18T23:57:35+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Revisiting this format.
LithTech engine seems to be used for a lot of 3D games. At least, old ones anyways.

Someone sent me supposed specifications, but they were only for a specific game.
It is still useful, because the structure of each node should be similar.

I am looking for abc samples from a variety of games. The generic structure looks like it's a bunch of nodes with pointers to the next node. So pretty much a linked list.

One can parse the entire format by simply doing something like

```
nextNode = self.inFile.readInt()
while nextNode != -1:
	print(node)            

	#go to the next node
	self.inFile.seek(nextNode)
	node = self.read_name()
	nextNode = self.inFile.readInt()            

```


And then just read the node name and determine which function to call.
Some people might notice a logical flaw in this code: it doesn't parse the last node.

Lol, which is true. I guess I'll probably just build a list of nodes and go back to parse each one individually.
All information is welcome and encouraged. If there are already tools for this format that would be great as well.
## Post #3
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-02-21T13:12:53+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-21T15:28:16+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Ltb format I have a couple from Zu Online.
Would be interesting to see if there is a general data structure.

I've read that there are two dtx format (generic one from lithtech, and some version used by nexon which is basically the same thing except they just switched the first 12 bytes of the header??)

There seems to be some pascal source code for LTB format but it was only for a specific game and it hardcodes a bunch of offsets.

the ABC format was pretty easy to figure out its general structure, but the LTB not so much.

I don't know the format for the dtx files.

Here's something I quickly threw together from the zu online ltb's

I'm still stuck on which value indicates which mesh type I'm looking at, considering how there are 4 different vertex types already.

It's basically

```
numMesh Mesh
   numSubmesh Submeshes
Bones
Animation

```


```
	word
	word
	dword[4]
	dword[3]
	dword numBones
	dword[10]
	word[2]
	dword
	word len #may be 0
	len "Shadow Enable"
	float
	dword
	dword numMesh
}

Struct Vertex {

	if type == 
		32 bytes
	elif type ==
		36 bytes
	elif type ==
		40 bytes
	elif type == 
		44 bytes
}

Struct Face {
	word[3] v1, v2, v3
}

struct unk_struct {
	dword count
	count {
		12 bytes
	}
	byte

Struct submesh {
	dword 1
	dword 2 
	dword 1
	dword 2 
	dword 3
	dword (0, 1, 2, 3)
	byte ?
	dword
	dword sectionSize (from now until the end of unk_struct)
	dword numVerts
	dword numFaces
	dword[2]
	dword 0x13
	if type == ?
		byte[13]
	else if type == ?
		byte[12]
		dword
	endif
	numVerts Vertex
	numFaces Face
	
	unk_struct

Struct Mesh {
	word len
	char[len] meshName
	dword numSubmesh
	if numSubmesh == 1
		dword[1]
	elif numSubmesh == 3
		dword[3]
	dword
	dword
	numSubmesh Submesh
}

Struct Bone {
	word len
	len Name
	word boneIndex
	byte ?
	float[16] matrix
	dword
}

Struct Animation {
	?
}
	

```
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-21T18:41:22+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Got some LTB models out for Zu Online.
Freezes on some models though. Assumes textures are located in a folder called "texture"

I'm hardcoding material names and skipping a whole section in the submesh because I don't know which flag to check.
This works for Zu Online because they name their textures like "name", "name_a", "name_b", but this won't work in general.

For the dtx files, I'm also just doing some hardcoding here and there.

Model import: [http://db.tt/WhaVroBD](http://db.tt/WhaVroBD)
Textures: [http://db.tt/g8MZyIBy](http://db.tt/g8MZyIBy)
## Post #6
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-21T22:53:41+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

very good job, the truth that is at work all, congratulations for your skills.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-21T22:56:51+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Here's another ltb model from a different game.
Someone sent it to me but I'm not sure which game it is.

I'm guessing lta is the ascii version while ltb is the binary version.
Neither of them seem to store the material information, or at least I don't see it (the model file is called "model67" but the textures are called "zom", which is not obvious).

The good thing about that is it becomes easier to figure out what's what. Trying to parse the lta directly is kindof annoying because text-parsing is pretty annoying in general (compared to binary anyways)
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-21T23:58:51+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

> Reply from finale00
>
> 

Here's another ltb model from a different game.
Someone sent it to me but I'm not sure which game it is.

I'm guessing lta is the ascii version while ltb is the binary version.
Neither of them seem to store the material information, or at least I don't see it (the model file is called "model67" but the textures are called "zom", which is not obvious).

The good thing about that is it becomes easier to figure out what's what. Trying to parse the lta directly is kindof annoying because text-parsing is pretty annoying in general (compared to binary anyways)well freaky model xD, about game maybe is one of same companies of LithTech or too can ask guy who send you file
## Post #9
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2012-02-22T03:28:12+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

That's from crossfire online. (a mutant character called smoke, or something like that)
## Post #10
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-02-22T05:29:50+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

> Reply from finale00
>
> http://i.imgur.com/K3KLg.jpg

Here's another ltb model from a different game.
Someone sent it to me but I'm not sure which game it is.

I'm guessing lta is the ascii version while ltb is the binary version.
Neither of them seem to store the material information, or at least I don't see it (the model file is called "model67" but the textures are called "zom", which is not obvious).

The good thing about that is it becomes easier to figure out what's what. Trying to parse the lta directly is kindof annoying because text-parsing is pretty annoying in general (compared to binary anyways)

Whoa! Nice to see this. Is it can load animations yet?
textures name is "zom" for zombie. I have extracted it via Hex a long time ago. Model name is "model67" because i use ltb extractor on MPGH

.LTA lost UV because of ltb2lta tool. And .abc convert from .lta via ModelEdit Talon so it lost UV too.
I can rip all .LTB model by the way import it to "No one lives forever 2"
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-22T05:58:26+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

No unfortunately I don't really understand animations all that much aside from the fact that they use keyframes...
## Post #12
- Username: Seyiji
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Sep 20, 2011 11:37 pm
- Post datetime: 2012-02-24T00:15:23+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

> Reply from finale00
>
> I am looking for abc samples from a variety of games. The generic structure looks like it's a bunch of nodes with pointers to the next node. So pretty much a linked list.Here is a sample character file from Atlantis: Search for the Journal a game I got in a cereal box years ago 

[http://db.tt/qO1wkLcU](http://db.tt/qO1wkLcU)

Your plugin imports the model but its all pointy polygons and jumbled together.
## Post #13
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T02:38:09+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Ok cool I figured out the geometry. Previously I got it all wrong lol
It now parses the atlantis model, and all the might and magic models correctly as well.

I don't know which version these abc files are, but I haven't seen any other versions either to figure out how to check.

Now the next step is to get the dtx out. I think they have tools for that already though.



```
struct Face {
	float[2] UV1
	word v1
	float[2] UV2
	word v2
	float[2] UV3
	word v3
}

struct Vertex {
	word bone count?
	word ?
	count {
		dword bone index?
		float[4] weights?
	}
	float[3] vx, vy, vz
        float[3] nx, ny, nz
}

struct Submesh {
	dword numFaces
	numFaces Face
	dword numVerts
	numVerts Vertex
}

struct Mesh {
	word
	float[3]
	word
	word len
	char[len] meshName
	numSubmesh Submesh
}

```
## Post #14
- Username: Seyiji
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Sep 20, 2011 11:37 pm
- Post datetime: 2012-02-26T02:31:45+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

> Reply from finale00
>
> Ok cool I figured out the geometry. Previously I got it all wrong lol
It now parses the atlantis model, and all the might and magic models correctly as well.

I don't know which version these abc files are, but I haven't seen any other versions either to figure out how to check.

Now the next step is to get the dtx out. I think they have tools for that already though.Milkshape says that Atlantis file is version 13.
## Post #15
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-15T08:01:40+00:00
- Post Title: LithTech Models (.abc, .ltb, .dat)

Hi!
finale00, you say it opens .abc files with Noesis, but I only found .ltb there. Could you please tell me how to
open those .abc files (Might and Magic 9).
May be I did something wrong: I put in Noesis\plugins\python these files:
fmt_ZuOnline_ltb.py
fmt_LithTech_dtx.py
rapi_model_template.py
__init__.py
Sanae.py
I don't remember what version of python I installed - probably 2.6.
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T18:05:24+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

It's in my dropbox folder.
## Post #17
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-15T18:59:48+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

Thanks!
But though I could get the textures there seem to be no texture coordinates. I used 3ds max 7 and tried
converting models into .obj, .dae, .smd - but still the models didn't have tex coordinates. 
And is it possible to get bones/animation?
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-15T19:07:56+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

I don't have texcoords for abc's because I never loaded them since I don't know how to get the textures.
What did you use?

I'll add skeleton when I get around to figuring that stuff out.
## Post #19
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-16T04:59:08+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

The Textures are in the Data\Skins.rez file. They are in .DTX format, readable and convertable by your Noesis plugin.
To unpack the .rez files I used “Dragon Unpacker” (maybe version doesn’t matter, but just in case ver.5, or 5.6.2 more precisely). I downloaded it from google search by typing ‘Dragon Unpacker’. 
Models are in the Data\Models.rez and then in Models.rez\Models . There are also some subfolders in Models.rez\Models\Gibs like: Cat, Dagrel, Dragonfly – there are files in those folders called like Bones for them: Bip01 Head.abc, Bip01 Pelvis.abc etc.
## Post #20
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T13:15:33+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

I don't read dtx files properly so many of them cannot be read.
In particular I couldn't read most of the MM9 textures (I could read some simple ones like effects).
## Post #21
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-16T15:41:28+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

Here are 3 sample models from Might and Magic 9 - .abc models (Banshee,Basilisk and Bigfoot) and their .tga textures (2.5Mb)
[https://rapidshare.com/files/2614279712 ... Models.rar](https://rapidshare.com/files/2614279712/3SampleModels.rar)

And 4 extracted folders (almost the whole game): Models, Skins(aka Textures for models) and some more, it also includes Dragon Unpacker 5, but it’s not needed for these files since they are already extracted with it (it extracts .rez game files). Textures in Skins folder are both in dtx and tga (302 tga(s)).
Models are in: Extractions\Models_Rez\MODELS
Their textures are in: Extractions\Skins_Rez\SKINS
[https://rapidshare.com/files/3305677300/Extractions.rar](https://rapidshare.com/files/3305677300/Extractions.rar)
(235Mb)

This is how I got textures:
1 – Extracted with Dragon Unpacker the .rez files from the game
2 – Thus I got textures in .dtx format. They were extracted from Data\Skins.rez 
3 – I opened Noesis (with your dtx plugin) and all the textures from that .rez file were viewable very well, and I used Tools->Batch Process-> Input extension: DTX, Output extension: TGA, addidional parameters I didn’t change (they were -texpre "$inname$_") and pressed the button Folder Batch. Picked Skins.Res\Skins (it’s where I extracted dtx from rez) and OK.
So, I got all the models textures from that folder – I found no problems with reading dtx files with your Noesis dtx plugin. (302 tga(s) are in that Skins.Res\Skins folder)
## Post #22
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-16T17:22:59+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

I found a mistake. 
If you use Noesis plugin to extract the .rez files it extracts not all of their contents. For example, if I extract the Might and Magic 9 file MM9\Data\SKINS.REZ where the models textures are stored, the Noesis extractor will extract only  2 subfolders: GIBS and PROPS in the folder SKINS.
And if I extract SKINS.REZ with Dragon Unpacker 5, it extracts in the folder SKINS (in its root)  303 DTX files (they are the models/monsters textures) and the following subfolders: GIBS, MODELPROPS, PICKUPITEMS, PROJECTILES, PROPS, SPELLS, WEAPONS.
Just in case, here’s the Dragon Unpacker 5 setup file separately:
[https://rapidshare.com/files/715099791/ ... 5setup.rar](https://rapidshare.com/files/715099791/DragonUnpacker5setup.rar)
(3Mb)
## Post #23
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T18:53:51+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

aluigi has a bms script for lithtech rez archives. I used that.

[http://aluigi.altervista.org/papers/bms/rez.bms](http://aluigi.altervista.org/papers/bms/rez.bms)

But still, I'm surprised my dtx plugin loaded some textures lol

Anyways like the ltb format, I don't know how the textures are assigned.
For example in banshee, I can see that there are 5 textures labeled A B C D E, whereas in basilisk it has 2 and...no number for the first one. While bigfoot uses 1 2 3.

There's no obvious pattern at all.
Maybe there is another file that indicates which materials are used, and each mesh simply specifies the index for it, but I don't see anything like that in the files. In fact, I don't even see any way to distinguish which meshes use what materials. There are some unknowns in the mesh, but they don't seem to change across meshes. Submesh doesn't have any unknowns.

There doesn't seem to be any material names in the model itself...and even if the index represents which texture to use, they don't even have consistent naming schemes...

I have updated the script to load UV's (though I did a pretty brute-forced job at it, will make it look more sophisticated at a later time), but it doesn't automatically load textures, and it assumes all meshes use the same material.
## Post #24
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-16T20:03:17+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

Do you mean that there are the texture coordinates now? I exported from Noesis with the new version of the .abc plugin, but found no tex coords. I tried exporting to .dae - the model consisted of many parts some of which seemed to be the same, and to .obj, but no tex coords. If you had the models textured, could you please tell me how to do it - maybe I should use some 'advanced options' when exporting from Noesis, like -forcetc (I tried it, but it didn't help). And how to use that rez.bms file to extrace .rez? May be the .abc files I exported with Dragon Unpacker and with Noesis plugin are wrong, since I don't have tex coordinates.
## Post #25
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T20:17:41+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

There should be.

While the materials are assigned wrong, it does group them by mesh, so assuming all faces for a single mesh use the same material, you could still manually assign the appropriate textures.

(currently it assumes the texture used is the same as the model name, so I just renamed one of them)



It actually looks like each variation is just a different palette, which makes sense, might and magic games like to use different colors to distinguish between monsters of the same kind.

But either way, there's no pattern to the texture names.

Btw the transparency is kind of messed up. When I loaded the textures normally nothing showed up...
## Post #26
- Username: Antonkf
- Rank: n00b
- Number of posts: 15
- Joined date: Sun Feb 19, 2012 1:47 am
- Post datetime: 2012-03-17T05:43:04+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

Cool! Thanks a lot!
And did you find there any bones/animations?
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-17T07:25:46+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

I would assume that's what the other nodes are, but I don't know the format.
Maybe later.
## Post #28
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-02T02:13:49+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

.dat map format added to the list.
Samples: [viewtopic.php?f=16&t=8674](http://forum.xentax.com/viewtopic.php?f=16&t=8674)

It is difficult to do type checking and only checks the first one to see if it's a particular integer.

Just from combat arms and MM9 alone, it's evident that they both share similar structs, but also have different structs because the version is different. I will be re-factoring the plugin so that I can use a single parser where each of the different versions is implemented as separate interfaces.
## Post #29
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-04-02T15:22:31+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

Some sample from [Sudden Attack](http://en.wikipedia.org/wiki/Sudden_Attack):
[http://www.mediafire.com/?bthzqd3925hv5o1](http://www.mediafire.com/?bthzqd3925hv5o1)
This game have a lot of idols: BIGBANG, 2Ne1, Bi Rain, ...   
In this sample is Rain   
Weapons ltb is encrypt or something so I can't convert.
Characters ltb contain 4 or 5 models (low -> high poly) and all animations. LTB2LTA can get one model with UV (i thought). Use ModelEdit Talon can convert lta to abc and it can be import with ms3d (only have mesh, uv, bone)
Most of map can be import with your plugin, map in this sample can't import

Thank you very much for all plugins!
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-02T18:27:35+00:00
- Post Title: Re: LithTech Models (.abc, .ltb)

The ltb format is the same. There was a typo in the code where I assigned matName instead of texName. The material assigning is pretty much all wrong and I should delete it from the script completely because it's wrong.

Of course I still don't know how the texture names work. Maybe I should convert some of those ltb's to lta's and see what texture they use? Might give some clues. The faces are a little messed up though. Wonder what the issue is. The LTB plugin should assign UV as well.

For the dat file, it is the header again. The fact that it loads up some of them fine means that I might be on to something, but the ones you uploaded follows the same pattern but has some more bytes. There might be specific integers I should be reading but am overlooking.



I am kind of surprised some of the dtx loads. The tronwiki says that dtx files are just based on the dxt format, but I don't know...
Maybe I am just missing one or two flags for the other dtx.

Still don't know where the UV's are for the .dat file.
## Post #31
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-04-07T04:19:06+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Basic dtx format can now be loaded...somewhat. The offset might be off a little...not sure.

Both variations of it (I think people in the modding community refer to them as "nexon" vs "lithtech" although I don't see much of a difference besides where the width/height is stored)

eg:

```
check = self.inFile.readUInt()
if check != 0:
	self.inFile.seek(-4, 1)
	width, height = self.inFile.read('2H')
	self.inFile.read("2L")
else:
	self.inFile.readInt()
	width, height = self.inFile.read('2H')   

```


Here's a model from MM9



Unfortunately the textures related to maps (ceiling, floors, etc) seem to have compressed pixel format...don't know how to deal with those yet. But I haven't found the UV's for the map files either so it doesn't really make much of a difference.
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T04:27:26+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Started looking at world files from Might and Magic 9 cause I enjoyed the game. It was built on an earlier engine but the format is somewhat similar to the combat arms and stuff.

Really don't like the fact that the faces can be whatever they want it to be. Triangles, quads are common, but then there are 5-sides, 6-sides, 7-sides, .........
## Post #33
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T08:23:50+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

After some hours only got the meshes out for maybe 2 or 3 models...lots of unknown structs.
Already having problems just skipping the header.
## Post #34
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-22T17:27:24+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Looks like your dtx plugin makes BGR textures instead of RGB.
I convert pallete for your samples:
[](http://clip2net.com/clip/m144578/1345655285-24sob-225kb.png)[](http://clip2net.com/s/2ekhT)[](http://clip2net.com/clip/m144578/345655566-w4qlm-180kb.png)[](http://clip2net.com/clip/m144578/1345655428-ikc9r-202kb.png)
Last one looks suspicious, so i google a little and find that screen:
[](http://clip2net.com/clip/m144578/1345655822-might-and-magic-ix-windows-screenshot-lich-kings-101kb.jpg)
So, problem exist.

LTB2X converter has sources on download page, not sure about posting direct link here, so google "ltb2x" and check out page with "cote-duke" in their adress.

And point me out to good manual how-to-put-your-plugins-to-noesis =)
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T17:45:03+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Just take the script and put it in the python plugins folder.
I looked at the source but I think it is only for a specific game and not ltb in general.
## Post #36
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-22T18:30:04+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I try LTB2X with "Combat Arms" game and models converts fine, but without smoothing groups and materials (didn't check for UVs).
Upload sample for you [here](http://zalil.ru/33699990).

Got plugins to work after reinstall Noesis with latest version, but some error pops up when i select dtx-file (no preview, but ask for convert).
I used DTXConvert v1.0 by BlackAngel and converted textures from "Nexon" type to "LithTech" type, and error gone but textures displays black.
## Post #37
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T19:41:31+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I don't know the dtx format I just randomly assume it is rgb. Some may be RLE compressed I don't know.

I just went to look at my plugin and noticed that I had already realized it was BGR but never uploaded it lol
## Post #38
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-22T20:09:24+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I found Photoshop plugin for DTX and some info about format - "Nexon" type used only in "Combat Arms", and conversion to "LithTech" type is required for compatibility with Photoshop plugin.
[http://www.blackangel-software.com/?q=lithtech](http://www.blackangel-software.com/?q=lithtech)
## Post #39
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T20:13:37+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Unfortunately I don't have photoshop (lol only have paint.NET)

I have found the format using texture finder



Currently looking into the rest.

I've updated the plugin to load a couple DXT1 and DXT5's. There's probably some DXT3's somewhere.
Now I can properly look into map files for UV data.
## Post #40
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-22T21:22:17+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I figured out this format =)
It's DDS with modified header:
[](http://clip2net.com/clip/m144578/1345670056-clip-154kb.png)
([sample](http://zalil.ru/33700294))

Format variations from nVidia DDS photoshop plugin:
[](http://clip2net.com/clip/m144578/1345672603-dds_variants-15kb.png)
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-22T21:59:11+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Well, hopefully ilthtech only used the common ones lol

The general issue I had with ltb and abc files was the fact that I didn't know how the material names worked.
Some monsters have different colors, so the textures would be named like "monster1", "monster2", etc.

Or it might be something like "monsterRed", "MonsterBlue"

Totally random, and there were no texture names inside ltb/abc files. Might have been in a string table somewhere in some archive I didn't bother looking at.

The mesh format should be ok. Skipped a bunch of stuff, but ya.
## Post #42
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-23T11:48:05+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Forgot save options for DTX:
[](http://clip2net.com/clip/m144578/1345707735-clip-5kb.png)

> Reply from finale00
>
> Totally random, and there were no texture names inside ltb/abc files. Might have been in a string table somewhere in some archive I didn't bother looking at.
For MM9 it's in actor.txt or/and monsters.txt inside data.rez.
Standart text file separated with tabs, easy to open in excel:
[](http://clip2net.com/clip/m144578/1345716029-clip-117kb.png) [](http://clip2net.com/clip/m144578/1345716202-clip-117kb.png)

For Combat Arms all text i found is encrypted...
But you can assign materials to objects with texture named same as object name, some of them correspond.
Much better than without materials / texture names.

Found some obsolete ABC format description (v6, MM9 is v13 i think): [http://www.bop-mod.com/download/docs/Li ... ormat.html](http://www.bop-mod.com/download/docs/LithTech-ABC-v6-File-Format.html)

Also found that LTBtoLTA commandline tool with -debug key generates interesting files - looks like models and bones in txt format ([sample](http://zalil.ru/33701123)). And this tool has "-view" switch that separates models like hands or guns from others (dunno why, but must be important).

Now i downloading "Lithtech Jupiter Enterprise with NOLF2 Source" - maybe i can find some interesting sources.

Full(?) LithTech games list here: [http://www.moddb.com/engines/lithtech/games](http://www.moddb.com/engines/lithtech/games)


Converted model to .X then .obj and export from Noesis same model to .ojb, add material and textures and get this:
[](http://clip2net.com/clip/m144578/1345723684-clip-131kb.jpg)
Your variant has just one object with incorrect name and flipped UVs 
Even smoothing looks wrong:
[](http://clip2net.com/clip/m144578/1345724298-clip-112kb.png)
But this knife has strange normals:
[](http://clip2net.com/clip/m144578/1345724661-knives-nrm-451kb.png)
(left is yours, left side of handle has inverted normals for both models)

In LithTech model "editor" smoothing looks similar to yours:
[](http://clip2net.com/clip/m144578/1345725111-clip-36kb.png)
So, maybe there nothing to to, but unsmoothed result of LTB2X looks good for knife...
## Post #43
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-23T17:37:56+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I don't actually know where the normals are. And yes my UV's are always flipped. I'm not sure how to flip them lol

But...face normals AND vertex normals...?
How does that work? I've never seen that before.
## Post #44
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2012-08-23T21:23:11+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from finale00
>
> But...face normals AND vertex normals...?
How does that work? I've never seen that before.
I resolve that buggy normals:
[](http://clip2net.com/clip/m144578/1345755649-clip-194kb.jpg)
it's modelling bug or knife handle is transparent - this normals is from rivets inside handle )

> Reply from finale00
>
> I don't actually know where the normals are. And yes my UV's are always flipped. I'm not sure how to flip them lol
Maybe rotate textures or read they backward?..
## Post #45
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2012-09-10T06:52:12+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

For those still working on these LithTech files, there is a file floating around called nolf2_gpl_src.rar which seems to contain source code relevant to the LithTech engine and its inner workings.
## Post #46
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-10T14:11:23+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

@jfwfreo: [http://www.mpgh.net/forum/242-crossfire ... -info.html](http://www.mpgh.net/forum/242-crossfire-hack-source-code/430636-lithtech-jupiter-enterprise-suite-see-inside-info.html)

you mean this?
## Post #47
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-09T03:03:20+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Hello and greetings from the far corners of the internets. I'm new as you can probably tell, and  was a little worried about necroposting until I realized my newbie status limits this account to posting in old threads (at least I think that's how it works). 

So on with the request. Every lithtech model format has the ability to have child models added or removed  to and from nodes except for the first one(s), abc version 6-8. (blood2, kiss psycho circus, shogo MAD) There are 3dsmax plugins that come with the tools which are quite worthless save for 3dsmax version 2, a hard to find item. So my request is this:

Are there any kindly-type coder folks out there who would like to take a try at making us a pluggin for noesis? There are more than a few modders out here who would be mighty grateful.

In kindness and good will,
zZaRDoZz
## Post #48
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-16T04:37:27+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

For those of you out there who might be curious as to why anyone would want to work with such an old and clumsy format, I can only point to this:

[http://www.autodesk.com/products/softimage/overview](http://www.autodesk.com/products/softimage/overview)

ImageSoft was the software used to create many of the original models for early lithtech games. Now that they're shutting down, there is no way currently to edit or create abc models, at least not in the old format..
## Post #49
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-16T10:38:37+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from zZaRDoZz
>
> who would like to take a try at making us a pluggin for noesis?there are some Noesis py scripts from finale00: fmt_LithTech_abc.py and fmt_LithTech_ltb.py for example
## Post #50
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-16T18:55:07+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> there are some Noesis py scripts from finale00: fmt_LithTech_abc.py and fmt_LithTech_ltb.py for example
First off, thank you shakotay2 for replying.

 I've dl'ed some of finale00's scripts and have used them to view models from nolf 1 and 2.
I haven't been able to find a py script for Shogo m
ad or Kiss psycho circus though (abc versions 6-8). Also, while converting such models to obj. format is great for extensive modifications, I'm hoping to save changes to the actual abc model, like adding new nodes, changing meshes, maybe even new animations. I know that's a tall order, so my chances are slim. 

Still, our small community would be grateful for even the ability to add child models, as the model viewer for nolf and avp2 can already do.
## Post #51
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-17T02:58:28+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from zZaRDoZz
>
> I haven't been able to find a py script for Shogo mad or Kiss psycho circus though (abc versions 6-8).If you uploaded a model sample I could have a look at.

> Still, our small community would be grateful for even the ability to add child models, as the model viewer for nolf and avp2 can already do.Do you know what that does mean technically, "add child models" to a model?
It's not just like creating a submesh, is it?
## Post #52
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-17T05:33:21+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Please bare with me on this as filefactory has been less than fully cooperative.

This should contain 2 versions of lithtech modeledit and 2 folders with models in them. I only say that because I've had filefactory upload a correctly labeled folder that had something else from my desktop in the distant past. -fun, fun.

[http://www.filefactory.com/file/6pa05pa ... ples6-9.7z](http://www.filefactory.com/file/6pa05pabnmvd/abcMODELviewer%26amp%3Bsamples6-9.7z)

Not sure about the child model being a sub mesh. The sample models above are from the demo versions of blood2, ShogoM.A.D, and Kiss psycho circus. Unlike lta files of later lith games, these are compiled if that makes a difference.

EDIT: Sorry about no following the file attachment protocol. If this file were small enough, it would have saved me an hour of hassle from ff. 512k size limit, that's tight.
## Post #53
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-17T16:40:50+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

while from 1X1_SQUARE.ABC the format seemed to be simple I couldn't get a decent obj from sanjuro.abc, for example.



sanjuro.JPG (134.03 KiB) Viewed 208 times



Since the source for ModelEdit is to be found in the net my question would be:
is there a source for the exe files you uploaded?

If 'no' maybe there's a convertor from .abc to .ltb?
## Post #54
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-17T22:01:32+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

shakotay2 said:

> Since the source for ModelEdit is to be found in the net my question would be:
>
> is there a source for the exe files you uploaded?

The only source released for modeledit is for the Jupiter version, see attachment.
The source for the format is available though.
[http://bop-mod.com/download/docs/ABC-Format-v6.html](http://bop-mod.com/download/docs/ABC-Format-v6.html)

[http://www.bop-mod.com/download/docs/Li ... ormat.html](http://www.bop-mod.com/download/docs/LithTech-ABC-v6-File-Format.html) 


> If 'no' maybe there's a convertor from .abc to .ltb?

There are plugins for abc version 12 that allow models to be converted. Version 6
plugins don't function even with the right software. There is one app that can load meshes for both abc v 6 and 12 called Ultimate unwrap3d. The demo version uses a plugin listed under shogo to open both 6, 12, and claims to do ltb although I could never get an ltb to load.

[http://www.unwrap3d.com/u3d/index.aspx](http://www.unwrap3d.com/u3d/index.aspx)
[ModelEdit.7z](https://xentaxbackup.github.io/file/8090_ModelEdit.7z)
## Post #55
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-17T23:43:51+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

thx for your infos - sadly it doesn't help with my sanjuro problem.
Not sure whether this TransformationIndex byte in the vertex block might help.

From the BERETTA_PV.ABC I got the hand at least. Searching for the rest...



beretta_hand.jpg (84.38 KiB) Viewed 185 times
## Post #56
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-18T01:27:34+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

That is truly awesome to see. Thank you for all this. If you knew how many modders had gone up against the infamous early lithtech file formats and gone away defeated, it would blow your mind!  

Well played sir.
## Post #57
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-18T14:45:26+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from zZaRDoZz
>
> If you knew how many modders had gone up against the infamous early lithtech file formats
For the LithTech ABC v6 File Format description it is said: "Last updated on June 19, 1999"

So the most important format infos seem to be available since many years.
But I guess the modders lost interest in the games which use this engine.

Since the last version update was 2005 it might have lost the competiton against 
other popular 3D engines (although it uses Per-Pixel-Lighting for example).

The cause might be the missing of an official SDK, who knows.

Then I realized that there is one for F.E.A.R. (fear_publictools_108.exe)
but the tools did not install with the F.E.A.R. Perseus Mandate demo despite registry hacking.
Then I tried manually installing and 1.3 GB of data were unpacked -
ModelEdit.exe and all cpps were missing - of course (although appearing in the uniextract.txt).

That's the point where it's becoming too time consuming for me.

> Well played sir.I got vertices and face indices only - that wasn't too hard.  
I think I'll release a tiny .ABC extractor as soon as I solved the sanjuro prob more or less.
## Post #58
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-19T04:33:56+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Shakotay2 said:

> So the most important format infos seem to be available since many years.
>
> But I guess the modders lost interest in the games which use this engine.
>
> 
>
> Since the last version update was 2005 it might have lost the competiton against 
>
> other popular 3D engines (although it  uses Per-Pixel-Lighting for example).

This is true, After Nolf 2 lithech settled into its role as a 'budget' engine. By the time Fear rolled onto the scene there were publicly available, open source engines that could do most of what Jupiter EX could do.

Shakotay2 said:

> The cause might be the missing of an official SDK, who knows.

Before anyone goes off  linking to the SDKs for Shogo & Blood2, those releases contained tools and the source for the game dlls, not the binaries. 

For the curious:

[http://www.moddb.com/games/blood-2-the- ... ource-code](http://www.moddb.com/games/blood-2-the-chosen/downloads/blood-2-source-code)

[http://www.moddb.com/games/shogo-mobile ... r-division](http://www.moddb.com/games/shogo-mobile-armor-division/downloads/shogo-mobile-armor-division)

If anyone suffers the  same allergy to 16 bit installers that I do, let me know. 


Shakotay2 said:

> Then I realized that there is one for F.E.A.R. (fear_publictools_108.exe)
>
> but the tools did not install with the F.E.A.R. Perseus Mandate demo despite registry hacking.
>
> Then I tried manually installing and 1.3 GB of data were unpacked -
>
> ModelEdit.exe and all cpps were missing - of course (although appearing in the uniextract.txt).

I have most of the Jupiter source release minus all the game code. That includes the source for various tools. If Shakotay2 or anyone would like me to upload anything specific, just say so.

Shakotay2 said:

> I think I'll release a tiny .ABC extractor as soon as I solved the sanjuro prob more or less.

Then I will thank you for your time and diligence again Shakotay2.
btw, VGames, modder for doom3 perfect -ted, says He can get the 3dsMax 2 plugin working for blood2 models. I'm a little skeptical, but if  he can do it, then its just another mad hunt for the right software.
## Post #59
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-20T00:39:16+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

first step done - I succeeded in separating the submeshes:



separateSMs.jpg (81.16 KiB) Viewed 144 times



Just tested it with sanjuro giving decent submeshes, too, by the sorting of the faces, very strange, since it's the same vertices.
Also half of the vertices are unused so the char is uncomplete.
I'll upload the exporter (mesh only) tomorrow so that you can test it and maybe have an idea concerning sanjuro.
## Post #60
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-20T10:48:54+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

here a test version (v0.0)


 ABC2obj.zip
(105.64 KiB) Downloaded 77 times


todo: calculate absolute positions
uvs

Note that sanjuro has 694 vertices but maximum face index is 390. Dunno why.
## Post #61
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-11-20T11:08:33+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Attached files could be helpful.
[lithtech-pc-lta.7z](https://xentaxbackup.github.io/file/8106_lithtech-pc-lta.7z)
## Post #62
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-20T12:16:36+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

thx. They possibly could if  
- you had an lta file that was derived from an original ABC v6 file.

The problem is how to calculate the positions.
The ABC v6 format specs says:
the vertex positions are "relative to object's origin".

I was thinking to add the parents pos as an offset to the child's pos.
(I don't see any matrices in the ABC files which would make things easier.)

ModelEdit shows identical Translations for parent and child bones:



sanjuro_abs_rel.jpg (114.03 KiB) Viewed 237 times



There's bounding boxes (Min/Max) for each node in the ABC file.
I'll try to calculate a median and use it as an pos offset.
## Post #63
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2014-11-20T12:33:11+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> thx. They surely would if  
- you had an lta file that was derived from an original ABC v6 file.I need to get back home to find out what makes *.lta files.
## Post #64
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-20T12:48:05+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I looked at some noone lives forever ltas which seems to be the old format that won't help with ABC format, I guess.
## Post #65
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-20T16:05:26+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> thx. They possibly could if  
- you had an lta file that was derived from an original ABC v6...

I don't know of anything like an lta for an abc v6 model, Sanity akins artifact  does have  some  abcV6 models that were later turned into abcV12 models for mm9- they are both compiled however.
## Post #66
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-11-20T17:20:54+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

did some translations:



puzzleMe.jpg (53.71 KiB) Viewed 228 times


(Looks like an improvement but sadly is far from being correct.)

This is the skeletal hierarchy:

```
                1 pelvis # NumChildren: 4
                        2 right_legu_1 # NumChildren: 1
                                3 right_legu_2 # NumChildren: 1
                                        4 right_legl_1 # NumChildren: 1
                                                 5 right_legl_foot # NumChildren: 0

                        6 pelvis_1 # NumChildren: 0
                        7 left_legu_1 # NumChildren: 1
                                8 left_legu_2 # NumChildren: 1
                                        9 left_legl_1 # NumChildren: 1
                                                10 left_legl_foot # NumChildren: 0

                        11 torso # NumChildren: 5
                                12 left_armu_shoulder1 # NumChildren: 0
                                13 left_armu_shoulder # NumChildren: 1
                                        14 left_armu # NumChildren: 1
                                                15 left_arml # NumChildren: 1
                                                        16 left_arml_hand # NumChildren: 0
                                17 head_neck # NumChildren: 1
                                        18 head # NumChildren: 1
                                                19 head_helmet # NumChildren: 1
                                                        20 head_2 # NumChildren: 0
                                21 right_armu_shoulder1 # NumChildren: 0
                                22 right_armu_shoulder # NumChildren: 1
                                        23 right_armu # NumChildren: 1
                                                24 right_arml # NumChildren: 1
                                                        25 right_arml_hand # NumChildren: 1
                                                                26 GUN_HAND # NumChildren: 0
```

and this the parent ID array which I created manually as a quick hack:
parIDs[27]= {0,0,1,2,3,4,1,1,7,8,9,1,11,11,13,14,15,11,17,18,19,11,11,22,23,24,25}

(first 0 normally being -1 but it's unused here)
## Post #67
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-20T19:33:21+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

just pm'd shakotay2.
## Post #68
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-11-29T15:56:39+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Let's see if I can get the old dat format up.


No broadband, no upload.
I'll try again later.
## Post #69
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-12-10T02:56:32+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Okay, hopefully I've got all my ducks in a row this time. Let's see...

meh, had to use filefactory.

[http://www.filefactory.com/file/1g7kg4v ... Hv1MAPS.7z](http://www.filefactory.com/file/1g7kg4v8dwcl/LITHv1MAPS.7z)

that should contain the ed. files for KPCs Bad Streets, shogo's Avernus, and their corresponding dat files.
## Post #70
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-10T13:50:37+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

here's a point cloud of a map:



07_Avernus1.JPG (37.73 KiB) Viewed 176 times
## Post #71
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2014-12-11T03:12:59+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> I'm aware of abc models having to be shelved, that's understandable. As useless as the following info probably is, please understand I' only posting it for documentation purposes.

From VGames:

> If you open up a model with a hex editor, search for a node u want to get rid of, change the 3rd character after the last letter or number of the name of the node to 01 that will null that node. Go into modeledit and select all null nodes button in the model section in top menu. Then select remove node and it will remove them but it will stick that piece of the model to the next node. We need to figure out how to stop that and get rid of the model piece altogether.
## Post #72
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-06T09:57:36+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

can you give me any script or plugin?

i have 3ds max 7 , 2011 | 2012 , maya 7 , 2012
## Post #73
- Username: zZaRDoZz
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 09, 2014 10:17 am
- Post datetime: 2015-02-16T03:35:20+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from knifelemon
>
> can you give me any script or plugin?

i have 3ds max 7 , 2011 | 2012 , maya 7 , 2012

Sorry knifemelon, bur the only version of 3dsMax that worked with abc version 6 was 3dsmax 2.0 and you had to have windows nt for the plugins to work. the ltb files you're dealing with are a different format for all its worth.
## Post #74
- Username: knifelemon
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Feb 06, 2015 5:08 pm
- Post datetime: 2015-02-17T11:24:18+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from zZaRDoZz
>
> knifelemon wrote:can you give me any script or plugin?

i have 3ds max 7 , 2011 | 2012 , maya 7 , 2012

Sorry knifemelon, bur the only version of 3dsMax that worked with abc version 6 was 3dsmax 2.0 and you had to have windows nt for the plugins to work. the ltb files you're dealing with are a different format for all its worth.

OMG 

Thank you for letting us know.
## Post #75
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-03-20T12:18:37+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Hello
Could you mind updating new .ltb plugins, all files of Sudden Attack Korea can't be imported, they had been updated to ver 2.0
sample files:
[PSY.LTB](http://www.mediafire.com/download/fwn1mei5bsz135w/ak472014_aim_m_on.ltb)
[ak47.ltb](http://www.mediafire.com/download/7d9jut2a3g8zqli/psy_gangnam_blue.ltb)
## Post #76
- Username: Mirrorman95
- Rank: ultra-veteran
- Number of posts: 355
- Joined date: Tue Jul 20, 2010 9:08 am
- Post datetime: 2016-03-23T19:35:29+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Hope this isn't too off topic, but do any of these work on Blood 2?
## Post #77
- Username: UED
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 29, 2017 6:58 am
- Post datetime: 2017-05-28T23:22:46+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Hey, I was wondering if there is any chance for the ABC models from 'Kiss Psycho Circus' (LithTech 1.5)?
It would be really great if I could get the models.

I have attached 3 models and their DTX textures. I've also included ModelEdit, a nice model viewer with texture support.

[KPC.zip](http://ripued.com/dl/KPC.zip)
## Post #78
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-01T03:24:21+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from UED
>
> KPC.zip
i have no clue about the dtx texture samples   
but the structure of your abc samples follows these specs
[http://bop-mod.com/download/docs/LithTe ... ormat.html](http://bop-mod.com/download/docs/LithTech-ABC-v6-File-Format.html)
that model format looks interesting, 6 float UV data?   

i can get this from ARACHNICLOWN.ABC with Hex2obj 



ARACHNICLOWN_ABC.png (37.26 KiB) Viewed 266 times


all of the meshes are sitting in the center on top of each other there,
but you can split and move them to the correct position in your favorite 3d software

of course no UVs because i don't know how it works in the abc format   

this is what the "Model Info" window shows in the ModelEdit program about UV coordinates
 
if someone could explain how 6 float UV data should be interpreted that would be great!
## Post #79
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-06-01T08:34:00+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from AceWell
>
> if someone could explain how 6 float UV data should be interpreted that would be great!
UV1+UV2+UV3 for example
## Post #80
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-01T10:48:31+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

it's a matter of sorting into a texture coords array vt_arr[vertex count][2] where the index is a face index (f[][]).
The problem is that you have 658 vertices here and a face cnt of 1149,
 so there's 1149 x 3 (tx, ty) values.
In the end my code solution looks like this (cnt= face count, f[face count][3] is the array of face indices, FIs):

```
		for (k=0;k<3;k++) {				// three indices per face
			for (i=0;i<2;i++) {			// get tx, ty
                pFloat = (float*) pFBuf ;		 // pFBuf: pointer to file buffer
                vt_arr[f[l][k]][i] = *pFloat ;  // some vt_arr[][] get multiple writes
                pFBuf += 4 ; j+= 4 ;			   // j: address counter
			}
		}
		pFBuf += 9 ; j += 9 ;
	}
```
(there's some chance that I'm wrong, some uvs look overlapped at least)

I've updated ABC2obj to care for uvs:


 ABC2obj.zip
(11.01 KiB) Downloaded 58 times
## Post #81
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-02T12:50:09+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> I've updated ABC2obj to care for uvs:
ABC2obj.zipthanks for the update!
However some files are not working properly and characters are not working at all. can you take a look?
[http://rgho.st/68SsdRJXT](http://rgho.st/68SsdRJXT)

here's original topic:
[http://cgig.ru/forum/viewtopic.php?p=9280#p9280](http://cgig.ru/forum/viewtopic.php?p=9280#p9280)
## Post #82
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-02T13:55:30+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

yeah, there's many odds - maybe another uv sorting is required, dunno:



Juggernaut-ABC.JPG (116.58 KiB) Viewed 223 times



Most characters in ABC format are dead ugly, imho.  
The only reason for me to care for them is the skeleton and animation keyframes
which I'd like to use like ModelEdit (included in KPD.zip of UED's post) does.

(I tried to use the position of the first translation keyframe of each node to get proper skeletal positions
at no avail up to now.)
## Post #83
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-02T15:32:17+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> yeah, there's many odds - maybe another uv sorting is required, dunnothanks for reply.
ofcourse would be great to have the tool for converting all versions of .ABC into readable format like .FBX of .SMD but this task is unsolvable for me for several years now. Maybe daemon (a real pro here) could lay his hands on to lithtech engine someday.
p.s: is it possible you could update abc2obj to support .ABC I send you recently or is it a waste of time you think?
## Post #84
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-02T20:41:53+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from Tosyk
>
> p.s: is it possible you could update abc2obj to support .ABC I send you recentlyspeaking of which?
The picture in my previous post shows one of the samples which you uploaded. (Characters are no fun, as I wrote.  )

(You might try to use ninja ripper with the ModelEdit.exe I spoke of.)
## Post #85
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-06-03T09:05:57+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

> Reply from shakotay2
>
> Tosyk wrote:p.s: is it possible you could update abc2obj to support .ABC I send you recentlyspeaking of which?
The picture in my previous post shows one of the samples which you uploaded. (Characters are no fun, as I wrote.  )

(You might try to use ninja ripper with the ModelEdit.exe I spoke of.)ah, okay. the characters were the goal. but well thanks anyway
## Post #86
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2017-06-26T14:39:29+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Hi guys someone know if AVP2 Model + Animation can be properly use ? I've tried link for plugins on the main page but they seem broken!  
This is the Pulse Rifle files for testing!
[https://cdn.discordapp.com/attachments/ ... fle_hh.ABC](https://cdn.discordapp.com/attachments/220242494250549259/328911512934809600/mPulserifle_hh.ABC)
[https://cdn.discordapp.com/attachments/ ... fle_hh.ABC](https://cdn.discordapp.com/attachments/220242494250549259/328911512934809600/mPulserifle_hh.ABC)
## Post #87
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2017-06-27T05:37:47+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

The attachment x.jpg is no longer available
> Reply from GENTEK
>
> Hi guys someone know if AVP2 Model + Animation can be properly use ? I've tried link for plugins on the main page but they seem broken!  
This is the Pulse Rifle files for testing!
https://cdn.discordapp.com/attachments/ ... fle_hh.ABC
https://cdn.discordapp.com/attachments/ ... fle_hh.ABC

Milkshake 3D is the best choice. Unfortunately, no animation supported! 
[x1.jpg](https://xentaxbackup.github.io/file/13036_x1.jpg)
## Post #88
- Username: GENTEK
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Dec 26, 2015 12:22 pm
- Post datetime: 2017-06-27T15:45:28+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

This importer can import meshes and skeletons from ABC version 11 and 12.  This is the No One Lives Forever Importer I'm extacly at the same step with MS3D so this is why I search another way or tool to use AVP2 Animations.
## Post #89
- Username: pekayatt
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 01, 2017 9:37 pm
- Post datetime: 2017-09-01T13:49:01+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Have been trying to open this .abc files for a while now.

I believe this is the only source on Internet that got me closer to understand the "problems" with the ABC (it is alembic, right?) files from Shogo .

Unfortunately even using this tool from shakotay I could not get nice results. Maybe it is better to just remodel everything from scratch, but that would take much more time to have a simple version.

I have an idea of remake Shogo on UE4, maybe with VR support. Just for learning, what you guys think is better approach? To learn how to model and animated and everything or to crack this files?
## Post #90
- Username: avp2avidfan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Aug 26, 2017 2:28 pm
- Post datetime: 2017-09-01T14:02:11+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

,,,
## Post #91
- Username: fp63
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 10, 2017 11:05 pm
- Post datetime: 2017-10-29T11:29:46+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

so... has someone found a way to export .ABC animations into any other format?
## Post #92
- Username: AlpacaNox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 02, 2018 7:46 pm
- Post datetime: 2020-05-02T19:51:26+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

The link to the python plugin doesn't work anymore. However the plugin is hosted also here:
[https://github.com/RoadTrain/noesis-plu ... ech_abc.py](https://github.com/RoadTrain/noesis-plugins-official/blob/master/finale00/fmt_LithTech_abc.py)
Needed it for Might and Magic IX models, it works really great!
## Post #93
- Username: gryplg
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 30, 2022 12:09 am
- Post datetime: 2022-09-29T21:26:25+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

Does anyone have any information about Global Operations .ABC models? I want to convert them to .OBJ format.
## Post #94
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-04-25T11:41:35+00:00
- Post Title: Re: LithTech Models (.abc, .ltb, .dat)

I tried Ultimate Unwrap 3D but it's not freeware. Is there a Blender plugin that can import .abc files from Global Operations? LithTechGuru said "I don't know".

Samples:
[https://mega.nz/file/8LI00DhR#jcXwHpu84 ... hHuwzwWp6c](https://mega.nz/file/8LI00DhR#jcXwHpu84tZWkJBvjaK-4vSuo7mUABm-ahHuwzwWp6c)
