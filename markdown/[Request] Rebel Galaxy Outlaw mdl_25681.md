## Post #1
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-08T00:12:27+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

I'm looking for help trying to extract the models for Rebel Galaxy Outlaw.

I've never really dealt with 3D models before, so I'm a bit at a loss here, and I'm hoping that someone more experienced can more easily solve this, or at least give me a helping hand.
I did give hex2obj a couple of shots, but the formats between the tutorial and the game seem to be too different for an inexperienced user to really make any progress there.


Things I think I know:

 The .mdl files are a custom Ogre binary mesh format
 The custom format includes both the mesh and the material data (source)
 The material data seems to be at the beginning of the file
 The lead programmer for the game previously worked for Runic Games (Torchlight), which also used Ogre as the game 3D engine.
	They also had a custom exported already for the Torchlight games (source)
 The mesh string is "MeshSerializer_Runic", which also indicates a connection to Runic games, however the format still seems to be different.
	For example, it seems to use 4 bytes for the indicies instead of 2 bytes as for Runic games
 The lead programmer is not active anymore and now does audio books, so he's not available for help


I hope that the custom format is basically just the default Ogre format (or at least one of them) + the material data prepended at the beginning of the file, which could make it relatively easy to create a splitter to separate the metarial data from the actual mesh data. But I'm not familiar enough with the mesh binary data syntax yet.

