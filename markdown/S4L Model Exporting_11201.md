## Post #1
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-11T16:55:28+00:00
- Post Title: S4L Model Exporting

Hi, i have seen this forums a lot of times, but i didn't post anything until now, the main reason was because this forum is full of experienced people, making rips of tons of games, and well, i just started C++ like 3 months ago and i feel pretty much useless right now, and i can't do more things than fors, whiles and writing in binary files, i just don't know how to start in this world, and i don't feel like i can actually do something for this community at all.


But well, i would like to ask the help of some experienced Jack the Ripper in this forum, I asked in somewhere else and he told me that this was the best place to ask for it, he also told me that the files were pretty much straight foward and they were very easy, however i am noob enough to not to know how to handle them. Even if they are easy, i don't want to pressure anyone about this.


The game itself is S4L, you can find the official game here:[WEBSITE DOESN'T ExIST ANYMORE (pretty much straight foward also)
It's a F2P Game released by Pentavision in 2008 (More like p2win, that's why i don't enjoy playing it anymore). 

Read more before downloading the game if you are interested on this. (Also the game it's not that huge, 2GB, not that big at all)

The files, aside with the configuration and all stuff people uses for hacking the game are in a folder called: resources.

There are actually 20.872 files in that folder, all of them named with names like "1a5e09f2c13ccd56"

If you want to start from that point, you can download the game and extract the files from those resources, i will provide a tool that will get the files out of there.

However i am not interested in hacking the game or anything...

Inside the resources, there are mainly (aside Txt, and format of the code called x7, which i am not interested at the moment, but they seem unreadable, they have the same characters i have when i write files in binary like black nulls and stuff, if someone can confirm me this i would be happy to know it, so i can recognize binary files when i see them, and makes me feel useful at some points,):


.DDS files, which are the textures for the objects, i can actually see and edit them since they are Direct Draw files (correct me if wrong)
.SCN Files, which i SUPPOSE they are the models of the objects, but since i can't manage to open them in any way i don't know what they are, and this is mainly the point of this post, open them in programs like 3DS MAX, or blender, or whatever.

They also have animations and bones which would be great to get them 

.SEQ files which apparently they are effects that render into the game.

The main point of asking help here is being able to open the models in a program, and apply the DDS textures on them, and if i can learn something else from this Game i would love to know it (how you did it would be great to learn it by myself)

In order to not to make you take the files from the resources or download the whole game (it's not that big tho, 2GB) i will provide a DDS, SCN and SEQ File.
.

If you are curious about why i am doing this, i want to be a game developer in a future (really long future, it's my first year studying C++, not even a year, but 3/4 months), and i want to modify this game for myself and do stuff like my own weapons and such (There is a emulator to make your own server, if you are more interested on this game, i can provide more information)

I am thinking also doing this not from the game itself, but getting a free 3D game software (Unity3D was a good one isn't it), take the models from this game and make my "own" rework of this game. But since i am too far away from this, i will probably just look at the models, and change the textures and recolor clothes and that kind of things,i love modding anyway.

Also the game looks a bit horrible and i think their models can be improved in other Engines (to look better i mean)

I hope this doesn't sound bad to anyone, i mean, making games from other games, seems kind of evil :s

I would also thank you for answering this post even if it's a no, but at least to know if it's impossible to do, or you are just not into this because you don't like my intentions, but it's not like i want to decieve anyone asking for something and lying about my purposes.

In the link i will provide:

1 - A sword and it's texture (I am not sure if the model is the sword, but you know, it's called sword.scn, i don't thik there is another one)
2 - Another model (asteroid), with it's SEQ (unknown), 2 additional textures
3 - The resource editor in case someone downloads the game
(Warning, there are some files the editor can't extract, according to it the file is not there

File: [http://puu.sh/6SbLT.rar](http://puu.sh/6SbLT.rar)

(Password attached to the post)

This is all the help i can provide you to make it as easy as possible.

I know it won't seem legit since it's my first post, so help me if you feel confident about it, it's in a RAR, so you should notice a virus before it does anything (or however this works).
Thanks in advance:

-Seyren.

TL;DR: I would like to know how to use open those models in a model editor, could you help me please?
[pwd.rar](https://xentaxbackup.github.io/file/7006_pwd.rar)
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-11T19:30:09+00:00
- Post Title: S4L Model Exporting

I've had a quick look at the files, and I wrote a quick and dirty MAXScript to import the sword.scn file. I've tried parsing asteroid.scn too but it's made up of multiple objects and the model data doesn't have enough info (for example, the texture names have a long array of null-bytes and the array's length is nowhere to be found). I've only parsed the geometry data so far, no UVs or normals yet (well I found a block which might contain them but they don't look right at all).

[](http://www.imagebam.com/image/71fb85307386998) 

Without further ado, here's the script:
EDIT: Updated to import UVs properly, thanks shakotay!

```
types:"S4League Models (*.scn)|*.scn|"

if fSCN != undefined then
(
	f = fopen fSCN "rb"
	clearlistener()

	Face_array=#()
	Vert_array=#()
	UV_array=#()

	fseek f 2438 #seek_set
	
	-- vertex data
	
	count = readlong f #unsigned
	for x = 1 to count do
	(
		vx = readfloat f
		vy = readfloat f
		vz = readfloat f
		append Vert_array[vx,vy,vz]
	)
	
	-- face data
	
	count = readlong f #unsigned
	for i = 1 to count do
	(
		fa = readshort f #unsigned
		fb = readshort f #unsigned
		fc = readshort f #unsigned
		append Face_array[fa+1,fb+1,fc+1]
	)
	
	-- normals data

	count = readlong f #unsigned
	for i = 1 to count do
	(
		nx = readfloat f
		ny = readfloat f
		nz = readfloat f
	}

	-- UV data

	count = readlong f #unsigned
	for i = 1 to count do
	{
		tu = readfloat f
		tv = readfloat f
		append UV_array[tu,1-tv,0]
	)

	msh = mesh vertices:Vert_array faces:Face_array name:(getFilenameFile fSCN)
	msh.numTVerts = UV_array.count
	buildTVFaces msh
	for j = 1 to UV_array.count do setTVert msh j UV_array[j]
	for j = 1 to Face_array.count do setTVFace msh j Face_array[j]

	Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
	gc()
	fclose f 
)
```


Hopefully it'll come in handy somehow.
## Post #3
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-11T20:34:37+00:00
- Post Title: S4L Model Exporting

I searched in the resource files all of them who had "asteroid" in their name, and there are 20 files concerning the asteroid, 5 of them are scn (4 if we count the one we have right now) and the rest are SEQ which i suppose they are animations 

If this helps you i zipped all the files of the asteroid here: [http://puu.sh/6SpKJ.rar](http://puu.sh/6SpKJ.rar) (Same password as the older files) in case you want to complete the monster , or at least, i hope you can complete it with that.

I tested your script and works perfectly with the sword, however, i couldn't manage to make it work on any other model, it pops me this error everytime:



I would try to fix it myself but at the moment i don't know anything about MAXScripting, i should learn soon if i am able to do this kind of things.

Even if you can't /won't fix it thank you a lot for making me able to get at least the sword into the editor, really thanks a lot, i will look foward for your progress if you are still helping me :)

Again, thanks a lot.
## Post #4
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-11T21:08:21+00:00
- Post Title: S4L Model Exporting

Unfortunately the problem isn't lack of files, but my lack of knowledge about the SCN format. I've tried guessing what I can, but I just can't figure some stuff out  . But if I discover anything new I'll let you know.

I know nothing about animations so I'm afraid I can't help you with that.

On the other hand, since it's a PC game, you might be able to extract the models using a program like [NinjaRipper](http://cgig.ru/en/2012/10/ho-to-use-ninja-ripper/).

Good luck
## Post #5
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-11T22:07:18+00:00
- Post Title: S4L Model Exporting

Well, thank you so much , i will do what i can and i will try the NinjaRipper (if i manage to run the game without the updater, which is the main problem i can't use it), if i manage to do something i will post it here if someone is interested 

EDIT: I tried and the injections failed, so i guess i can't use it,i will keep looking at the program if i manage to inject it.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-02-12T11:55:32+00:00
- Post Title: S4L Model Exporting

sword.scn: offset 0x2056 0x159= 345
-> 345 normals at 0x205A

0x3086 0x159= 345
then uvs follow (2 floats)

[](http://www.pic-upload.de/view-22244706/sword.jpg.html)

Asteroid.scn, first submesh:
[](http://www.pic-upload.de/view-22244879/Asteroid.jpg.html)

uvs looking a little bit weird, although the block should be from 0x1C4AF to 0x1D216
(429x 2 floats)
[](http://www.pic-upload.de/view-22244920/Asteroid_uvs.jpg.html)

edit: again, use of a script like barti did might be useful for the submeshes.

for the sword it get's the uvs with a small change:

```
   for i = 1 to count do
   (
      nx = readfloat f
      ny = readfloat f
      nz = readfloat f
   )

   count = readlong f #unsigned
   for i = 1 to count do
   (
      tu = readfloat f
      tv = readfloat f
      append UV_array[tu,1-tv,0]
   )
```
## Post #7
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-12T13:47:39+00:00
- Post Title: S4L Model Exporting

Thank you all for your help , we are closer to get it

Cra0kalo helped me also to get the models.

He started this script and he told me to post it here if someone can finish it.

```
// DataFormat little ENDIAN (x86)
struct SCNHeader
{
uint32 unknownIdentifier
uint32 ??IDK
string ModelName
 
 
 
 
}
 
 
 
 
//Vert Count unit32 before structure
uint32 VertexCount
 
struct VBufStruc1
{
float vd x
float vd y
float vd z
 
}
 
 
//FaceCount before structure
uint32 FaceCount
 
struct FaceList
{
uint16 faceA
uint16 faceB
uint16 faceC
}
 
 
struct VBufStruc2
{
hfloat vn_x
hfloat vn_y
hfloat vn_z
hfloat vn_w
}
```


Thank you all for helping me ^^

Edit: I got the shader dump from intel GPA, however i don't know how to use it, but i heard it helps a lot. so i will attach it in this post.

(i don't know why it's so messed up, it came up all in a single line, so i made a program that made an end of the line every time it saw at ";", "{" (not } because structs can get screwed) . so it looks weird at some points.)

HLSL 

[http://puu.sh/6U2Ye.txt](http://puu.sh/6U2Ye.txt)

IL Assembly:

[http://puu.sh/6UpBK.txt](http://puu.sh/6UpBK.txt)
I will also attach the GPa where i got it in case you want it too

[http://puu.sh/6U2Ue.gpa_frame](http://puu.sh/6U2Ue.gpa_frame)
## Post #8
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-02-13T12:32:38+00:00
- Post Title: S4L Model Exporting

most likely the cpu handles boneblends I don't see anything in the shader code
## Post #9
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-13T15:56:33+00:00
- Post Title: S4L Model Exporting

> Reply from shakotay2
>
> sword.scn: offset 0x2056 0x159= 345
-> 345 normals at 0x205A
...
then uvs follow (2 floats)

*facepalm* can't believe I overlooked that  Thanks

I'm trying to parse the submeshes in asteroid.scn now, I managed to find the length of some data but one block changes in size and I'm still looking for a count value.

[](http://www.imagebam.com/image/609304307770241)

Here's what I figured out by now (note that this script is broken and is meant to work only with asteroid.scn)

```
types:"S4League Models (*.scn)|*.scn|"

if fSCN != undefined then
(
	f = fopen fSCN "rb"
	clearlistener()

	Face_array=#()
	Vert_array=#()
	UV_array=#()
	
	fseek f 8 #seek_set
	modelName = readstring f
	fseek f 81 #seek_cur
	
	for i = 1 to 4 do
	(
		submeshName = readstring f
		modelName = readstring f
		fseek f 88 #seek_cur
		fseek f 2052 #seek_cur
		print ("Mesh: " + submeshName)
		someint = readlong f #unsigned
		print ("\tSomeint: " + someint as string)
		count = readlong f #unsigned
		print("\tVertices: " + count as string)
		for x = 1 to count do
		(
			vx = readfloat f
			vy = readfloat f
			vz = readfloat f
			append Vert_array[vx,vy,vz]
		)
		
		count = readlong f #unsigned
		print("\tFaces: " + count as string)
		for i = 1 to count do
		(
			fa = readshort f #unsigned
			fb = readshort f #unsigned
			fc = readshort f #unsigned
			append Face_array[fa+1,fb+1,fc+1]
		)
			
		count = readlong f #unsigned
		print("\tNormals: " + count as string)
		for i = 1 to count do
		(
			nx = readfloat f
			ny = readfloat f
			nz = readfloat f
		)

		count = readlong f #unsigned
		print("\tUVs: " + count as string)
		for i = 1 to count do
		(
		  tu = readfloat f
		  tv = readfloat f
		  append UV_array[tu,1-tv,0]
	   )

		fseek f 12 #seek_cur
		str = readstring f
		fseek f 73 #seek_cur
		str = readstring f
		b = readbyte f
		fseek f 1420 #seek_cur -- I need to find the size of this block, it seems to change between submeshes
		fseek f 48 #seek_cur


		msh = mesh vertices:Vert_array faces:Face_array name:submeshName
		msh.numTVerts = UV_array.count
		buildTVFaces msh
		for j = 1 to UV_array.count do setTVert msh j UV_array[j]
		for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
		free Face_array
		free Vert_array
		free UV_array
	)
	gc()
	fclose f 
)
```
## Post #10
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-14T13:52:43+00:00
- Post Title: S4L Model Exporting

Tested Barti's script and works great for the asteroid.

As you told me i tried the Ninja Ripper and i managed to Rip the models from the game.


most of the textures get reverted and mirrored, so i have to mirror the whole model and revert the texture.

Also, there is something i don't understand.



The hole of the of the chains should be transparent, and something is wrong that is making not to use the alpha color.



Does someone know why does this happen and how can i fix it? Thanks in advance 

Although i am able to see and edit the models, it's not a great progress since i am not able to conver the model back to scn, so the only thing i can actually mod is the textures (Which is an actual progress ).

There must be a way to do this, i would like to contribute with scripts, but i don't know yet, i am so sorry, that's why i keep asking you guys for help

Thanks in advance, i will help all i can for this extractions
## Post #11
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-02-14T15:53:26+00:00
- Post Title: S4L Model Exporting

3DS Max doesn't display alpha channels in textures by default. You'll need to use [this method](http://www.horribledeath.com/tut-alpha.htm) to get the alpha channel to show up
## Post #12
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-02-26T22:29:06+00:00
- Post Title: S4L Model Exporting

Thank you for tell me that on 3DS Max 

I would like to revive this thread since it's been a while i don't get answers at all and i would like to let you know if you could help me converting the scn to obj and viceversa for testing them in-game, (or any other format for editing)

I posted all the help i could provide and if there is something more you need i will do my best to help you

I will be waiting, Thanks in advance
## Post #13
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-04-21T14:44:24+00:00
- Post Title: S4L Model Exporting

I would like to bump this thread again in case someone can get anything else from this game, thank you so much in advance <:, i'm trying to learn how this was done so i can do it on my own and not bother anyone with this game :c
## Post #14
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-04-22T16:57:25+00:00
- Post Title: S4L Model Exporting

What actually are you up to now?
.scn is not a difficult format but mixed with mesh, dummy, animation in there!
eg: 0x081098F8 is mesh ID, 0x6D411AD1 is dummy ID and 0x6278D57A is Header ID (I think).



Clipboard02.jpg (179.43 KiB) Viewed 589 times


Since there is only 1 samples(asteroid) I got here, so there is no point for me to say the format structure.
Some more different samples!

I also want to ask if you can actually unpack/encrypt the latest S4L Cyborgs resources!?
Can you share it with me. Thanks!
## Post #15
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-04-25T14:43:12+00:00
- Post Title: S4L Model Exporting

There are different types of scns, but They ones from the cyborgs and the ones from the seasons i have (mines are from Season 3) share the same encryption, so if you decrypt these scn's you wil lbe able to get the cyborg ones easily.

If you are interested i can pack for you every kind of different SCN this game has 

The game is online so everything that i'm intersted about the SCN has nothing to do with the actual game, i want to explore the format, see the animations, use them in my own game projects because i love the assets from those games
## Post #16
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-04-29T21:06:16+00:00
- Post Title: Re: [Request] Model Exporting

The format basically like this:

```
<object>
<object>
...


struct Common_Obj_Properties {
  dword	Object_ID
  char[]	Object_Name
  char[]	Parent_Name
  float		??				//always 0.1
  float[16]	Object_Transform_Matrix		//Object_Version = 0.1 parent base, or 0.2 world base
  float	Object_Version
}


struct SCN_ROOT {				//Object_ID = 0x6278D57A
  Common_Obj_Properties
  dword		num_Object
  *char[]	??				//only on Object_Version = 0.2
}


struct Bonesystem {				//Object_ID = 0x5E74333F
  Common_Obj_Properties
}


struct Bone {					//Object_ID = 0x6D411AD1
  Common_Obj_Properties
  dword		num_Animation

  struct Anim {
    char[]	Anim_Name
    *char[]	Anim_Copy			//same animation as this name
    dword	Anim_Tick_Time
    byte	Unknown_Flag
    float[3]	Initial_Translation
    float[4]	Initial_Rotation
    float[3]	Initial_Scale
    
    dword	num_Trans_Animation
    struct Trans_Anim {
      dword	Tick_Time
      float[3]	Trans_XYZ
    }

   dword	num_Rotate_Animation
    struct Rotate_Anim {
      dword	Tick_Time
      float[4]	Rotate_XYZW
    }

   dword	num_Scale_Animation
    struct Scale_Anim {
      dword	Tick_Time
      float[3]	Scale_XYZ
    }

    dword	num_Visibility_Animation
    struct Visibility_Anim {
      dword	Tick_Time
      float	Visibility_Value
    }
    
  }

}


struct Helper {					//?? Object_ID = 0x25ADF0D1
  Common_Obj_Properties
  float[16]	??
}


struct Light {					//?? Object_ID = 0xC3E8BE62
  Common_Obj_Properties
  float[4]	Color01_RGBA
  float[4]	Color02_RGBA
  float[4]	Color03_RGBA
  float[11]	??
}


struct Line {					//?? Object_ID = ADEE38A2
  Common_Obj_Properties
  float[7]	??
}


struct Mesh {					//Object_ID = 0x081098F8
  Common_Obj_Properties
  dword		??
  float		??
  dword		ExtraUVs
  dword		num_Texture

  struct Texture {
    char[128]	Texture_Name
    dword	Face_Start
    dword	Face_Count
  }

  dword	num_Vert
  struct Vert_Coord {
    float[3]	Coord_XYZ
  }

  dword	num_Face
  struct Face {
    word[3]	Index_XYZ
  }

  dword	num_Normal
  struct Normal {
    float[3]	Normal_XYZ
  }

  dword	num_UV
  struct UV {
    float[2]	Tex_UV
  }

  dword	num_Tangent
  struct Tangent {
    float[3]	Tangent_XYZ
  }

  struct Skin {
    dword	num_Skin_Bone
    struct Skin_Bone {
      char[]	Bone_Name
      float[16]	Inverse_Matrix
      dword	num_Skin_Data
      struct Skin_Data {
        dword	Vert_Index
        float	weight
      }
    }
  }

  dword	num_Animation
  struct Anim {
    char[]	Anim_Name
    *char[]	Anim_Copy				//same animation as this name
    dword	Anim_Tick_Time
    byte	Unknown_Flag
    float[3]	Initial_Translation
    float[4]	Initial_Rotation
    float[3]	Initial_Scale
    
    dword	num_Trans_Animation
    struct Trans_Anim {
      dword	Tick_Time
      float[3]	Trans_XYZ
    }

   dword	num_Rotate_Animation
    struct Rotate_Anim {
      dword	Tick_Time
      float[4]	Rotate_XYZW
    }

   dword	num_Scale_Animation
    struct Scale_Anim {
      dword	Tick_Time
      float[3]	Scale_XYZ
    }

    dword	num_Visibility_Animation
    struct Visibility_Anim {
      dword	Tick_Time
      float	Visibility_Value
    }

    dword	num_Morph_Animation			//??
    struct Morph_Animation {
      dword	Tick_Time
      dword	count1
      struct Anim_Data1 {
        dword	 Index
        float[3] value
      }
      dword	count2
      struct Anim_Data2 {
        dword	Index
        word[2]	??					//?
        float	value
      }
    }

  }

}
```


Animation just not look right in Object_Version 0.2. (possibly I don't have patient to reuse/copy keys)
## Post #17
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-01T10:36:46+00:00
- Post Title: Re: [Request] Model Exporting

Let's start form a simple file: 27_female_face.scn
You should phase the file like this.



27_female_face_SC.jpg (169.58 KiB) Viewed 316 times


offset 0x04 is the first object with Object_ID: 0x6278D57A
start form 0x08 is the Common_Obj_Properties

offset 0x68 is the 2nd object with Object_ID: 0x6D411AD1
2nd Common_Obj_Properties start form 0x6C

3rd Object start from 0x127, Object_ID: 0x081098F8
3rd Common_Obj_Properties start form 0x12B

etc...
## Post #18
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-01T22:30:07+00:00
- Post Title: Re: [Request] Model Exporting

I got stuck here...

```
	(	
		print "--------------------------------"
		print "Chunk ID: Mesh"
		Common_Obj_Properties()
		readlong f
		readfloat f
		readlong f
		readlong f
		
		Texture_array=#()
		counter = 2048
		
		for i = 1 to counter do
		(	
			tex = readstring f
			if tex != "" then
			(
				counter = counter - (tex.count)
				append Texture_array tex
				
			)
		)
			print "Textures:"
			print Texture_array
			print counter
		
	)	

```


I don't know how to update the counter, it always goes to 2048... if i were able to update the counter so it removes the string sizes it could fit and go ahead to the mesh... 

I tried puting the counter as global value but i got no luck...

Also it's my first ever maxscript so noob errors are expected... i had a hard time finding some stuff so it's probably a very poor script ><
## Post #19
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-02T06:42:57+00:00
- Post Title: Re: [Request] Model Exporting

Try using do/while instead of for/next

```
num_object = 1     --since there is at least SCN_ROOT object(0x0x6278D57A) there
obj_counter = 0
do (
 object_ID = readlong fstream
 Common_Obj_Properties ()
 if object_ID = 0x0x6278D57A then (
  num_object += readlong fstream
 ) else if object_ID = XXX then (
  ...
 ) else if object_ID = XXX then (
  ...
 )
 obj_counter += 1 
) while obj_counter < num_object
```
## Post #20
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-02T14:16:07+00:00
- Post Title: Re: [Request] Model Exporting

YESSSSSSSSSSSSSSSSSSSSSS

Thank you for your help! 



I'm SO HAPPY ABOUT THIS 

However this was face 00, not 27


 for some reason this happens when i use the 27 one...

I guess i'll have to do some fixes to make this work since this one is weird, but all of them work except this one o_o

EDIT: Okay so i did the new structure you gave me and it works in some faces like 00 female but in some others it doesn't...
## Post #21
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-03T17:36:46+00:00
- Post Title: Re: [Request] Model Exporting

Sorry for the double post, it's just to point out some progress >_<

I remade the whole script again (Ver 5, the 4 is old now)

And now i'm able to import almost all weapons and faces



However there are Some Ver 0.2 Weapons like the katana which has a different Animation pattern



The "BASE" Animation shares the same structure than other ones, however after that one Starts putting up Animation Names without any property

AT first i don't know how to deal with this but i know i solve it soon...

EDIT: Another known Issue

Skin is not readed properly

I'm trying to parse properly the Skin Weights but something goes wrong.

The file i'm trying to parse is attached in this post.

This is the code i'm using according to fatduck's file structure

```
		print "Number of Skin Weights:"
		print Num_Skin
		
		for i = 1 to Num_Skin do
		(
			num_Skin_Bone = readlong f
			for i = 1 to Num_Skin_Bone do
			(
				BoneName = readstring f
				print "Bone Name:"
				print BoneName
				
				for m = 1 to 16 do readfloat f
				
				num_Skin_Data = readlong f
				for i = 1 to num_Skin_Data do
				(
					Vert_Index =readlong f #unsigned
					Weight = readfloat f
				)
			)

```


The log displays like this:

```
820
"Faces:"
841
"Normals:"
820
"Number of UV's:"
820
"Number of Tangents:"
820
"Number of Skin Weights:"
13
"Bone Name:"
"ip01 Pelvis"
"Bone Name:"
"Bip01 Spine"
"Bone Name:"
"Bip01 Spine1"
"Bone Name:"
"Bip01 Spine2"
"Bone Name:"
"Bip01 Neck"
"Bone Name:"
"Bip01 Head"
"Bone Name:"
"Bip01 L Clavicle"
"Bone Name:"
"Bip01 L UpperArm"
"Bone Name:"
"Bip01 L Forearm"
"Bone Name:"
"Bip01 R Clavicle"
"Bone Name:"
"Bip01 R UpperArm"
"Bone Name:"
"Bip01 R Forearm"
"Bone Name:"
"Female_Breast_Bone_01"
"Bone Name:"
""
"Bone Name:"
""
"Bone Name:"
""
"Bone Name:"
undefined
-- Error occurred in i loop; filename: C:\Users\Seyren Windsor\Desktop\test5.ms; position: 8445; line: 447
--  Frame:
--   i: 17
--   BoneName: undefined
--   num_Skin_Data: undefined
--   called in i loop; filename: C:\Users\Seyren Windsor\Desktop\test5.ms; position: 8453; line: 448
--  Frame:
--   i: 1
--   num_Skin_Bone: 1107296256
--   called in anonymous codeblock; filename: C:\Users\Seyren Windsor\Desktop\test5.ms; position: 8459; line: 449
--  Frame:
--   Texture_array: #("00_female_body_atex.tga", "00_female_body_n.tga")
--   Num_UV: 820
--   msh: undefined
--   counter: 2010
--   vert_array: #([-0.00652255,200.618,-18.3713], [-0.00652228,198.654,-18.7464], [0.0582619,202.839,13.8164], [-0.00651711,196.875,10.6435], [-0.00652487,193.976,-15.546], [-0.00652486,208.534,15.4597], [-19.1828,222.384,1.24953], [-16.7811,212.394,-6.7046], [-17.0796,215.661,-2.37712], [-13.1488,214.932,-5.28716], [-12.9451,206.757,-13.887], [-8.3649,210.683,-14.4909], [-5.14348,203.351,-19.7685], [-3.39289,206.063,-18.6364], [-14.6014,215.671,15.6438], [-15.5689,209.907,15.5989], [-7.75438,208.534,15.4149], [-5.93106,199.075,-20.038], [-13.9935,200.026,-15.2819], [-16.0568,203.013,-10.0848], ...)
--   Num_Tangent: 820
--   Normal_array: #([-0.267179,0.190111,-0.944708], [0.0372846,-0.230603,-0.972333], [0.118771,-0.362523,0.924376], [0.139529,-0.254226,0.957027], [0.0244996,-0.388565,-0.921095], [0.0160021,-0.238871,0.970919], [-0.319085,0.575294,-0.753141], [-0.668708,0.45332,-0.589348], [-0.494675,0.350334,-0.795338], [-0.376597,0.642894,-0.66698], [-0.640225,0.357189,-0.680094], [-0.487356,0.498109,-0.717197], [-0.0998374,0.231343,-0.967736], [-0.014206,0.392957,-0.919447], [0.203665,0.0452499,0.977994], [-0.193522,-0.224551,0.955053], [-0.00535212,-0.142643,0.98976], [-0.166585,-0.214546,-0.962403], [-0.776572,-0.124208,-0.617663], [-0.949303,-0.109832,-0.294553], ...)
--   UV_array: #([0.440083,0.27141,0], [0.440376,0.255625,0], [0.0186661,0.299197,0], [0.0186661,0.243351,0], [0.440558,0.216921,0], [0.0186661,0.352517,0], [0.289006,0.452292,0], [0.282699,0.370048,0], [0.295327,0.415993,0], [0.32787,0.390824,0], [0.344095,0.324518,0], [0.366027,0.355734,0], [0.403793,0.29453,0], [0.420272,0.315937,0], [0.0887454,0.431739,0], [0.099458,0.3775,0], [0.0577131,0.352517,0], [0.398121,0.260445,0], [0.342347,0.270135,0], [0.311871,0.293816,0], ...)
--   bitmappath: undefined
--   Object_ID: 135305464
--   i: 2010
--   Tg_array: #([0.963603,0.0621032,-0.260025], [0.9993,0.00567165,0.0369736], [-0.992166,-0.0796488,0.0962444], [-0.985402,-0.130858,0.108904], [0.9997,0.00889141,0.0228395], [-0.999871,-0.00516332,0.015209], [0.584509,0.745002,0.321437], [0.72264,0.209703,-0.658647], [0.732925,0.659959,-0.165155], [0.92519,0.224586,-0.305915], [0.732238,0.016096,-0.680859], [0.836196,0.0296461,-0.54763], [0.99481,0.00402659,-0.101668], [0.996922,0.0764695,0.0172788], [-0.749569,-0.635404,0.185495], [-0.978189,-0.0307155,-0.205432], [-0.801131,-0.591742,-0.0896132], [0.985032,0.00763363,-0.172203], [0.624883,-0.0268144,-0.780258], [0.303927,-0.0812187,-0.949227], ...)
--   Num_Vertex: 820
--   Num_Skin: 13
--   map: undefined
--   Num_Face: 841
--   face_array: #([10,8,9], [9,7,10], [10,11,8], [11,10,12], [12,14,13], [13,11,12], [14,1,13], [17,15,16], [18,13,1], [1,2,18], [13,18,19], [19,11,13], [8,11,20], [20,21,8], [22,21,20], [21,22,86], [86,85,21], [24,23,85], [85,86,24], [25,8,21], ...)
--   NumAnim: undefined
--   tex: ""
--   Num_Normals: 820
--   num_faces: 841
-- Unable to convert: undefined to type: Integer

```


So we can see it actually gets the Model right, but when it's trying to parse the Skinning something goes wrong.
The first thing that is pointed out is that it doesn't get the first bone name right, "ip01 Pelvis" instead of "Bip01 Pelvis", this was done by using readbyte the fstream instead of readlong in hopes to do the trick (if i use readlong it gets "1 Pelvis"), but it didn't

This is really strange for me because in the file it actually fits a double byte


After reading some Bones it starts to get messed up until it reaches to "SOH" which is under Breast, so it stops reading bones or something is wrong in the pattern.

I know no one really cares about this game because it's involved in a Online f2p game, but my intentions are not inside the online game and i don't have intentions to involve this to the actual game, and well, i'm doing my best to make my first ever MAXScript perfect 

If someone is interested he is welcome to help 
[00_female_body.rar](https://xentaxbackup.github.io/file/7294_00_female_body.rar)
## Post #22
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-04T06:24:58+00:00
- Post Title: Re: [Request] Model Exporting

sorry my fault, there SHOULD NOT have "dword	num_Skin" in then structure!!!

So delete your following lines(Outer i loop) will do:

```
      print "Number of Skin Weights:"
      print Num_Skin
      
      for i = 1 to Num_Skin do
      (


      )
```

@0xC075: that 0x0D is actually num_Skin_Bone!
## Post #23
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-04T21:28:24+00:00
- Post Title: Re: [Request] Model Exporting

Again, you are awesome, thank you ^_^ i don't know what i could have done without you 


What i found today:

In the Mesh ID, there is a dword before the Texture strings that tells you the number of Textures the model has.

With this new information i'm trying to get a good loop for the textures, but i'm having a hard time, since the multi textured models have a strange pattern.

I'm using as an example ds4_station.scn which i attached on the post.

This is mi loop (pretty crappy)

```
		print "Number of Textures:"
		print Num_Tex
		Texture_array=#()
		
		for i = 1 to Num_Tex do
		(	
			texture = readstring f
			counter = (2051 - texture.count)
			for i = 1 to counter do readbyte f
			append Texture_array texture	
		)

```


The reason it's 2051 it's because it usually works that way, since the string of the texture is Tex + it's bump tex, which explains why is 1024 bytes at some points and more at others, since even if there is no bump there is still space for it.

I couldn't get to parse correctly the textures from the file attached before since there are a lot of weird things on that file

This file also has Dummies (helpers)


EDIT: The file is too big to upload it, sorry 


Also i haven't found any Animation structure that follows the same pattern than Katana_a.scn, it's really strange, it just goes and gets all the animations strings and then starts describing them.

Attached if someone is interested.
[katana_a.rar](https://xentaxbackup.github.io/file/7298_katana_a.rar)
## Post #24
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-05T11:39:20+00:00
- Post Title: Re: [Request] Model Exporting

Format updated: [viewtopic.php?p=94248#p94248](http://forum.xentax.com/viewtopic.php?p=94248#p94248)

Key points here: 
The Texture block is:

```
    char[128]	Texture_Name
    dword	Face_Start
    dword	Face_Count
  }
```

And found a flag for Extra_UV!
the extra UV data is directly continue from the standard UV block.
eg: num_UV = 100
<100 UV Data>
<100 Extra UV Data>
..

Two new objects as well: Light? and Line?
## Post #25
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-06T01:54:56+00:00
- Post Title: Re: [Request] Model Exporting

The texture structure works on all scn's , thank you so much, didn't know about the 2 values after the empty bytes

Things i found today:

As far as i found only the models that have 0 number of tangents actually work, (at least for me, since my script is probably a mess.)

I got this error in the following file: ds4_station01 ([http://puu.sh/8AYhD.rar](http://puu.sh/8AYhD.rar))

```
"Object23"
"Parent:"
"ds4_station01.scn"
"Object Version:"
0.1
"sub_wall.tga"
"ds5_sector02_sidewall01.tga"
"sub_wall3.tga"
"ds5_sector02_sidewall01.tga"
"sub_wall2.tga"
"ds5_sector02_sidewall01.tga"
"sub_wall8.tga"
"ds5_sector02_sidewall01.tga"
"ds5_bottom.tga"
"ds5_sector02_sidewall01.tga"
"sub_wall7.tga"
"ds5_sector02_sidewall01.tga"
"Number of Vertex:"
4851
"Faces:"
2125
"Normals:"
4851
"Number of UV's:"
4851
"Number of Tangents:"
972691840

```


and then it goes boom
so there must be something in the file that changes the pattern, i'll look it up tomorrow

New ID: Sky

not sure how it's the struct tho

the values were taken also from ds4_station01

```
struct SCN_ROOT //Object_ID = 0xC3E8BE62
{            
  Common_Obj_Properties

dword  // 1
float    // 0.95
float // 0.95

float // 1, 00 00 80 3F, this value is very common on the files
float // 1, 00 00 80 3F

float    // 0.95
float // 0.95

float // 1, 00 00 80 3F, this value is very common on the files
float // 1, 00 00 80 3F

dword[5]

float // 0.99

dword[2]

float // 1, 00 00 80 3F
float // 1, 00 00 80 3F

dword[4]
}

```

So pretty much 92 bytes can be skipped since there doesn't seem to be anything useful anyway
## Post #26
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-06T06:45:07+00:00
- Post Title: Re: [Request] Model Exporting

I told you there is a flag of Extra_UV. it's located before the value of num_Texture!!!

You had reached one in ds4_station01.scn:
so after the standard UV block
you have to read/skip the extra UV block! (it's the same size of the standard one)
and then read the value of num_Tangent, and continue...

After that mesh, you will found a new object (Light) as well.
## Post #27
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-07T01:20:56+00:00
- Post Title: Re: [Request] Model Exporting

Oh my bad, i'm sorry, thank you again

I'm learning a lot but again i'm very bad at this so yeah my bad >_<

Now i managed to get the ds4_station fully imported ^^ ty again 



The Position seems fine, however as you can see the whole map is rotated 90 degrees.

That's not really an issue since it seems it should be that way =o

However, although many textures seem fine the ones with multi texture seem screwed:



This is pretty obvious from my side since i use the following to apply textures:

```
			
		while bitmappath[bitmappath.count] != "\\" do 
		(
			bitmappath = substring bitmappath 1 (bitmappath.count - 1)
		)
		bitmappath = bitmappath + Texture_Array[1]
		bitmappath = (substring bitmappath 1 (bitmappath.count - 3)) + "dds"
			
		map = StandardMaterial name: (ModelName +"_Material")
		map.diffuseMap = bitmaptexture name: (ModelName + "Diffuse")
		map.diffuseMap.filename = bitmappath
			
		if((findstring ModelName "nocull") != undefined) then map.twoSided = true
			
		if((findstring ModelName "alphablend") != undefined) then
				(
					map.opacityMap = bitmaptexture name:("Opacity_"+ModelName)
					map.opacityMap.filename = bitmappath
					if((findstring ModelName "alphablend1") != undefined) then
					map.opacityMap.monoOutput = 1
				)

```


It's pretty  much a provisional one to get textures easy and only if they are dds.

Update: Matrix applied *-*, i don't know how i will fix the multi texture, i guess it's just a matter of time
## Post #28
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-07T17:24:24+00:00
- Post Title: Re: [Request] Model Exporting

What you need is multimaterial instead of standardmaterial. And place each texture in each material layer(sub-material)

And also you mesh need multi-Face-material IDs to the corresponding sub-materials
remember the structure:

```
    char[128]	Texture_Name
    dword	Face_Start
    dword	Face_Count
  }
```

That Face_Start and Face_Count values help you to create those IDs.
## Post #29
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-08T19:35:08+00:00
- Post Title: Re: [Request] Model Exporting

Thank you it totally Worked *-*



However there is an issue with the number of Extra UV's.

The one textured objects are supposed to have this value as 0, such as weapons, however, Clothes have them as 2.

Which means, the whole script gets wrecked unless the value of the clothes, this means this means something more...

I really thought it was the number of Extra Uv structs since it only seemed to work

```
		(
			for i = 1 to Num_UV do
			(
				tu = readfloat f
				tv = readfloat f
				append UV_array[tu,1-tv,0]
				--print UV_array
			)
		)
```


Works really fine :C,but since this shouldn't be used on clothes (used female 00) it wrecks up

HOWEVER turns out thatt model female 00 has two model structures, but i think it's a coincidence since the second one has a 0.

Apparently all clothes are 2, so this may be something more like a Texture type, who knows...
## Post #30
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-08T20:13:01+00:00
- Post Title: Re: [Request] Model Exporting

Sorry for my bad, That ExtraUVs is just a flag! (I think it's actually a 8 bits flag)
You only need to skip the UV layers when it's value is 1!(or bit 0 set)

Anyway, good to know you finally got your script working!
## Post #31
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-10T00:52:39+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Thank you so much!, this couldn't have been done without you 

I will keep working on the format since there are more things to do, if anyone wants to join will be great , i will provide all i can so it's easy for anyone


Things i found today:

Had a hard time about models with 0 textures since some of them had 0 vertex and had to put a check for the number of vertex >_> (not a big deal, solved o:)

So after that little issue of just adding checks i would say that model chunk is 100% completed     




Thank you all for helping, specially fatduck  , i really appreciate all the effort you put on this thread, because i'm sure no one else would have been so patient with me and helped me to learn to read formats, it's probably something i will never forget ^^, again, thank you so much.

Now i will keep working on Bones, skinning and animation and it should be done , in fact, i have already the bones and their respective parents:



For some reason they appear misplaced, and probably has something to do with global and local coordinates of the items, i'll have to look foward for this and how to fix it by maxscript.

At first i did my own bone script:

```
		(
			if((findstring BoneName "Bip") != undefined) or ((findstring BoneName "Bone") != undefined) then
			(	
				if((findstring BoneName "Nub") != undefined) then
				(
					BipDummy = dummy name: BoneName
					BipDummy.parent = (GetNodeByName ParentName)
					BipDummy.transform = Transformation
					BipDummy.transform = BipDummy.transform * (BipDummy.parent.transform)
				)
				else
				(
					BipDummy = bone name: BoneName
					BipDummy.parent = (GetNodeByName ParentName)
					BipDummy.transform = Transformation
					BipDummy.transform = BipDummy.transform * (BipDummy.parent.transform)
				)
			)

```


Since i don't think there is an indication about if it's a bone or a dummy i just did it by names and it totally did the  trick.
After this i looked up this thread   ( [viewtopic.php?f=16&t=10928](http://forum.xentax.com/viewtopic.php?f=16&t=10928) ) and used chrrox's code, but i ended up in the same result, so my conclusion is that is not the bone creating script but something else, probably has something to global and local transformations, that might be the key to solve this, the cheap way to fix it is by using parent's transform but that would wreck maps, so it's discarded.

About skinning with the structure this format has should be a piece of cake, select the bone, and then weight all skins according to that bone, i'll look it up tomorrow 

About the animations i have no idea yet, i'll get some clues tomorrow i guess, it's too late i'll leave it for now , heading to sleep

I got it fixed by simply removing the transform of the model in case the parent was BONESYSTEM, except the face and hair, i used local transformation on them and although most of the faces and heads seem to be fine:



Also some ones get screwed.



Actually only this one screws up and don't know why... may be different to other for some reason, the name is 09_male_face.scn, it's attached to the post.

What i used:

```

				msh.parent = (GetNodeByName ParentName)
				
				if ParentName == "Hair_Bone_Dummy" then
				(
					msh.transform = Transformation
					msh.transform = msh.transform * msh.parent.transform
				)
				else if msh.parent != $BONESYSTEM then
				(
					msh.transform = Transformation
					msh.transform = msh.transform * msh.parent.transform
				)

```


Since both faces and hairs have hair dummy as parent.

Also, anothe real problem  here is that if it's not a biped the skeletons get screwed.



In the screenshot i selected the accessory (the two things on the sides and it's supposed skeleton, totally misplaced.
Maybe there is somewhere a tag that defines it as an acessory of the object and moves it to the center of the skeleton, i don't know yet.

Also i got again with the same problem as the katana:

[http://puu.sh/8GUT2.png](http://puu.sh/8GUT2.png)

It starts naming all the animation names as strings and the ocnverter wrecks up, don't know how to fix this yet, it's inside the rar also, the funny thing is that both have their first animation as "000000", so this may be the answer.

I'll keep looking if i get to know how to fix this :C

files: [http://puu.sh/8Htz5.rar](http://puu.sh/8Htz5.rar)

looks like rigging was not as easy as i thought...


i used this:

```
				(
					max modify mode
					skinMod = Skin()
					addModifier msh skinMod
					select msh
					modPanel.setCurrentObject skinMod
					for i = 1 to num_Skin_Bone do
					(
						
						maxbone = (GetNodeByName Skin_Bones[i])

						skinOps.addBone skinMod maxbone 1
						
						
					)
					
					--Skin_Bones =#()
					--Skin_Data=#()
					--Skin_Vert_Index=#()
					--Skin_Vert_Weight=#()
					print Vert_Array.count
					print Skin_Vert_Index.count
					print 
					
					for b = 1 to Skin_Bones.count do
					(
					
						for s = 1 to Skin_Data.count do
						(
							skinOps.ReplaceVertexWeights skinMod s b Skin_Vert_Weight[s]
						)
					
					)		
					

```


And goes veryr wrong, specially because most of the clothes don't have the hands on their rigged bone list, which makes everything even more annoying.
## Post #32
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-15T10:53:02+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Sorry again for double post, new things i found.

Although the bonesfor the biped work, they only work for the bipeds.



This is not a playable character, so the character is pretty much messed up, i don't know the reason of this.

My skeleton buildup:

```
					(
						BipDummy = bone name: BoneName
						BipDummy.parent = (GetNodeByName ParentName)
						BipDummy.transform = Transformation
						BipDummy.transform = BipDummy.transform * (BipDummy.parent.transform)
					)

```


This only seems to work on Biped characters, the rest are completely messed up and i don't know why, if someone knows how to fix it would be great >_<

[Here is the model of the pic](http://puu.sh/8N70X.rar)
(the maxscript is attached to the post)

Also, with this maxscript, when i try to get the Asteroid.scn model, the whole 3ds max crashes, and i don't know why since logs are useless when it gets frozen.
[Asteroid](http://puu.sh/8N74a.rar)
Also i don't know how to deal with the skinning either, i tried this:
this is how i parse (according to fatduck's structure, thanks again):

```
					--print "Number of Skin Bones:"
					--print num_Skin_Bone
				
					Skin_Bones =#()
					Skin_Data=#()
					Skin_Vert_Index=#()
					Skin_Vert_Weight=#()
				
					for i = 1 to Num_Skin_Bone do
					(
						BoneSkinName = readstring f
						--print "Bone Name:"
						print BoneSkinName
						append Skin_Bones BoneSkinName
						
						for m = 1 to 16 do readfloat f
						
						num_Skin_Data = readlong f
						--print "Number of Skin Data:"
						--print num_Skin_Data
						append Skin_Data num_Skin_Data
						for i = 1 to num_Skin_Data do
						(
							Vert_Index =readlong f #unsigned
							Weight = readfloat f
							append Skin_Vert_Index Vert_Index
							append Skin_Vert_Weight Weight
						)

```


how did i apply it:

```
				(
					max modify mode
					skinMod = Skin()
					addModifier msh skinMod
					select msh
					modPanel.setCurrentObject skinMod
					maxbone
					for i = 1 to num_Skin_Bone do
					(
						maxbone = (GetNodeByName Skin_Bones[i])
						skinOps.addBone skinMod maxbone 1
					)
					bone_id = for k=1 to (skinOps.GetNumberBones skinMod) where skinOps.GetBoneName skinMod k 0 == maxbone.name do exit with k 
					ClassOf ObjectToExportt
					
					for j=1 to Skin_Vert_Index.count do
					(
						skinOps.replaceVertexWeights msh.skin (Skin_Vert_Index[j]+1) bone_id Skin_Vert_Weight[j]
					)
				)

```

[I test skinning with this character set.](http://puu.sh/8N79v.rar)

This is probably wrong, but i really don't know how to deal with skinning and bones, sorry for not being able to do this by myself... this is my very first format ever and i'm still learning   

I tried a lot fo XentaX methods but none of them worked for me, or i  applied them wrong

I know i have asked a lot for help and looks like i'm getting the job done... but i'm seriously learning a lot with this ><

I left here all i could if someone wants to check it out

Thanks in advance
-Seyren
## Post #33
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-16T07:21:21+00:00
- Post Title: Re: [Request]S4 League Model Exporting

You Bones Initial transformation are WRONG!

Remember the struct I post:

```
  dword	Object_ID
  char[]	Object_Name
  char[]	Parent_Name
  float		??				//always 0.1
  float[16]	Object_Transform_Matrix		//Object_Version = 0.1 parent base, or 0.2 world base
  float	Object_Version
}
```

if Object_Version is 0.2, the Object_Transform_Matrix is already a world matrix. No need to consider the parent transformation
## Post #34
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-16T12:20:09+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from Seyren
>
> Also, with this maxscript, when i try to get the Asteroid.scn model, the whole 3ds max crashes, and i don't know why [...]hehehe, the reason is: you're reading a count of 1,324,679,169 here

```
		for i = 1 to num_Morph_Animation do
		(
			Tick_Time = readlong f
			readlong f
			count = readlong f

```

after address 0x47891 in asteroid.scn (4 bytes at 0x49571 I guess, didn't investigate further)

By the way: nice progress you've made. Wish I had the energy to learn like you do!
fn AnimMesh should be devided up into some sub functions imho. It's a little bit hard to overview.

Maybe you should place your name in the script as the author.
## Post #35
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-19T10:31:53+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Thank you so much for your support, i'm happy that you liked my progress , but this couldn't have be made without this forum, i owe this community a lot =)

Thanks shakotay2 for telling me why, i thought i had the Mesh reading perfectly, but seems that some of them crash, i will have to study this and see what can be wrong...   


Okay so i have been a bit busy and i couldn't continue,

I got a recommendation from fatduck to use the skinOps.replaceVertexWeight, and although i tried, i didn't manage to get it correctly.

I changed a bit the structure and this is how it is right now the skinning part.


```
					Skin_Data=#()
					Skin_Vert_Index=#()
					Skin_Vert_Weight=#()
						
					num_Skin_Bone = readlong f
					--print "Number of Skin Bones:"
					--print num_Skin_Bone
					
					max modify mode
					skinMod = Skin()
					addModifier msh skinMod
					select msh
					modPanel.setCurrentObject skinMod
					for i = 1 to Num_Skin_Bone do
					(
						BoneSkinName = readstring f
						--print "Bone Name:"
						print BoneSkinName
						append Skin_Bones BoneSkinName
						
						for m = 1 to 16 do readfloat f
						
						
						skinOps.addbone skinMod (GetNodeByName BoneSkinName) 1
						bone_id = for k=1 to (skinOps.GetNumberBones skinMod) where skinOps.GetBoneName skinMod k 0 == (GetNodeByName BoneSkinName).name do exit with k 
						  
						ClassOf msh
						UsedVertex = readlong f
						for j=1 to UsedVertex do
						(
							VertexID = readlong f 
							VertexWeight = readfloat f
							skinOps.replaceVertexWeights msh.skin (VertexID) bone_id VertexWeight
						)
						
					)		

```


Note that the arrays aren't used, since i was trying with them and without them i didn't remove them at all.

So the thing is:

I get the number of bones that are actually rigged and a for loop starts.

BoneSkinName gets me the bone we are going to skin, and i append it into the array, this is not very useful in this case, and after with 
```
						bone_id = for k=1 to (skinOps.GetNumberBones skinMod) where skinOps.GetBoneName skinMod k 0 == (GetNodeByName BoneSkinName).name do exit with k
```


I get the bone in the skin mod.

At this point everything is okay, works fine, now the hard thing is here:

```
						UsedVertex = readlong f
						for j=1 to UsedVertex do
						(
							VertexID = readlong f 
							VertexWeight = readfloat f
							skinOps.replaceVertexWeights msh.skin (VertexID) bone_id VertexWeight
						)
						
					)

```

Since not all the bones use all vertex, they are specified for each bone, so the first thing i thought was to do a loop with the number of used vertex, after that there are floats and ints, One of them specifies the vertex number and the other one the weight, so i finished doing this way.

Although everything seemed to be fine, This doesn't work.
Also the mesh and the bones have been made before the skinning so everything should be okay, but it's not working

If someone knows how to get this fixed Please let me know, i can't figure it out
Thanks again =) (attached latest plugin)
## Post #36
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-29T02:22:08+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Hi guys again, in case someone is following up, i'm still stuck in the same place, i didn't expect this to be so hard... i added a TL;DR at the end in case someone doesn't want to eat the Charles Dickens chapter, this is going to be a big post since it's been a while i don't post so i'm gonna spit it all out.

> Reply from fatduck
>
> You Bones Initial transformation are WRONG!

Remember the struct I post:
Code: Select allstruct Common_Obj_Properties {
  dword	Object_ID
  char[]	Object_Name
  char[]	Parent_Name
  float		??				//always 0.1
  float[16]	Object_Transform_Matrix		//Object_Version = 0.1 parent base, or 0.2 world base
  float	Object_Version
}
if Object_Version is 0.2, the Object_Transform_Matrix is already a world matrix. No need to consider the parent transformation

I know , but thank you i managed to get the bones properly... however... 
But the problem goes as follows.
I did the follwing check:

```
							(		
								newBone.transform = Transformation
							)
							else newBone.transform = Transformation * (newBone.parent.transform)

```


This goes for bones, However i had to do it the other way around in Meshes(Using local transform when it is 0.2)

Although this is supposed to be working most of the times I got forced to do A LOT OF CHECKS on the flags the name has to see if the model needs local or world transformation, because although i thought the 0.1 or 0.2 should be fine, it isn't   

Let's take a look at a "Monster" and the "Player" bones.

I'm going to use 3 examples, the first one is the Player biped, which is in the character folder.

First, our beloved female shirt (Reminding i'm always the piece of code from the upper part)



The version is 0.1, there is not a single object that is 0.2, so we can say that it works.

Next Let's go to the first monster,  the little girl.



Looks fine too, and the bones are 0.2, so everything is fine for now

Howeeeeever if we go to the second monster...





So there are two problems here


The first thing is that that is misplaced and should be up, this item is version 0.1, however, why it doesn't work with this object yet with the rest does?

This bug happens when the checks i did on the mesh transform are applied, but however, if i remove the checks and leave it just to the one above (Because i did extra checks on the mesh aside that one) This one will be right and the others won't

So the only thing it comes to my mind is that there must be something else that defines what is local and global transformation

Also as a curious thing The little girl had Bonesystem's version 0.2, while the Shirt and the grim reaper were 0.1, could this mean something? i don't know, but anyway, the only way to get the characters properly displayed is by removing the transformation matrix if their parent is the BONESYSTEM, so this at first shouldn't bother much..., but this is really weird, even though the world and local matrix are stated all the time i am forced to do a lot of checks because it changes too often.

First i have to check if the object has "oct" on it's name, since this is the collision mesh and must be local transformed so it belongs to the mesh, and this is 0.1! 

Then, i have to check if the objects belong to the "blast" helper, since this moves a lot of objects in the map and if i don't apply local transformation the objects go all over the place.

```
					(
						msh.transform = Transformation * (msh.parent.transform)
					)

```


And some of them are parent of parents, so even if i add this, there are some maps like [this one](http://puu.sh/95zhO/a8b4976670.scn) that need to get the local matrix applied, so i would have to  check the parent's parent if it's "blast" to get the job done.

Buuut if i do this, the following error appears when i try to run the grim reaper:

```
 -- Unknown property: "name" in undefined 
```
 
in line 440. 
```
else if((findstring msh.parent.name "blast") != undefined) then
```

The reason is probably because there is no parent, i guess, or i don't know,

So summing up, the transformation is screwed no matter how hard i try, but i'm sure the 0.2 and 0.1 floats are not enough.

Some screwed weapons.



Also, i'm sorry, i may be too dumb, but i don't know how to get skinning working, i tried a lot of stuff from differen't people's help, and i didn't get with the right key, i thought this could be done easier than the rest but i'm having a REALLY hard time to do skinning, i'm sorry, i am totally lost here and i don't know anymore what to do >_<, i even rewrote the whole script to make it more organized but didn't do the trick. Also fatduck you told me to check your fatimporter's skinning script but it's encrypted so i can't really check it q_q

I tried my best, but skinning beats me, maybe it's easier than i think, but i ran out of ideas and sources..., crawled from all the skinning scripts, (such as Diablo II for example), but got no results.

I belive It's almost done, but something is missing:




It looks like some vertex don't get skinned, but some of them actually get applied.

The last thing i have is from shakotay2, which helped me to point out the follwing issue:

```
				(
					BoneSkinName = readstring f
					--print "Bone Name:"
					print BoneSkinName
					--append Skin_Bones BoneSkinName
					
					MaBone = (GetNodeByName BoneSkinName)
					skinOps.addbone skinMod MaBone 1

					
					for m = 1 to 16 do readfloat f
					
					ClassOf ObjectToExportt
					
					kmax = skinOps.GetNumberBones skinMod                  
					k= 0; 
					while k < kmax do
					(
						k = k + 1; --print k
						BN1 = skinOps.GetBoneName skinMod k 0; BN2 = (GetNodeByName BoneSkinName).name
						format "<%> <%>\n" BN1 BN2
						if BN1 == BN2 then
						(   
							bone_id = k
							k = kmax; print "break k-loop"
						)
					)
					
					ClassOf msh
					num_Skin_Data = readlong f
					--print "Number of Skin Data:"
					--print num_Skin_Data
					append Skin_Data num_Skin_Data
					for i = 1 to num_Skin_Data do
					(
						Vert_Index =readlong f #unsigned
						Weight = readfloat f
						skinOps.setVertexWeights skinMod (Vert_Index+1) bone_id Weight
						--append Skin_Vert_Index Vert_Index
						--append Skin_Vert_Weight Weight
					)
				)

```

So it turns out that if we check at the log, BN1 and BN2 will never met, however i managed to make some of them get met.

which may mean why some of the vertex are never met, but i am not sure how to handle this.

Found out a minor issue, that although is not a big deal, maybe someone knows how to deal with, it has to do with the materials,
in concrete with the MultiMaterial.

In line 483:

```
							(
								map.opacityMap = bitmaptexture name:("Opacity_"+ObjName)
								map.opacityMap.filename = map.diffuseMap.filename
								
								if((findstring ObjName "alphablend1") != undefined) then
								(
									map.opacityMap.monoOutput = 1
								)
								else if((findstring ObjName "Alphatest") != undefined) then
								(
									map.opacityMap.monoOutput = 1
								)
								
							)

```

The error is: -- Unknown property: "opacityMap" in undefined, so i guess it doesn't identify it, however this only happens in the map 
i gave above, ds5_station (in case you missed it, [this one](http://puu.sh/95zhO/a8b4976670.scn))
Again this is not a great deal, but if someone knows what is wrong it will be great 


Anyways.

Script redone

To do list:

Skinning
Animation

- Fix the Transformation matrix issue (world and local things,there must be something else that tells what to use rather than a lot of checks, or maybe not...)
Some models with multiple objects [here.](http://puu.sh/95ELc/5f583c9a83.rar)
- Rewrite the material section into something that doesn't make the program throw errors(mostly multi-material issues).
- Fix the mesh import, since there are still models that are not working, these models are packed [here.](http://puu.sh/95DX8/7d1c066bc3.rar)

The errors are mostly in the material section and in the transformation section (the checks are bad and it might crash since it lacks parents probably), and some others make the whole program crash
(As shakotay2 stated before, there is a point that reads a giant count and it crashes, but i am not sure where the problem is.)



For some reason the script stops working everytime i close 3DS so i have to do some random changes and put it back how it was everytime i start, not sure if i'm the only one, would be good to know if osmeone else experiences this, it's like it doesn't open the file, or i don't know, it's a weird bug because it actually works.

I have to rewrite the whole script in another file and when i finish it works on the previous one, i seriously don't understand this.


Other things i found:

Remember the Katana_a.scn, which had a weird animation pattern?, well i never noticed, but we allways got a unknown flag that always was 0, and turns out that in this one the flag is 1, and then it starts naming all the animation names, this can lead to an unknown loop i don't know yet, i will find it out eventually, but thank god i found out that there was a difference, i was so desperate about this issue!

Anyways, in case that you did it, thank you for reading all of this, and if you have any clues on how to get any things fixed, please, let me know, this thing is going to kill me this way   

And that's it for today, heading to the bed, good night   

TL;DR: Transformation is a mess and I'm getting really annoyed by Skinning, yet i think it's almost done, but i don't know to be honest.
## Post #37
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-29T09:21:19+00:00
- Post Title: Re: [Request]S4 League Model Exporting

I don't have any of your problem at all?
Remember the whole format is object based. It means every chunk(ID) is a object, and they can have parent/children.
Your "multi-objects" error is possibly missing some "mesh parent"?



And I follow my format post above, everything (transformation, skinning) just fine!





which MOB file give you mis-aligned bones?
## Post #38
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-29T12:42:24+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Oh god it made me so happy look at that for some reason   

[This one.](http://puu.sh/965A3/6d99c111bc.rar)

It may be what you mean, some missing parents, it would make sense, but i can't really tell... Specially because i have to apply local when is 0.1 on bones, however i have to apply world when it's a mesh, also i don't know how you check it, but if the parent is the BONESYSTEM the only way i have to apply it properly is by applying NO transformation matrix.

I made sure every single object appeared, even if it was a helper (for helpers, 0.1 is world transformation, since theuy don't have parent at all, not even the .scn header dummy)
It's also curious about the helpers because they have 2 transformation matrix.

If we apply the one from the common_obj_properties:



the position actually looks right, it's where the "ball" spawns, so everything is okay, however the size of the helpers doesn't seem to be that okay.



alpha_limited_area03 helper from /background/ds5_station.scn

this is supposed to be the lower part of the map, if you fall, you are supposed to die, so i thought this should be a big helper that cover the whole floor.

What happens if i apply the matrix from the chunk?
To my surprise:



The helper suddenly fits the floor of the map!, so this means the final transformation matrix should be the postion and rotation of the common_obj_properties, yet the size of the second transformation matrix, this is only an assumption, though, or maybe i am getting all the stuff wrong again...



The reason my mesh importer fails though is probably at the texture part, because the structure is supposed to be 2 strings with a fixed size of 1024 bytes and two long bytes that tells you the start and how many faces does it take in case it's a multi texture (in case it's a single texture, the first long will be 0 and the next one will be the same than the number of faces, that's why it tells you the number of faces TWICE every time we import a mesh, but if we take a multi texture object this number will be different)

And well, to do this i did the following loop:

```
			print "Number of Textures:"
			print NumTex
			
			Texture_array=#()
			Bump_array=#()
			FaceStart_array=#()
			FaceCount_array=#()
			
			for i = 1 to NumTex do
			(
				tex = readstring f
				print tex
				fseek f -1 #seek_cur
				for i = 1 to (1024 - tex.count) do readbyte f
				append Texture_Array tex
				
				tex = readstring f
				print tex
				fseek f -1 #seek_cur
				for i = 1 to (1024 - tex.count) do readbyte f
				append Bump_Array tex
				
				Face_Start = readlong f
				--print Face_Start
				append FaceStart_array Face_Start
				Face_Count = readlong f
				--print Face_Count
				append FaceCount_array Face_Count
			)

```


since Maxscript is very limited and doesn't have many tools about this i'm afraid (or at least i haven't found anything on the internet or other forums) this was the only way to do the loop correctly, however i'm not very confident about this loop and it probably fails hard at some meshes, making it crash.

Aside from that, i will keep looking about the transformation thing, but i can't really find a solution for this, since i made spawn all the objects even as helpers to make sure not a single parent was missing...

And well, the skinning almost looks done, but as i said before some of the vertex don't get skinned and it wrecks up, i'll keep looking at this...

an almost, yet screwed Skinning.

Attached again, this time it displays helpers.
## Post #39
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-05-29T19:23:17+00:00
- Post Title: Re: [Request]S4 League Model Exporting

You are right that "grimreaper.scn" doesn't follow objVer(0.1/0.2), all bones are world transformation.
Are there any models don't follow this objVer!?

For your world/parent transformation problem.
If the object didn't have parent then the transformation is simply world transformation, right?
so you can code it like this:

```
if (objVer == 0.1) and (obj_parent_String != "" ) then (
 obj.parent = (getNodeByName obj_parent_String)
 obj.transform *= obj.parent.transform
)
```


In scn, every chunk is an object, and objects have transform (It represent "something" in the world/game coordinate)

For the "Helper" things, ID = 0x25ADF0D1.(I am no sure is it really a helper, I just define it as helper).
There are some data I havn't decoded, maybe that contains area/size/effect etc.
But definately not transformation matters! Since 
1> In 3dsMax, helpers object had no volume, the "size" of the helper is for visualisation only.
2> the scale part of "alpha_limited_area03" is [1,1,1](from common_obj_transform), I can't see any reason will fit your scene!?

Lastly, what do you mean have 2 transformation matrix?


this is [ds5_station max file (3dsmax 2009) and a log](http://1drv.ms/1mvQA8Q) for your reference.
I still using objVer to set the transformation without any problem!?
## Post #40
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-05-29T21:50:44+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from fatduck
>
> You are right that "grimreaper.scn" doesn't follow objVer(0.1/0.2), all bones are world transformation.
Are there any models don't follow this objVer!?

For your world/parent transformation problem.
If the object didn't have parent then the transformation is simply world transformation, right?
so you can code it like this:
Code: Select allobj.transform = common_obj_transform
if (objVer == 0.1) and (obj_parent_String != "" ) then (
 obj.parent = (getNodeByName obj_parent_String)
 obj.transform *= obj.parent.transform
)

In scn, every chunk is an object, and objects have transform (It represent "something" in the world/game coordinate)

For the "Helper" things, ID = 0x25ADF0D1.(I am no sure is it really a helper, I just define it as helper).
There are some data I havn't decoded, maybe that contains area/size/effect etc.
But definately not transformation matters! Since 
1> In 3dsMax, helpers object had no volume, the "size" of the helper is for visualisation only.
2> the scale part of "alpha_limited_area03" is [1,1,1](from common_obj_transform), I can't see any reason will fit your scene!?

Lastly, what do you mean have 2 transformation matrix?


this is ds5_station max file (3dsmax 2009) and a log for your reference.
I still using objVer to set the transformation without any problem!?

If you remember your structure:

```
  Common_Obj_Properties
  float[16]   ??
}

```


I think those 16 floats are a transformation matrix   

I think The first transformation matrix positions the object, and the second rotates it and scales it, since they are not "actually" helpers, depends on how you want to take it, they are spawn positions from the game, places where if you step on it you die, so they can't be just little cubes

So i thought using the scale and rotation from the second matrix aaand looks "more accurate"

but still screwed since probably in the engine Y => Z and Z => Y, but makes more sense.


tested on city_highway.scn

But i'll leave it the way it is since this is not important at all... and the results are more messy, so we can just pass it out.

About other transformations, i tried your code and it works great, thank you ^^, i applied it this way on meshes:

```
				(
					msh.transform = Transformation
					if (ObjVer == 0.1) and (ParentName != "" ) then 
					(
						msh.transform *= msh.parent.transform
					)
				)

```


Since if i don't check about the bonesystem the shirt and stuff gets screwed.

I'm going to list the models that don't get the position applied properly:


09_male_face
This face looking up.

The parent is Hair_Bone_Dummy, and this is one of the few faces that don't get the position right, because others do.

07_male_face 

Another thing that gets not properly positioned:


07_male_skirt
The mesh is WELL POSITIONED BUUUUT the bones are right here:

You can imagine that more or less they have the same shape
log:[http://puu.sh/96IbZ/53dd46bcc8.txt](http://puu.sh/96IbZ/53dd46bcc8.txt)
the bones are called:

07_Male_L_skirt_bone1
07_Male_L_skirt_Dummy1
07_Male_R_skirt_bone1
07_Male_R_skirt_Dummy1

So you don't have to kill yourself while searching on the log :c

Another similar file:
01_female_spine00


This is the skirt from the bottom part of the shirt, and you can see the bones are completely messed.


Now it's weird because grimreaper.scn gets an error in the scythe object, because it doesn't identify the transformation, i'll fix it later
if i manage to.
log: [http://puu.sh/96HBm/bdb8555ff5.txt](http://puu.sh/96HBm/bdb8555ff5.txt)

here are all the ones that are messy that i found:

I added aditional ones that are not actually screwed, but since what is screwed is the accessories and not the base shirt i guess is needed to check if everything is okay.

[http://puu.sh/96Jq9/a1a5e75801.zip](http://puu.sh/96Jq9/a1a5e75801.zip)

Added aside:
One face that gets positioned correctly
07_male_muffler which probably won't work since it has a different animation pattern, but it belongs to the same shirt than the 07_male_skirt, in case you want to test.

Updated script  Thank you again for your help
## Post #41
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-05-31T14:00:20+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Finally I managed to get your script logging the morphing part of taserplasma.scn without errors.
(Hah, really exhausting, I'm curious how fatduck solved this.)

Since my changes depend on absolute addresses for this one file I'll send the script per PM, Seyren.
(I'm too tired now to search for flags which could help to get rid of the addresses.)

Here's the last logged chunk from file's end:
"32. start: 0x40f2a -----------------------------------"
CHUNK: 135305464 (MESH)
ObjName: Plane77_alphablend2_nocull (Sword_Wea_Dummy)

so the changes seem to be ok.
## Post #42
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-01T08:37:21+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Updated the Morph_Animation part:

```
    struct Morph_Animation {
      dword	Tick_Time
      dword	count1
      struct Anim_Data1 {
        dword	 Index
        float[3] value
      }
      dword	count2
      struct Anim_Data2 {
        dword	Index
        word[2]	??					//?
        float	value
      }
    }
```

You should be able to phasing the animation without any errors now!

For the "grimreaper.scn" and "01_female_spine00.scn" etc, I can't found and special/difference from others scn!?
## Post #43
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-06-02T12:28:11+00:00
- Post Title: Re: [Request]S4 League Model Exporting

well, the asteroid caused me some headache. Though I manged to get rid of absolute addresses I had to introduce some file specific conditions (if count==x) which make the script hard to read:

```
	    nmaAddr= ftell f
		print ("num_morph_anims at "+"0x"+bit.intAsHex(nmaAddr) as string)
		num_Morph_Animation = readlong f
		format "No of Morph Anims: %\n" num_Morph_Animation
		if  num_Morph_Animation > 1000 then num_Morph_Animation = 0 ; -- for debugging purposes only
		End_Morph=#()
		if num_Morph_Animation==0 then cnt=0 else cnt=1
		count = 0
		for k = 1 to num_Morph_Animation do	-- k was i before, a bug, but maxscript didn't mind...
		(
			if k==1 then Tick_Time = readlong f
				else if cnt==0 then  Tick_Time = readlong f
					else if count==9 or count==14 then  Tick_Time = readlong f		-- asteroid only
			cnt = readlong f			
			count = readlong f
			format "%. cnt % %\n" k cnt count
			if cnt !=0 then if count !=jMax then count =jMax		-- for debug only
			if cnt==0 then cntx=cnt else cntx=count				
			if count==9 or count==14 then				-- asteroid only
			for i = 1 to count do (
				a = readlong f; b = readshort f; c = readshort f
				d = readfloat f; 	format "% % %  %\n" a b c d
			)
			else if count==143 or count==58 then				-- asteroid only
			for i = 1 to count do (
				a = readlong f; b = readfloat f; c = readfloat f
				--format "% % %\n" a b c
			)
			else			
			for i = 1 to cntx do (
				a = readfloat f; b = readfloat f; c = readfloat f
				d = readlong f; 	--format "% % % - %\n" a b c d
			)
			if cnt !=0 then ( e = readlong f; print e; print)
		)
		if cnt !=0 then (			
			if j==1 then (
				delta = nmaAddr-startA; print delta
				delta -= 3; g_delta = delta	-- global var (required for j==2)
			)
			print ("before skip "+"0x"+bit.intAsHex(ftell f) as string+", delta= "+g_delta as string)
			if count==9 or count==14 then fseek f -16#seek_cur	-- asteroid only
				else (
					if j !=jMax then fseek f g_delta#seek_cur		-- skipping 79/95 bytes in taserplasma.scn	
					else fseek f -4#seek_cur
				)
		)
)
```


Though the complete script does a corrrect scan of asteroid.scn now I guess there's a much better solution?

btw:I used Seyren's script where I added my "horrible function" and a modified call:

```
				addr = ftell f -- used in horrible() to calculate delta
				print ("startA: 0x"+bit.intAsHex(addr) as string)
				tmp = readlong f; tmp = readlong f; fseek f -8#seek_cur
				--format "%. tmp: %" i tmp
				if (i==1) or tmp!=0 then Anim() -- parameter Flag removed
				addr = ftell f
				if (addr<fsize) then horrible addr i NumAnim
			)
		)	
		
		--OBJECT LOCATION
		else if object_ID == 632156369 then
		(...
```




asteroid.JPG (20.28 KiB) Viewed 126 times
## Post #44
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-03T06:24:29+00:00
- Post Title: Re: [Request]S4 League Model Exporting

If just want to phase the file without animation. Use these codes:

```
       fseek f (num_Trans_Animation*0x10) #seek_cur
       num_Rotate_Animation = readlong f
       fseek f (num_Rotate_Animation*0x14) #seek_cur
       num_Scale_Animation = readlong f
       fseek f (num_Scale_Animation*0x10) #seek_cur
       num_Visibility_Animation = readlong f
       fseek f (num_Visibility_Animation*0x8) #seek_cur

       num_Morph_Animation = readlong f
       for i = 1 to num_Morph_Animation do (
        tm = readlong f
        Cnt1 = readlong f
        fseek f (Cnt1*16) #seek_cur
        Cnt2 = readlong f
        fseek f (Cnt2*12) #seek_cur
       )--end for Manm
```


And It  seems like only "character" and "weapons" files need to consider parent transform!? All "monster", "slaughter" are already in world transformation.

asteroid.scn should look like this:
[asteroid_scn.jpg](https://xentaxbackup.github.io/file/7422_asteroid_scn.jpg)
## Post #45
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-03T12:31:22+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from fatduck
>
> If just want to phase the file without animation

I'm planning to get animations too, but right now i can't manage to parse the mesh properly, so i can't proceed to animations until i make sure the mesh is properly imported 

I have been looking for unknown values and there are 2 values we have been ignoring all this time, they are the first two values that we read once we start the mesh chunk.

In case of our asteroid, this is most of the time the values of those two:

```
Unknown Values: [8] [1045220557]
```

I checked other scns and the second value is ALWAYS  1045220557. This may be a "Texture header", the other is unknown.

The value of the first one goes from 8 to 105, and then goes down to 8, and up to 105, it switches between those two numbers.
Grim Reaper for example is 33, 4, 12...  can't really tell the value.

However, ALL the weapons have this value in 0, when the monsters don't, so we can't get anything out of here right now.

To my surprise, at the moment that the program crashes (but doesn't freeze the program tho) the value is [32873], i really don't know what it means

AAAaaand i fixed the asteroid, i'm retarded, i'm sorry:



I was reading vw in scale, messing everything up, sorry for bothering this much   

> Reply from fatduck
>
> 
And It  seems like only "character" and "weapons" files need to consider parent transform!? All "monster", "slaughter" are already in world transformation.

Because of this i'm forced to do the follwing:

```
				(
					msh.transform = Transformation
					if (ObjVer == 0.2) and (ParentName != "" ) then 
					(
						msh.transform *= msh.parent.transform
					)
				)

```


If you remember you gave me this condition, however it was if ObjVer == 0.1, if i let it in 0.1, maps and characters work fine,  but slaughters and weapons are messed up, and if i change it to 0.2 it goes the other way around, you didn't really find any differnce aside the 0.1 and 0.2? because there must be something else that determines it, i can't really tell :c

Things yet to solve:

-Transformation Matrix
-Skinning
-Material application

Skinning:

```
-- Unable to convert: undefined to type: <node>
```

Apparently MaBone = (GetNodeByName BoneSkinName) doesn't get any Bone from the scene and this crashes
Materials(Multi)

```
-- Unknown property: "opacityMap" in #Multi/Sub-Object:chaser_ophelia_lock_alphablend1_nocull_Map(Standard:Material #146, Standard:Material #147)
```

Doesn't locate opacityMap and well, i guess this material coding is really bad, if someone else knows a better way to apply materials let me know   
By the way it crashes with this line of code: multimap.opacityMap.monoOutput = 1 (in Line 538)

These are the only 3 things that are wrecking up the converter, Transformation for Position, Skinnin for crashing some models (like Lilith) and MultiMaterial issues, i'll bring some news of what i have done in a few hours

Attached latest version

Again thanks for helping and i'm sorry for doing such mistake
## Post #46
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-03T21:22:56+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Seyren,
multimap[v].opacityMap.monoOutput = 1

for Transform, I end up using a custom switch in GUI to force the transform by parent or not.
## Post #47
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-04T03:08:28+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from fatduck
>
> Seyren,
multimap[v].opacityMap.monoOutput = 1

for Transform, I end up using a custom switch in GUI to force the transform by parent or not.

Aaaw, whoops x2, i'm sorry   , thanks again for answering that

Since i don't have a gui yet, i did this:

```
else if((findstring fSCN "character") != undefined) then TValue = 0.1
else TValue = 0.2	

```


Since luckily all the ones from the same folder have the same "transformation", i can do this and will work fine for now.

Animation chunk is probably fully parsed, remember there was an issue with "special animations" such as the katana? well, here it is:


So once i manage to fix the  skinning i think we are ready to go for the animations  (Have no idea how to, but well, everything at it's time)

That being said, i'll list up again what is left:

To be fixed:

Skinning
And if someone discovers the hidden mistery of it, the Transformation Matrix, but i can perfectly deal with what i did before.

To do:
Animations(This is probably the hardest thing of all, i can imagine   , but everything at it's time).

I'll post or edit this post if something new pops up, but there is nothing real new but fixes at the moment.

Again thank you all for helping me this far and being so patient with me, nothing of this could have been done without you
## Post #48
- Username: ChrisX930
- Rank: veteran
- Number of posts: 154
- Joined date: Sun Feb 23, 2014 11:10 pm
- Post datetime: 2014-06-05T05:24:29+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Could you tell me how can I extract a Map (for Example Station 2) so I can use it in 3dsmax?
## Post #49
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-06T02:58:59+00:00
- Post Title: Re: [Request]S4 League Model Exporting

I just decided to add a lot of checks according to the models to display the model properly, i'm not going to bother anymore on the matrices for now, i'll leave it for later.

Working on skinning now.



Still having the same issue, not all the vertex get parsed, looks like many of them do and get properly positioned, but others don't, and i honestly have no idea why this is going on.

I am not really sure why this is happening since i think the process is fine, or at least that's what i thought.

```
					num_Skin_Data = readlong f

					append Skin_Data num_Skin_Data
					for i = 1 to num_Skin_Data do
					(
						Vert_Index =readlong f #unsigned
						Weight = readfloat f
						skinOps.setVertexWeights skinMod (Vert_Index+1) bone_id Weight
					)
				)

```


If someone is good at skinning please i would like to know how to gets this solved, since althought i know how to rig in 3DS max and i'm kind of good at it, this is another different world and i don't get how to get the proper formula

i tried a lot of different combinations but this is the one that gives me best results.

attached the full thing for testing, i would thank a lot if someone knows how to fix this, because it has been bugging me for almost two months and i have no idea on how to...

> Reply from ChrisX930
>
> Could you tell me how can I extract a Map (for Example Station 2) so I can use it in 3dsmax?
I am not sure what do you mean, what do you want to do with the map?
## Post #50
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-06T06:37:11+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Since in your i loop, you will add a new bone to skin modifier.
That is the index of your bone in skin modifier, so:
skinOps.setVertexWeights skinMod (Vert_Index+1) i Weight
## Post #51
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-06T19:48:32+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from fatduck
>
> Since in your i loop, you will add a new bone to skin modifier.
That is the index of your bone in skin modifier, so:
skinOps.setVertexWeights skinMod (Vert_Index+1) i Weight

Did you test it? because it doesn't work for me :c

```
-- Runtime error: Bone index out of range: 2
```


The loop is from i = 1 to Num_Skin_Data, which is the number of vertex the bone has skinned, so if for example they are 45 i do a loop of those 45 vertices, get each vetrex ID and the Weight they should have, and the bone id is stated here:

```
					while k < kmax do
					(
						k = k + 1; --print k
						BN1 = skinOps.GetBoneName skinMod k 0; BN2 = (GetNodeByName BoneSkinName).name
						format "<%> <%>\n" BN1 BN2
						if BN1 == BN2 then
						(   
							bone_id = k
							k = kmax; print "break k-loop"
						)
					)

```


So the bone ID should be fine o.o
## Post #52
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-06T20:12:41+00:00
- Post Title: Re: [Request]S4 League Model Exporting

In your script:

for i = 1 to Num_Skin_Bone do
(
  ...
	for i = 1 to num_Skin_Data do
	(
	  ...
	)
  ...
)

You are using the same variable twice! Although 3dsmax will set all variable as local variable, you can't reference to the outer loop inside inner loop...
## Post #53
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-07T02:53:59+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from fatduck
>
> In your script:

for i = 1 to Num_Skin_Bone do
(
  ...
	for i = 1 to num_Skin_Data do
	(
	  ...
	)
  ...
)

You are using the same variable twice! Although 3dsmax will set all variable as local variable, you can't reference to the outer loop inside inner loop...

Yes, but it gives the same result i do have :s

It's true though, that the bone id integer is now useless since i could have used the i value, didn't think of it   



It's like some of the vertex are linked to the other bones, or something like that, i don't know.

Then i realized something:




They have the vertex weights properly positioned.

If for example, if the left boot was carrying away part of the right boot when rotating it how come there are no weighted vertex on the right one?



There are not a single weighted vertex on the right boot in the left boot bone, however, let's move the left boot.



It doesn't make any sense!

This means i had the vertex weight properly done all this time and for some other reasons this is happening to me...

I have no idea what is going on... could this be some weird 3DS Max Settings? Or how could this happen? It's really weird...
## Post #54
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2014-06-07T06:44:39+00:00
- Post Title: Re: [Request]S4 League Model Exporting

OK, I tested with your method and it seems that evertime you addbone to your skin modifier, the skin weight changed!!!
(Mainly in 1st skin bone)

So you have to add all bones before start on weighting!
## Post #55
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-07T16:55:50+00:00
- Post Title: Re: [Request]S4 League Model Exporting

I tried both, once i set all the bones and while setting them in, ended up in the same result, i ended up fixed it by using replacevertexweights instead of setvertexweights, i don't know how, but it worked.



I'm not sure if it's about the files or just me but there are still some flaws in skinning



Am i the only one getting this? (lilit.scn)


Also i'm having some problems positioning the skirts and accessories of the clothing...



This is the skirt and the bones from the skirt are down there, does anyone know how to put them on the top?

All the bones are parented to a Dummy, and this Dummy is parented to BONESYSTEM, and since BONESYSTEM is always on 0,0,0.

So there must be a way to put the bones up to the skirt.

Any suggestions? :C
## Post #56
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-10T02:43:54+00:00
- Post Title: Re: [Request]S4 League Model Exporting

More Weird checks



This check function is just too big, i am probably doing it wrong but since there is no way i can find a clue on when to apply global and local transformation and the 0.1/0.2 is not even enough i must proceed to more weird stuff.

Anyway, although there are a lot of stuff to fix i guess i'm going to animation now 

Let's see how it turns out



I did put them by layers since i thought it was more organized this way, correct me if wrong, i have no idea about animations either how to continue, i'll keep looking up stuff i guess.
## Post #57
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-19T03:46:39+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Sorry for not posting very often, i have been doing some research about the game.

I discovered that the accessories of the clothes is attached automatically in-game with the engine, so there is no way i can actually put that, maybe reading a game file or something, but that's not a priority for now.

I'm working on animations.

Working on animations, and well, since i have no clue how animations work, i did the following:

For Position animation for example:

```
		--Initial_Translation=#()   
		(
		Pos_vx = readfloat f
		Pos_vy = readfloat f
		Pos_vz = readfloat f
		
		Ipos = point3 Pos_vx Pos_vy Pos_vz		
		--format "Initial Translation: [%,%,%]\n" Pos_vx Pos_vy Pos_vz
		)
                num_Trans_Animation = readlong f
		--format "Translation Animations: %\n" num_Trans_Animation		
		for x = 1 to num_Trans_Animation do
		(
			Tick_Time = ((readlong f #unsigned) / 80)
		  
			vx = readfloat f - Pos_vx
			vy = readfloat f - Pos_vy
			vz = readfloat f - Pos_vz
			
			Apos = point3 vx vy vz
			--Apos = Anode.pos * Apos
			
			if ANode != undefined then
			(
				with animate on 
				(
				   at time Tick_Time
				   (
						--in coordsys local ANode.pos += Apos
						in coordsys parent ANode.pos += Apos
						--in coordsys world ANode.pos += Apos
				   )
				)
			)
		)

```


So what basically i do is to animate using parent coordinate system, or that's how it's supposed to work (First i do the current cord - the Initial position (vx = readfloat f - Pos_vx), and i'm sure this is not the best way to do it.

As you can see i tried using local, global and parent transformation, global is totally messed up, so it's discarded, while local and parent do give the same result.

Here is a comparision of the supposed original animation and the one i am having (Mine is on the left, the good one is on the right)
[http://puu.sh/9zZSQ/89d31daf9e.avi](http://puu.sh/9zZSQ/89d31daf9e.avi)
(The weapon is in [This Folder](http://puu.sh/9wYNJ/3f3e41d66e.rar), assault_rifle.scn)
(The video doesn't even last 1 second so i recommend you to stop it frame by frame to see the difference)

You may think this is not that different but when the animation gets more complex everything goes all over the place, and is very messy.

So it looks like the animation is "FINE", but it goes way harder than it should, like it moves and rotates more than it should, and the more the animation goes on, the further it goes




So it's like there is a value that makes it get more screwed the harder the animation goes.

Does anyone know how to apply animations correctly? This is my first time i ever do an animation maxscript and i'm failing horrible at it, so it would be great if someone tells me how, since i'm 100% sure what i am doing s wrong,  i searched all over the place and i can't really get a clue on how to do this.


Thanks in advance
Seyren
## Post #58
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-06-29T04:11:11+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Position Animation and Scale work now 





[X]Pos
[]Rot
[X]Scale
[]Alpha/Transparent
[]UV Animation

Without a doubt the rotation is the hardest one.

I'm using this for rotation:

```
		(
			Tick_Time = ((readlong f #unsigned) / 80) --Frame
		  
			vx = readfloat f
			vy = readfloat f
			vz = readfloat f
			vw = readfloat f
			
			Arot = quat vx vy vz vw
			
			if ANode != undefined then
			(
				with animate on 
				(
				   at time Tick_Time
				   (
					   
						in coordsys parent ANode.rotation = IRot --this is the initial rotation of the model/bone before the whole thing starts
						in coordsys parent ANode.rotation += Arot --Stated before this is the rotation of the current frame
						
				   )
				)
			)
		)

```


I have been playing with + and - to get different animations, also with local, world and parent but this is the most accurate thing i got.



You see the thing from the right goes to the left instead of right, it's like the whole thing is inverted, but i tried putting -vw, -vy, -vx and -vz to see if it could get fixed

This one is creepy, yet curious.

The bones are actually reversed for some reason, if i comment the animations it goes like this:


What is actually impressive is that the bones and skinning are working properly, lol.

And the one that is totally screwed up.(sentipumbe.scn)
Parent rotation:



Local:



World:



This actually makes me chuckle every time i see it.

We can conclude that parent rotation is the one.

You may think that the problem is in in coordsys parent ANode.rotation = IRot but it's not since if i left only that line alone everything is fine and the bones don't get screwed at all, the problem is in the other one.

I am probably doing this wrong and there is actually a better way to do this, but i can't really tell, if someone cand recommend me a script with a rotation animation already made that would work better than this it would be appreciated it.

Until then, i'll keep working on this.

EDIT: I tried to divide the values (v rotation values) by 100000 and 500000 (because why not) and this happened:
100000:

500000:


Does it make sense? No (At least not to me)

Works? Not really, but for some reason the animations is clearer.

So now this means that i have to divide the value by a number and that the angle is reversed in some models, I honestly don't know how is this going on but well, i had to try.
## Post #59
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-04T20:02:06+00:00
- Post Title: Re: [Request]S4 League Model Exporting

Animations "work" now:



See the asteroid being blown in low framerate 

However, there is a issue that in a lot of models although the angles are okay, the angles are reverted, let me show it:



You can see that the fingers are going up instead of down, this happens on a lot of anims.



Here is even worse, lol.

I have no clue why this happens, i tried a lot of stuff and i can't manage to get it right.

Since the devs work on maya i'm trying to do a py script on maya in hopes of getting this working somehow, because i did all sorts of attempts on MS and i can't manage to get it.

I'll keep working on both 3DS and Maya to get some clues.
## Post #60
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-07-24T05:29:21+00:00
- Post Title: Re: [Request]S4 League Model Exporting

> Reply from Seyren
>
> Animations "work" now:



See the asteroid being blown in low framerate 

However, there is a issue that in a lot of models although the angles are okay, the angles are reverted, let me show it:



You can see that the fingers are going up instead of down, this happens on a lot of anims.



Here is even worse, lol.

I have no clue why this happens, i tried a lot of stuff and i can't manage to get it right.

Since the devs work on maya i'm trying to do a py script on maya in hopes of getting this working somehow, because i did all sorts of attempts on MS and i can't manage to get it.

I'll keep working on both 3DS and Maya to get some clues.Hello friends can share latest 3dmax script, please, thank you
## Post #61
- Username: Seyren
- Rank: advanced
- Number of posts: 63
- Joined date: Sat Oct 30, 2010 8:39 pm
- Post datetime: 2014-07-26T01:17:22+00:00
- Post Title: Re: S4L Model Exporting

> Reply from raykingnihong
>
> Hello friends can share latest 3dmax script, please, thank you

I'm sorry but there has been a lot of tension lately on achieving to get the scn models for hacking purposes in-game on other forums, so for now i will keep this project private unless someone can actually help me getting the quaternions working and also to be someone to be trusted, i'm afraid this gets on the wrong hands.
## Post #62
- Username: ibreakdev
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 25, 2014 6:23 pm
- Post datetime: 2014-08-26T17:35:47+00:00
- Post Title: Re: S4L Model Exporting

hey guys, how can i insert in my s4 private server a new scn (for exemple taserplasma.scn)?, because if i import a new model .scn into my client, client crashes. Please help me
## Post #63
- Username: denny9700
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 04, 2014 5:50 am
- Post datetime: 2014-12-03T22:04:47+00:00
- Post Title: Re: S4L Model Exporting

> Reply from raykingnihong
>
> Seyren wrote:Animations "work" now:



See the asteroid being blown in low framerate 

However, there is a issue that in a lot of models although the angles are okay, the angles are reverted, let me show it:



You can see that the fingers are going up instead of down, this happens on a lot of anims.



Here is even worse, lol.

I have no clue why this happens, i tried a lot of stuff and i can't manage to get it right.

Since the devs work on maya i'm trying to do a py script on maya in hopes of getting this working somehow, because i did all sorts of attempts on MS and i can't manage to get it.

I'll keep working on both 3DS and Maya to get some clues.Hello friends can share latest 3dmax script, please, thank you

Hello, how i can open scn models? Please help me =D
## Post #64
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-05T11:59:10+00:00
- Post Title: Re: S4L Model Exporting

> Reply from denny9700
>
> Hello, how i can open scn models? Please help me =DHi and welcome to the forum!  

First of all: this is Seyren's grandiose thread on reversing animations.
It's a WIP and imho it's not aimed at beginners.
So you may run into many troubles when using it as your starting point with scn files.

I remember barti having made a simple scn script which you might use as a startup.
(Search for barti as an author and then in the "Search these results:" edit box enter scn:
will give you 3 matches)

If you insist on continuing here  , well, Seyren's post as of Tue Jun 03, 2014 1:31 pm might be a good starting point.
Try out SeySCNTool.

(If you're meeting problems: read this thread from the very beginning.)
## Post #65
- Username: Ryuta
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 12, 2015 12:35 pm
- Post datetime: 2015-11-12T05:04:43+00:00
- Post Title: Re: S4L Model Exporting

sorry can spend the full scrip please would appreciate it
