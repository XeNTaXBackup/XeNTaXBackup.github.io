## Post #1
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-22T04:05:45+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

Only way to import TDU 1/2 models was with zmodeler 2. any importer for blender or 3ds max would be appreciated.

EDIT: Textures will be ignored since TDUMT2 Texture Tools by Knyazev exists that works for both Test Drive Unlimited 1 and Test Drive Unlimited 2 texture format
[FirePW.rar](https://xentaxbackup.github.io/file/24091_FirePW.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-22T10:02:11+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

Annoying data mapping; some fiddling required to get the parts (values in magic tables could help):
.



FirePW.png (97.88 KiB) Viewed 201 times
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-22T12:22:31+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

Not very detailed:
.



FirePW_all.jpg (151.39 KiB) Viewed 182 times
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-07-22T12:53:04+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

i made Plugin for Noesis [fmt_3DG.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_3DG.py)
*(I'm too lazy to read chunks, so search for keywords)



FirePW.3DG.png (16.59 KiB) Viewed 179 times
## Post #5
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-22T13:02:06+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

more samples incoming
[interior.rar](https://xentaxbackup.github.io/file/24096_interior.rar)
## Post #6
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-22T13:02:26+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

rim sample
[rim.rar](https://xentaxbackup.github.io/file/24097_rim.rar)
## Post #7
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-07-23T19:08:24+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

```
clearlistener()

/*
Maxscript: Test Drive Unlimited 1/2 (PC?)
WrittenBy: mariokart64n (July 23 2023)

3DG BLOCK OVERVIEW
 weird format, it looks like a hierarchy based chunk format
 so alot of unnecessary node headers and jumping around for 
 something so simple.. 

    GEOA-------+
               |
        HASH<--+   // Object Name
        |
        GEOM---+
               |
            PRIM-+ // Mesh Info
                 |
    VBA.         |
        DXVB<----+ // Mesh Data
    IBA.         |
        DXIB<----+
    MORA
        REAL
*/
struct fmt3DG_Chunk (
	pos = 0,
	/*char[8]*/ type = "",
	/*uint32*/  end = 0, -- relative from start of block, skips block
	/*uint32*/  size = 0, -- relative from start of block, if 0 then no children blocks
	fn read &f = (
		pos = ftell f
		local i = 1, b = 0
		for i = 1 to 8 do (
			b = readByte f 
			if b > 0 then (
				type += bit.IntAsChar b
				)
			else (
				fseek f (8 - i) #seek_cur
				exit
				)
			)
		end = readLong f #unsigned
		size = readLong f #unsigned
		)
	)
struct fmt3DG_PRIM (
	/*uint32*/unk004 = 0, -- always 0?
	/*uint32*/unk005 = 0, -- always 4?
	/*uint32*/dxib_addr = 0, -- absolute offset
	/*uint32*/dxvb_addr = 0, -- absolute offset
	/*uint32*/unk006 = 0, --0
	/*uint32*/unk007 = 0, --0
	/*uint16*/unk008 = 0, --0
	/*uint16*/index = 0, --index? goes out of range of the sub materials.. so maybe global material index?
	/*uint32*/unk009 = 0, --1
	/*uint32*/unk010 = 0,--0
	/*uint32*/dxvb_count = 0,
	/*uint32*/unk011 = 0, --0
	/*uint32*/dxib_count = 0,
	
	-- the values below look like counts but i'm unable to connect it with anything
	/*uint32*/unk031 = 0, -- 1
	/*uint32*/unk012 = 0, -- 2304
	/*uint32*/unk013 = 0, -- 513
	/*uint32*/unk014 = 0, -- 0
	/*uint32*/unk015 = 0, -- 3073
	/*uint32*/unk016 = 0, -- 5632
	/*uint32*/unk017 = 0, -- 2304
	/*uint32*/unk018 = 0, -- 4352
	/*uint32*/unk019 = 0, -- 0
	/*uint32*/unk020 = 0, -- 0
	/*uint32*/unk021 = 0, -- 0
	/*uint32*/unk023 = 0, -- 0
	/*uint32*/unk024 = 0, -- 0
	/*uint32*/unk025 = 0, -- 0
	/*uint32*/unk026 = 0, -- 0
	/*uint32*/unk027 = 0, -- 0
	/*uint32*/unk028 = 0, -- 0
	/*uint32*/unk029 = 0, -- 0
	/*uint32*/unk030 = 0, -- 0
	
	/*
		addresses to vertex components are given witin the dxvb
		however there isn't a definition provided to explain 
		what each component is... we would need to assume its 
		fixed until more information is discovered...
		
		the dxvb block starts with 64 bytes of grabage then the
		vertex positions are defined. the addresses given below
		are relative to the start of the vertex positions, also
		the address for the vertex positions is not given.
	*/
	buffer_addr = #(0), -- first one is always going to be vertex positions
	/*
		its unclear why some blocks are larger then others
		the larger blocks just appear to contain more garbage
		at the end of the file.. it doesn't look meaningful though
	*/
	fn read &f &header = (
		unk004 = readLong f #unsigned
		unk005 = readLong f #unsigned
		dxib_addr = readLong f #unsigned
		dxvb_addr = readLong f #unsigned
		unk006 = readLong f #unsigned
		unk007 = readLong f #unsigned
		unk008 = readShort f #unsigned
		index = readShort f #unsigned
		unk009 = readLong f #unsigned
		unk010 = readLong f #unsigned
		dxvb_count = readLong f #unsigned
		unk031 = readLong f #unsigned
		dxib_count = readLong f #unsigned
		unk011 = readLong f #unsigned
		unk012 = readLong f #unsigned
		unk013 = readLong f #unsigned
		unk014 = readLong f #unsigned
		unk015 = readLong f #unsigned
		unk016 = readLong f #unsigned
		unk017 = readLong f #unsigned
		unk018 = readLong f #unsigned
		unk019 = readLong f #unsigned
		unk020 = readLong f #unsigned
		unk021 = readLong f #unsigned
		unk023 = readLong f #unsigned
		unk024 = readLong f #unsigned
		unk025 = readLong f #unsigned
		unk026 = readLong f #unsigned
		unk027 = readLong f #unsigned
		unk028 = readLong f #unsigned
		unk029 = readLong f #unsigned
		unk030 = readLong f #unsigned
		local addr = ftell f
		while addr < (header.pos + header.end) do (
			addr = readLong f #unsigned
			if addr != 0xCDCDCDCD and addr > 0 then (
				append buffer_addr addr
				) else (exit)
			)
		-- theres more stuff here but I don't think its important
		)
	)
struct fmt3DG_Hash (
	index = 0,
	name = "", -- hash may sometimes be a valid name
	/*char[8]*/ hash = #(),
	/*uint32*/  addr = 0, -- absolute offset to GEOM block
	/*uint32*/  unk003 = 0,
	fn read &f = (
		local i = 1, b = 0
		hash = #(
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned
			)
		
		name = ""
		for i = 1 to 8 do (
			if (hash[i] > 66 and hash[i] < 123) do (
				name += bit.IntAsChar hash[i]
				)
			)
		
		if name == "" do (
			name = "0x"
			local n = ""
			for i = 1 to 8 do (
				name += subString (n = (bit.IntAsHex (hash[i] as integer)) + "00") (n.count - 1) -1
				)
			if classOf toUpper != UndefinedClass do (
				name = toUpper(name)
				)
			)
		addr = readLong f #unsigned
		unk003 = readLong f #unsigned
		)
	)
struct fmt3DG_GEOA (
	hash = #(),
	geom = #(),
	fn read &f &header = (
		local c = fmt3DG_Chunk()
		while ftell f < (header.pos + header.end) do (
			c = fmt3DG_Chunk()
			c.read(&f)
			
			case c.type of (
				"HASH": (
					local hash_count = ((c.size - 16) / 16) as integer
					hash = #()
					if hash_count > 0 do (
						hash[hash_count] = fmt3DG_Hash()
						local i = 1
						for i = 1 to hash_count do (
							hash[i] = fmt3DG_Hash()
							hash[i].read(&f)
							)
						)
					)
				"GEOM": (
					local g = fmt3DG_Chunk()
					local prim = #()
					while ftell f < (c.pos + c.end) do (
						g = fmt3DG_Chunk()
						g.read(&f)
						case g.type of (
							"PRIM": (
								local p = fmt3DG_PRIM()
								p.read &f g
								append prim p
								)
							default: (
								format "Unsupported Block {%}\n" g.type
								)
							)
						fseek f (g.pos + g.end) #seek_set
						)
					append geom prim
					local i = 1
					for i = 1 to hash.count do (
						if hash[i].addr == c.pos do (
							hash[i].index = geom.count
							exit
							)
						)
					)
				default: (
					format "Unsupported Block {%}\n" c.type
					exit
					)
				)
			fseek f (c.pos + c.end) #seek_set
			)
		)
	)
struct fmt3DG_Header (
	/*uint32*/unk001 = 0,
	/*uint32*/unk002 = 0,
	/*uint32*/fsize = 0,
	/*uint32*/type = 0,
	fn read &f = (
		unk001 = readlong f #unsigned
		unk002 = readlong f #unsigned
		fsize = readlong f #unsigned
		type = readlong f #unsigned
		)
	)
struct fmt3DG (
	header = fmt3DG_Header(),
	geoa = fmt3DG_GEOA(),
	vba = #(),
	iba = #(),
	mora = #(),
	fn read &f mscale:39.3701 verbose:false = (
		header.read(&f)
		if header.type == 0x4744332E do (
			local c = fmt3DG_Chunk()
			local o = 1, m = 1, v = 1, x = 0, i = 1
			local msh = undefined
			local face_off = 1
			local vertArray = #()
			local faceArray = #()
			local matidArray = #()
			local tvertArray = #()
			local fa = 1,fb = 1,fc = 1
			local face_flip = false
			local face_reset = false
			local buffer_sizes = #()
			local dxvb_stride = 0
			while ftell f < header.fsize do (
				c = fmt3DG_Chunk()
				c.read(&f)
				case c.type of (
					"GEOA": (
						geoa.read &f c
						
						-- Loop through each member in the geom table
						
						for o = 1 to geoa.geom.count do (
							if verbose do print o
							vertArray = #()
							tvertArray = #()
							faceArray = #()
							matidArray = #()
							face_off = 1
							
							-- loop through each sub material
							for m = 1 to geoa.geom[o].count do (
								
								if verbose do print geoa.geom[o][m]
								
								-- Read the vertices
								fseek f (geoa.geom[o][m].dxvb_addr + 80) #seek_set
								for v = 1 to geoa.geom[o][m].dxvb_count do (
									append vertArray ([readFloat f, readFloat f, readFloat f] * mscale)
									vertArray[vertArray.count] = [vertArray[vertArray.count][1], -vertArray[vertArray.count][3], vertArray[vertArray.count][2]]
									)
								
								-- Try to Read UV's
								dxvb_stride = 0
								buffer_sizes = #()
								if geoa.geom[o][m].buffer_addr.count > 0 do (
									buffer_sizes = copy geoa.geom[o][m].buffer_addr #nomap
									fseek f (geoa.geom[o][m].dxvb_addr + 8) #seek_set
									append buffer_sizes ((readLong f #unsigned) - 80)
									sort buffer_sizes
									-- i inserted a 0 in the array earlier, so search from second entry
									for i = 2 to geoa.geom[o][m].buffer_addr.count do (
										x = findItem buffer_sizes geoa.geom[o][m].buffer_addr[i]
										if x > 0 do (
											dxvb_stride = ((buffer_sizes[x + 1] - buffer_sizes[x]) / geoa.geom[o][m].dxvb_count) as integer
											if dxvb_stride == 8 do ( -- probably UV's
												fseek f (geoa.geom[o][m].dxvb_addr + geoa.geom[o][m].buffer_addr[i] + 80) #seek_set
												for v = 1 to geoa.geom[o][m].dxvb_count do (
													append tvertArray [readFloat f, 1.0 - readFloat f, 0.0]
													)
												exit
												)
											)
										)
									)
								if dxvb_stride != 8 do (for v = 1 to geoa.geom[o][m].dxvb_count do (append tvertArray [0.0, 0.0, 0.0]))
								
								-- Read the faces
								x = 0
								face_flip = false
								face_reset = true
								fseek f (geoa.geom[o][m].dxib_addr + 80) #seek_set
								while x < geoa.geom[o][m].dxib_count do (
									x+=1
									if face_reset then (
										x+=2
										fa = (readShort f #unsigned) + face_off
										fb = (readShort f #unsigned) + face_off
										fc = (readShort f #unsigned) + face_off
										face_reset = false
										if fa != fb and fb != fc and fc != fa do (
											append matidArray m--(geoa.geom[o][m].index + 1)
											if face_flip then (
												append faceArray [fa,fc,fb]
												)
											else(
												append faceArray [fa,fb,fc]
												)
											face_flip = not face_flip
											)
										)
									else(
										fa = fb
										fb = fc
										fc = readShort f #unsigned
										if fc != 0xFFFF and fc != -1 then (
											fc += face_off
											
											if fa != fb and fb != fc and fc != fa do (
												append matidArray m--(geoa.geom[o][m].index + 1)
												if face_flip then (
													append faceArray [fa,fc,fb]
													)
												else (
													append faceArray [fa,fb,fc]
													)
												)
											face_flip = not face_flip
											)
										else (
											face_reset = true
											)
										)
									)
								face_off += geoa.geom[o][m].dxvb_count
								)
							msh = mesh vertices:vertArray faces:faceArray tverts:tvertArray materialIDs:matidArray
							msh.backfacecull = on
							msh.displayByLayer = false
							msh.wirecolor = random (color 0 0 0) (color 255 255 255)
							if tvertArray.count > 0 do (
								buildTVFaces msh
								for i = 1 to faceArray.count do (setTVFace msh i faceArray[i])
								)
							for i = 1 to faceArray.count do setFaceSmoothGroup msh i 1
							
							if geoa.geom[o].count > 0 do (
								msh.material = MultiMaterial numsubs:geoa.geom[o].count
								for i = 1 to geoa.geom[o].count do (
									msh.material[i] = StandardMaterial()
									msh.material[i].diffuse = random white black
									)
								)
							
							-- try to get the name
							x = 0
							for v = 1 to geoa.hash.count do (
								if o == geoa.hash[v].index do (
									if getNodeByName geoa.hash[v].name != undefined then (
										msh.name = uniqueName geoa.hash[v].name
										)
									else (
										msh.name = geoa.hash[v].name
										)
									exit
									)
								
								)
							--if o == 4 do exit
							)
						
						exit -- skip the other blocks, they're addressed from here anyway
						)
					"VBA.": ()
					"IBA.": ()
					"MORA": ()
					"REAL": ()
					default: (
						format "Unsupported Block {%}\n" c.type
						)
					)
				fseek f (c.pos + c.end) #seek_set
				)
			)
		)
	)

fn read file = (
	local f = try(fopen file "rb")catch(undefined)
	if f != undefined do (
		local threeDG = fmt3DG()
		threeDG.read(&f)
		)
	fclose f
	)

--delete $*
read (
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW_F_01.3DG" -- 14kb
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW_I.3DG" -- 296kb
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW.3DG" -- 505kb
	GetOpenFileName types:"3DG Mesh files (*.3dg)|*.3dg|All files (*.*)|*.*|"
	)

```
## Post #8
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-24T07:32:53+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

> Reply from mariokart64n ↑Mon Jul 24, 2023 3:08 am at Mon Jul 24, 2023 3:08 am
>
> 
Code: Select allgc()
clearlistener()

/*
Maxscript: Test Drive Unlimited 1/2 (PC?)
WrittenBy: mariokart64n (July 23 2023)

3DG BLOCK OVERVIEW
 weird format, it looks like a hierarchy based chunk format
 so alot of unnecessary node headers and jumping around for 
 something so simple.. 

    GEOA-------+
               |
        HASH<--+   // Object Name
        |
        GEOM---+
               |
            PRIM-+ // Mesh Info
                 |
    VBA.         |
        DXVB<----+ // Mesh Data
    IBA.         |
        DXIB<----+
    MORA
        REAL
*/
struct fmt3DG_Chunk (
	pos = 0,
	/*char[8]*/ type = "",
	/*uint32*/  end = 0, -- relative from start of block, skips block
	/*uint32*/  size = 0, -- relative from start of block, if 0 then no children blocks
	fn read &f = (
		pos = ftell f
		local i = 1, b = 0
		for i = 1 to 8 do (
			b = readByte f 
			if b > 0 then (
				type += bit.IntAsChar b
				)
			else (
				fseek f (8 - i) #seek_cur
				exit
				)
			)
		end = readLong f #unsigned
		size = readLong f #unsigned
		)
	)
struct fmt3DG_PRIM (
	/*uint32*/unk004 = 0, -- always 0?
	/*uint32*/unk005 = 0, -- always 4?
	/*uint32*/dxib_addr = 0, -- absolute offset
	/*uint32*/dxvb_addr = 0, -- absolute offset
	/*uint32*/unk006 = 0, --0
	/*uint32*/unk007 = 0, --0
	/*uint16*/unk008 = 0, --0
	/*uint16*/index = 0, --index? goes out of range of the sub materials.. so maybe global material index?
	/*uint32*/unk009 = 0, --1
	/*uint32*/unk010 = 0,--0
	/*uint32*/dxvb_count = 0,
	/*uint32*/unk011 = 0, --0
	/*uint32*/dxib_count = 0,
	
	-- the values below look like counts but i'm unable to connect it with anything
	/*uint32*/unk031 = 0, -- 1
	/*uint32*/unk012 = 0, -- 2304
	/*uint32*/unk013 = 0, -- 513
	/*uint32*/unk014 = 0, -- 0
	/*uint32*/unk015 = 0, -- 3073
	/*uint32*/unk016 = 0, -- 5632
	/*uint32*/unk017 = 0, -- 2304
	/*uint32*/unk018 = 0, -- 4352
	/*uint32*/unk019 = 0, -- 0
	/*uint32*/unk020 = 0, -- 0
	/*uint32*/unk021 = 0, -- 0
	/*uint32*/unk023 = 0, -- 0
	/*uint32*/unk024 = 0, -- 0
	/*uint32*/unk025 = 0, -- 0
	/*uint32*/unk026 = 0, -- 0
	/*uint32*/unk027 = 0, -- 0
	/*uint32*/unk028 = 0, -- 0
	/*uint32*/unk029 = 0, -- 0
	/*uint32*/unk030 = 0, -- 0
	
	/*
		addresses to vertex components are given witin the dxvb
		however there isn't a definition provided to explain 
		what each component is... we would need to assume its 
		fixed until more information is discovered...
		
		the dxvb block starts with 64 bytes of grabage then the
		vertex positions are defined. the addresses given below
		are relative to the start of the vertex positions, also
		the address for the vertex positions is not given.
	*/
	buffer_addr = #(0), -- first one is always going to be vertex positions
	/*
		its unclear why some blocks are larger then others
		the larger blocks just appear to contain more garbage
		at the end of the file.. it doesn't look meaningful though
	*/
	fn read &f &header = (
		unk004 = readLong f #unsigned
		unk005 = readLong f #unsigned
		dxib_addr = readLong f #unsigned
		dxvb_addr = readLong f #unsigned
		unk006 = readLong f #unsigned
		unk007 = readLong f #unsigned
		unk008 = readShort f #unsigned
		index = readShort f #unsigned
		unk009 = readLong f #unsigned
		unk010 = readLong f #unsigned
		dxvb_count = readLong f #unsigned
		unk031 = readLong f #unsigned
		dxib_count = readLong f #unsigned
		unk011 = readLong f #unsigned
		unk012 = readLong f #unsigned
		unk013 = readLong f #unsigned
		unk014 = readLong f #unsigned
		unk015 = readLong f #unsigned
		unk016 = readLong f #unsigned
		unk017 = readLong f #unsigned
		unk018 = readLong f #unsigned
		unk019 = readLong f #unsigned
		unk020 = readLong f #unsigned
		unk021 = readLong f #unsigned
		unk023 = readLong f #unsigned
		unk024 = readLong f #unsigned
		unk025 = readLong f #unsigned
		unk026 = readLong f #unsigned
		unk027 = readLong f #unsigned
		unk028 = readLong f #unsigned
		unk029 = readLong f #unsigned
		unk030 = readLong f #unsigned
		local addr = ftell f
		while addr < (header.pos + header.end) do (
			addr = readLong f #unsigned
			if addr != 0xCDCDCDCD and addr > 0 then (
				append buffer_addr addr
				) else (exit)
			)
		-- theres more stuff here but I don't think its important
		)
	)
struct fmt3DG_Hash (
	index = 0,
	name = "", -- hash may sometimes be a valid name
	/*char[8]*/ hash = #(),
	/*uint32*/  addr = 0, -- absolute offset to GEOM block
	/*uint32*/  unk003 = 0,
	fn read &f = (
		local i = 1, b = 0
		hash = #(
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned,
			readByte f #unsigned
			)
		
		name = ""
		for i = 1 to 8 do (
			if (hash[i] > 66 and hash[i] < 123) do (
				name += bit.IntAsChar hash[i]
				)
			)
		
		if name == "" do (
			name = "0x"
			local n = ""
			for i = 1 to 8 do (
				name += subString (n = (bit.IntAsHex (hash[i] as integer)) + "00") (n.count - 1) -1
				)
			if classOf toUpper != UndefinedClass do (
				name = toUpper(name)
				)
			)
		addr = readLong f #unsigned
		unk003 = readLong f #unsigned
		)
	)
struct fmt3DG_GEOA (
	hash = #(),
	geom = #(),
	fn read &f &header = (
		local c = fmt3DG_Chunk()
		while ftell f < (header.pos + header.end) do (
			c = fmt3DG_Chunk()
			c.read(&f)
			
			case c.type of (
				"HASH": (
					local hash_count = ((c.size - 16) / 16) as integer
					hash = #()
					if hash_count > 0 do (
						hash[hash_count] = fmt3DG_Hash()
						local i = 1
						for i = 1 to hash_count do (
							hash[i] = fmt3DG_Hash()
							hash[i].read(&f)
							)
						)
					)
				"GEOM": (
					local g = fmt3DG_Chunk()
					local prim = #()
					while ftell f < (c.pos + c.end) do (
						g = fmt3DG_Chunk()
						g.read(&f)
						case g.type of (
							"PRIM": (
								local p = fmt3DG_PRIM()
								p.read &f g
								append prim p
								)
							default: (
								format "Unsupported Block {%}\n" g.type
								)
							)
						fseek f (g.pos + g.end) #seek_set
						)
					append geom prim
					local i = 1
					for i = 1 to hash.count do (
						if hash[i].addr == c.pos do (
							hash[i].index = geom.count
							exit
							)
						)
					)
				default: (
					format "Unsupported Block {%}\n" c.type
					exit
					)
				)
			fseek f (c.pos + c.end) #seek_set
			)
		)
	)
struct fmt3DG_Header (
	/*uint32*/unk001 = 0,
	/*uint32*/unk002 = 0,
	/*uint32*/fsize = 0,
	/*uint32*/type = 0,
	fn read &f = (
		unk001 = readlong f #unsigned
		unk002 = readlong f #unsigned
		fsize = readlong f #unsigned
		type = readlong f #unsigned
		)
	)
struct fmt3DG (
	header = fmt3DG_Header(),
	geoa = fmt3DG_GEOA(),
	vba = #(),
	iba = #(),
	mora = #(),
	fn read &f mscale:39.3701 verbose:false = (
		header.read(&f)
		if header.type == 0x4744332E do (
			local c = fmt3DG_Chunk()
			local o = 1, m = 1, v = 1, x = 0, i = 1
			local msh = undefined
			local face_off = 1
			local vertArray = #()
			local faceArray = #()
			local matidArray = #()
			local tvertArray = #()
			local fa = 1,fb = 1,fc = 1
			local face_flip = false
			local face_reset = false
			local buffer_sizes = #()
			local dxvb_stride = 0
			while ftell f < header.fsize do (
				c = fmt3DG_Chunk()
				c.read(&f)
				case c.type of (
					"GEOA": (
						geoa.read &f c
						
						-- Loop through each member in the geom table
						
						for o = 1 to geoa.geom.count do (
							if verbose do print o
							vertArray = #()
							tvertArray = #()
							faceArray = #()
							matidArray = #()
							face_off = 1
							
							-- loop through each sub material
							for m = 1 to geoa.geom[o].count do (
								
								if verbose do print geoa.geom[o][m]
								
								-- Read the vertices
								fseek f (geoa.geom[o][m].dxvb_addr + 80) #seek_set
								for v = 1 to geoa.geom[o][m].dxvb_count do (
									append vertArray ([readFloat f, readFloat f, readFloat f] * mscale)
									vertArray[vertArray.count] = [vertArray[vertArray.count][1], -vertArray[vertArray.count][3], vertArray[vertArray.count][2]]
									)
								
								-- Try to Read UV's
								dxvb_stride = 0
								buffer_sizes = #()
								if geoa.geom[o][m].buffer_addr.count > 0 do (
									buffer_sizes = copy geoa.geom[o][m].buffer_addr #nomap
									fseek f (geoa.geom[o][m].dxvb_addr + 8) #seek_set
									append buffer_sizes ((readLong f #unsigned) - 80)
									sort buffer_sizes
									-- i inserted a 0 in the array earlier, so search from second entry
									for i = 2 to geoa.geom[o][m].buffer_addr.count do (
										x = findItem buffer_sizes geoa.geom[o][m].buffer_addr[i]
										if x > 0 do (
											dxvb_stride = ((buffer_sizes[x + 1] - buffer_sizes[x]) / geoa.geom[o][m].dxvb_count) as integer
											if dxvb_stride == 8 do ( -- probably UV's
												fseek f (geoa.geom[o][m].dxvb_addr + geoa.geom[o][m].buffer_addr[i] + 80) #seek_set
												for v = 1 to geoa.geom[o][m].dxvb_count do (
													append tvertArray [readFloat f, 1.0 - readFloat f, 0.0]
													)
												exit
												)
											)
										)
									)
								if dxvb_stride != 8 do (for v = 1 to geoa.geom[o][m].dxvb_count do (append tvertArray [0.0, 0.0, 0.0]))
								
								-- Read the faces
								x = 0
								face_flip = false
								face_reset = true
								fseek f (geoa.geom[o][m].dxib_addr + 80) #seek_set
								while x < geoa.geom[o][m].dxib_count do (
									x+=1
									if face_reset then (
										x+=2
										fa = (readShort f #unsigned) + face_off
										fb = (readShort f #unsigned) + face_off
										fc = (readShort f #unsigned) + face_off
										face_reset = false
										if fa != fb and fb != fc and fc != fa do (
											append matidArray m--(geoa.geom[o][m].index + 1)
											if face_flip then (
												append faceArray [fa,fc,fb]
												)
											else(
												append faceArray [fa,fb,fc]
												)
											face_flip = not face_flip
											)
										)
									else(
										fa = fb
										fb = fc
										fc = readShort f #unsigned
										if fc != 0xFFFF and fc != -1 then (
											fc += face_off
											
											if fa != fb and fb != fc and fc != fa do (
												append matidArray m--(geoa.geom[o][m].index + 1)
												if face_flip then (
													append faceArray [fa,fc,fb]
													)
												else (
													append faceArray [fa,fb,fc]
													)
												)
											face_flip = not face_flip
											)
										else (
											face_reset = true
											)
										)
									)
								face_off += geoa.geom[o][m].dxvb_count
								)
							msh = mesh vertices:vertArray faces:faceArray tverts:tvertArray materialIDs:matidArray
							msh.backfacecull = on
							msh.displayByLayer = false
							msh.wirecolor = random (color 0 0 0) (color 255 255 255)
							if tvertArray.count > 0 do (
								buildTVFaces msh
								for i = 1 to faceArray.count do (setTVFace msh i faceArray[i])
								)
							for i = 1 to faceArray.count do setFaceSmoothGroup msh i 1
							
							if geoa.geom[o].count > 0 do (
								msh.material = MultiMaterial numsubs:geoa.geom[o].count
								for i = 1 to geoa.geom[o].count do (
									msh.material[i] = StandardMaterial()
									msh.material[i].diffuse = random white black
									)
								)
							
							-- try to get the name
							x = 0
							for v = 1 to geoa.hash.count do (
								if o == geoa.hash[v].index do (
									if getNodeByName geoa.hash[v].name != undefined then (
										msh.name = uniqueName geoa.hash[v].name
										)
									else (
										msh.name = geoa.hash[v].name
										)
									exit
									)
								
								)
							--if o == 4 do exit
							)
						
						exit -- skip the other blocks, they're addressed from here anyway
						)
					"VBA.": ()
					"IBA.": ()
					"MORA": ()
					"REAL": ()
					default: (
						format "Unsupported Block {%}\n" c.type
						)
					)
				fseek f (c.pos + c.end) #seek_set
				)
			)
		)
	)

fn read file = (
	local f = try(fopen file "rb")catch(undefined)
	if f != undefined do (
		local threeDG = fmt3DG()
		threeDG.read(&f)
		)
	fclose f
	)

--delete $*
read (
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW_F_01.3DG" -- 14kb
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW_I.3DG" -- 296kb
-- 	"C:\\Users\\Corey\\Downloads\\test drive unlimited 1,2 3dg\\FirePW.3DG" -- 505kb
	GetOpenFileName types:"3DG Mesh files (*.3dg)|*.3dg|All files (*.*)|*.*|"
	)

How do I use this code btw? do I have to copy/paste to 3ds max scripts folder or what?

EDIT: I'm asking this because it doesn't work on my end after copying the code
## Post #9
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-07-24T23:56:53+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

for 3dsmax go to the the applications menus, select: Scripting -> Run Script, and open the script.

similarly if this was a python script for blender, you could paste it into the script editor and press run. also you can do the same thing in 3dmax, open the script editor, paste it into a new script file and press execute script. 

files in your script folder for either 3dsmax or blender require you to install the script through its addon system, you can't just drop a random script in the scripts folder. I would guess your probably use to that method because your use to using noesis since you just drop files into the plugin folder.

if this is the case then you need to not request codebases for 3dsmax and blender, rather specify that your using noesis and require a noesis plugin.

> Reply from UB833 ↑Sat Jul 22, 2023 12:05 pm at Sat Jul 22, 2023 12:05 pm
>
> 
any importer for blender or 3ds max would be appreciated.
many times I make a program that someone requested in some other program they don't use and don't know how to use. later its a whole story of how they need the program remade for noesis, would have made sense if you just requested it for noesis to begin with... anyway just ranting about the silly logic I encounter with people all the time..
## Post #10
- Username: UB833
- Rank: advanced
- Number of posts: 79
- Joined date: Tue Jan 04, 2022 4:55 pm
- Post datetime: 2023-07-25T06:54:00+00:00
- Post Title: Test Drive Unlimited 1/2 3dg file

> Reply from mariokart64n ↑Tue Jul 25, 2023 7:56 am at Tue Jul 25, 2023 7:56 am
>
> 
if this is the case then you need to not request codebases for 3dsmax and blender, rather specify that your using noesis and require a noesis plugin.

I use only noesis for only texture extracting purposes, most of the time so okay. and for model manipulation, I use blender btw. next time for model case, I'll request it.
