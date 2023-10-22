## Post #1
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-04-28T01:49:01+00:00
- Post Title: Fatal Frame Models?

Hi there! Recently I started to play the games again, so I decided to try and get the models of the first game, but as far I know, no one tried to figure out how to load the models properly. The last advance people did (me too) is getting the MDL files where are contained the model files, but they cannot be opened sadly. 

As far I now, the game used the RenderWare Engine.

If someone had some idea or a theory about the files, I hope can be answered here.

Here's the MDL files provided by another user:
[http://www.mediafire.com/?igrg7215dd5nlni](http://www.mediafire.com/?igrg7215dd5nlni)


I guess they're from the PS2 version, I have the XBOX ones.
## Post #2
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-28T06:29:44+00:00
- Post Title: Fatal Frame Models?

I can find vertices with Model Researcher



Untitled.png (103.18 KiB) Viewed 554 times


Not at all sure where to find faces though (no pun intended )
## Post #3
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-04-28T17:13:20+00:00
- Post Title: Fatal Frame Models?

> Reply from Natsuki Okusawa ↑Thu Apr 28, 2022 2:29 pm at Thu Apr 28, 2022 2:29 pm
>
> 
I can find vertices with Model Researcher
Untitled.png
Not at all sure where to find faces though (no pun intended )

Oh! Thats interesting! It's even more than other people was able to find. So these files can be loaded after all. Any idea about why the faces arent showing? or the rest of the body?
## Post #4
- Username: Natsuki Okusawa
- Rank: n00b
- Number of posts: 19
- Joined date: Thu Oct 27, 2011 4:19 pm
- Post datetime: 2022-04-28T17:58:17+00:00
- Post Title: Fatal Frame Models?

Well, I haven't looked deeper into the files, but hopefully someone with more experience's gonna take a look at this. Maybe what I've found can be helpful as some starting point or something. I'm quite a noob when it comes to this.
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-04-28T20:51:02+00:00
- Post Title: Fatal Frame Models?

(I NO LONGER UPDATE THE INFORMATION, IT MAY NO LONGER CORRESPOND)
[.MDL] container, inside: .XPR and .MPX and .MDL  (many nesting)

```
  -COUNT_FILE    INT
  -ZERO          12_BYTES
  
  FOR COUNT_FILE:
	-SIZE_FILE     INT
	-TYPE_FILE     INT
	-ZERO          8_BYTES
	
	IF TYPE_FILE:
		6 - XPR textures
		5 - MPX meshes
		0 - MDL recursion

```

[.ACS] container, inside: .XPR and .MPX (one nesting)

```
  -COUNT_FILE    INT
  -ZERO          12_BYTES
  
  FOR COUNT_FILE:
	-SIZE_FILE     INT
	-ZERO          12_BYTES
	
	file:
		-[58 50 52 30] .XPR
		-[60 10 00 00] .MPX

```

[.XPR] container, inside: DXT5 textures

```
 RES = [1,2,4,8,16,32,64,128,256,512,1024]
 
 XPR_HEADER:
	-MAGIC      STRING 4_BYTES ('XPR0')
	-SIZE_FILE   INT
	-OFFSET_DATA INT
 
 TX_INFO  ARRAY[]
 
 WHILE TX_MAGIC != -1:
	-TX_MAGIC   INT [01 00 04 00]
	-OFFSET     INT (this + OFFSET_DATA)
	-ZERO       4_BYTES
	-TX_TYPE    INT
	-ZERO       4_BYTES
	-TX_INFO.PUSH
	
 SEEK(OFFSET_DATA)
 
 FOR TX_INFO:
	WIDTH     = RES[(TX_TYPE & 0x00F00000) >> 20]
	HEIGHT    = RES[(TX_TYPE & 0x0F000000) >> 24]
	SIZE_DATA = WIDTH * HEIGHT

```

[.MPX] file contains meshes

```
FILE_MPX:
 MPX_HEADER:
	-NUM_OBJ  INT
	-ZERO     12_BYTES
	
 OBJECTS  ARRAY_OBJ[NUM_OBJ]
 
-------------------------------------------------
BONE (244 BYTES) (in .mdl 248)
 -MATRIX   MATRIX4x4_64_BYTES
 -ZERO     128_BYTES
 -UNK      VEC4
 -PARENT   INT
 -ZERO     12_BYTES
 
MATERIAL (144 BYTES)
 -DIFFUSE  VEC4
 -SPEC?    VEC4
 -ZERO     32_BYTES
 -UNK      FLOAT
 -ZERO     4_BYTES
 -ID_TX    INT
 -NAME_TX  STRING_64_BYTES
 -UNK      INT

OBJ
 -OBJ_SIZE INT
 -ZERO     12_BYTES
 
  #you need to remember the offset in front of the header. 
  #because all offset in the object is local
  
  HEADER: (40 + NUM_BONE * 4 BYTES)
	-MAGIC        INT (60 10 00 00) <- HEX
	-ZERO         8_BYTES
	-MAT_NUM      INT
	-OFFSET_VERT  INT
	-SIZE_VERT    INT
	-OFFSET_BONE  INT
	-OFFSET_MAT   INT
	-OFFSET_VERT0 INT (in start file, unused, repeat)
	-NUM_BONE     INT
	-OFFSET_MESH ARRAY_INT[NUM_BONE]
	
  IF OFFSET_BONE > 0:
  BONES_BLOCK: (NUM_BONE * 244 BYTES) <- seek(OFFSET_BONE)
	-BONES   ARRAY_BONE[NUM_BONE - 1] (0 - root scene)
	
  MATERIALS_BLOCK: (MAT_NUM * 144 BYTES) <- seek(OFFSET_MAT)
	-BONES   ARRAY_MAT[MAT_NUM]
	
  UNK_VERT_BLOCK: (vert with weight and bone id)
	-NUM      INT (always 3)
	
	FOR NUM: (second always have [4, 0, 0, 0])
		-UNK       INT (always 4)
		-OFFSET_V  INT (offset vertex block)
		-OFFSET_N  INT (offset normal block)
		-OFFSET_COUNT_INFO      INT (in last offset count vert info value, other always 0)
	-DATA      REMAINING_BYTES(if one bone, stride 16 bytes(vec3 and 1 float weight) or if two bone 32 bytes(vec3, 1 float weight vec3 and 4 weight indices(1 byte))
	...
	-NUM_INF_1BONE     INT
 	FOR NUM_INF_1BONE     :
		-COUNT_VERT     INT

	-NUM_INF_2BONE     INT
 	FOR NUM_INF_2BONE:
		-BONE_ID     SHORT
		-BONE_ID     SHORT
		-COUNT_VERT     INT
	-NUM_INF_2BONE     INT
 	FOR NUM_INF_2BONE:
		-BONE_ID     SHORT
		-BONE_ID     SHORT
		-COUNT_VERT     INT


  FOR (OFFSET_MESH): (if zero then skip)
	M_HEADER (16 BYTES)
	  -UNK     INT (always 16)
	  -UNK     INT (always 3)
	  -BONE_ID INT
	  -FLAG    INT (0 but last always 1, multy bones mesh?)
	
	IF FLAG = 0: (skip this block 'SIZE' BYTES)
		-SIZE     INT (always 144)
		-UNK      INT (always 4)
		-BONE_ID  INT
		-ZERO     4_BYTES
		-UNK      ARRAY_VEC4[8] or [(SIZE - 16) / 16]
		
	FACE_BLOCK:
		WHILE TYPE_VERT != 0:
			FHEADER: (64 BYTES)
			  -TYPE_VERT      INT (12 vec3?)
			  if TYPE_VERT = 0: break
			  -TYPE_INDICES   INT (2 short?)
			  -MAT_ID         INT
			  -NEXT_FB        INT (+ 12)
			  -UNK            INT (0 or 1)
			  -ZERO           INT
			  -VERT_OFFSET    INT (+ OFFSET_VERT)
			  -ZERO           INT
			  -VERT_NUM       INT
			  -ZERO           INT
			  -INDICES_OFFSET INT (in .mdl from header)
			  -ZERO           INT
			  -INDICES_NUM    INT
			  -ZERO           INT
			  -STRIDE_FLAG    INT (stride 32 if flag > 0 else 24)
			  -END_BLOCK      INT (FF FF FF FF)
			  
			  #create mesh:
			  SEEK(INDICES_OFFSET)
			  -INDICES        BYTES[INDICES_NUM * 2]
			  SEEK(OFFSET_VERT + VERT_OFFSET)
			  -VBUF           BYTES[VERT_NUM * STRIDE]
			  -SEEK(NEXT_FB)

```


update:
mesh and bones;

(now version XBOX)

update:
material, texture, mesh, uv, weight(mesh with 1 bone)
problem with mesh who have weight over 1 bone


PS.
I don’t know how everyone unpacks the BIN archive for PS2. i wrote a plugin for myself.
unpack files (IMG_HD.BIN, IMG_BD.BIN and NORG_ENG.00) from a disk image into one folder.
then open the file using the plugin "NORG_ENG.00".
[fmt_FF1_00[PS2].zip](https://xentaxbackup.github.io/file/22472_fmt_FF1_00[PS2].zip)
## Post #6
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-04-28T21:20:38+00:00
- Post Title: Fatal Frame Models?

> Reply from Durik256 ↑Fri Apr 29, 2022 4:51 am at Fri Apr 29, 2022 4:51 am
>
> 
bones, vertex cloud (1st submesh, not all)

(maybe i'll do it later)

Wow! What an advance! I saw thats Noesis, correct? Did u made the script?

If you guys need the XBOX MDL files too, I think I can share them.
## Post #7
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-05-17T19:24:38+00:00
- Post Title: Fatal Frame Models?

> Reply from Durik256 ↑Fri Apr 29, 2022 4:51 am at Fri Apr 29, 2022 4:51 am
>
> 
bones, vertex cloud (1st submesh, not all)

(maybe i'll do it later)

Any good news about this? We've been getting closer to view the models properly.
## Post #8
- Username: nfs333
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 26, 2021 11:39 am
- Post datetime: 2022-05-27T19:42:56+00:00
- Post Title: Fatal Frame Models?

Hi! I am currently working on a full decompilation of FF2 and I did a lot of work on reversing the 3D file format or the FF franchise. I am able to get what seems to be vertices (I think) of maps and characters to fully render (see videos). However, I am beaten when it comes to creating meshes. Feel free to join the community in this decompilation!

The files are fully mapped and I have the real names for the pointers and such, but I lack experience with 3D to know what to do with each of them. If it helps, the PS2 version of the games have full debug symbols so you can easily see what is being done. Just use ghidra with a PS2 elf loader.

Definition of the types are here: [https://github.com/wagrenier/Mikompilat ... gd_types.h](https://github.com/wagrenier/Mikompilation/blob/main/engine/sgd/sgd_types.h)

Code for maping the pointers and such is located here: [https://github.com/wagrenier/Mikompilat ... loader.cpp](https://github.com/wagrenier/Mikompilation/blob/main/engine/sgd/sgd_loader.cpp)

Here is the decompilation project: [https://github.com/wagrenier/Mikompilation](https://github.com/wagrenier/Mikompilation) .

[https://imgur.com/C4tC2C5](https://imgur.com/C4tC2C5)
[https://imgur.com/tlQgJC7](https://imgur.com/tlQgJC7)

Hope all of this helps! If you need more, I have a private project thaat reads the entirety of a FF1/2 mdl file and renders what it finds
## Post #9
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-05-28T10:09:23+00:00
- Post Title: Fatal Frame Models?

> Reply from nfs333 ↑Sat May 28, 2022 3:42 am at Sat May 28, 2022 3:42 am
>
> 
Hi! I am currently working on a full decompilation of FF2 and I did a lot of work on reversing the 3D file format or the FF franchise. I am able to get what seems to be vertices (I think) of maps and characters to fully render (see videos). However, I am beaten when it comes to creating meshes. Feel free to join the community in this decompilation!

The files are fully mapped and I have the real names for the pointers and such, but I lack experience with 3D to know what to do with each of them. If it helps, the PS2 version of the games have full debug symbols so you can easily see what is being done. Just use ghidra with a PS2 elf loader.

Definition of the types are here: https://github.com/wagrenier/Mikompilat ... sgdTypes.h

Code for maping the pointers and such is located here: https://github.com/wagrenier/Mikompilat ... Loader.cpp

Here is the decompilation project: https://github.com/wagrenier/Mikompilation .

https://imgur.com/C4tC2C5
https://imgur.com/tlQgJC7

Hope all of this helps! If you need more, I have a private project thaat reads the entirety of a FF1/2 mdl file and renders what it finds

Wait, this is...this is fantastic! I didnt had idea this project exists, I can recognize the maps youre showing on the gifs, from FF1.
How much time this project has been worked? Theres a ton of work behind this.
## Post #10
- Username: nfs333
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 26, 2021 11:39 am
- Post datetime: 2022-05-29T04:30:58+00:00
- Post Title: Fatal Frame Models?

I would say I am reaching into the year and half on reversing the FF franchise, started out with file formats, then my ps2 undubs and now the game logic. Here is the latest development for the reversing, we are booting into some parts of the main menu! 

[https://www.reddit.com/r/fatalframe/com ... _recently/](https://www.reddit.com/r/fatalframe/comments/udl8yb/small_teaser_on_what_ive_been_working_on_recently/)
## Post #11
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-05-29T10:12:51+00:00
- Post Title: Fatal Frame Models?

> Reply from nfs333 ↑Sun May 29, 2022 12:30 pm at Sun May 29, 2022 12:30 pm
>
> 
I would say I am reaching into the year and half on reversing the FF franchise, started out with file formats, then my ps2 undubs and now the game logic. Here is the latest development for the reversing, we are booting into some parts of the main menu! 

https://www.reddit.com/r/fatalframe/com ... _recently/

This is pretty awesome. Why I was unaware of this project? I've looked everywere related to reverse engine FF1 and 2 or ripping the files, etc...
## Post #12
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-05T12:12:06+00:00
- Post Title: Fatal Frame Models?

> Reply from DaniKH ↑Thu Apr 28, 2022 9:49 am at Thu Apr 28, 2022 9:49 am
>
> 
I have the XBOX ones version.
plugin Fatal Frame 1 XBOX version
edit: fix 2 bone weight on vert


sample model: [m000_miku.mdl](https://drive.google.com/file/d/1SnUcBhTgVuDc5S6QwkgwdqL-LgEm79tk/view?usp=sharing) (XBOX ver)
[fmt_FF1_MDL[XBOX].zip](https://xentaxbackup.github.io/file/22474_fmt_FF1_MDL[XBOX].zip)
## Post #13
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-07-05T15:17:33+00:00
- Post Title: Fatal Frame Models?

> Reply from Durik256 ↑Tue Jul 05, 2022 8:12 pm at Tue Jul 05, 2022 8:12 pm
>
> 
DaniKH wrote: ↑Thu Apr 28, 2022 9:49 am
I have the XBOX ones version.

using "rapi.rpgSkinPreconstructedVertsToBones(BONES)" where there are 2 bones per top, very bad results are obtained

using  "NoeMat43.transformPoint(NoeVec3())" only the first bone:
if T-POSE then it's ok:

but some models have gaps:

Oh my! Finally! gonna update the link for the plugin or youll still working for better results?

EDIT: I didnt seen the other posts, wow I never expected that. Reading them rn!
## Post #14
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-10T14:27:40+00:00
- Post Title: Fatal Frame Models?

> Reply from DaniKH ↑Tue Jul 05, 2022 11:17 pm at Tue Jul 05, 2022 11:17 pm
>
> 
Oh my! Finally!
dont quote all post(edit your previous posts)

plugin Fatal Frame 1 PS2 version
and plugin for FF1 PS2 (without assigning textures.)
when exporting, all textures will be unpacked near the model
fix 2 bone weight on vert

(no more updates)
sample model: [M000_MIKU.MDL](https://drive.google.com/file/d/16vs_OYsxOwKKQuXklTIyIy1wK4pfh3ln/view?usp=sharing) (PS2 ver)
[fmt_FF1_MDL[PS2].zip](https://xentaxbackup.github.io/file/22475_fmt_FF1_MDL[PS2].zip)
## Post #15
- Username: DaniKH
- Rank: n00b
- Number of posts: 18
- Joined date: Thu Oct 11, 2018 5:15 am
- Post datetime: 2022-07-10T16:24:48+00:00
- Post Title: Fatal Frame Models?

> Reply from Durik256 ↑Sun Jul 10, 2022 10:27 pm at Sun Jul 10, 2022 10:27 pm
>
> 
DaniKH wrote: ↑Tue Jul 05, 2022 11:17 pm
Oh my! Finally!

dont quote all post(edit your previous posts)

plugin Fatal Frame 1 PS2 version
and plugin for FF1 PS2 (without assigning textures.)
when exporting, all textures will be unpacked near the model
(problems with "gaps" as in the xbox version)

(no more updates)
sample model: M000_MIKU.MDL (PS2 ver)

Sorry, it has been almost 6 years since I talked in a forum and I totally forgot about that. My apologies.

Thank you very much with all your work. You're amazing. 

I just wanted to get back this thread that has been talked in the past many times but no one got any answers nor someone got interested on researching about Fatal Frame model type file. 

And I'm not good at reverse engineering, all I had was the files of the models so, I thought, if I contribute sharing the models, maybe nowdays someone will help with the stuff.

Thanks again for all your effort.
## Post #16
- Username: ngovandang1997
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 14, 2023 3:23 pm
- Post datetime: 2023-08-07T06:03:28+00:00
- Post Title: Re: Fatal Frame Models?

> Reply from Durik256 ↑Tue Jul 05, 2022 8:12 pm at Tue Jul 05, 2022 8:12 pm
>
> 
plugin Fatal Frame 1 XBOX version
edit: fix 2 bone weight on vert

Amazing work
I am facing errors on opening these mdl
[https://mega.nz/file/60Z32brJ#5Kq_wr2_x ... v9TLxQ7nDA](https://mega.nz/file/60Z32brJ#5Kq_wr2_xLJ5j4RpUorRPciD_Rf6r4zO7v9TLxQ7nDA)

Also do you have any plan with FF2 and FF3 too?
