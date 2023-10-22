## Post #1
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-07-16T06:40:41+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Hey all, newcomer to these forums, figured this'd be the place to ask this.
Since stumbling upon the SWGExplorer project here, I've had an interesting time extracting models, etc. I'd like to convert some of these for use in gmax to port them into Jedi Academy, but the problem is I can't find support for the format outside of Ultimate Unwrap3d. Unfortunately, I don't have the funds to shell out $50 to convert like 5 rather smallish models. I'm wondering if anyone here would be willing to have a look at the files/plugin and write/create a base for something I could use in gmax, blender or the like? I have a basic knowledge of C++, so I may be able to finish writing such a plugin.
EDIT: Just remembered-- The  MGN is not just a mesh but also has references to shader files and bones. Thought it might be good to include.
## Post #2
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2006-08-22T14:52:35+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

I have enough of the mgn figured out to do mesh and textures so I'll go ahead and post up my horrible maxscript importer
## Post #3
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2006-08-22T14:53:40+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

utility swgmgntest "SWG MGN Importer"
(
	----------
	-- Vars --
	----------
	local modelName

	local impTypes

	local seqs			-- Sequences
	local mtls			-- Materials
	local geos			-- Geometry
	local objs			-- Bones, Helpers, Lights, Attachments
	local pivot

	local geobones

	local notes			-- Note Track

	local meshes = #()
	----------------
	-- Structures --
	----------------
	struct File
	(
		pos, end, bstream,

		-- Helper function to init the top-level chunk rover
		fn Init stream=
		(
			bstream = stream
			pos = ftell bstream
			fseek bstream 0 #seek_end
			end = ftell bstream
		),

		fn fReadHead=
		(
			fseek bstream pos #seek_set
			local id = ReadLong bstream #unsigned
			local tag = File.GetName id
			pos += 4
			tag
		),

		fn fReadFloat=
		(
			local id
			local i = 0
			while (id == undefined) and (i < 10) do
			(
				fseek bstream pos #seek_set
				id = ReadFloat bstream
				i += 1
			)
			if i == 10 then
			(
				print ("problem: " + (pos as string))
			)
			pos += 4
			id
		),

		fn fReadLong=
		(
			fseek bstream pos #seek_set
			local id = ReadLong bstream
			pos += 4
			id
		),

		fn fReadShort=
		(
			fseek bstream pos #seek_set
			local id = ReadShort bstream #unsigned
			pos += 2
			id
		),

		fn fReadByte=
		(
			fseek bstream pos #seek_set
			local id = ReadByte bstream
			pos += 1
			id
		),

		fn fReadString n=
		(
			fseek bstream pos #seek_set
			local id = ReadString bstream
			pos += n*80
			id
		),
		fn GetName id=
		(
			case id of
			(
				0x33544F44: #DOT3
				0x4C54494F: #OITL
				0x20435A4F: #OZC
				0x4C434456: #VDCL
				--UNKNOWN
				default: #UNKNOWN
 			)
		)

	)
	fn sflip numb =
	(
		local bits = #()
		local n
		for n = 1 to n = 16 do
		(
			bits[n] = bit.get numb n
		)
		for n = 1 to n = 8 do
		(
			numb = bit.set numb n bits[(n+8)]
		) 		for n = 9 to n = 16 do
		(
			numb = bit.set numb n bits[(n-8)]
		) 		return numb
	)
	fn lflip numb =
	(
 		local bits = #()
		local n
		for n = 1 to n = 32 do
		(
			bits[n] = bit.get numb n
		)
		for n = 1 to n = 8 do
		(
			numb = bit.set numb n bits[(24+n)]
		) 		
		for n = 9 to n = 16 do
		(
			numb = bit.set numb n bits[(8+n)]
		) 	
		for n = 17 to n = 24 do
		(
			numb = bit.set numb n bits[(n-8)]
		) 		
		for n = 25 to n = 32 do
		(
			numb = bit.set numb n bits[(n-24)]
		) 		
		return numb
	)	


	--------------------
	-- User Interface --
	--------------------
	group "Import MSH"
	(
		button importButton "Import MGN..."
	)

	--------------------------
	-- Main Import Function --
	--------------------------

	on importButton pressed do
	(
		-- Show open file dialog box
		local objFileName = getOpenFileName caption:"Import MGN" types:"SWG model File (*.mgn)|*.mgn|All Files (*.*)|*.*|"


		local isValid = true
		if objFileName != undefined then
		(
			-- If user made a selection, begin importing
			if doesFileExist objFileName then
			(
				-- Open up the file as a binary stream
				local bstream = fopen objFileName "rb"			
				local mdx = File()
				local refx 
				local refy 
				local refz 
				local verts = #()
				local test = #()
				local faces = #()
				local normals = #()
				mdx.Init bstream
				mdx.pos = 44
				local nbones = mdx.fReadLong()
				local nverts = mdx.fReadLong()
				local nweights = mdx.fReadLong()
				local nnormals = mdx.fReadLong()
				mdx.pos = 60
				local nummesh = mdx.fReadLong()
				mdx.pos = 83
				local str = mdx.fReadByte()
				--messagebox ("str length is " + (str as string))
				mdx.pos += (str + 6)
				--messagebox ("reading nverts at " + (mdx.pos as string))				
				local tests = mdx.fReadShort()
				--messagebox ("tests before flip is " + (tests as string))
				tests = sflip tests
				mdx.pos += (8 + tests)
				--messagebox ("reading verts at " + (mdx.pos as string))					
				for n = 1 to n = nverts do
				(
					x = mdx.fReadFloat()
					y = mdx.fReadFloat()
					z = mdx.fReadFloat()
					verts[n] = point3 x z y
				)
				mdx.pos += 6 				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len + 6)
				--messagebox ("pos before twit is " + (mdx.pos as string))					
				--twdt
				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len + 6)
				messagebox ("pos before norm is " + (mdx.pos as string))		
				--norm 				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len)
				messagebox ("pos before head reading is " + (mdx.pos as string))
				local head = mdx.fReadHead()

				if (head == #DOT3) then (	
					mdx.pos += 2		
					--dot3
					local len = mdx.fReadShort()
					len = sflip len
					mdx.pos += (len)
				) else (
					mdx.pos -= 4
				)

				mdx.pos += 7
				str = mdx.fReadByte()
				mdx.pos += (str)
				local type
				if mdx.fReadHead() == #OZC then
				(
					type = true
				) else (
					type = false
				)
				mdx.pos += 2
				local j = mdx.fReadShort()
				j = sflip j
				mdx.pos += j

				for w = 1 to w = nummesh do
				(
					messagebox ("pos of form is " + (mdx.pos as string))
					mdx.pos += 19					
					str = mdx.fReadByte()
					mdx.pos += (str + 6)
					local jump = mdx.fReadShort()
					jump = sflip jump
					jump += mdx.pos
					local size = mdx.fReadLong()
					local ppoints = #()
					for n = 1 to n = size do
					(
						x = mdx.fReadLong()					
						ppoints[n] = (x + 1)
					)		
					mdx.pos = (jump + 6)
					--NIDX
					messagebox ("pos of NIDX is " + (mdx.pos as string))				
					jump = mdx.fReadShort()
					jump = sflip jump				
					mdx.pos += (jump)
					local header = mdx.fReadHead()
					if ((header == #DOT3) or (header == #VDCL)) then
					(
						mdx.pos += 2
						--DOT3
						messagebox ("pos of dot3 is " + (mdx.pos as string))					
						jump = mdx.fReadShort()
						jump = sflip jump				
						mdx.pos += (jump + 6)
					) else (
						mdx.pos += 2
					)
					--TXCI
					messagebox ("TXCI pos is " + (mdx.pos as string))					
					jump = mdx.fReadShort()
					jump = sflip jump				
					mdx.pos += (jump + 18)
					--FORM
					messagebox ("FORM pos is " + (mdx.pos as string))					
					jump = mdx.fReadShort()
					jump = sflip jump
					local tverts = #()
					for m = 1 to m = (jump /  do
					(
						x = mdx.fReadFloat()
						y = mdx.fReadFloat()
						tverts[m] = point3 x (1-y) 0
					)
					mdx.pos += 24				
					messagebox ("pos of face is " + (mdx.pos as string))
					local fc					
					--face block

					mdx.pos += 6
					jump = mdx.fReadShort()	
					jump = sflip jump
					local jump2 = jump
					jump += mdx.pos
					fc = mdx.fReadLong()
					messagebox ("nfaces: " + (fc as string))												
					for n = 1 to n = fc do
					(
						if (((fc * 14) + 4) <= jump2) then (mdx.pos += 2)
						x = mdx.fReadLong()
						y = mdx.fReadLong()
						z = mdx.fReadLong()
						--messagebox ("x is " + (x as string) + " y is " + (y as string) + " z is " + (z as string))
						faces[n] = point3 ppoints[(x+1)] ppoints[(y+1)] ppoints[(z+1)]
					)
					mdx.pos = jump
					test[w] = mesh numverts: nverts numfaces: fc
					for b = 1 to b = nverts do
					(
						test[w].vertices = verts
					)
					for b = 1 to b = fc do
					(
						test[w].faces = faces
					)
					setNumTVerts test[w] nverts		
					for k = 1 to k = tverts.count do
					(
						setTVert test[w] ppoints[k] tverts[k]
					)
					buildTVFaces test[w]

					for k = 1 to test[w].numfaces do
					(
						setTVFace test[w] k faces[k]
					)
					for k = 1 to k = tverts.count do
					(
						setTVert test[w] ppoints[k] tverts[k]
					)				
				)	
			) 		)
	)
)

