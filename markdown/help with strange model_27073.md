## Post #1
- Username: reggin2023
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 07, 2023 1:49 pm
- Post datetime: 2023-08-07T07:12:00+00:00
- Post Title: help with strange model

i tried to parse the 3d model file and i was able to decipher the pattern, but i can't get the correct point cloud. I need your help.
thank you in advance

```
while num_submesh
    int vnum?
    int vnum?
unk 60 bytes (36unk,24zero)
while num_submesh
    int zero
    matrix44 (64bytes)
    4 short unks
     data 96bytes per vertex

```


[files.zip](https://xentaxbackup.github.io/file/24198_files.zip)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2023-08-07T09:13:50+00:00
- Post Title: help with strange model

instead of the buffer containing a repeating collection of floats in the form of {X, Y, Z} its {{X1, X2, X3}, {Z1, Z2, Z3}, {Y1, Y2, Y3}} where 1,2,3 denotes a point on the triangle




MaxScript for reference:

```
	written by mariokart64n, august 07 2023
*/
gc()
clearListener()
try(destroyDialog imp_dat)catch(imp_dat)
rollout imp_dat "Import DAT" (
	
	struct fmtDAT_Mesh (
		/*float[20]*/unk002 = #(
			#(0.0, 0.0, 0.0, 0.0, 0.0),
			#(0.0, 0.0, 0.0, 0.0, 0.0),
			#(0.0, 0.0, 0.0, 0.0, 0.0),
			#(0.0, 0.0, 0.0, 0.0, 0.0)
			),
		/*uint16_t[4]*/unk003 = #(0, 0, 0, 0),
		/*float[]*/vertex_x = #(),
		/*float[]*/vertex_z = #(),
		/*float[]*/vertex_y = #(),
		/*float[]*/normal_x = #(),
		/*float[]*/normal_z = #(),
		/*float[]*/normal_y = #(),
		/*float[]*/tvertex_x = #(),
		/*float[]*/tvertex_z = #(),
		/*float[]*/tvertex_y = #(),
		fn build = (
			local vertArray = #()
			local tvertArray = #()
			local normArray = #()
			local faceArray = #()
			local i = 1, j = 1
			for i = 1 to vertex_x.count do (
				for j = 1 to 3 do (
					append vertArray [vertex_x[i][j], -vertex_y[i][j], vertex_z[i][j]]
					)
				append faceArray ([1, 2, 3] + ((i - 1) * 3))
				)
			
			for i = 1 to normal_x.count do (
				for j = 1 to 3 do (
					append normArray [normal_x[i][j], -normal_y[i][j], normal_z[i][j]]
					)
				)
			
			for i = 1 to tvertex_x.count do (
				for j = 1 to 3 do (
					append tvertArray [tvertex_x[i][j], -tvertex_y[i][j], tvertex_z[i][j]]
					)
				)
			
			
			local msh = mesh vertices:vertArray faces:faceArray tverts:tvertArray
			buildTVFaces msh
			for i = 1 to faceArray.count do (setTVFace msh i faceArray[i])
			msh.backfacecull = on
			msh.displayByLayer = false
			msh.wirecolor = random (color 0 0 0) (color 255 255 255)
			--for i = 1 to msh.numfaces do setFaceSmoothGroup msh i 1
			select msh
			modPanel.addModToSelection (Vertex_Weld threshold:0.001) ui:off
			modPanel.addModToSelection (smooth smoothingBits:1) ui:off
			modPanel.addModToSelection (Normalmodifier flip:off unify:on) ui:off
			msh
			),
		fn read &f &vertex_count &normal_count = (
			unk002 = #(
				#(readfloat f, readfloat f, readfloat f, readfloat f, readfloat f),
				#(readfloat f, readfloat f, readfloat f, readfloat f, readfloat f),
				#(readfloat f, readfloat f, readfloat f, readfloat f, readfloat f)
				)
			readFloat f
			readFloat f
			unk003 = #(readShort f, readShort f, readShort f, readShort f)
			vertex_x = #()
			for i = 1 to vertex_count do (
				append vertex_x [readFloat f, readFloat f, readFloat f]
				)
			vertex_z = #()
			for i = 1 to vertex_count do (
				append vertex_z [readFloat f, readFloat f, readFloat f]
				)
			vertex_y = #()
			for i = 1 to vertex_count do (
				append vertex_y [readFloat f, readFloat f, readFloat f]
				)
			normal_x = #()
			for i = 1 to vertex_count do (
				append normal_x [readFloat f, readFloat f, readFloat f]
				)
			normal_z = #()
			for i = 1 to normal_count do (
				append normal_z [readFloat f, readFloat f, readFloat f]
				)
			normal_y = #()
			for i = 1 to normal_count do (
				append normal_y [readFloat f, readFloat f, readFloat f]
				)
			tvertex_x = #()
			for i = 1 to normal_count do (
				append tvertex_x [readFloat f, readFloat f, 0.0]
				)
			tvertex_z = #()
			for i = 1 to vertex_count do (
				append tvertex_z [readFloat f, readFloat f, 0.0]
				)
			tvertex_y = #()
			for i = 1 to vertex_count do (
				append tvertex_y [readFloat f, readFloat f, 0.0]
				)
			)
		)
	
	struct fmtDAT_Info (
		/*uint32_t*/vertex_count = 0,
		/*uint32_t*/normal_count = 0,
		fn read &f = (
			vertex_count = readLong f #unsigned
			normal_count = readLong f #unsigned
			)
		)
	
	struct fmtDAT (
		/*uint32_t*/count = 0,
		/*uint32_t[]*/info = #(),
		/*float[12]*/unk001 = #([0.0, 0.0, 0.0], [0.0, 0.0, 0.0], [0.0, 0.0, 0.0]),
		/*fmtDAT_Mesh[]*/meshes = #(),
		fn read &f = (
			local i = 1
			count = readLong f #unsigned
			info = #()
			if count > 0 do (
				info[count] = fmtDAT_Info()
				for i = 1 to count do (
					info[i] = fmtDAT_Info()
					info[i].read(f)
					)
				)
			unk001 = #(
				[readfloat f, readfloat f, readfloat f], 
				[readfloat f, readfloat f, readfloat f], 
				[readfloat f, readfloat f, readfloat f], 
				[readfloat f, readfloat f, readfloat f], 
				[readfloat f, readfloat f, readfloat f]
				)
			meshes = #()
			if count > 0 do (
				meshes[count] = fmtDAT_Mesh()
				for i = 1 to count do (
					meshes[i] = fmtDAT_Mesh()
					meshes[i].read f info[i].vertex_count info[i].normal_count
					meshes[i].build()
					)
				)
			)
		)
	
	fn open file = (
		local f = try(fopen file "rb")catch(undefined)
		if f != undefined do (
			local dat = fmtDAT()
			delete $*
			dat.read(f)
			fclose f
			)
		)

	)
--createDialog imp_dat

imp_dat.open(
	GetOpenFileName caption:"Open Dat File" types: "dat (*.dat)|*.dat|All Files (*.*)|*.*|"
	)

```