I did see the [Hob MDL thread](https://forum.xentax.com/viewtopic.php?f=16&t=18107) by Kva3imoda, which is pretty similar to the request here, but the Hob game was created after the lead programmer had already left Runic Games, and the mdl files don't seem to be compatible (e.g. they seem to be using 2 bytes instead of 4 bytes as well). But maybe it's something to build upon.

I've uploaded a couple of mdl files, from the simplest I could find up to a full ship model:
[http://sp00n.net/rgo/mdl/rgo-mdl-files.7z](http://sp00n.net/rgo/mdl/rgo-mdl-files.7z)


Here's a screenshot of the simplest mdl file (1_CARPET_A1.MDL):


I assume the marked area would be the indices, starting at 0x196, but I'm not sure. Bigger mdl files seem to have multiple of these entries.



Any help is appreciated.


(And this is a quote so that Kva3imoda gets notified, as @Kva3imoda doesn't seem to work here)

> Reply from Kva3imoda ↑Fri May 18, 2018 10:03 am at Fri May 18, 2018 10:03 am
>
> ...
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T12:30:44+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

This part of the asteroid is all I can serve with:
.


Asteroid_01.jpg (155.79 KiB) Viewed 131 times



H2O file to be used with hex2obj (view link in my sig):

0x168DD 1949
Vb1
12 99
0x205B 1758
040000
0x0 255
## Post #3
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-08T12:56:09+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from shakotay2 ↑Mon Aug 08, 2022 8:30 pm at Mon Aug 08, 2022 8:30 pm
>
> 
This part of the asteroid is all I can serve with:
.Asteroid_01.jpg

H2O file to be used with hex2obj (view link in my sig):

0x168DD 1949
Vb1
12 99
0x205B 1758
040000
0x0 255

0x1DCAF for the Vertices gives me at least something round:



1_ASTEROID_01.MDL.1DCAF.jpg (53.89 KiB) Viewed 126 times



I'm still pretty confused by the general structure of these files, i.e. the three or four possible locations where I could start with the Vertices.
Are there maybe multiple different versions/shapes of the same object in one file? For asteroids this would make some sense, but for ships not so much.
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-08-08T13:22:56+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from sp00n ↑Mon Aug 08, 2022 8:56 pm at Mon Aug 08, 2022 8:56 pm
>
> 
0x1DCAF for the Vertices gives me at least something round:

your sphere is most likely vert normals not vert positions
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T13:58:06+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from sp00n ↑Mon Aug 08, 2022 8:56 pm at Mon Aug 08, 2022 8:56 pm
>
> 0x1DCAF for the Vertices gives me at least something round:hex2obj says it's normals ("NORM" in lower left window)

> I'm still pretty confused by the general structure of these files, i.e. the three or four possible locations where I could start with the Vertices.So am I. Here's some point clouds (addr and count):
.



Asteroid, pt clouds.jpg (87.21 KiB) Viewed 118 times


.
btw, for the Largefighter I get partially good results for cylindric elements when using auto created face indices (tri strips). The rectangled elements are bogus, though. More or less.
## Post #6
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-08T14:23:25+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

So for regular Ogre binary mesh files I found this definition. Not sure if it will be of much help here though.

[https://github.com/OGRECave/ogre/blob/m ... leFormat.h](https://github.com/OGRECave/ogre/blob/master/OgreMain/src/OgreMeshFileFormat.h)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T14:51:30+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

I might help if you uploaded a more regular sample than an asteroid.  200 kB <size <500 kB, no collision mdl.
## Post #8
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-08T15:35:29+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from shakotay2 ↑Mon Aug 08, 2022 10:51 pm at Mon Aug 08, 2022 10:51 pm
>
> 
I might help if you uploaded a more regular sample than an asteroid.  200 kB <size <500 kB, no collision mdl.

I tried to collect a couple of files where the name should imply what to expect and that didn't seem too complex:
[http://sp00n.net/rgo/mdl/rgo-mdl-files-2.7z](http://sp00n.net/rgo/mdl/rgo-mdl-files-2.7z)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T16:09:11+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

Thanks! The table may serve as a starting point.
.



1_BASE_TABLE01-mdl.jpg (108.46 KiB) Viewed 100 times



There's some doubles. Usually one should get rid of them (blender, remove doubles.)
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T16:24:26+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

well, what about this one?  
.



table.jpg (84.43 KiB) Viewed 98 times
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-08T16:32:12+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

Asteroid; now the boring part to come...
-



Asteroid_part.jpg (147.66 KiB) Viewed 98 times


.
Deco_Box05:

0x299BA 2538
Vb1
12 99
0x29C0 1368
040000
0x0 255
## Post #12
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-08-09T06:27:07+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

this format is annoying



Maxscript

```
maxscript to import mdl from rgo
by mariokart64n, aug 8 2022
*/
try(destroyDialog ui_rgomdl)catch(ui_rgomdl)
rollout ui_rgomdl "Rebel Galaxy Outlaw" (
	struct fmtRGOMDL_String (
		/*string[] 	*/ 						value 			= "",
		/*uint8_t  	*/ 						type 				= 1,
		/*uint16_t	*/							unk003 			= 0,
		/*uint16_t	*/							unk004 			= 0,
		fn read &f = (
			local b = 0
			local s = ""
			local p = ftell f
			while b != undefined do (
				b = readByte f
				if b > 31 and b != undefined then (
					s += bit.IntAsChar b
					p = ftell f
					)
				else (exit)
				)
			fseek f p #seek_set
			local type = readByte f
			case type of (
				0x01: unk003 = readByte f
				0x0A: (
					unk003 = readShort f
					unk004 = readShort f
					)
				)
			value = s
			s
			)
		)
	
	struct fmtRGOMDL_Vertex_Def ( -- 10 Bytes
		/*uint16_t	*/							map 				= 0, -- channel?
		/*uint16_t	*/							datatype 		= 0, -- data type?
		/*uint16_t	*/							vertextype 	= 0, -- component type?
		/*uint16_t	*/							vertexpos 		= 0, -- component position
		/*uint16_t	*/							unk006 			= 0, -- ?
		fn read &f = (
			map 									= readShort f
			datatype 							= readShort f
			vertextype							= readShort f
			vertexpos 							= readShort f
			unk006 								= readShort f
			)
		)
	
	struct fmtRGOMDL_Table2 (
		
		indicies1 = #( --32 shorts
			0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
			0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0
			),
		unk016 = [0.0, 0.0, 0.0],
		unk017 = [0.0, 0.0, 0.0],
		indicies2 = #( --12 longs
			-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1
			),
		mat_name = fmtRGOMDL_String(),
		fn read &f &headerName = (
			local i = 1
			for i = 1 to 32 do (
				indicies1[i] = readShort f
				)
			unk016 = [readFloat f, readFloat f, readFloat f]
			unk017 = [readFloat f, readFloat f, readFloat f]
			if headerName.unk003 == 14 do (
				fseek f 20 #seek_cur
				)
			for i = 1 to 12 do (
				indicies2[i] = readLong f
				)
			mat_name.read(&f)
			)
		)
	
	struct fmtRGOMDL_Table9 (
		unk034 = 0,
		count = 0,
		indices3 = #(),
		fn read &f = (
			indices3 = #()
			unk034 = readShort f
			count = readLong f 
			if count > 0 do (
				local i = 1
				local count_tmp = count * 3
				indices3[count_tmp] = 0
				for i = 1 to count_tmp do (
					indices3[i]  = readLong f
					)
				)
			)
		)
	
	struct fmtRGOMDL (
		/*uint8_t  	*/ 						unk001 = 0,
		/*uint8_t  	*/ 						unk002 = 0x10,
		/*fmtRGOMDL_String*/ 			fileVer = fmtRGOMDL_String(),
		/*uint16_t	*/							unk007 = 0,
		/*uint16_t	*/							unk008 = 0,
		/*uint16_t	*/							fvf_count = 0,
		/*fmtRGOMDL_Vertex_Def[]*/ 	fvf_table = #(),
		/*float    	*/ 						unk009 = 0.0,
		/*uint32_t	*/							unk010 = 0,
		/*uint32_t	*/							unk011 = 0,
		/*uint32_t	*/							unk012 = 0,
		/*uint32_t	*/							unk013 = 0,
		/*uint32_t	*/							table2_count = 0,
		/*uint32_t	*/							texture_count = 0,
		/*string[]	*/							texture_array = #(),
		/*fmtRGOMDL_String*/ 			model_name = fmtRGOMDL_String(),
		table2 = #(),
		position = [0.0, 00.0, 0.0],
		array1 = #(), -- Indices
		array2 = #(), -- Vertices
		array3 = #(), -- Normals?
		array4 = #(), -- Tagents?
		value5 = 0,
		array6 = #(), -- TVert0[]
		array7 = #(), -- TVert1[]
		array8 = #(), -- Vertices
		array5 = #(), -- Indices
		unk022 = 0,
		unk023 = 0,
		unk024 = 0,
		unk025 = 0,
		unk026 = 0,
		array9 = #(), -- Indices[]?
		
		fn read &f debug:false = (
			
			local i = 1
			local pos = ftell f
			local fileType = readLong f
			
			if fileType == 0x4D5B1000 then (
				fseek f pos #seek_set
				unk001 = readByte f
				unk002 = readByte f
				fileVer.read(&f)
				case fileVer.value of (
					"[MeshSerializer_Runic]": (
						unk007 = readShort f
						unk008 = readShort f
						fvf_count = readShort f
						fvf_table = #()
						if fvf_count > 0 do (
							fvf_table[fvf_count] = fmtRGOMDL_Vertex_Def()
							for i = 1 to fvf_count do (
								fvf_table[i] = fmtRGOMDL_Vertex_Def()
								fvf_table[i].read(&f)
								)
							)
						unk009 = readFloat f
						unk010 = readLong f
						unk011 = readLong f
						unk012 = readLong f
						unk013 = readLong f
						table2_count = readLong f
						texture_count = readLong f
						texture_array = #()
						if texture_count > 0 do (
							texture_array[texture_count] = fmtRGOMDL_String()
							for i = 1 to texture_count do (
								texture_array[i] = fmtRGOMDL_String()
								texture_array[i].read(&f)
								)
							)
						model_name.read(&f)
						table2 = #()
						if table2_count > 0 do (
							table2[table2_count] = fmtRGOMDL_Table2()
							for i = 1 to table2_count do (
								table2[i] = fmtRGOMDL_Table2()
								table2[i].read &f fileVer
								)
							)
						position = [readFloat f, readFloat f, readFloat f]
						local v = 1
						local count1 = 0
						local count2 = 0
						local count3 = 0
						local count5 = 0
						local count6 = 0
						local array6_tmp = #()
						local array7_tmp = #()
						value5 = 0
						array1 = #()
						array2 = #()
						array3 = #()
						array4 = #()
						array5 = #()
						array6 = #()
						array7 = #()
						for i = 1 to fvf_count do (
							case fvf_table[i].vertextype of (
								1: (	-- Faces?
									count1 = readLong f
									if count1 > 0 do (
										array1[count1] = 0
										for v = 1 to count1 do (
											array1[v] = readLong f
											)
										)
									)
								9: (	-- Positions?
									count2 = readLong f
									if count2 > 0 do (
										array2[count2] = [0.0, 0.0, 0.0]
										for v = 1 to count2 do (
											array2[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									)
								8: (	-- Normal?
									count3 = readLong f
									if count3 > 0 do (
										array3[count3] = [0.0, 0.0, 0.0]
										for v = 1 to count3 do (
											array3[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									)
								4: (	-- ??
									
									if count3 > 0 do (
										array4[count3] = [0.0, 0.0, 0.0]
										for v = 1 to count3 do (
											array4[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									value5 = readShort f -- ? type
									)
								7: (	-- 0 	1 	7 	52 	0 vert 12
									if count3 > 0 do (
										if count1 > 0 do (
											array7_tmp = #()
											array7_tmp[count1] = 0
											for v = 1 to count1 do (
												array7_tmp[v] = readLong f
												)
											append array7 array7_tmp
											)
										count6 = readLong f
										if count6 > 0 do (
											array6_tmp = #()
											array6_tmp[count6] = [0.0, 0.0, 0.0]
											for v = 1 to count6 do (
												array6_tmp[v] = [readFloat f, readFloat f, 0.0]
												)
											append array6 array6_tmp
											)
										)
									)
								default: (format "Error: \tUnknown Vertex Type: \t%\n" fvf_table[i].vertextype)
								)
							)
						
						unk022 = readShort f -- ? type
						array8 = #()
						array5 = #()
						if count3 > 0 do (
							if count1 > 0 do (
								array5[count1] = 0
								for i = 1 to count1 do (
									array5[i] = readLong f
									)
								)
							local count8 = readLong f
							if count8 > 0 do (
								array8[count8] = [0.0, 0.0, 0.0]
								for i = 1 to count8 do (
									array8[i] = [readFloat f, readFloat f, readFloat f]
									)
								)
							unk023 = readLong f -- ?
							)
						unk024 = readLong f -- 0
						unk025 = readLong f -- index table count
						unk026 = readLong f  -- how many index tables
						if unk026 > 0 do (
							array9 = #()
							array9[unk026] = fmtRGOMDL_Table9()
							for i = 1 to unk026 do (
								array9[i] = fmtRGOMDL_Table9()
								array9[i].read(&f)
								)
							)
						)
					default: (
						format "error: \tUnsupported file type %\n" fileVer
						)
					)
				) else (format "error: \tinvalid file type\n")
			),
		
		fn build = (
			delete $*
			local array1_count = array1.count
			local faceArray = #()
			local vertArray = #()
			if array1_count > 0 do (
				local v = 1
				local i = 0
				local x = 1
				for x = 1 to array9.count do (
					v = 0
					for i = 1 to array9[x].count do (
						append faceArray ([array9[x].indices3[v + 1], array9[x].indices3[v + 3], array9[x].indices3[v + 2]] + 1)
						v += 3
						)
					)
				local array2_count = array2.count
				vertArray[array1_count] = [0.0, 0.0, 0.0]
				for i = 1 to array1_count do (
					vertArray[i] = array2[array1[i] + 1]
					)
				)
			local msh = mesh vertices:vertArray faces:faceArray
			)
		)
	
	local mdl = fmtRGOMDL()
	
	fn open file = (
		
		-- Open File
		local f = try(fopen file "rb")catch(undefined)
		if f != undefined then (
			mdl = fmtRGOMDL()
			
			mdl.read(&f)
			mdl.build()
			
			-- Close File
			fclose f
			) else (format "error: \tfailed to open file\n")
		)
	)

fn read file = (ui_rgomdl.open(file))
read (getOpenFileName caption:"Open RGO Model" types:"Model (*.mdl)|*.mdl|All|*.*" historyCategory:"RGOMDL")

```
## Post #13
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-09T16:35:08+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from mariokart64n ↑Tue Aug 09, 2022 2:27 pm at Tue Aug 09, 2022 2:27 pm
>
> 
this format is annoying



Maxscript
Code: Select all/*
maxscript to import mdl from rgo
by mariokart64n, aug 8 2022
*/
try(destroyDialog ui_rgomdl)catch(ui_rgomdl)
rollout ui_rgomdl "Rebel Galaxy Outlaw" (
	struct fmtRGOMDL_String (
		/*string[] 	*/ 						value 			= "",
		/*uint8_t  	*/ 						type 				= 1,
		/*uint16_t	*/							unk003 			= 0,
		/*uint16_t	*/							unk004 			= 0,
		fn read &f = (
			local b = 0
			local s = ""
			local p = ftell f
			while b != undefined do (
				b = readByte f
				if b > 31 and b != undefined then (
					s += bit.IntAsChar b
					p = ftell f
					)
				else (exit)
				)
			fseek f p #seek_set
			local type = readByte f
			case type of (
				0x01: unk003 = readByte f
				0x0A: (
					unk003 = readShort f
					unk004 = readShort f
					)
				)
			value = s
			s
			)
		)
	
	struct fmtRGOMDL_Vertex_Def ( -- 10 Bytes
		/*uint16_t	*/							map 				= 0, -- channel?
		/*uint16_t	*/							datatype 		= 0, -- data type?
		/*uint16_t	*/							vertextype 	= 0, -- component type?
		/*uint16_t	*/							vertexpos 		= 0, -- component position
		/*uint16_t	*/							unk006 			= 0, -- ?
		fn read &f = (
			map 									= readShort f
			datatype 							= readShort f
			vertextype							= readShort f
			vertexpos 							= readShort f
			unk006 								= readShort f
			)
		)
	
	struct fmtRGOMDL_Table2 (
		
		indicies1 = #( --32 shorts
			0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
			0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0
			),
		unk016 = [0.0, 0.0, 0.0],
		unk017 = [0.0, 0.0, 0.0],
		indicies2 = #( --12 longs
			-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1
			),
		mat_name = fmtRGOMDL_String(),
		fn read &f &headerName = (
			local i = 1
			for i = 1 to 32 do (
				indicies1[i] = readShort f
				)
			unk016 = [readFloat f, readFloat f, readFloat f]
			unk017 = [readFloat f, readFloat f, readFloat f]
			if headerName.unk003 == 14 do (
				fseek f 20 #seek_cur
				)
			for i = 1 to 12 do (
				indicies2[i] = readLong f
				)
			mat_name.read(&f)
			)
		)
	
	struct fmtRGOMDL_Table9 (
		unk034 = 0,
		count = 0,
		indices3 = #(),
		fn read &f = (
			indices3 = #()
			unk034 = readShort f
			count = readLong f 
			if count > 0 do (
				local i = 1
				local count_tmp = count * 3
				indices3[count_tmp] = 0
				for i = 1 to count_tmp do (
					indices3[i]  = readLong f
					)
				)
			)
		)
	
	struct fmtRGOMDL (
		/*uint8_t  	*/ 						unk001 = 0,
		/*uint8_t  	*/ 						unk002 = 0x10,
		/*fmtRGOMDL_String*/ 			fileVer = fmtRGOMDL_String(),
		/*uint16_t	*/							unk007 = 0,
		/*uint16_t	*/							unk008 = 0,
		/*uint16_t	*/							fvf_count = 0,
		/*fmtRGOMDL_Vertex_Def[]*/ 	fvf_table = #(),
		/*float    	*/ 						unk009 = 0.0,
		/*uint32_t	*/							unk010 = 0,
		/*uint32_t	*/							unk011 = 0,
		/*uint32_t	*/							unk012 = 0,
		/*uint32_t	*/							unk013 = 0,
		/*uint32_t	*/							table2_count = 0,
		/*uint32_t	*/							texture_count = 0,
		/*string[]	*/							texture_array = #(),
		/*fmtRGOMDL_String*/ 			model_name = fmtRGOMDL_String(),
		table2 = #(),
		position = [0.0, 00.0, 0.0],
		array1 = #(), -- Indices
		array2 = #(), -- Vertices
		array3 = #(), -- Normals?
		array4 = #(), -- Tagents?
		value5 = 0,
		array6 = #(), -- TVert0[]
		array7 = #(), -- TVert1[]
		array8 = #(), -- Vertices
		array5 = #(), -- Indices
		unk022 = 0,
		unk023 = 0,
		unk024 = 0,
		unk025 = 0,
		unk026 = 0,
		array9 = #(), -- Indices[]?
		
		fn read &f debug:false = (
			
			local i = 1
			local pos = ftell f
			local fileType = readLong f
			
			if fileType == 0x4D5B1000 then (
				fseek f pos #seek_set
				unk001 = readByte f
				unk002 = readByte f
				fileVer.read(&f)
				case fileVer.value of (
					"[MeshSerializer_Runic]": (
						unk007 = readShort f
						unk008 = readShort f
						fvf_count = readShort f
						fvf_table = #()
						if fvf_count > 0 do (
							fvf_table[fvf_count] = fmtRGOMDL_Vertex_Def()
							for i = 1 to fvf_count do (
								fvf_table[i] = fmtRGOMDL_Vertex_Def()
								fvf_table[i].read(&f)
								)
							)
						unk009 = readFloat f
						unk010 = readLong f
						unk011 = readLong f
						unk012 = readLong f
						unk013 = readLong f
						table2_count = readLong f
						texture_count = readLong f
						texture_array = #()
						if texture_count > 0 do (
							texture_array[texture_count] = fmtRGOMDL_String()
							for i = 1 to texture_count do (
								texture_array[i] = fmtRGOMDL_String()
								texture_array[i].read(&f)
								)
							)
						model_name.read(&f)
						table2 = #()
						if table2_count > 0 do (
							table2[table2_count] = fmtRGOMDL_Table2()
							for i = 1 to table2_count do (
								table2[i] = fmtRGOMDL_Table2()
								table2[i].read &f fileVer
								)
							)
						position = [readFloat f, readFloat f, readFloat f]
						local v = 1
						local count1 = 0
						local count2 = 0
						local count3 = 0
						local count5 = 0
						local count6 = 0
						local array6_tmp = #()
						local array7_tmp = #()
						value5 = 0
						array1 = #()
						array2 = #()
						array3 = #()
						array4 = #()
						array5 = #()
						array6 = #()
						array7 = #()
						for i = 1 to fvf_count do (
							case fvf_table[i].vertextype of (
								1: (	-- Faces?
									count1 = readLong f
									if count1 > 0 do (
										array1[count1] = 0
										for v = 1 to count1 do (
											array1[v] = readLong f
											)
										)
									)
								9: (	-- Positions?
									count2 = readLong f
									if count2 > 0 do (
										array2[count2] = [0.0, 0.0, 0.0]
										for v = 1 to count2 do (
											array2[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									)
								8: (	-- Normal?
									count3 = readLong f
									if count3 > 0 do (
										array3[count3] = [0.0, 0.0, 0.0]
										for v = 1 to count3 do (
											array3[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									)
								4: (	-- ??
									
									if count3 > 0 do (
										array4[count3] = [0.0, 0.0, 0.0]
										for v = 1 to count3 do (
											array4[v] = [readFloat f, readFloat f, readFloat f]
											)
										)
									value5 = readShort f -- ? type
									)
								7: (	-- 0 	1 	7 	52 	0 vert 12
									if count3 > 0 do (
										if count1 > 0 do (
											array7_tmp = #()
											array7_tmp[count1] = 0
											for v = 1 to count1 do (
												array7_tmp[v] = readLong f
												)
											append array7 array7_tmp
											)
										count6 = readLong f
										if count6 > 0 do (
											array6_tmp = #()
											array6_tmp[count6] = [0.0, 0.0, 0.0]
											for v = 1 to count6 do (
												array6_tmp[v] = [readFloat f, readFloat f, 0.0]
												)
											append array6 array6_tmp
											)
										)
									)
								default: (format "Error: \tUnknown Vertex Type: \t%\n" fvf_table[i].vertextype)
								)
							)
						
						unk022 = readShort f -- ? type
						array8 = #()
						array5 = #()
						if count3 > 0 do (
							if count1 > 0 do (
								array5[count1] = 0
								for i = 1 to count1 do (
									array5[i] = readLong f
									)
								)
							local count8 = readLong f
							if count8 > 0 do (
								array8[count8] = [0.0, 0.0, 0.0]
								for i = 1 to count8 do (
									array8[i] = [readFloat f, readFloat f, readFloat f]
									)
								)
							unk023 = readLong f -- ?
							)
						unk024 = readLong f -- 0
						unk025 = readLong f -- index table count
						unk026 = readLong f  -- how many index tables
						if unk026 > 0 do (
							array9 = #()
							array9[unk026] = fmtRGOMDL_Table9()
							for i = 1 to unk026 do (
								array9[i] = fmtRGOMDL_Table9()
								array9[i].read(&f)
								)
							)
						)
					default: (
						format "error: \tUnsupported file type %\n" fileVer
						)
					)
				) else (format "error: \tinvalid file type\n")
			),
		
		fn build = (
			delete $*
			local array1_count = array1.count
			local faceArray = #()
			local vertArray = #()
			if array1_count > 0 do (
				local v = 1
				local i = 0
				local x = 1
				for x = 1 to array9.count do (
					v = 0
					for i = 1 to array9[x].count do (
						append faceArray ([array9[x].indices3[v + 1], array9[x].indices3[v + 3], array9[x].indices3[v + 2]] + 1)
						v += 3
						)
					)
				local array2_count = array2.count
				vertArray[array1_count] = [0.0, 0.0, 0.0]
				for i = 1 to array1_count do (
					vertArray[i] = array2[array1[i] + 1]
					)
				)
			local msh = mesh vertices:vertArray faces:faceArray
			)
		)
	
	local mdl = fmtRGOMDL()
	
	fn open file = (
		
		-- Open File
		local f = try(fopen file "rb")catch(undefined)
		if f != undefined then (
			mdl = fmtRGOMDL()
			
			mdl.read(&f)
			mdl.build()
			
			-- Close File
			fclose f
			) else (format "error: \tfailed to open file\n")
		)
	)

fn read file = (ui_rgomdl.open(file))
read (getOpenFileName caption:"Open RGO Model" types:"Model (*.mdl)|*.mdl|All|*.*" historyCategory:"RGOMDL")

Oh wow! That looks pretty complete.

Is there any way to run maxscript code without having to use 3dsmax?
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-09T16:52:08+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from sp00n ↑Wed Aug 10, 2022 12:35 am at Wed Aug 10, 2022 12:35 am
>
> Is there any way to run maxscript code without having to use 3dsmax?No.
## Post #15
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-08-09T23:39:32+00:00
- Post Title: [Request] Rebel Galaxy Outlaw mdl

> Reply from sp00n ↑Wed Aug 10, 2022 12:35 am at Wed Aug 10, 2022 12:35 am
>
> 
Oh wow! That looks pretty complete.

Is there any way to run maxscript code without having to use 3dsmax?

I've ported the maxscript to python as a Blender addon.

It was refreshing to see a post start with more than a few words demanding models so I thought I would have a quick look into the format.

However work on this format has far exceeded the time that I intended to put into it.. so you should know that the script only imports the basic geometry as a proof of concept.

That being said this about day 3 now and I'm not interested in investing any more time into it. 

I hope the code serves to help educate you in some way,
-mariokart64n



 py_rebel_galaxy_outlaw.zip
BlenderAddon: Rebel Galaxy Outlaw Importer (18.73 KiB) Downloaded 15 times
## Post #16
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-10T00:08:44+00:00
- Post Title: Re: [Request] Rebel Galaxy Outlaw mdl

> Reply from mariokart64n ↑Wed Aug 10, 2022 7:39 am at Wed Aug 10, 2022 7:39 am
>
> 
sp00n wrote: ↑Wed Aug 10, 2022 12:35 am
Oh wow! That looks pretty complete.

Is there any way to run maxscript code without having to use 3dsmax?


I've ported the maxscript to python as a Blender addon.

It was refreshing to see a post start with more than a few words demanding models so I thought I would have a quick look into the format.

However work on this format has far exceeded the time that I intended to put into it.. so you should know that the script only imports the basic geometry as a proof of concept.

That being said this about day 3 now and I'm not interested in investing any more time into it. 

I hope the code serves to help educate you in some way,
-mariokart64n


py_rebel_galaxy_outlaw.zip

Oh wow, thanks!
I actually was in the process of modifying your original code to convert it into Lua or something (just because the mod tools for Rebel Galaxy Outlaw are based on Lua as well), to hopefully eventually be able to create an Ogre XML file out of it, but since I don't really know any MaxScript (or C on which it seems to be based on?) I first had to check what you're actually doing there and understand your code.
I'm actually a bit embarrassed by the speed you where able to reverse engineer this, on the other hand I had never dealt with 3d files before, so that's at least some comfort for me.   

That python Blender importer will be really helpful as well.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-10T04:30:09+00:00
- Post Title: Re: [Request] Rebel Galaxy Outlaw mdl

> Reply from sp00n ↑Wed Aug 10, 2022 8:08 am at Wed Aug 10, 2022 8:08 am
>
> I'm actually a bit embarrassed by the speed you where able to reverse engineer this,He's simply one of the best, so no surprise. 

> Reply from mariokart64n ↑Wed Aug 10, 2022 7:39 am at Wed Aug 10, 2022 7:39 am
>
> 
# ====================================================================================
# MAXCSRIPT FUNCTIONS
# ====================================================================================
# These function are written to mimic native functions in
# maxscript. This is to make porting my old maxscripts
# easier...Well done!  Based on your work this could be the start of a frame work for an automated MS2py converter. Sooner or later. Hopefully.

(Was always thinking of it, but... my mind, is so ... weak.  )
-----------------------------------------------------------------
.
using the py script:
.



RGO_py_mariokart64n.jpg (170.37 KiB) Viewed 49 times
## Post #18
- Username: sp00n
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Jul 12, 2022 9:07 pm
- Post datetime: 2022-08-10T11:06:09+00:00
- Post Title: Re: [Request] Rebel Galaxy Outlaw mdl

> Reply from mariokart64n ↑Wed Aug 10, 2022 7:39 am at Wed Aug 10, 2022 7:39 am
>
> ...
Can I put your scripts on Github to make them available to the general public?
## Post #19
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2022-08-10T22:32:10+00:00
- Post Title: Re: [Request] Rebel Galaxy Outlaw mdl

to preserve some chronology, I've uploaded the blender plugin to my github here;
[https://github.com/coreynguyen/bpy_rebel_galaxy_outlaw](https://github.com/coreynguyen/bpy_rebel_galaxy_outlaw)
