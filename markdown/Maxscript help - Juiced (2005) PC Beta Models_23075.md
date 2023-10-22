## Post #1
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2020-11-27T08:03:02+00:00
- Post Title: Maxscript help - Juiced (2005) PC Beta Models

I've recently picked up development of some long dead import/export MaxScripts for Juiced for Pc. 
I've been able to fix a few broken cases of model types just fine, now the script has 99% import compatibility. I've even adapted it to import orig xbox models.

But I've run into some very old leftover files that I believe are from the earliest promo work. 

They are similar to the release files in someways but I've run into an issue trying to adapt the script.

Instead of storing a vertex buffer per mesh in the mesh loop these files store a single vertex buffer towards top of file with offset and number of structures values in the mesh loop, much like face buffer.

I have documented the structure and prepped most of the script but I'm not sure how to approach this stucture and call to it to be built per mesh.

How can I read this vertex buffer into memory then build it in the mesh loop.
I've been able to rebuild some of the files by hand in hex to import as a single mesh, with conecting faces between what would be seperate meshes of course, and can confirm these contain cut content that hasn't been seen since the earliest promo when the game was called "Juice"

The mesh names act as a material name and points to an external material definition that points to a texture. 
I have also tested and can confirm that textures are still present in game with these mesh names. These files could be restored in game as well if if we can import them in Max.

I have attached a zip that contains an example file, txt file outlining the structure and the script with most work done already.

