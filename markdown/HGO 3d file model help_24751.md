## Post #1
- Username: GoldNeo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 30, 2020 7:59 am
- Post datetime: 2021-11-19T14:45:56+00:00
- Post Title: HGO 3d file model help

Hello everyone! could someone take a look at this 3d file? it contains the meshes, textures and rig of the character.
From the game Crash Bandicoot: The Wrath of Cortex, Gamecube version
Could you have a script on noesis\quickbms\blender or something that allows you to modify the mesh and re-import it back into hgo?

some file example:
.



i have some partial parsing:

```
; All number fields are big endian, with the exception of in .hgo.blk files.
; The game exectuable comes with function name symbols, which were an aid in deciphering the structures.
	
struct matrix ; This is a 4x4 matrix, of size 0x40.
	float m11, m12, m13, m14
	float m21, m22, m23, m24
	float m31, m32, m33, m34
	float m41, m42, m43, m44
endstruct

struct vector3d
	float x, y, z
endstruct

struct vector2d
	float x, y
endstruct

struct chunk
	i32 type
	i32 size ; Size in bytes. Self-inclusive; TSH0 with only 1 contained i32 is size 0xC.
	; The type field contains 4 ASCII characters as a name for the structure contained.
	; These are all possible values for the type field, adjusted for clarity:
	;   HGOF - Root
	;   NTBL - NameTable
	;   TST0 - TextureSet
	;   TSH0 - TextureSet Counter
	;   TXM0 - TextureSet Material
	;   MS00 - MaterialSet
	;   TAS0 - TexAnimSet
	;   HGO0 - HGobjSet
	; The field is stored with chars in reverse order,
	; for example HGOF would appear as FOGH in a hex editor.
	; When read with big endianness,
	; chunk.type == 0x464F4748 should be true for the HGOF chunk.
	;;; For convenience, let this struct have an attribute END that points to the end of its data.
endstruct

struct blk ; This is an array of chunk headers from the HGO it's named after, like a summary.
	; The fields in this struct are THE OPPOSITE ENDIANNESS, they are little endian.
	for struct until EOF
		i32LE type ; An example of the endianness' char order is HGOF appearing as HGOF, rather than FOGH.
		i32LE offset ; This is a file offset to the chunk's size field, such that HGOF's is 4. Stops matching after a bitmap chunk.
	endfor
	; The offsets after the bitmap chunks appear broken, this file may not be fully used, if at all.
endstruct

struct hgo_geom ; Defines a 3D model. Used many times inside the HGO struct.
	i32 models_n
	for struct in [models_n] ; Only occurs as 1.
		i32 type
		if type == 0
			i32 unknown0
			i32 unknown1
			i32 unknown2
			i32 meshes_n ; The model is split into meshes according to its materials.
			for struct in [meshes_n]
				i32 material_id
				i32 vertices_n
				for struct in [vertices_n]
					vector3d position
					vector3d normals
					i32 colour ; ARGB format.
					vector2d uv
				endfor
				
				i32 geom_cntrl ; Only 0.
				i32 primitives_n
				for struct in [primitives_n]
					i32 primtype
					i32 indices_n
					i16 indices [indices_n]
					;;; Explanation:
					; If primtype == 5, then every grouping of 3 indices is 1 polygon.
					; If primtype == 6, then the indices describe triangle strips. Uncertain parsing method.
				endfor
				
				i32 geomskin_present ; Yes, this is a 32-bit boolean.
				if geomskin_present != 0 ; This is known in Blender lingo as bone weights.
					i8 type
					if type == 0 ; This type is unused.
						i32 unknown
						i32 unknown_len
						i32 unknown_n
						i32 unknown_a [unknown_n]
						i32 unknown_b [unknown_len] [unknown_n]
					else
						for struct in [vertices_n]
							f32 influence0
							f32 influence1
							f32 influence2
							i8 bone_id0
							i8 bone_id1
							i8 bone_id2
							i8 unused
						endfor
					endif
					;;; Explanation:
					; This stuff describes bone weights, how far a bone has to travel to move a vertex.
					; For type != 0, take each bone_id and connect the bone to the vertex with the corresponding influence.
					; Ignore bone_id values that are 0.
					; The limitation of this structure is that only 3 bones can have influence over a given vertex.
					;
					; I have not tested the type == 0 path, as it's unused, but it seems likely to me that it's an
					; extended version of the same, to have the option of having more than 3 bone influences on a vertex.
				endif
				
				i32 blendshapes_n
				if blendshapes_n != 0 ; Known in Blender lingo as shape keys.
					i32 blendshapes_ids [blendshapes_n]
					i32 blendshape_len
					i8 blendshape [blendshape_len]
					i8 blendshape_presence [blendshapes_n]
					;;; Explanation:
					; The numbers in blendshapes_ids are unique identification numbers (not indices) for the blendshapes involved,
					; and it dictates the order in which these blendshapes will be defined here.
					;
					; The blendshape buffer stores vectors for all the mesh's vertices, for each new blendshape defined.
					; blendshape_presence determines which blendshapes are included in the buffer, and which are omitted.
					; This saves a lot of space for meshes that are not involved in the new shape.
					; For that reason, blendshape_len == sizeof(vector)*vertices_n*sum(blendshape_presence).
					; Alternatively, blendshape can be defined as: vector blendshape [vertices_n] [sum(blendshape_presence)]
				endif
			endfor
		elseif type == 1 ; Unused.
			i32 unknown_n
			for struct in [unknown_n]
				i32 unknown0
				i32 unknown1_n
				i32 unknown2
				f32 unknown3
				i8 unknown1 [0x18] [unknown1_n]
			endfor
		endif
	endfor
endstruct

struct hgo
	chunk rootchunk
	; This is the HGOF chunk, it envelops the entire file.
	; Its size is padded to the 4 byte boundary,
	; despite the file not being padded, and likely being shorter.
	; Contained is an array of chunks:
	for chunk hgochunk until EOF
		elseif hgochunk.type == NTBL
			i32 table_len ; Size in bytes of the buffer just ahead.
			i8 table [table_len] ; A buffer of concatenated, null-terminated strings, such as bone names.
			; Everything that uses the name table stores offset value relative to the start of the name table,
			; but 1 too far; subtract 1 and it will match.
		elseif hgochunk.type == TST0 ; Chunk array.
			for chunk taschunk until hgochunk.END
				if hgochunk.type == TSH0
					i32 images_n ; The amount of bitmaps packed.
				elseif hgochunk.type == TXM0 ; Bitmaps.
					i32 bitmap_type ; 0x80 for DXT1, 0x81 for RGB5A3, 0x82 for an unknown tiled format.
					i32 bitmap_width  ; In pixels.
					i32 bitmap_height ; In pixels.
					i32 bitmap_len ; Size in bytes of the buffer just ahead.
					i8 bitmap [bitmap_len]
					; All formats follow a pattern of 4 tiles in a Z-shape.
				endif
				; The TSH0 chunk is unnecessary, but may have been more convenient with the in-house chunk utilities.
			endfor
		elseif hgochunk.type == MS00 ; Material definitions, indexes into bitmaps.
			i32 materials_n
			for struct in [materials_n] ; Struct size 0x54.
				i32 unknown0
				i32 unknown1
				i32 unknown2
				i32 unknown3
				i32 unknown4
				f32 diffuse_r
				f32 diffuse_g
				f32 diffuse_b
				f32 unknown8
				f32 unknown9
				i32 unknown10
				i32 unknown11
				f32 unknown12
				f32 unknown13
				i32 bitmap_id ; Negative if no bitmap, and uses diffuse colours. Otherwise an index into the bitmaps.
				f32 unknown15
				f32 unknown16
				f32 unknown17
				f32 unknown18
				f32 unknown19
				f32 unknown20
			endfor
		elseif hgochunk.type == TAS0 ; Completely unknown.
			i32 anims_n
			i32 unknown
			for struct in [anims_n] ; Size 0x20.
				i32 unknown0
				i32 unknown1
				i32 unknown2
				i32 unknown3
				i32 unknown4
				i32 unknown5
				i32 unknown6
				i32 unknown7
			endfor
			i32 shorts_n
			i16 shorts [anim_shorts_n]
		elseif hgochunk.type == HGO0 ; Contains all the 3D stuff.
			i32 bones_n
			for struct in [bones_n]
				i8 unknown
				matrix rotation
				matrix position
				matrix scale ; Conjecture.
				i32 unknown0
				f32 unknown1
				f32 unknown2
				i8 parent
				i32 name_offset ; Bone name in the name table.
			endfor
			i8 unknown0_len
			i8 unknown0 [unknown0_len]
			i8 unknown1_len
			i8 unknown1 [unknown1_len]
			i8 layers_n
			for struct in [layers_n]
				name_offset ; Layer name in the name table.
				
				i8 primary_bone_meshes_present
				if primary_bone_meshes_present != 0
					for - in range(bones_n)
						i8 primary_bone_mesh_present
						if primary_bone_mesh_present != 0
							hgo_geom
						endif
					endfor
				endif
				i8 primary_mesh_present
				if primary_mesh_present != 0
					hgo_geom
				endif
				
				i8 secondary_bone_meshes_present
				if secondary_bone_meshes_present != 0
					for - in range(bones_n)
						i8 secondary_bone_mesh_present
						if secondary_bone_mesh_present != 0
							hgo_geom
						endif
					endfor
				endif
				i8 secondary_mesh_present
				if secondary_mesh_present != 0
					hgo_geom
				endif
			endfor
			i8 points_n
			for struct in [points_n]
				i8 bone_id
				matrix position
				i32 name_offset ; Point name in the name table.
			endfor
			i8 unknown3_n
			for struct in [unknown3_n]
				i8 unknown0_n
				i8 unknown0 [0x30] [unknown0_n]
				i8 unknown1_n
				i8 unknown1 [0x30] [unknown1_n]
				i8 unknown2_n
				for struct in [unknown2_n]
					i32 unknown0_n
					i8 unknown0 [0x10] [unknown0_n]
					i32 unknown1_n
					i8 unknown1 [0x10] [unknown1_n]
				endfor
				i8 unknown3
			endfor
			f32 unknown_f0
			f32 unknown_f1
			f32 unknown_f2
			f32 unknown_f3
			f32 unknown_f4
			f32 unknown_f5
			f32 unknown_f6
			f32 unknown_f7
			f32 unknown_f8
			f32 unknown_f9
			f32 unknown_f10
		endif
	endfor
endstruct
```


