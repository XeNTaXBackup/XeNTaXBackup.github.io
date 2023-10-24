## Post #1
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-08-06T08:04:22+00:00
- Post Title: Startopia (2001) 3D models

Hi gang,

Back again for more trouble.

Startopia 2001 is a building game and management sim set in a multi level curved space station.

It features a bunch of aliens, buildings with dynamic floor plans with a simple system for putting items inside so you can design the station yourself.

Timestamped Example of that here [https://youtu.be/xnyGewyoN7w?t=294](https://youtu.be/xnyGewyoN7w?t=294)

I've been looking at trying to rip these 3D models from the game, but I have no idea on the file format. I've worked out that the .ddt files are just renamed tga image files basically, thats no problem.

The 3D models I think i've pinned down to the .ssm files, but im not good at reverse engineering file formats 

The game is available at archive.org for copyright exempted fair use research purposes

I've also added a few samples of each type of 3D asset in the game to a zip file here [https://drive.google.com/file/d/1rH_UgE ... sp=sharing](https://drive.google.com/file/d/1rH_UgECLKoluiARsyxJhuxRqmqZh_Cl3/view?usp=sharing) Again I better state for the moderators that this sample is protected under fair use for education and research provisions.

If anyone with more experience than me would like to take a crack at this, that would be awesome!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-06T11:44:02+00:00
- Post Title: Startopia (2001) 3D models

Hi!

> Reply from urammar ↑Sat Aug 06, 2022 4:04 pm at Sat Aug 06, 2022 4:04 pm
>
> The 3D models I think i've pinned down to the .ssm files, but im not good at reverse engineering file formatsWelcome to the club!  
I have no idea why I'm failing so badly:
.



crate_SSM.jpg (96.34 KiB) Viewed 291 times



Maybe I need to use those numbers (1,3,0,1 etc [0..22]) for some kind of vertex grouping?

```
15906 16005 57152 16255 38832 15245 38101 15047 65360 49023     1     0 
24810 16189 57154 16255 41101 47716 27315 15232 65401 49023     3     0 
65024 14850 15908 16005  1744 15023 17562 47748 65512 49023     0     0 
15906 16005 57152 16255 36111 15900 19288 48947 31948 16178     1     0 
24810 16189 57154 16255 61269 48670 20538 48947 22060 16178     3     0 
65024 14850 15908 16005 39642 16057   759 15786 41849 16237     4     0 
57152 16255 24815 16189 38525 47643  2305 15133 65485 49023     4     0 
57152 16255 24815 16189 44798 48946 20654 48674 50983 16178     5     0 
57154 16255 15916 16005  2762 14866 37678 47945 65454 49023     5     0 
57154 16255 15916 16005 50218 48946 30249 15906 45017 16178     7     0 
24814 16189     0 14851   237 14738 40084 48099 65131 49023     6     0 
15914 16005 63488 14850 36683 46101 43138 48125 65033 49023     7     0 
24814 16189     0 14851 40102 48671 30621 16179  9434 16178     6     0 
15914 16005 63488 14850 51196 15934 58121 16214 46454 16130     1     0 
24810 16189 57154 16255 35153 16147 43649 16148 13014 48915     9     0 
57152 16255 57156 16255 35153 16147 43649 16148 13014 48915     4     0 
```
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-06T12:30:40+00:00
- Post Title: Startopia (2001) 3D models

Cargo's looking slightly better:
.



Cargo_SSM.jpg (113.78 KiB) Viewed 286 times


(High word of most DWORD face indices is 0x8000, maybe some kind of flag. But how to use it?  )
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-06T13:07:07+00:00
- Post Title: Startopia (2001) 3D models

> Reply from shakotay2 ↑Sat Aug 06, 2022 7:44 pm at Sat Aug 06, 2022 7:44 pm
>
> 
I have no idea why I'm failing so badly
I think I may be a little rusty... 
[crate.SSM.png](https://xentaxbackup.github.io/file/22595_crate.SSM.png)
## Post #5
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-08-06T13:10:52+00:00
- Post Title: Startopia (2001) 3D models

Hey I just appreciate the attempt at all. This community is so awesome.

> Reply from shakotay2 ↑Sat Aug 06, 2022 8:30 pm at Sat Aug 06, 2022 8:30 pm
>
> 
Cargo's looking slightly better

Well, its at least not total gibberish, especially in the 1st pic you can see the corners and stuff there. A lot of the form of the cargo crate.

Progress is progress. I wonder if they include the animations in this same file, that makes sense I dont know where else in the structure they would be. These crates do have an opening animation (if needed that can be seen in the first 10 seconds of that youtube vid I showed, no use time-stamping another link for that)

I have no idea if they are grouped or how they might have done any of their models, sadly. My only insight, which I dont think is relevant in this case at all, is that the game takes place in a toroidal (bike-wheel-type) station that you can rotate freely around, so a lot of the larger building probably have some kind of very gentle curve to them, I would assume.

Thats all I got :/
## Post #6
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-08-06T13:11:28+00:00
- Post Title: Startopia (2001) 3D models

> Reply from Bigchillghost ↑Sat Aug 06, 2022 9:07 pm at Sat Aug 06, 2022 9:07 pm
>
> 
I think I may be a little rusty...

Heyyy!!! Now thats looking good!

*Edit* I just realized its a new contender! Hello and also thanks very much for helping!
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-06T15:22:55+00:00
- Post Title: Startopia (2001) 3D models

One of the creatures with texture applied:



Grey.png (114.92 KiB) Viewed 254 times



It does contain anim data BTW. Here's a rough template of the format for HexEdit:

```
<!DOCTYPE binary_file_format SYSTEM "BinaryFileFormat.dtd">
<binary_file_format name="Default" type_name="" comment="">
	<define_struct type_name="ms" comment="" expr="">
		<data type="int" name="unk1" format="signed" len="1" display=""/>
		<data type="int" name="unk2" format="signed" len="1" display=""/>
		<data type="int" name="posCnt" format="signed" len="4" display=""/>
		<data type="none" name="posDat" len="posCnt*12"/>
		<data type="int" name="hasAnimData" len="1" format="signed" display=""/>
		<if test="hasAnimData == 1" comment="">
			<struct name="animDat" type_name="" comment="" expr="">
				<data type="int" name="boneCnt" format="signed" len="4" display=""/>
				<for name="bone" count="boneCnt" stop_test="" type_name="" comment="">
					<struct name="" type_name="" comment="" expr="">
						<data type="string" name="boneName" format="ascii" display=""/>
						<data type="none" name="boneDat" len="0x48"/>
					</struct>
				</for>
				<data type="int" name="totalFrameCnt" format="signed" len="4" display=""/>
				<data type="real" name="frameRate" format="ieee" len="4" display=""/>
				<data type="none" name="framesDat" len="totalFrameCnt*boneCnt*60"/>
				<data type="none" name="vertTranformRecs" len="posCnt*12"/>
				<data type="int" name="unk" format="signed" len="4" display=""/>
				<for name="animSet" count="" stop_test="strlen(this.name) == 0" type_name="" comment="">
					<struct name="" type_name="" comment="" expr="strlen(this.name) !=0 ? this.beginKeyIdx : 0">
						<data type="string" name="name" format="ascii" display=""/>
						<if test="strlen(name) != 0" comment="">
							<data type="int" name="beginKeyIdx" format="signed" len="4" display=""/>
						</if>
					</struct>
				</for>
			</struct>
		</if>
		<data type="int" name="texCnt" format="signed" len="4" display=""/>
		<data type="string" name="texName" format="ascii" display=""/>
		<if test="strlen(texName) != 0" comment="">
			<struct name="mat" type_name="" comment="" expr="">
				<data type="string" name="matName" format="ascii" display=""/>
				<data type="none" name="unk3" len="7"/>
			</struct>
		</if>
		<data type="int" name="uvNmCnt" len="4" format="signed" display=""/>
		<data type="none" name="uvNmDat" len="uvNmCnt*24"/>
		<data type="int" name="faceCnt" len="4" format="signed" display=""/>
		<data type="none" name="faceDat" len="faceCnt*24"/>
		<data type="string" name="boneName" format="ascii" display=""/>
		<data type="string" name="parentName" format="ascii" display=""/>
	</define_struct>
	<for name="mesh" count="" stop_test="" type_name="" comment="">
		<use_struct name="" expr="this.uvNmCnt" type_name="ms" comment=""/>
	</for>
	<data type="none" name="none"/>
</binary_file_format>

```
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-07T12:13:58+00:00
- Post Title: Startopia (2001) 3D models

> Reply from Bigchillghost ↑Sat Aug 06, 2022 9:07 pm at Sat Aug 06, 2022 9:07 pm
>
> I think I may be a little rusty...Nope. There's no one who's more rusty than me!  

Data reorganizing. How could I forget about it? 
> Reply from shakotay2 ↑Fri Jul 30, 2021 3:29 pm at Fri Jul 30, 2021 3:29 pm
>
> (Seems, I lost focus just in the minute, I wrote that post...  )
## Post #9
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-08-07T20:13:35+00:00
- Post Title: Startopia (2001) 3D models

> Reply from Bigchillghost ↑Sat Aug 06, 2022 11:22 pm at Sat Aug 06, 2022 11:22 pm
>
> 
One of the creatures with texture applied:

This is absolutely awesome. Is it possible to get this as a noesis plugin/script?

I'm just a noob script kiddy, I dont really know too much about hex editing or what to do with it, sadly. But I would love to learn.

You guys blow me away every time.
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-08-08T00:01:55+00:00
- Post Title: Startopia (2001) 3D models

> Reply from urammar ↑Mon Aug 08, 2022 4:13 am at Mon Aug 08, 2022 4:13 am
>
> 
Is it possible to get this as a noesis plugin/script?
Sure. But who's gonna do it? 

> Reply from urammar ↑Mon Aug 08, 2022 4:13 am at Mon Aug 08, 2022 4:13 am
>
> 
But I would love to learn.
Seems it's now or never. Well then, welcome aboard!  

You can start by visiting the tutorial section.
## Post #11
- Username: urammar
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Jan 12, 2022 9:09 am
- Post datetime: 2022-08-10T14:29:59+00:00
- Post Title: Startopia (2001) 3D models

> Reply from Bigchillghost ↑Mon Aug 08, 2022 8:01 am at Mon Aug 08, 2022 8:01 am
>
> 
You can start by visiting the tutorial section.

Thanks I guess? haha
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-10T18:07:20+00:00
- Post Title: Startopia (2001) 3D models

@urammar: this format is surely not the best to start with in a tutorial. I'm too busy with other things atm but sooner or later I'll try to integrate Startopia SSM into my Make_obj project.

edit: cancelled, because of:

> Mucky Foot veteran Jan Svarovsky wrote the plugin that can be used with 3D Studio Max v2 and v2.5, while Ed Mack wrote the plugin that can be used with 3D Studio Max v3 (with help from Daniel Yu).
[https://plantmonster.net/startopia/startopia.html#MOD03](https://plantmonster.net/startopia/startopia.html#MOD03)
## Post #13
- Username: MooNFish
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 27, 2020 11:18 am
- Post datetime: 2022-12-02T12:56:19+00:00
- Post Title: Startopia (2001) 3D models

> Reply from shakotay2 ↑Thu Aug 11, 2022 2:07 am at Thu Aug 11, 2022 2:07 am
>
> 
sooner or later I'll try to integrate Startopia SSM into my Make_obj project. But don't expect it too soon (months, at least, sorry).

Hello. I also wish to get several models from Startopia. Will be much obliged for your help)

...
This game already have modding tools.
[https://plantmonster.net/startopia/startopia.html#MOD03](https://plantmonster.net/startopia/startopia.html#MOD03)

...
But they didn't figure out how to convert models from .ssm.
## Post #14
- Username: MooNFish
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 27, 2020 11:18 am
- Post datetime: 2022-12-02T17:22:39+00:00
- Post Title: Startopia (2001) 3D models

> Reply from shakotay2 ↑Thu Aug 11, 2022 2:07 am at Thu Aug 11, 2022 2:07 am
>
> 
edit: cancelled, because of:
Mucky Foot veteran Jan Svarovsky wrote the plugin that can be used with 3D Studio Max v2 and v2.5, while Ed Mack wrote the plugin that can be used with 3D Studio Max v3 (with help from Daniel Yu). 
https://plantmonster.net/startopia/startopia.html#MOD03

Funny, but several years ago I tried just the same thing and stopped because of this:

> The reverse however (converting .ssm files into .max) is not possible.

But you gave me hope
And at least we have textures converter already.
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-12-05T03:26:19+00:00
- Post Title: Startopia (2001) 3D models

gave it a go in 3dsmax... maxscript attached below with basic mesh import functionality


{% raw %}
```
	3ds max's MaxScript for Importing Startopia for pc

	written by mariokart64n
	dec 4 2022
	
	Script written around a dozen file samples uploaded here
	https://forum.xentax.com/viewtopic.php?t=25669

	notes:
		file format is messy,
		they designate a byte which I believe defines the data that follows.
		but they don’t provide a block size, so its not possible to skip
		to the next data block.
		
		that being said don't expect this to work on all files, it will 
		likely crash on most.
		
		I would project that either I interpreted the block wrong, or
		the file contains a sub type which throws everything into chaos...
		
		Wrote everything into structures, each having a Read and Write 
		function. However, the Build function only does some basic stuff,
		materials weights, animations, bones, all that is parsed into the
		structures but not brought into 3dsmax...
		format was too messy and took up my weekend so don't wish to
		continue working anymore on this..
		
*/
clearListener()

try(destroyDialog ui_ssm)catch(ui_ssm)
rollout ui_ssm "SSM" (
	
	struct fmtSSM_Take (
		unk023 = "",
		unk024 = 0,
		fn read &f = (
			local result = false
			unk023 = readString f
			if unk023 != "" do (
				unk024 = readLong f #unsigned
				result = true
				)
			result
			),
		fn write &s = (
			writeString s unk023
			writeLong s unk024 #unsigned
			)
		)
	
	struct fmtSSM_Weight (
		/*int32_t*/  	index = -1, -- vertex index
		/*float*/    	weight = 0.0, -- weight
		/*int32_t*/  	bone_id = -1,
		fn read &f = (
			local result = true
			index = readLong f #signed
			if index > -1 then (
				weight = readFloat f
				bone_id = readLong f #signed
				) else (result = false)
			result
			),
		fn write &s = (
			writeLong s index #signed
			if index > -1 do (
				writeFloat s weight
				writeLong s bone_id #signed
				)
			)
		)
	
	struct fmtSSM_Face (
		/*
			the face data here is weird.
			it could be one face index is 24bits
			or maybe 16 or even 8 bits..
			
			not enough samples to make a better guess..
		*/
		face = #(0, 0, 0),
		flag = #(0, 0, 0), -- no clue, flag, weight, or colour?
		normal = [0.0, 0.0, 0.0], -- probably face normal
		fn read &f = (
			local b = 0
			local i = 1
			local j = 1
			
			for i = 1 to 3 do (
				face[i] = 0
				for j = 1 to 3 do (
					face[i] += ((readbyte f #unsigned) * (2 ^ (8 * (j - 1))))
					)
				
				flag[i] = readbyte f #unsigned
				)
			normal = [readFloat f, readFloat f, readFloat f]
			
			),
		fn write &s = (
			local i = 1
			local j = 1
			for i = 1 to 3 do (
				for j = 1 to 3 do (
					writeByte s (bit.and (bit.shift 0xAABBCC -((j - 1) * 8)) 0xFF) #unsigned
					)
				writeByte s flag[i] #unsigned
				)
			writeFloat s normal[1]
			writeFloat s normal[2]
			writeFloat s normal[3]
			)
		)
	
	struct fmtSSM_Vertex (
		index = 0,
		texcorrd = [0.0, 0.0, 0.0],
		normal = [0.0, 0.0, 0.0],
		fn read &f = (
			index = readLong f #signed
			texcorrd = [readFloat f, readFloat f, 0.0]
			normal = [readFloat f, readFloat f, readFloat f]
			),
		fn write &s = (
			writeLong s index #signed
			writeFloat s texcorrd[1]
			writeFloat s texcorrd[2]
			writeFloat s normal[1]
			writeFloat s normal[2]
			writeFloat s normal[3]
			)
		)
	
	struct fmtSSM_Texture (
		name = "",
		file = "",
		fn read &f = (
			local result = false
			name = readString f
			if name != "" do (
				file = readString f
				result = true
				)
			result
			),
		fn write &s = (
			if name.count > 0 then (
				writeString s name
				writeString s file
				) else (writeByte s 0)
			)
		)
	
	struct fmtSSM_Animation ( -- 60 bytes
		unk040 = #(), -- 195 floats
		fn read &f &count = (
			local i = 1
			local j = 1
			if count > 0 do (
				unk040[count] = #()
				for j = 1 to count do (
					unk040[j] = #()
					unk040[j][15] = 0.0
					for i = 1 to 15 do (
						unk040[j][i] = readFloat f
						)
					)
				)
			),
		fn write &s = (
			local i = 1
			local j = 1
			local count = unk040.count
			if count > 0 do (
				for j = 1 to count do (
					for i = 1 to 15 do (
						writeFloat s unk040[j][i]
						)
					)
				)
			)
		)
	
	struct fmtSSM_Bone ( -- 72 + n bytes
		name = "",
		unk027 = [0.0, 0.0, 0.0],
		unk028 = [0.0, 0.0, 0.0],
		unk029 = [0.0, 0.0, 0.0],
		unk030 = [0.0, 0.0, 0.0],
		unk031 = [0.0, 0.0, 0.0],
		unk032 = -1,
		unk033 = -1,
		unk034 = -1,
		
		fn read &f = (
			name = readString f
			unk027 = [readFloat f, readFloat f, readFloat f]
			unk028 = [readFloat f, readFloat f, readFloat f]
			unk029 = [readFloat f, readFloat f, readFloat f]
			unk030 = [readFloat f, readFloat f, readFloat f]
			unk031 = [readFloat f, readFloat f, readFloat f]
			unk032 = readLong f #signed
			unk033 = readLong f #signed
			unk034 = readLong f #signed
			),
		
		fn write &s = (
			writeString s name
			
			writeFloat s unk027[1]
			writeFloat s unk027[2]
			writeFloat s unk027[3]
			
			writeFloat s unk028[1]
			writeFloat s unk028[2]
			writeFloat s unk028[3]
			
			writeFloat s unk029[1]
			writeFloat s unk029[2]
			writeFloat s unk029[3]
			
			writeFloat s unk030[1]
			writeFloat s unk030[2]
			writeFloat s unk030[3]
			
			writeFloat s unk031[1]
			writeFloat s unk031[2]
			writeFloat s unk031[3]
			
			writeLong s unk032 #signed
			writeLong s unk033 #signed
			writeLong s unk034 #signed
			)
		
		)
	
	struct fmtSSM_Light (
		name = "",
		parent = "",
		unk050 = [0.0, 0.0, 0.0],
		unk051 = [0.0, 0.0, 0.0],
		unk052 = [0.0, 0.0, 0.0],
		unk053 = 0.0,
		
		fn read &f = (
			name = readString f
			parent = readString f
			unk050 = [readFloat f, readFloat f, readFloat f]
			unk051 = [readFloat f, readFloat f, readFloat f]
			unk052 = [readFloat f, readFloat f, readFloat f]
			unk053 = readFloat f
			),
			
		fn write &s = (
			writeString s name
			writeString s parent
			writeFloat s unk050[1]
			writeFloat s unk050[2]
			writeFloat s unk050[3]
			writeFloat s unk051[1]
			writeFloat s unk051[2]
			writeFloat s unk051[3]
			writeFloat s unk052[1]
			writeFloat s unk052[2]
			writeFloat s unk052[3]
			writeFloat s unk053
			)
		
		)
	
	struct fmtSSM_Mesh (
		/*uint32_t*/           	vertex_count = 0,
		/*fmtSSM_Vertex[]*/ 	vertices = #(),
		/*uint32_t*/          	face_count = 0,
		/*fmtSSM_Face[]*/     	faces = #(),
		/*fmtSSM_Texture*/   	texture = fmtSSM_Texture(), -- ?
		
		/*uint32_t*/           	unk060 = 0,
		/*uint16_t*/           	unk061 = 0,
		/*uint8_t*/           	unk062 = 0,
		
		fn read &f = (
			
			-- hmm.. i donno if this is suppose to be here
			texture.read(&f)
			if texture.name != "" do (
				unk060 = readLong f #unsigned
				unk061 = readShort f #unsigned
				unk062 = readByte f #unsigned
				)
			
			vertices = #()
			face_count = #()
			
			vertex_count = readLong f #unsigned
			if vertex_count > 0 do (
				vertices[vertex_count] = fmtSSM_Vertex()
				for i = 1 to vertex_count do (
					vertices[i] = fmtSSM_Vertex()
					vertices[i].read(&f)
					)
				
				-- Read Faces
				face_count = readLong f #unsigned
				if face_count > 0 do (
					faces[face_count] = fmtSSM_Face()
					for i = 1 to face_count do (
						faces[i] = fmtSSM_Face()
						faces[i].read(&f)
						)
					)
				)
			),
		
		fn write &s = (
			
			texture.write(&s)
			if texture.name != "" do (
				writeLong s unk060 #unsigned
				writeShort s unk061 #unsigned
				writeByte s unk062 #unsigned
				)
			
			local i = 1
			
			writeLong s (vertex_count = vertices.count) #unsigned
			for i = 1 to vertex_count do (
				vertices[i].write(&s)
				)
			
			writeLong s (face_count = faces.count) #unsigned
			for i = 1 to face_count do (
				faces[i].write(&s)
				)
			)
		
		)
	
	struct fmtSSM_Model ( -- Type 1
		/*uint8_t*/            	count = 0, -- number of submeshes (materials)
		/*uint8_t*/            	unk005 = 0,
		/*uint16_t*/          	unk006 = 0,
		/*fmtSSM_Mesh[]*/   	submesh = #(),
		/*string[]*/          	unk013 = "", -- mesh name?
		/*string[]*/         	unk014 = "", -- parent?
		fn read &f = (
			
			count = readByte f #unsigned
			unk005 = readByte f #unsigned
			unk006 = readShort f #unsigned
			
			submesh = #()
			if count > 0 do (
				local i = 1
				submesh[count] = fmtSSM_Mesh()
				for i = 1 to count do (
					submesh[i] = fmtSSM_Mesh()
					submesh[i].read(&f)
					)
				
				unk013 = readString f
				unk014 = readString f
				)
			),
		
		fn write &s = (
			
			writeByte s (count = submesh.count) #unsigned
			writeByte s unk005 #unsigned
			writeShort s unk006 #unsigned
			
			local i = 1
			for i = 1 to count do (
				submesh[i].write(&s)
				)
			
			writeString s unk013
			writeString sunk014
			)
		)
	
	struct fmtSSM_Material ( -- Type 0
		/*fmtSSM_Texture*/   	texture = fmtSSM_Texture(),
		/*uint32_t*/          	boneArr_count = 0,
		/*fmtSSM_Bone[]*/    	boneArr = #(),
		/*uint32_t*/          	anim_count = 0,
		/*fmtSSM_Animation[]*/ 	anim = #(),
		/*float*/             	unk041 = 0,
		/*fmtSSM_Weight[]*/ 	weight = #(),
		/*fmtSSM_Take[]*/    	take = #(),
		
		fn read &f &fsize = (
			boneArr = #()
			anim = #()
			weight = #()
			
			-- if one then mesh is static?, otherwise contains additional data
			boneArr_count = readLong f #unsigned
			if boneArr_count > 1 then (
				
				local i = 1
				boneArr[boneArr_count] = fmtSSM_Bone()
				for i = 1 to boneArr_count do (
					boneArr[i] = fmtSSM_Bone()
					boneArr[i].read(&f)
					)
				
				anim_count = readLong f #unsigned
				if anim_count > 0 do (
					anim[anim_count] = fmtSSM_Animation()
					for i = 1 to anim_count do (
						anim[i] = fmtSSM_Animation()
						anim[i].read &f boneArr_count
						)
					)
				
				unk041 = readFloat f
				while ftell f < fsize do (
					append weight (fmtSSM_Weight())
					if not weight[weight.count].read(&f) do (
						exit
						)
					)
				
				while ftell f < fsize do (
					append take (fmtSSM_Take())
					if not take[take.count].read(&f) do (
						exit
						)
					)
				
				fseek f -1 #seek_cur -- hrm..
				) else (texture.read(&f))
			
			),
		
		fn write &f = (
			writeLong s (boneArr_count = boneArr) #unsigned
			if boneArr_count > 1 then (
				
				local i = 1
				for i = 1 to boneArr_count do (
					boneArr[i].write(&s)
					)
				
				
				writeLong s (anim_count = anim) #unsigned
				if anim_count > 0 do (
					for i = 1 to anim_count do (
						anim[i].write(&s)
						)
					)
				
				writeFloat s unk041
				
				for i = 1 to weight.count do (
					weight[i].write(&s)
					)
				
				for i = 1 to weight.count do (
					take[i].write(&s)
					)
				
				fseek s -1 #seek_cur
				) else (texture.write(&s))
			)
		)
	
	struct fmtSSM_VertBuf ( -- Type 8
		type = 0,
		count = 0,
		position = #(),
		
		fn read &f = (
			local result = true
			position = #()
			
			type = readByte f #unsigned
			case type of (
				0x00: (
					count = readLong f #unsigned
					if count > 0 do (
						position[count] = [0.0, 0.0, 0.0]
						local i = 1
						for i = 1 to count do (
							position[i] = [readFloat f, readFloat f, readFloat f]
							)
						)
					)
				--0x01: {}
				default: (
					result = false
					format "error: \tUnknown Buffer Type {%}\n" type
					)
				)
			result
			),
		
		fn write &s = (
			writeByte s type #unsigned
			case type of (
				0x00: (
					writeLong s (count = position.count) #unsigned
					count = readLong f #unsigned
					local i = 1
					for i = 1 to count do (
						writeFloat s position[i][1]
						writeFloat s position[i][2]
						writeFloat s position[i][3]
						)
					)
				)
			)
		
		)
		
	struct fmtSSM_Object ( -- Asset
		/*
			there are different object types, I could only document
			what wasin the few samples given so there are likely
			more undocumented types.
			
			types;
			- 0: Material
			- 1: mesh
			- 8: vertex positions
			--------------------
			- Bones
			- skinned mesh
			- animations
			- vertex blobs
			are amoung the chaos in the SSM format..
		*/
		/*uint8_t*/          	unk001 = 255, -- asset type? 8 = static mesh
		/*fmtSSM_VertBuf*/    	vertices = undefined,
		/*fmtSSM_Mesh*/      	model = undefined,
		/*fmtSSM_Material*/    	material = undefined,
		/*fmtSSM_Light*/      	light = undefined,
		
		fn read &f &fsize = (
			local result = true
			
			-- Read Header?
			unk001 = readByte f #unsigned
			case unk001 of (
				0x00: (
					model = fmtSSM_Model()
					model.read(&f)
					)
				0x01: (
					material = fmtSSM_Material()
					material.read &f fsize
					)
				0x08: (
					-- if followed by a 1, is not a mesh but a light?
					if readByte f == 1 then (
						light = fmtSSM_Light()
						light.read(&f)
						)
					else (
						fseek f -1 #seek_cur
						vertices = fmtSSM_VertBuf()
						result = vertices.read(&f)
						)
					)
				default: (
					result = false
					format "Error: \tReading Aborted Due to a weird number here [%]\n" unk001
					)
				)
			result
			),
		
		fn write &s = (
			if vertices != undefined then (
				writeByte s 8
				vertices.write(&s)
				)
			else if model != undefined then (
				writeByte s 0
				model.write(&s)
				)
			else if material != undefined then (
				writeByte s 1
				material.write(&s)
				)
			else if light != undefined then (
				writeByte s 8
				writeByte s 1
				light.write(&s)
				)
			)
		
		)
	
	struct fmtSSM (
		asset = #(),
		
		fn read &f = (
			
			-- Get File Size
			local pos = ftell f
			fseek f 0 #seek_end
			local fsize = ftell f
			fseek f pos #seek_set
			
			-- read until end of file is reached
			while ftell f < fsize do (
				append asset (fmtSSM_Object())
				if not (asset[asset.count].read &f fsize) do (
					format "Error: \tReading Aborted...\n"
					exit
					)
				)
			),
		
		fn write &s = (
			local i = 1
			for i = 1 to asset.count do (
				asset[i].write(&s)
				)
			),
		
		fn build clearScene:true impNormals:false fpath:"" = (
			if clearScene do (delete $*)
			
			local i = 1
			local count = asset.count
			local msh = undefined
			local vertArray = #()
			local faceArray = #()
			local uvwArray = #()
			local normArray = #()
			local tfaceArray = #() -- triangulated faces (series)
			local face_count = 0
			local v = 1
			local x = 1
			local j = 1
			local m = 1
			local n = 1
			
			-- Loop Through Each Asset
			for i = 1 to count do (
				
				
				
				
				if asset[i].unk001 == 8 and asset[i].vertices != undefined do (
					
					vertArray = #()
					if asset[i].vertices.position.count > 0 do (
						vertArray[asset[i].vertices.position.count] = [0.0, 0.0, 0.0]
						for v = 1 to asset[i].vertices.position.count do (
							vertArray[v] = [ \
								asset[i].vertices.position[v][1], \
								-asset[i].vertices.position[v][2], \
								-asset[i].vertices.position[v][3] \
								]
							)
						)
					
					-- jump to next valid mesh block
					for n = i to count do (
						
						
						if asset[n].unk001 == 0 and asset[n].model != undefined do (
							
							-- build any submeshes
							for m = 1 to asset[n].model.submesh.count do (
								
								faceArray = #()
								uvwArray = #()
								normArray = #()
								tfaceArray = #()
								
								face_count = asset[n].model.submesh[m].faces.count
								
								if face_count > 0 do (
									faceArray[face_count] = [1,1,1]
									tfaceArray[face_count] = [1,1,1]
									uvwArray[face_count * 3] = [0.0, 0.0, 0.0]
									for v = 1 to face_count do (
										x = (v - 1) * 3
										tfaceArray[v] = [1, 2, 3] + x
										faceArray[v] = [ \
											asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[1] + 1].index + 1, \
											asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[2] + 1].index + 1, \
											asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[3] + 1].index + 1 \
											]
										for j = 1 to 3 do (
											normArray[x + j] = [ \
												asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[j] + 1].normal[1], \
												asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[j] + 1].normal[2], \
												asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[j] + 1].normal[3] \
												]
											uvwArray[x + j] = [ \
												asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[j] + 1].texcorrd[1], \
												1.0 - asset[n].model.submesh[m].vertices[asset[n].model.submesh[m].faces[v].face[j] + 1].texcorrd[2], 0.0 \
												]
											)
										)
									)
								if faceArray.count > 0 do (
									msh = mesh vertices:vertArray faces:faceArray tverts:uvwArray
									buildTVFaces msh
									for v = 1 to tfaceArray.count do (setTVFace msh v tfaceArray[v])
									
									msh.backfacecull = on
									msh.displayByLayer = false
									msh.wirecolor = random (color 0 0 0) (color 255 255 255)
									for v = 1 to faceArray.count do setFaceSmoothGroup msh v 1
									
			-- 						if asset[n].model.submesh[m].material.count > 0 and asset[n].model.submesh[m].material[1].unk004 != "" do (
			-- 							msh.material = Standard diffuseMap:(Bitmaptexture fileName:(fpath + (getFilenameFile asset[n].model.submesh[m].material[1].unk004) + ".dds"))
			-- 							showTextureMap msh.material true
			-- 							)
									
									if impNormals do (
										local normID = #{}
										local normMod = Edit_Normals()
										addmodifier msh normMod ui:off
										normMod.selectBy = 1
										normMod.displayLength = 0
										
										msh.Edit_Normals.MakeExplicit selection:#{1..(vertArray.count)}
										
										normID = #{}
										--apply normals
										for x = 1 to normArray.count do (
											normID = #{} --free normID
											normMod.ConvertVertexSelection #{x} &normID
											for j in normID do (
												normMod.SetNormal j (normalize normArray[x])
												)
											)
										--collapseStack asset
										subobjectLevel = 0
										)
									)
								
								)
							
							exit
							)
						)
					)
				)
			)
		)
	
	
	button btn_open "Import"
	group "About" (
		label lbl_about "by mariokart64n" align:#left
		label lbl_date "Dec 4 2022" align:#left
		)
	
	local ssm = fmtSSM()
	
	fn read file = (
		if file != undefined and file != "" do (
			local f = try(fopen file "rb")catch(undefined)
			if f != undefined then (
				local ssm = fmtSSM()
				
				ssm.read(&f)
				ssm.build fpath:(getFilenamePath file)
				
				print "Done!"
				fclose f
				) else (format "error: \tfailed to open file {%}\n" file)
			)
		)
	
	on btn_open pressed do (read(getOpenFileName caption:"Open A File:" types:"ssm (*.ssm)|*.ssm|All|*.*|"))
	
	)
createDialog ui_ssm

```
{% endraw %}

[startopia_ssm_maxscript__by_mariokart64n.zip](https://xentaxbackup.github.io/file/23105_startopia_ssm_maxscript__by_mariokart64n.zip)
## Post #16
- Username: MooNFish
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 27, 2020 11:18 am
- Post datetime: 2022-12-05T10:02:06+00:00
- Post Title: Re: Startopia (2001) 3D models

> Reply from mariokart64n ↑Mon Dec 05, 2022 11:26 am at Mon Dec 05, 2022 11:26 am
>
> 
gave it a go in 3dsmax... maxscript attached below with basic mesh import functionality

Script works fine. Thank you very much!

It crashed on couple of models, but I got what I wanted)
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-05T10:46:38+00:00
- Post Title: Re: Startopia (2001) 3D models

> Reply from mariokart64n ↑Mon Dec 05, 2022 11:26 am at Mon Dec 05, 2022 11:26 am
>
> 
gave it a go in 3dsmax... maxscript attached below with basic mesh import functionality
...
format was too messy and took up my weekend so don't wish to
		continue working anymore on this..
...Well, Sir, thank you and respect for your work! 
I'm very impressed that you did this though knowing this game not being too popular any more.

Especially I'm loving your structural thinking (which I'm lacking widely), such gems as

> /*
>
> 			there are different object types, I could only document
>
> 			what wasin the few samples given so there are likely
>
> 			more undocumented types.
>
> 
>
> 			types;
>
> 			- 0: Material
>
> 			- 1: mesh
>
> 			- 8: vertex positions
>
> 			--------------------
>
> 			- Bones
>
> 			- skinned mesh
>
> 			- animations
>
> 			- vertex blobs
>
> 			are amoung the chaos in the SSM format..
>
> 		*/
Kudos!
---------------
@MooNFish:

> Reply from MooNFish ↑Mon Dec 05, 2022 6:02 pm at Mon Dec 05, 2022 6:02 pm
>
> 
...
It crashed on couple of models, but I got what I wanted)Since I don't have Max installed any more could you give one ore two examples, which crash (and the error message if any)?
## Post #18
- Username: MooNFish
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 27, 2020 11:18 am
- Post datetime: 2022-12-05T16:12:55+00:00
- Post Title: Re: Startopia (2001) 3D models

> Reply from shakotay2 ↑Mon Dec 05, 2022 6:46 pm at Mon Dec 05, 2022 6:46 pm
>
> Since I don't have Max installed any more could you give one ore two examples, which crash (and the error message if any)?

I'll try some other later, but right now I got crash on "dj", and got no effect or error from "penance suit" and "Arona"
[https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1ZxBoEvtjmu6RX2uySjlWoHGmCNHiYHQM?usp=share_link)
## Post #19
- Username: MooNFish
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Nov 27, 2020 11:18 am
- Post datetime: 2022-12-05T16:35:27+00:00
- Post Title: Re: Startopia (2001) 3D models

I tried 3ds max 2022 and 2023 btw.

Here is crash message for dj and ships:

```
--Line number: 125
```


+Casino almost same, but line 124
## Post #20
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-12-05T16:46:02+00:00
- Post Title: Re: Startopia (2001) 3D models

Thanks! I'll care for dj.  But don't expect it to soon (I'm very slow).

(Since I don't have Max installed as I wrote I'll try to get the parameters for AXE.
 Should be possible having mariokart64n's structures as a base.

Before that I used ugly explanations like such (for crate.SSM for example)
find parameter vertex count after the strings, cargo, tex01.tga, pod2
0x146: 0x90 = 144 verts
)

edit: so, well, yes, got parameters for dj.SSM:
.



AXE-dj_SSM.jpg (244.16 KiB) Viewed 84 times

(had to cut some parts to have the picture size < 250 kB)

Don't forget the Multi source filenames (File menu): first four, 3 of them are ../dj.SSM
while for Vertex Position it's ../dj.SSM.out

You'll need to create the .out file for yourself using the Data Reorganizer from tools menu.

(well, Bigchillghost, I really wished you could include those Data Reorganizer Params into the .plc file. Just as a thought...)
Ok, I see, that would include to start the data reorganization in memory when loading such a .plc file - matter of concept...
## Post #21
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-12-05T23:19:41+00:00
- Post Title: Re: Startopia (2001) 3D models

theres a mistake I made with the naming of one of the structures which I labelled fmtSSM_Material.

It actually should be named something like "Skinned Data" it contains animations, bones, weights all into the same block which is mislabeled as material. I should have renamed it, but it had slipped my mind before uploading the script. The game doesn't appear to have materials, it'll just optionally provide a single texture name between the vertex buffer and the mesh structure.
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-12-07T09:55:35+00:00
- Post Title: Re: Startopia (2001) 3D models

> Reply from shakotay2 ↑Tue Dec 06, 2022 12:46 am at Tue Dec 06, 2022 12:46 am
>
> 
AXE-dj_SSM.jpg
I remember testing the GUI on a low DPI screen once and the font size didn't appear to be a problem then. BTW, the UI under the XP style seems more user-friendly: 



axe_on_xp.png (78.93 KiB) Viewed 46 times



> Reply from shakotay2 ↑Tue Dec 06, 2022 12:46 am at Tue Dec 06, 2022 12:46 am
>
> 
I really wished you could include those Data Reorganizer Params into the .plc file ... that would include to start the data reorganization in memory when loading such a .plc file - matter of concept...
Theoretically it can be solved by introducing a pre-processing params set and output the reorganized data to local files while the data channels can reference the corresponding file as they did before. Problem is there're too many params that need to be included hence burdens the workload of loading, verifying and saving the parameters. I doubt the necessity of putting such efforts on a less-frequently used feature. After all, the Data Reorganizer is just a small utility for quick validation.