--getNodeByName <string> exact:<boolean>
## Post #4
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-08-22T16:51:12+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Will test, post results shortly. FYI the board's smilified some of the characters, I'll have a hack at converting them back to the original.
Many thanks ^_^
EDIT: Ok, after doing a few copy/paste operations and taking 5 minutes to realize there's a new rollout XD I try and import a few models. I keep getting some variable type errors, str will come up as being of an undefined type. Apparently it doesn't care if it was modified in the previous line without error.
I'm trying to do a little bit of degugging here, but unfortunately I'm not really familiar with MAXscript. For starters, there are no variable types.
## Post #5
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2006-08-24T15:08:43+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

yeah, maxscript is super ugly the filkes I've tested this with so far are palpatine_l3.mgn, palpatine_l0.mgn and bantha_l0.mgn
## Post #6
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2006-08-24T15:09:47+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

also, you need to flip the normals
## Post #7
- Username: nicoli_s
- Rank: advanced
- Number of posts: 77
- Joined date: Fri Jan 07, 2005 2:47 pm
- Post datetime: 2006-08-24T15:11:23+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

but if its still not working, post up the model yer trying to tes tand ill take a look and see if it changed
## Post #8
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-08-24T19:17:48+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Found a new error on a different model-- When I try to load the composite helmet, I get a message saying we got a negative number in an array index. This doesn't seem to appear on any other model. Original problem was with a '+' operation on an undefined type of variable. Attaching test models for your examination.
[MGNs.zip](https://xentaxbackup.github.io/file/825_MGNs.zip)
## Post #9
- Username: General_ONeil
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2006 8:59 am
- Post datetime: 2006-11-09T18:15:01+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Ok so I entered in the code and the problem I get is, how do I open and or import the .mgn file? As far as I can tell I went to MAXscript hit run and clicked on the mgn script I entered, I get no messages or success or failure, so I try to open the file and go to "All files" and click the file to open but 3ds max says it can't open it, and when I try to import it says improper format. I'd appreciate any and all help, thanks.
## Post #10
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T00:35:01+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

... What version of MAX are you using?
## Post #11
- Username: General_ONeil
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2006 8:59 am
- Post datetime: 2006-11-11T00:52:41+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

3ds Max 9
## Post #12
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T02:06:11+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Works in 8, wouldn't surprise me if Autodesk b0rked everything again like they did with 6... Oh well.
## Post #13
- Username: General_ONeil
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2006 8:59 am
- Post datetime: 2006-11-11T08:34:20+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

Alright I'll get 8, and this Script doesn't do animation right? just the actual "picture"?
## Post #14
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-11T08:54:05+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

No, bones aren't supported I believe. Just the model is imported.
## Post #15
- Username: Intoxicated
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 13, 2006 1:12 am
- Post datetime: 2006-11-12T17:14:54+00:00
- Post Title: Star Wars Galaxies .MGN format (not the same as .MSH)

hello i'm a swg modder but i have no knowledge of such scripts. Anyone want to tell me how to use/install the one posted?

EDIT: or can someone just post the plug-in they created with the script?

EDIT #2: i noticed someone posted something about Autodesk. Does this mean the plug-in will work with Maya as well?
## Post #16
- Username: General_ONeil
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2006 8:59 am
- Post datetime: 2006-11-12T18:51:25+00:00
- Post Title: 

Ya I got Maya PE as well but haven't found anything in the program to actually create the script
## Post #17
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2006-11-13T20:22:13+00:00
- Post Title: 

Makes sense though, with the Alias/Autodesk merger I'd assume they'd port features...

Anyhow just drop that script in your 3dsmax/scripts folder, and then go to the little hammer tab on your right, (default layout) hit the little 'MAXScript' thingy and then click 'Run Script" in the rollout that appears. Then just open your saved file and you're good to go.
## Post #18
- Username: General_ONeil
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2006 8:59 am
- Post datetime: 2006-11-14T03:07:18+00:00
- Post Title: 

ok, I get some weird errors, i'll look into them, but is there any place you can upload the file somewhere so thsi forum doesn't mess it up? Thanks a bunch by the way


EDIT: Errors are "pos before norm is 6078" "pos before head reading is 51144" Then it opens the script and shows the code "mdx.pos+= (str)" and says "--Incompatible types: 51152, and undefinded"

EDIT2: I get the same thing on Max 8

EDIT3: Ok i'm at my school trying this on Max 9 again, and now I get these errors: "pos before norm is 3547" "pos before head reading is 30176" "pos of form is 95052" "--No""+"" function for undefined" *shows this one while highlighting "mdx.pos+= (str + 6)" Btw I officially hate MaxScript now, lol, looks alot like JScript but of course it has it's differences.
## Post #19
- Username: OneOneSeven
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Jul 16, 2006 1:54 pm
- Post datetime: 2007-01-11T22:02:49+00:00
- Post Title: 

'Twas a bit of a while after these were posted, but FYI max 9 doesn't work with a lot of stuff, including many plugins.
## Post #20
- Username: Jaret
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 14, 2007 8:57 pm
- Post datetime: 2007-02-15T07:07:36+00:00
- Post Title: 

I had to reinstall WinXP to be able to install MAX8 but I finaly did and the script doesn't work 
If anyone is still active would you please give me a little help to open one of the character meshes from SW Galaxies.
I already have the MGH models and the textures in BMP. I just need to know how to run the script properly.
Thanks!!!
## Post #21
- Username: crazyjayloc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2007 3:34 pm
- Post datetime: 2007-05-10T07:25:13+00:00
- Post Title: 

heres the script with smileys disabled, hope it works, if not then could you repost the script with smileys deactivated nicloi_s?

> Reply from nicoli_s
>
> utility swgmgntest "SWG MGN Importer"
(
	----------
	-- Vars --
	----------
	local modelName

	local impTypes

	local seqs			-- Sequences
	local mtls			-- Materials
	local geos			-- Geometry
	local objs			-- Bones, Helpers, Lights, Attachments
	local pivot

	local geobones

	local notes			-- Note Track

	local meshes = #()
	----------------
	-- Structures --
	----------------
	struct File
	(
		pos, end, bstream,

		-- Helper function to init the top-level chunk rover
		fn Init stream=
		(
			bstream = stream
			pos = ftell bstream
			fseek bstream 0 #seek_end
			end = ftell bstream
		),

		fn fReadHead=
		(
			fseek bstream pos #seek_set
			local id = ReadLong bstream #unsigned
			local tag = File.GetName id
			pos += 4
			tag
		),

		fn fReadFloat=
		(
			local id
			local i = 0
			while (id == undefined) and (i < 10) do
			(
				fseek bstream pos #seek_set
				id = ReadFloat bstream
				i += 1
			)
			if i == 10 then
			(
				print ("problem: " + (pos as string))
			)
			pos += 4
			id
		),

		fn fReadLong=
		(
			fseek bstream pos #seek_set
			local id = ReadLong bstream
			pos += 4
			id
		),

		fn fReadShort=
		(
			fseek bstream pos #seek_set
			local id = ReadShort bstream #unsigned
			pos += 2
			id
		),

		fn fReadByte=
		(
			fseek bstream pos #seek_set
			local id = ReadByte bstream
			pos += 1
			id
		),

		fn fReadString n=
		(
			fseek bstream pos #seek_set
			local id = ReadString bstream
			pos += n*80
			id
		),
		fn GetName id=
		(
			case id of
			(
				0x33544F44: #DOT3
				0x4C54494F: #OITL
				0x20435A4F: #OZC
				0x4C434456: #VDCL
				--UNKNOWN
				default: #UNKNOWN
 			)
		)

	)
	fn sflip numb =
	(
		local bits = #()
		local n
		for n = 1 to n = 16 do
		(
			bits[n] = bit.get numb n
		)
		for n = 1 to n = 8 do
		(
			numb = bit.set numb n bits[(n+8)]
		) 		for n = 9 to n = 16 do
		(
			numb = bit.set numb n bits[(n-8)]
		) 		return numb
	)
	fn lflip numb =
	(
 		local bits = #()
		local n
		for n = 1 to n = 32 do
		(
			bits[n] = bit.get numb n
		)
		for n = 1 to n = 8 do
		(
			numb = bit.set numb n bits[(24+n)]
		) 		
		for n = 9 to n = 16 do
		(
			numb = bit.set numb n bits[(8+n)]
		) 	
		for n = 17 to n = 24 do
		(
			numb = bit.set numb n bits[(n-8)]
		) 		
		for n = 25 to n = 32 do
		(
			numb = bit.set numb n bits[(n-24)]
		) 		
		return numb
	)	


	--------------------
	-- User Interface --
	--------------------
	group "Import MSH"
	(
		button importButton "Import MGN..."
	)

	--------------------------
	-- Main Import Function --
	--------------------------

	on importButton pressed do
	(
		-- Show open file dialog box
		local objFileName = getOpenFileName caption:"Import MGN" types:"SWG model File (*.mgn)|*.mgn|All Files (*.*)|*.*|"


		local isValid = true
		if objFileName != undefined then
		(
			-- If user made a selection, begin importing
			if doesFileExist objFileName then
			(
				-- Open up the file as a binary stream
				local bstream = fopen objFileName "rb"			
				local mdx = File()
				local refx 
				local refy 
				local refz 
				local verts = #()
				local test = #()
				local faces = #()
				local normals = #()
				mdx.Init bstream
				mdx.pos = 44
				local nbones = mdx.fReadLong()
				local nverts = mdx.fReadLong()
				local nweights = mdx.fReadLong()
				local nnormals = mdx.fReadLong()
				mdx.pos = 60
				local nummesh = mdx.fReadLong()
				mdx.pos = 83
				local str = mdx.fReadByte()
				--messagebox ("str length is " + (str as string))
				mdx.pos += (str + 6)
				--messagebox ("reading nverts at " + (mdx.pos as string))				
				local tests = mdx.fReadShort()
				--messagebox ("tests before flip is " + (tests as string))
				tests = sflip tests
				mdx.pos += (8 + tests)
				--messagebox ("reading verts at " + (mdx.pos as string))					
				for n = 1 to n = nverts do
				(
					x = mdx.fReadFloat()
					y = mdx.fReadFloat()
					z = mdx.fReadFloat()
					verts[n] = point3 x z y
				)
				mdx.pos += 6 				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len + 6)
				--messagebox ("pos before twit is " + (mdx.pos as string))					
				--twdt
				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len + 6)
				messagebox ("pos before norm is " + (mdx.pos as string))		
				--norm 				local len = mdx.fReadShort()
				len = sflip len
				mdx.pos += (len)
				messagebox ("pos before head reading is " + (mdx.pos as string))
				local head = mdx.fReadHead()

				if (head == #DOT3) then (	
					mdx.pos += 2		
					--dot3
					local len = mdx.fReadShort()
					len = sflip len
					mdx.pos += (len)
				) else (
					mdx.pos -= 4
				)

				mdx.pos += 7
				str = mdx.fReadByte()
				mdx.pos += (str)
				local type
				if mdx.fReadHead() == #OZC then
				(
					type = true
				) else (
					type = false
				)
				mdx.pos += 2
				local j = mdx.fReadShort()
				j = sflip j
				mdx.pos += j

				for w = 1 to w = nummesh do
				(
					messagebox ("pos of form is " + (mdx.pos as string))
					mdx.pos += 19					
					str = mdx.fReadByte()
					mdx.pos += (str + 6)
					local jump = mdx.fReadShort()
					jump = sflip jump
					jump += mdx.pos
					local size = mdx.fReadLong()
					local ppoints = #()
					for n = 1 to n = size do
					(
						x = mdx.fReadLong()					
						ppoints[n] = (x + 1)
					)		
					mdx.pos = (jump + 6)
					--NIDX
					messagebox ("pos of NIDX is " + (mdx.pos as string))				
					jump = mdx.fReadShort()
					jump = sflip jump				
					mdx.pos += (jump)
					local header = mdx.fReadHead()
					if ((header == #DOT3) or (header == #VDCL)) then
					(
						mdx.pos += 2
						--DOT3
						messagebox ("pos of dot3 is " + (mdx.pos as string))					
						jump = mdx.fReadShort()
						jump = sflip jump				
						mdx.pos += (jump + 6)
					) else (
						mdx.pos += 2
					)
					--TXCI
					messagebox ("TXCI pos is " + (mdx.pos as string))					
					jump = mdx.fReadShort()
					jump = sflip jump				
					mdx.pos += (jump + 18)
					--FORM
					messagebox ("FORM pos is " + (mdx.pos as string))					
					jump = mdx.fReadShort()
					jump = sflip jump
					local tverts = #()
					for m = 1 to m = (jump / 8) do
					(
						x = mdx.fReadFloat()
						y = mdx.fReadFloat()
						tverts[m] = point3 x (1-y) 0
					)
					mdx.pos += 24				
					messagebox ("pos of face is " + (mdx.pos as string))
					local fc					
					--face block

					mdx.pos += 6
					jump = mdx.fReadShort()	
					jump = sflip jump
					local jump2 = jump
					jump += mdx.pos
					fc = mdx.fReadLong()
					messagebox ("nfaces: " + (fc as string))												
					for n = 1 to n = fc do
					(
						if (((fc * 14) + 4) <= jump2) then (mdx.pos += 2)
						x = mdx.fReadLong()
						y = mdx.fReadLong()
						z = mdx.fReadLong()
						--messagebox ("x is " + (x as string) + " y is " + (y as string) + " z is " + (z as string))
						faces[n] = point3 ppoints[(x+1)] ppoints[(y+1)] ppoints[(z+1)]
					)
					mdx.pos = jump
					test[w] = mesh numverts: nverts numfaces: fc
					for b = 1 to b = nverts do
					(
						test[w].vertices = verts
					)
					for b = 1 to b = fc do
					(
						test[w].faces = faces
					)
					setNumTVerts test[w] nverts		
					for k = 1 to k = tverts.count do
					(
						setTVert test[w] ppoints[k] tverts[k]
					)
					buildTVFaces test[w]

					for k = 1 to test[w].numfaces do
					(
						setTVFace test[w] k faces[k]
					)
					for k = 1 to k = tverts.count do
					(
						setTVert test[w] ppoints[k] tverts[k]
					)				
				)	
			) 		)
	)
)

--getNodeByName <string> exact:<boolean>


well aparently the script is working but not in 3ds max 9, and i have the same kind of error, it says its not a valid file format

so i guess its back to the drawing board for a working importer script for those of us using 3ds max 9

or is it possible that it might work with gmax? just curious...
## Post #22
- Username: Jaret
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 14, 2007 8:57 pm
- Post datetime: 2007-05-10T11:33:18+00:00
- Post Title: 

I tried it again in 3DS MAX 8 and 7, and it still doesn't work.
## Post #23
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-14T21:33:06+00:00
- Post Title: 

I am bored today, so looked at the mgn file format. It's petty easy. And I  wrote this maxscript to import MGN files. It should work in GMax. 

I didn't looked at nicoli_s's maxscript, just build it form ground. So test it to see if it helps?
## Post #24
- Username: Jaret
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Feb 14, 2007 8:57 pm
- Post datetime: 2007-05-15T13:06:40+00:00
- Post Title: 

I just tried it and it works perfectly!

I want to express my great appretiation and gratitute to fatduck  

I promise to use this new power only for good
## Post #25
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-05-15T17:00:54+00:00
- Post Title: 

Good to see people like it!
So I spent another hour to make this maxscript support msh as well. 

Enjoy.
[SWG_model_importer(100607).zip](https://xentaxbackup.github.io/file/1203_SWG_model_importer(100607).zip)
## Post #26
- Username: Ghostrider
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 01, 2007 4:09 am
- Post datetime: 2007-06-08T08:21:22+00:00
- Post Title: 

Fatduck, I like to say your effort is greatly appreciated.    Many of the SWG models can be used to greatly enhance the Jedi Academy and Battlefront games. The ATAT & ATST models alone can make a huge difference. See below: 




However, I have encountered a problem with the script. It seems any interior model files, whether it be an interior of a building or a cockpit, the UV won’t display correctly. Sometimes the interior files will crash the script outright. There is screenshot of what an interior model looks like if it imports below.



If you like to take look, I have attached a zip file containing the error message Max gave me when the script crashed, the model that crashed it, a cockpit file, and a file that the script works perfectly with.
[MsScript error.zip](https://xentaxbackup.github.io/file/1198_MsScript error.zip)
## Post #27
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-08T13:50:37+00:00
- Post Title: 

Ghostrider, your zip file seems have problem! I can't open the files inside the "Script error" folder!?

Please re-upload it and I'll check to see if any problem!
## Post #28
- Username: Ghostrider
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 01, 2007 4:09 am
- Post datetime: 2007-06-08T21:06:57+00:00
- Post Title: 

Sorry about that. I have attached a new one. If you still have trouble with this zip file should I use winrar instead?
[MsScript error2.zip](https://xentaxbackup.github.io/file/1199_MsScript error2.zip)
## Post #29
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-09T11:02:45+00:00
- Post Title: 

OK, the crash problem should be fixed!
But I'm not sure if the UV will correct form file to file!? Since it use some kind of FVF to store "Vertex Element", so the position of UV data might be different. 

These happened because the version of the .msh/.mgn  updated!

Go back to the above post to download the latest maxscript.
## Post #30
- Username: Ghostrider
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 01, 2007 4:09 am
- Post datetime: 2007-06-10T17:35:54+00:00
- Post Title: 

Fatduck, when I first ran your script it would only import the mgn files and whenever I tried to import a msh file it would crash and give me this in listener:

> -- Error occurred in i loop; filename: D:\3dsMax8\Scripts\SoulburnScripts\SWG_model_importer.ms; position: 4105
>
> --  Frame:
>
> --   mm1: undefined
>
> --   boundary: undefined
>
> --   f1: 40
>
> --   f2: undefined
>
> --   i: 1
>
> --   f3: undefined
>
> --   called in readINDX(); filename: D:\3dsMax8\Scripts\SoulburnScripts\SWG_model_importer.ms; position: 4304
>
> --  Frame:
>
> --   sizeElement: 4
>
> --   FCary: #()
>
> --   datasize: 532
>
> --   numIndex: 132
>
> --   f: <BinStream:C:\Temp\NOLF Files\MsScript error\thm_nboo_thed_emp_retreat_r11_mesh_r11.msh>
>
> --   called in impMGN.pressed(); filename: D:\3dsMax8\Scripts\SoulburnScripts\SWG_model_importer.ms; position: 5435
>
> --  Frame:

So I decided to delete these lines (;mm1=boundary mm1 f1) from your script then it started working perfectly. 

All of the files would import and vast majority of the time the UV data would load correctly as well, when the UV data didn’t load it was always a floor or a wall which are easy to fix. So you might want to update your script. Again great work and thank you for your effort, it's very much appreciated.
## Post #31
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-06-10T21:46:38+00:00
- Post Title: 

Thank you for letting me know about that!

Those lines are just for my own debug function, and yes, deleted them will be fine! I had upload the correct one above.
## Post #32
- Username: Ghostrider
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue May 01, 2007 4:09 am
- Post datetime: 2007-06-11T20:17:35+00:00
- Post Title: 

Thank you!
## Post #33
- Username: ThearinKalan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 16, 2007 10:49 am
- Post datetime: 2007-07-16T10:49:24+00:00
- Post Title: 

Very nice work fatduck!

Is it possible to get an exporter script for gmax? Maybe just the known parts DATA/INDX that contain the real data so the rest can be hexed together.
[star_destroyer_2005e3_r53_commandeck_mesh_r53.rar](https://xentaxbackup.github.io/file/1270_star_destroyer_2005e3_r53_commandeck_mesh_r53.rar)
## Post #34
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2007-07-20T09:15:33+00:00
- Post Title: 

exporting the DATA/INDX are easy. But Gmax didn't support binary export (even dump to listener). It is impossible to write an exporter for that!
## Post #35
- Username: ThearinKalan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 16, 2007 10:49 am
- Post datetime: 2007-07-21T03:17:22+00:00
- Post Title: 

Gna. Do you have any other ideas? We have (including your gmax script) three programs that import msh but none of them exports. It's the biggest limiting issue for modders.   

Is there another commercial/non-commercial tool around that allows exporter scripts?

My highest priority concerning mods is changing the local position of the entire object. I think this implies that all vertices have to be altered right?
## Post #36
- Username: crazyjayloc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 09, 2007 3:34 pm
- Post datetime: 2007-11-19T01:57:44+00:00
- Post Title: 

well there is an exporter out there, but im not sure if it supports the latest version of 3DS max or not, i used fatduck's script on my version of max (9) and it imports really nicely, the models however need to be assembled properly and there are no bones, 

something else i did notice is that the higher the number at the end of the msh or mgn file (ie, 10, 11, 12, 13) it will indicate lower polys, probably to give the effect of distant objects and decrease rendering down to something easier for those distant objects, so the lower the number, the higher the detail

you can also use the size changer and make a model import to 100 scale, but that is hell even on my system, so i would recommend no larger than 50 scale

nice work fatduck! i have been gone for a long time, but since im back to model building and modding again, i decided to check out the thread and see what happened since i left many eons ago LOL, looks like some things got ironed out! 

btw, i was wondering if anyone knew where the ships for the game were located, so far i have only been able to locate the tie bomber and the tie, nothing else seems to be obvious enough to extract, then again i could have a much older version of SGW to play with cause i never did get into the whole NGE version
## Post #37
- Username: borillionstar
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 13, 2009 3:20 am
- Post datetime: 2009-01-12T21:27:15+00:00
- Post Title: 

I dunno if this thread is still good or not,

I had some questions about moving the meshes from SWG to Battlefront!
How did you re-apply the textures to the meshes you got out of galaxies and into 3D MAX? 
Also about the skeletons how are you opening or changing them for use in BF?