thank you
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-19T17:02:18+00:00
- Post Title: HGO 3d file model help

> Reply from GoldNeo ↑Fri Nov 19, 2021 10:45 pm at Fri Nov 19, 2021 10:45 pm
>
> Could you have a script on noesis\quickbms\blender or something that allows you to modify the mesh and re-import it back into hgo?Hello GoldNeo, and yeah, "re-import it back"!   Any other tasks you wish to be fulfilled?  

> i have some partial parsing:Code: Select all;;; Structure of GameCube HGO files for TWOC.
>
> ; All number fields are big endian, with the exception of in .hgo.blk files.
>
> ; The game exectuable comes with function name symbols, which were an aid in deciphering the structures.
>
> 	
>
> struct matrix ; This is a 4x4 matrix, of size 0x40.[...]Whom is this from?
This "who" should be able to create a script, shouldn't he?  

Anyways, this looks to complicated to me, would take me ages understand it.
Here's what I got using hex2obj (maybe a H2O to follow on more progress):
.



crash-hgo.png (46.71 KiB) Viewed 83 times
## Post #3
- Username: GoldNeo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 30, 2020 7:59 am
- Post datetime: 2021-11-19T17:19:37+00:00
- Post Title: HGO 3d file model help

> Reply from shakotay2 ↑Sat Nov 20, 2021 1:02 am at Sat Nov 20, 2021 1:02 am
>
> Hello GoldNeo, and yeah, "re-import it back"!   Any other tasks you wish to be fulfilled?
yes, what about a verse of killing me softly?   jokes aside, I beg your pardon, I didn't mean to sound presumptuous 

> Reply from shakotay2 ↑Sat Nov 20, 2021 1:02 am at Sat Nov 20, 2021 1:02 am
>
> 
Whom is this from?
This "who" should be able to create a script, shouldn't he? 

Anyways, this looks to complicated to me, would take me ages understand it.
Here's what I got using hex2obj (maybe a H2O to follow on more progress)
the person who made this is not going to continue with the work as far as i know, but i found a blender plugin, with an import \ export that works partially.
There are unknown fields and it looks like it can't export to custom mesh.
 yes i know it's a complicated format so i'm trying to ask around 

blender plugin:


 Blender_HGO_IO_1.0.2.zip
(15.62 KiB) Downloaded 23 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-19T17:47:07+00:00
- Post Title: HGO 3d file model help

> Reply from GoldNeo ↑Sat Nov 20, 2021 1:19 am at Sat Nov 20, 2021 1:19 am
>
>  yes i know it's a complicated format so i'm trying to ask aroundwell, the author of the blender plugin is:
"Inuk#9439, in collaboration with CTWOC Modding Discord"

Guess, it's very unlikely that someone on Xentax will continue this "work in progress(?)".
(You could join that discord, couldn't you?)
