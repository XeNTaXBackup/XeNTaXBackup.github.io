## Post #1
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-12-25T06:12:07+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

I'll try to make a long story short here. I'm practicing using MAXScript to import binary 3D models, and my game of choice for testing is Midtown Madness 2. [It's well documented](http://mm2kiwi.apan.is-a-geek.com/index.php?title=PKG) - no big deal, right? Actually, it is. Here's my script so far:

Code updated 12/26/12: Recursive file searching, loads shaders information, lots of cleaning up

```
types:"Midtown Madness 2 (*.pkg)|*.pkg|"

if fPKG != undefined then (
	
	f = fopen fPKG "rb"
	clearlistener()

	fn readFixedStr bstream fixedLen =
	(
		local str = ""
		for i = 1 to fixedLen do
		(
		str+= bit.intAsChar (ReadByte bstream #unsigned)
		)
		str
	)

	fn getPos name: =
	(
		if name != unsupplied  then (
			Print ((name)+": 0x"+((bit.intAsHex(ftell f))as string))
		) else (
			Print ("Current position: 0x"+((bit.intAsHex(ftell f))as string))
		)
	)

	pkgTyp=readFixedStr f 4

	-- Must be PKG3 file, otherwise terminate
	if ((pkgTyp.count != 0) and (pkgTyp == "PKG3")) then (
	   
		struct pkgDat (nSections, nVerticesTot, nIndiciesTot, nSections2, fFVF)
		struct pkgSec (nStrips, nFlags, shaderOffset)
		struct pVertex (x, y, z, nx, ny, nz, u, v)
	   
		print "Angel Studios PacKaGe File Format V3"
		messageBox ("PKG3 file ("+(fPKG)+") loaded") title:"File type"
		
		-- PKG files begin at offset 4
		fseek f 4 #seek_set
		
		-- We need to determine how many occurances of FILE there are
		-- So recursively read each FILE (this method will not work for PKG2)
		-- Ignore shaders and offset!
		
		DAVE0=true
		hitOffset=false
		parse=true
		numFiles = 0
		filePosition=0
		
		do (
			
			getPos name:"FILE"
			idf=readFixedStr f 4
			fln=ReadByte f
			fls=readFixedStr f fln
			print fls
			
			if fls == "shaders" then (
				
				print ((numFiles as string)+" Geometry files found!")
				
				print "End of geometry."
				print "-------------------------"
				
				shadersLength=ReadLong f
				shadersPosition=ftell f
				shadersOffset=shadersLength+shadersPosition
				shadersType=ReadLong f
				shadersPerPaintjob=ReadLong f
				
				DAVE0=false
				
				fseek f 0 #seek_set
				
				print ("Shaders type: "+(shadersType as string))
				print ("Shaders per paintjob: "+(shadersPerPaintjob as string))
				print "End of shaders."
				print "-------------------------"
				
			) else (
				
				numFiles += 1
				fileLength=ReadLong f
				filePosition=ftell f
					
				fileOffset=fileLength+filePosition
				fseek f 0 #seek_set
				
				fseek f fileOffset #seek_cur
				getPos name:"OFFSET"
				
			) 
				
		) while DAVE0 == true
		
if parse == true do (
	
	fseek f 4 #seek_set
	
	for q = 1 to numFiles do (
		
		idFILE=readFixedStr f 4 -- "FILE"
		fLenName=ReadByte f #unsigned
		fStrName=readFixedStr f fLenName

		fFileLen=ReadLong f

		-- PKG File Data
		dataOffset = ftell f
		Print ("pkgDAT: "+fStrName+" @ 0x"+((bit.intAsHex(dataOffset))as string))
		fData = pkgDat nSections: (ReadLong f) nVerticesTot: (ReadLong f) nIndiciesTot: (ReadLong f) nSections2: (ReadLong f) fFVF: (ReadLong f)

		for pd = 1 to fData.nSections do (

			sectionOffset = ftell f
			fSection = pkgSec nStrips: (ReadShort f #unsigned) nFlags: (ReadShort f #unsigned) shaderOffset: (ReadLong f)
		
			fseek f sectionOffset #seek_set
			Print ("pkgSEC: "+fStrName+" @ 0x"+((bit.intAsHex(sectionOffset))as string))
		
			curVerts=#()
			curFaces=#()
			curUVs=#()
				
			for s = 1 to fSection.nStrips do (
		
				fNStrips=ReadShort f #unsigned -- Number of strips in this section
				fUnkFlags=ReadShort f #unsigned -- Flags (unused in MM2)
				fToShaders=ReadLong f -- Offset to assigned shader in list
		
				-- PKG Strip
				fPrimType=ReadLong f -- Primitive type for this strip (triangle)
				fNVertices=ReadLong f
				
				-- PKG Vertex
				for  v = 1 to fNVertices do (

					vert = pVertex x: (ReadFloat f) y: (ReadFloat f) z: (ReadFloat f) nx: (ReadFloat f) ny: (ReadFloat f) nz: (ReadFloat f) u: (ReadFloat f) v: (ReadFloat f)

					append curVerts[-vert.x,vert.z,vert.y]
					append curUVs[vert.u,-vert.v,0]
					
				)
		
				fNIndicies=ReadLong f
		
				for x = 1 to fNIndicies/3 do (
					fa=ReadShort f #unsigned+1
					fb=ReadShort f #unsigned+1
					fc=ReadShort f #unsigned+1
					append curFaces[fa,fb,fc]	
				)
		
			)

			pkg = mesh vertices:curVerts faces:curFaces
			pkg.numTVerts = curUVs.count
			buildTVFaces pkg
			pkg.name=fStrName
			for j = 1 to curUVs.count do setTVert pkg j curUVs[j]
			for j = 1 to curFaces.count do setTVFace pkg j curFaces[j]

			convertTo pkg PolyMeshObject

		)
	)
	
	Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
	
)

	) else (
			clearlistener()
			messageBox "Unsupported file type, terminating!" title:"PKG Tool"
	)
	
gc()
fclose f
	
) else (
	clearlistener()
	messageBox "No file was selected." title:"PKG Tool"
)
```


It loads models perfectly:



UVs are loaded perfectly as well:



My only problem is that each time it recursively searches each "Strip" from a section, it builds an entirely separate mesh based off of the information it was given. The reason the meshes get split is because the PKG file format has to offset to an entry in a shaders list, so it splits each "strip" into a separate object based on what material is assigned to it and how it corresponds to a shader entry.

 I have tried EVERYTHING to solve this problem, but it just completely screws up the face order. Vertices are loaded, but faces are in the wrong order. If I could have it build a separate mesh each time then just attach them into one object, would the export process get screwed up? Or would I still be able to write in a [Vertex, Faces..Vertex, Faces...Vertex, Faces..] order? If that's all I have to do, great, someone please tell me!

All help is appreciated! Happy holidays and Merry christmas!
## Post #2
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-12-25T08:07:12+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

sounds like you just need to keep track of how many vertices you processed so far and add or subtract that number from the indices of the current index buffer you are processing. without looking at the data I can't tell but this problem you are describing is fairly common (needing to adjust the indices by a certain offset).

An example would help... like

PKGStrip #1 has 100 vertices and 200 indices. indices range from 0 to 99.
PKGStrip #2 has 200 vertices and 300 indices. indices range from 100 to 299.
## Post #3
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-12-25T08:47:06+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

Here's a part from the PKG file that my script is reading: [https://dl.dropbox.com/u/69162797/partial_vp4x4.pkg](https://dl.dropbox.com/u/69162797/partial_vp4x4.pkg)

You can load it with the script provided in my original post.

Immediately after the end of the partial file, another "FILE" is defined (in this case, BODY_M). I'm still fairly new to MS and I need help understanding how to keep track of vertices, faces, that kind of stuff. The only references I have is some Visual C++ code from the ZModeler 1.07 SDK, which can be very loosely translated into MaxScript, but not much.
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-12-25T09:44:15+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

that's an easy format, it's just:

vertex buffer #1 (m vertices)
index buffer #1 (ranges from 0 to m - 1)

vertex buffer #2 (n vertices)
index buffer #2 (ranges from 0 to n - 1)

etc.

you are building only one mesh object after the loop. you must either:

#1 create multiple mesh objects (one for each vertex-index buffer pair)
or
#2 in the example above, because index buffer #2 ranges from 0 to n - 1, you have to add m to each index in the index buffer.

that's why only the first mesh is coming out correctly. i would prefer #1; it's easier.

btw, you are doing nothing recursively, kind of threw me off looking at your code expecting to find something recursive where there wasn't. sorry to nitpick he he he .
## Post #5
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-12-25T10:00:40+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

It recursively searches each pkgStrip as defined in the link found in the OP. I don't think I quite get what you want me to do with the buffers, maybe a sample if possible? I'm also very tired so maybe that's why 

Script updated in original post to fix a couple things and also add an open file dialog
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2012-12-25T10:20:11+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

actually i ran your script and it seems fine, as you are doing what I mentioned in #1 already. that's just the way the data is in the game. so if i get you correctly you want to merge meshes that use the same materials so that there aren't so many mesh objects? how many textures are there per "FILE" section? if it is only one texture per "FILE" section, the problem is easy; if more than one it's a bit more complex (requires bookkeeping in multidimensional arrays lol).
## Post #7
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2012-12-25T11:51:35+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

In your example there are 7 parts. And each part contain their own Verts , faces number and Shader ID (In 3dsmax, we call it materialIDs).
so by a simple math you can add the verts and faces together and then create the final mesh at the end of prasing.

method: (remember all index here are 0 base, and max are 1 base)
total_vert  = #()
total_face = #()
total_shaderID = #()

@0x28
you have 
total_vert = 0, and 108 new_verts
total_face = 0, and 171 new_indices (57 new_faces)
total_shaderID = 0, 57 new_ID
here the offset of face index = 0, since total_vert = 0

0xF12
total_vert = 108, and 28 new_verts
total_face = 57, and 87 new_indices (29 new_faces)
total_shaderID = 57, 29 new_ID
offset of face index = 108

@0x1354
total_vert = 136, and 84 new_verts
total_face = 86, and 108 new_indices (36 new_faces)
total_shaderID = 86, 36 new_ID
offset of face index = 136

@0x1EC0
total_vert = 220, and 86 new_verts
total_face = 122, and 168 new_indices (56 new_faces)
total_shaderID = 122, 56 new_ID
offset of face index = 220

@0x2AE4
total_vert = 306, and 47 new_verts
total_face = 178, and 126 new_indices (42 new_faces)
total_shaderID = 178, 42 new_ID
offset of face index = 306

@0x31D4
total_vert = 353, and 30 new_verts
total_face = 220, and 90 new_indices (30 new_faces)
total_shaderID = 220, 30 new_ID
offset of face index = 353

@0x365C
total_vert = 383, and 128 new_verts
total_face = 250, and 228 new_indices (76 new_faces)
total_shaderID = 250, 76 new_ID
offset of face index = 383

end 
total_vert = 511
total_face = 326 (978 face indices)

now create your mesh with:
mesh vertices:total_vert faces:total_face materialIDs:total_shaderID
## Post #8
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-12-25T22:21:17+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

So I need to create a variable that starts at zero, read the data, and for each vertice/face/materialID, add 1 to the total count? I'm trying to grasp this as much as possible and I do get the idea, now I just need to express it using MAXScript. I need something that will make my pea-brain click and go "OHHH I get it now", which is how I fixed my recursive "strip" finder that wasn't working and just skipped to the end of the file. Thanks for all of the help, I very much appreciate it. How would I go about adding a count to the "totals" based on information being put forth into an array?
## Post #9
- Username: CarLuver69
- Rank: advanced
- Number of posts: 50
- Joined date: Fri Mar 09, 2012 1:17 am
- Post datetime: 2012-12-26T10:33:36+00:00
- Post Title: [MAXSCRIPT] Binary 3D model with multiple "strips"

Tomorrow I will try and focus on getting everything into one mesh using your guys' advice. I've posted my most recent code just in case it affects anything, but very slowly I'm getting the hang of it.