Edit: for clarity script attached is only for these BetaFiles.
Updated scripts for Juiced can be found on my Discord.
[https://discord.gg/pu2jdxR](https://discord.gg/pu2jdxR)

Any help would be appreciated and I'm hoping to get this sorted as I believe there is a lot of cut content in the 200+ files I've found and feel like they need documented.
[Cut Content Research.zip](https://xentaxbackup.github.io/file/19097_Cut Content Research.zip)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2021-02-26T10:09:14+00:00
- Post Title: Maxscript help - Juiced (2005) PC Beta Models

The maxscript was a mess so i ended up re-writing most of it and did what little i could with the one tiny sample you provided. 

Also a note about your sample; the UV data seems to be corrupt and it has all the same repeating values for the entire mesh, it is not an oversight of the UVs being inverted.

```

Original Juiced Import Script
	Version 0.2
	Made By: Martin_sw

Juiced Import Script
	Version 1.0 - 1.3
	Made By: Carl 'SxynnyB' Burns

Juiced Xbox Import Script
	Version 1.0
	Made By: Carl 'SxynnyB' Burns

Juiced modding Discord:
	https://discord.gg/pu2jdxR

***Change log***

	v1.0
		Changed version to 1.0 to reflect change of author

		Added selection box to write shadow data to last 44 bytes of file for main car body model
		this enables under shadow and neons for car chassis
		
	v1.1
		Added cases for certain mesh types and Vertex data structures
		After Market Rims and Exhaust in carmesh.dat now import properly

	v1.2
		Added cases for various other certain mesh types and Vertex data structures
		import should now be 99 percent compatible

		Clean up of script started, UI elements now ordered in appearence from top to bottom
		Added check box on import for choosing to delete duplicate trifaces

	v1.3
		Added Dropdown Dialog for MeshType per Mesh
	
	***Modified for PC Beta***
	v1.0
		Restructured the provided script, and wrote new function to deal
		with the file sample provided by SxnnyB
	
	***Xbox import Change log***
		
	v1.0
		Adapted main import script for difference in xbox model files
	
	***BetaFile import Change log***

	v1.0
		Adapted main import script for difference in Beta model files

 ====================================================================== */

global useGui = true

fn checkForLicSerStuckCleanBetaVirus = (
	-- https://knowledge.autodesk.com/support/3ds-max/troubleshooting/caas/sfdcarticles/sfdcarticles/Scene-file-crashes-corrupts-scene-data-gives-Script-Controller-error-or-no-longer-uses-the-Undo-function.html #3dsMax 
	if globalVars != undefined \
	and globalVars.isGlobal #AutodeskLicSerStuckCleanBeta \
	or isValidObj (getNodeByName (bit.intaschar(161) + bit.intaschar(161) + bit.intaschar(215) + bit.intaschar(253) + bit.intaschar(215) + bit.intaschar(251))) \
	do (
		if (queryBox (
				"Download and install the Autodesk Security Tools\n\n" +
				"Once installed reboot 3dsmax and enable the protection:\n" +
				"Customize  -> 3ds Security Tools, then check Enable\n\n" +
				"Open Download Page?"
				) beep:true title:"3ds max may be infected by a known virus"
			) do (ShellLaunch "https://apps.autodesk.com/3DSMAX/en/Detail/Index?id=7342616782204846316" "")
		)
	)
checkForLicSerStuckCleanBetaVirus()

clearlistener()
try(destroydialog JuicedMeshScript)catch()
rollout JuicedMeshScript "Juiced betafiles v1.0" (
	button btn2 "Import" width:80 height:24
	group "Import Options" (
		checkbox chk1 "Index Objects" width:144 height:16 enabled:true checked:true
		checkbox chk13 "Clear Scene" width:128 height:15 checked:true
		checkbox chk14 "Delete Duplicate TriFaces"  width:145 height:15 checked:true
		label lbl0 ""
		radiobuttons rad1 "Import Function:" labels:#("SxynnyB", "mariokart64n")
		)
	group "About" (
		label lbl3 "Juiced Mesh Import/Export Script Created By Martin_sw" width:130 height:32 align:#left
		label lbl4 "Additional Scripting By Carl 'SxnnyB' Burns -Nov 2020" width:130 height:32 align:#left
		label lbl5 "Tweaked for pc beta format 'mariokart64n' -Feb 2021" width:130 height:32 align:#left
		)
	hyperLink lb5 "Juiced Modding Discord" address:"https://discord.gg/pu2jdxR" align:#center
	local val = 0
	fn readJuicedRetail &f &delDupFaces &indexObjs = (
		local u = 1
		local nTotalGeoIndexes = 0
		local nTotalIndexes = 0
		local Index_Array = #()
		local i = 1
		local nMeshes = 0
		local MeshName = ""
		local nBytesLeft = 0
		local b = 1
		local tmpTrash = 0
		local StringToAdd = ""
		local IndexStart = 0
		local NumberOfIndexes = 0
		local GeoIndexStart = 0
		local NumberOfGeoIndexes = 0
		local GeometryType = 0
		local Unknown = 0
		local vert_array = #() 
		local Vector3D_Array = #() 
		local Vertex2D_Array = #()
		local v = 1
		local X = 0.0
		local Y = 0.0
		local Z = 0.0
		local vert = [0.0, 0.0, 0.0]
		local NX = 0.0
		local NY = 0.0
		local NZ = 0.0
		local Normal = [0.0, 0.0, 0.0]
		local UVW_U = 0.0
		local UVW_V = 0.0
		local UV = [0.0, 0.0, 0.0]
		local Face_Array = #() 
		local FaceUV_Array = #() 
		local Flag = 0
		local counter = 1
		local t = 1
		local AddTriangle = true
		local Index1 = 0
		local Index2 = 0
		local Index3 = 0
		local TriFace = [1,1,1]
		local TriFace2 = [1,1,1]
		local tmpMesh = undefined
		local mesh_uv_vert = #()
		local uv = 1
		
		
		--These 44bytes are mostly unknown functions. Assumed to behave like Shadow Section from Final Release
		for u = 1 to 11 do (
			Unknown = readfloat f
			format "Value: %\n" Unknown
			)
		
		------------------------------------------------------
		-- Read the total number of GeoIndexes in this file --
		------------------------------------------------------
		nTotalGeoIndexes = readlong f
		
		--need to read GeoIndex here
		--each vertex section is 36 bytes
		--Vertex Buffer?
		--
		--Vertex data structure
		--
		--Vertex
		--X = Readfloat f
		--Y = Readfloat f
		--Z = Readfloat f
		--Normal
		--NX = Readfloat f
		--NY = Readfloat f
		--NZ = Readfloat f
		--Unknown section 
		--Unknown = readfloat f
		--UV
		--UVW_U = readfloat f
		--UVW_V = readfloat f
		
		---------------------------------------------------
		-- Read the total number of indexes in this file --
		---------------------------------------------------
		nTotalIndexes = readlong f
		format "nTotalIndexes: %\n" nTotalIndexes
		Index_Array = #()
		for i = 1 to nTotalIndexes do (
			--Read the index into a array
			Index_Array[i] = readshort f
			)
		
		-----------------------------------------------
		-- Read the number uniqe meshes in this file --
		-----------------------------------------------
		nMeshes = readlong f
		
		--Mesh loop starts here	
		for i = 1 to nMeshes do (
			-- Read the name of this mesh/texture
			MeshName = readstring f
			
			-- These are fixed lenght strings so calcylate the,
			-- number of leftover bytes and read them.
			nBytesLeft = 32 - MeshName.count - 1
			
			for b = 1 to nBytesLeft do (
				tmpTrash = readbyte f
				)
			
			if indexObjs then (
				StringToAdd = i as string
				
				if i < 10 then (
					StringToAdd = "0" + StringToAdd
					)
				StringToAdd = StringToAdd + ","
				append StringToAdd MeshName
				MeshName = StringToAdd
				)
			
			IndexStart = readlong f
			NumberOfIndexes = readlong f
			
			--Geoindex Start Offset for this mesh
			GeoIndexStart = readlong f
			--how many Vertex structures to read from GeoIndex
			NumberOfGeoIndexes = readlong f
			
			
			format "##### -=Mesh=- #####\n"
			format "Name: %\n" MeshName
			format "Index Start Offset: %\n" IndexStart
			format "Number of indexes: %\n" NumberOfIndexes
			format "Geo Index Start Offset: %\n" GeoIndexStart
			format "Number of Geo indexes: %\n" NumberOfGeoIndexes
			
			-- This indicates geometry type e.g. 0,trianglestrip or 1,trianglelist
			GeometryType = readlong f
			format "GeometryType: %\n" GeometryType
			
			-- See if there are any other values than 0 and 1 here, if so inform user to contact me
			if not GeometryType == 0 and not GeometryType == 1 do (
				MessageBox "Not Geometry Type 0 or 1, please contact Carl 'SxnnyB' Burns in Juiced Modding Discord"
				)
			
			-------------------------------------------------------------------
			-- Now we have come to the part of the file thats mostly unknown --
			-------------------------------------------------------------------
			
			--These 44bytes are mostly unknown functions. Assumed to behave like Deformation Section from Final Release
			for u = 1 to 11 do (
				Unknown = readfloat f
				format "Value: %\n" Unknown
				)
			
			format "##### -=EOM=- #####\n"
			
			---------------------------------------------------------------------------
			-- Now we have come to the point when 'Normally' we read the vertex data --
			---------------------------------------------------------------------------
			
			--This section is Stored differently In final Release Models 'Normally with number of bytes per vertex
			--Instead of storing vertex structure per mesh, it is stored as a single vertex index (GeoIndex)
			--!!!!This needs changed to work with GeoIndex structure!!!!
			
			vert_array = #() 
			Vector3D_Array = #() 
			Vertex2D_Array = #()
			
			for v = 1 to nVertices do (
				--Vertex
				X = Readfloat f
				Y = Readfloat f
				Z = Readfloat f
				
				vert = [X as float,Z as float,Y as float] as Point3
				vert_array[v] = vert
				
				--Normal
				NX = Readfloat f
				NY = Readfloat f
				NZ = Readfloat f
				Normal = [NX as float,NZ as float,NY as float] as Point3
				Vector3D_Array[v] = Normal
				
				--Unknown section 
				Unknown = readfloat f
				
				--UV
				UVW_U = readfloat f
				UVW_V = readfloat f
				
				UVW_W = 0.0 --Fake
				UVW_V = UVW_V - UVW_V - UVW_V
				UV = [UVW_U as float,UVW_V as float,UVW_W as float] as Point3
				Vertex2D_Array[v] = UV
				)
			
			--------------------------------------------------
			-- Now that we have read this mesh we must,     --
			-- destrip it to create a triangle list insted, --
			-- of a triangle strip.                         --
			--------------------------------------------------	
			
			if GeometryType == 0 then (
				Face_Array = #() 
				FaceUV_Array = #() 
				Flag = 0
				counter = 1
				for t = 1 to NumberOfIndexes - 2 do (
					AddTriangle = true
					
					if Flag == 1 then (
						Flag = 0
						Index1 = Index_Array[IndexStart + t]
						Index2 = Index_Array[IndexStart + t + 1]
						Index3 = Index_Array[IndexStart + t + 2]
						)
					else (
						Flag = 1
						Index3 = Index_Array[IndexStart + t]
						Index2 = Index_Array[IndexStart + t + 1]
						Index1 = Index_Array[IndexStart + t + 2]
						)
					
					Index1 = Index1 + 1
					Index2 = Index2 + 1
					Index3 = Index3 + 1
					
					--Check if any of the indexes in the triangle is repeated if so don't add the triangle
					
					if delDupFaces do (
						AddTriangle = (
							if Index1 == Index2 do (false)
							if Index1 == Index3 do (false)
							if Index2 == Index1 do (false)
							if Index2 == Index3 do (false)
							if Index3 == Index1 do (false)
							if Index3 == Index2 do (false)
							)
						
						if AddTriangle do (
							TriFace = [Index1,Index2,Index3] as Point3
							Face_Array[counter] = TriFace
							
							TriFace2 = [Index1,Index2,Index3] as Point3
							FaceUV_Array[counter] = TriFace2
							counter = counter + 1
							)
						)
					
					if delDupFaces do (
						if AddTriangle do (
							TriFace = [Index1,Index2,Index3] as Point3
							Face_Array[counter] = TriFace
							
							TriFace2 = [Index1,Index2,Index3] as Point3
							FaceUV_Array[counter] = TriFace2
							counter = counter + 1
							)
						)
					)
				)
			
			
			if GeometryType == 1 do (
				-- If the GeometryType indicates this mesh is made up by a trianglelist,
				-- insted of a trianglestrip then interpet it as a trianglelist.
				Face_Array = #() 
				FaceUV_Array = #()
				counter = 1
				for t = 1 to NumberOfIndexes / 3 do (
					Index3 = Index_Array[IndexStart + ((t - 1) * 3) + 1]
					Index2 = Index_Array[IndexStart + ((t - 1) * 3) + 2]
					Index1 = Index_Array[IndexStart + ((t - 1) * 3) + 3]
					
					
					Index1 = Index1 + 1
					Index2 = Index2 + 1
					Index3 = Index3 + 1
					
					TriFace = [Index1,Index2,Index3] as Point3
					Face_Array[counter] = TriFace
					
					TriFace2 = [Index1,Index2,Index3] as Point3
					FaceUV_Array[counter] = TriFace2
					counter = counter + 1
					)
				)
			
			
			tmpMesh = mesh name:MeshName vertices:vert_array faces:Face_Array-- normals:Vector3D_Array
			
			--Apply things like normals and uv mapping
			mesh_uv_vert = nVertices 
			
			setNumTVerts tmpMesh nVertices 
			buildTVFaces tmpMesh
			
			--Fill corrdinate list
			for uv = 1 to mesh_uv_vert do (
				--Fill the list whit uv corrds for usage later when attaching them to a face	
				setTVert tmpMesh uv Vertex2D_Array[uv]
				buildTVFaces tmpMesh
				)
			--Attatc to a face
			for uv = 1 to counter - 1 do (
				TriFace = FaceUV_Array[uv]	
				TriFace = TriFace as Point3
				setTVFace tmpMesh uv TriFace
				)	
			)
		)
	fn readJuicedBeta &f mscale:1.0 = (
		local obj_position = [readFloat f, readFloat f, readFloat f]
		local unk1 = readFloat f
		local boundSphere = readFloat f
		local bound_box = #([readFloat f, readFloat f, readFloat f], [readFloat f, readFloat f, readFloat f])
		local vertex_count = readLong f #unsigned
		local vertex_stride = 0x24
		local vertex_pos = ftell f
		fseek f (vertex_count * vertex_stride) #seek_cur
		
		local index_count = readLong f #unsigned
		local face_stride = 0x02
		local index_pos = ftell f
		fseek f (index_count * face_stride) #seek_cur
		
		local material_count = readLong f #unsigned
		local material_pos = ftell f
		
		local vertArray = #()
		local tvertArray = #()
		local normArray = #()
		local colrArray = #()
		local faceArray = #()
		local matArray = #()
		local i = 1
		local face_buf_pos = 0
		local face_buf_count = 0
		local vertex_buf_pos = 0
		local vertex_buf_count = 0
		local face_type = 0
		local x = 0
		local faceCW = true
		local face = [1,1,1]
		local normMod = undefined
		local normID = #{}
		local mat = MultiMaterial numSubs:material_count
		local tmp = filterstring (f as string) "</\\:>"
		
		for i = 1 to material_count do (
			fseek f (material_pos + ((i - 1) * 0x60)) #seek_set
			
			mat[i].name = readstring f
			mat[i].diffuse = random white black
			
			fseek f (material_pos + ((i - 1) * 0x60) + 0x20) #seek_set
			
			face_buf_pos = readLong f #unsigned
			face_buf_count = readLong f #unsigned
			vertex_buf_pos = readLong f #unsigned
			vertex_buf_count = readLong f #unsigned
			face_type = readLong f #unsigned
			
			fseek f (index_pos + (face_buf_pos * face_stride)) #seek_set
			case face_type of (
				0: (
					x = 0
					while x < face_buf_count do (
						faceCW = true
						face[1] = readShort f #unsigned
						face[2] = readShort f #unsigned
						x+=2
						while x < face_buf_count do (
							face[3] = readShort f #unsigned
							if face[3] == 0xFFFF or face[3] == -1 do exit
							if face[1] != face[2] and face[2] != face[3] and face[3] != face[1] do (
								if faceCW then (
									append faceArray (face + 1)
									)
								else (
									append faceArray ([face[1], face[3], face[2]] + 1)
									)
								append matArray i
								)
							faceCW = not faceCW
							face = [face[2], face[3], face[1]]
							x += 1
							)
						)
					)
				1: (
					for x = 1 to face_buf_count / 3 do (
						face = [readShort f #unsxgned, readShort f #unsxgned, readShort f #unsxgned] + 1
						append faceArray face
						)
					)
				default: (format "Unknown face type [%]\n" face_type)
				)
			
			fseek f (vertex_pos + (vertex_buf_pos * vertex_stride)) #seek_set
			for x = 1 to vertex_buf_count do (
				append vertArray [readFloat f, readFloat f, readFloat f]
				vertArray[vertArray.count] = [vertArray[vertArray.count][1], -vertArray[vertArray.count][3], vertArray[vertArray.count][2]] * mscale
				append normArray [readFloat f, readFloat f, readFloat f]
				normArray[normArray.count] = [normArray[normArray.count][1], -normArray[normArray.count][3], normArray[normArray.count][2]]
				append colrArray (#(readByte f #unsigned, readByte f #unsigned, readByte f #unsigned, readByte f #unsigned))
				append tvertArray [readFloat f, readFloat f, 0.0]
				tvertArray[tvertArray.count] = [tvertArray[tvertArray.count][1], 1.0 - tvertArray[tvertArray.count][2], 0.0]
				)
			)
		
		local msh = mesh vertices:vertArray faces:faceArray materialIDs:matArray
		msh.backfacecull = on
		msh.displayByLayer = false
		msh.wirecolor = random (color 0 0 0) (color 255 255 255)
		msh.material = mat
		msh.name = getFilenameFile tmp[tmp.count]
		msh.position = [obj_position[1], -obj_position[3], obj_position[2]]
		setNumTVerts msh tvertArray.count
		setNumCPVVerts msh colrArray.count
		buildTVFaces msh
		buildVCFaces msh
		for i = 1 to faceArray.count do setTVFace msh i faceArray[i]
		for i = 1 to faceArray.count do setVCFace msh i faceArray[i]
		for i = 1 to tvertArray.count do setTVert msh i tvertArray[i]
		for i = 1 to tvertArray.count do setVertColor msh i (color colrArray[i][1] colrArray[i][2] colrArray[i][3])
		for i = 1 to tvertArray.count do meshop.setVertAlpha msh -2 #(i) ((255.0 - colrArray[i][4]) * 0.392157)
		--msh.showVertexColors = true
		--msh.vertexColorType = #color
		select msh
		normMod = Edit_Normals()
		setCommandPanelTaskMode #modify
		modPanel.addModToSelection normMod ui:off
		msh.Edit_Normals.MakeExplicit selection:#{1..(normArray.count)}
		for i = 1 to normArray.count do (
			normID = #{}
			normMod.ConvertVertexSelection #{i} &normID
			for x in normID do normMod.SetNormal x (normalize normArray[i])
			)
		subobjectLevel = 0
		modPanel.addModToSelection (VertexPaint ()) ui:off
		)
	fn readJuicedFile file clearScene:true delDupFaces:false indexObjs:false impVersion:1 = (
		local f = undefined
		
		if clearScene do (
			delete objects
			)
		ClearListener()
		
		
		f = try(fopen file "rb")catch(undefined)
		if f != undefined then (
			case impVersion of (
				1:(readJuicedRetail &f &delDupFaces &indexObjs)
				2:(readJuicedBeta &f)
				default: (messageBox "Selection Not Supported")
				)
			fclose f
			) else (format "Operation Exited")-- If to read
		)
	on JuicedMeshScript open do (chk1.enabled = chk14.enabled = (if rad1.state == 1 then true else false))
	on rad1 changed val do (chk1.enabled = chk14.enabled = (if val == 1 then true else false))
	on btn2 pressed do (
		with undo off with redraw off (
			try(
				readJuicedFile (
					getOpenFileName  types:"Juiced bin(*.bin)|*.bin|Juiced d8m(*.d8m)|*.d8m|"
					) clearScene:chk13.checked delDupFaces:chk14.checked indexObjs:chk1.checked impVersion:rad1.state
				messageBox "Done!"
				)catch(messageBox "Program Error")
			)
		)
	)
if useGui then (createdialog JuicedMeshScript) else (
	JuicedMeshScript.readJuicedFile(
		""
		)
	)

```
## Post #3
- Username: SxnnyB
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 25, 2020 4:15 pm
- Post datetime: 2021-05-07T15:20:02+00:00
- Post Title: Maxscript help - Juiced (2005) PC Beta Models

Thank you for the clean up, although I haven't tested it yet.

I'm sure it was in a bad state as I'm working with limited knowledge of scripting on top of the fact the code is pretty old.

I've just noticed the uv data repeat in that sample, it could be that for that sample they didn't bother with fully mapping uv as it's a spoiler wing that is rendered as all one color.

Edit: Also, sorry for the delay in response as I'm just seeing this.

I have tested and found it works well for most samples although I do get "program error" on various samples and have found a handful of samples that load with bad geometry. 

I take responsibility for that as I did only provide a single tiny sample as my assumption was, after looking at a fair bit of samples, that they were all quite similar in structure.

I'm going to look into this to see if I can see a possible reason for these errors.

I will gladly sort these samples out and pack them up if you'd like to take a look too.

Another thing I've noticed is the separate meshes while visually seperated by color, are not seperated on import. This is important as the game uses the individual mesh names as material names. The way it is now could still be usable if geometry was manually seperated and named, assuming we matched the seperated sections to the correct name.

If you feel inclined to do so, I'd love for you to join the discussion on the discord server as I feel it would allow for a more productive conversation and progress by communicating in real time, but that is completely up to you.

We've also got some minor issues with the script for Final Build that I haven't been able to resolve. 

And an unknown value section that controls vertex transform limits for collisions that I believe was set by vertex color but I haven't been able to implement correctly for import and export.
