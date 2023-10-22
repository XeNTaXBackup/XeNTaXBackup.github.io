## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-02T01:46:01+00:00
- Post Title: Reign of Revolution MaxScript Help

Hello guys, well today unpack files of R2 to see if the maxscript made by chroox is working or not, after checking a lot fo files, no one opened, just a few of them, so here I upload some samples and maybe somebody can take a look and edit this maxscript? really would be cool if this can be fixed, and add material assign too, ok many thanks for all and hope can fix that, thanks for support it and have a nice day.

> if (heapSize < 20000000) then
>
> 	heapSize = 200000000
>
> 
>
> fname = getOpenFileName \
>
> caption:"R2 Model File" \
>
> types:"R2 Model File(*.rmb)|*.rmb" \
>
> historyCategory:"R2 Object Presets"
>
> f = fopen fname "rb"
>
> 
>
> fn PrintOffset Var =
>
> (
>
> 	local Var = Var
>
> print ("This is the offset 0x" + (bit.intAsHex Var) as string)
>
> 	Var
>
> )
>
> fn PrintCount Var =
>
> (
>
> 	local Var = Var
>
> print ("This is the Count 0x" + (bit.intAsHex Var) as string)
>
> 	Var
>
> )
>
> 
>
> fn Readword fstream = (
>
> return readshort fstream #unsigned
>
> )
>
> 
>
> fn ReadFixedString bstream fixedLen =
>
> (
>
> 	local str = ""
>
> 	for i = 1 to fixedLen do
>
> 	(
>
> 		str += bit.intAsChar (ReadByte bstream #unsigned)
>
> 	)
>
> 	str
>
> )
>
> 
>
> struct Mesh_Info_Struct
>
> (
>
> 	name1,name2,type1,type2,type3,vertcount,facecount
>
> )
>
> struct bone_Info_Struct
>
> (
>
> 	b1,b2,b3,b4
>
> )
>
> struct weight_Info_Struct
>
> (
>
> 	w1,w2,w3,w4
>
> )
>
> struct weight_data
>
> (
>
> 	boneids,weights
>
> )
>
> 
>
> fseek f 0x14 #seek_set
>
> texture_count = readlong f
>
> mesh_count = readlong f
>
> bone_count = readlong f
>
> mesh_offset = readlong f
>
> 
>
> for a = 1 to texture_count do (
>
>    texname = readstring f
>
> 	fseek f (0x103 - texname.count)#seek_cur
>
> meditMaterials[1] = Standardmaterial ()
>
> meditMaterials[1].diffuseMap = Bitmaptexture fileName:texname
>
> 	print texname
>
> )
>
> printoffset (ftell f)
>
> Mesh_Info_Array = #()
>
> for a = 1 to mesh_count do (
>
> null1 = readlong f
>
> null2 = readlong f
>
> name1 = readstring f
>
> fseek f (0x3F - name1.count)#seek_cur
>
> name2 = readstring f
>
> fseek f (0x3F - name2.count)#seek_cur
>
> type1 = readlong f
>
> type2= readlong f
>
> type3 = readlong f
>
> vertcount = readlong f
>
> facecount = readlong f
>
> fseek f 0x4B0 #seek_cur
>
> facecount2 = readlong f
>
> fseek f 0x18C #seek_cur
>
> vertcount = readlong f
>
> fseek f 0x18C #seek_cur
>
> append Mesh_Info_Array (Mesh_Info_Struct name1:name1 name2:name2 type1:type1 type2:type2 type3:type3 vertcount:vertcount facecount:facecount)
>
> )
>
> 
>
> printoffset (ftell f)
>
> 
>
> BNArr = #()
>
> for a = 1 to bone_count do (
>
> boneID = readlong f
>
> BoneParentID = readlong f
>
> unk04 = readlong f
>
> unk05 = readlong f
>
> fseek f 0x4C #seek_cur
>
> bone_name = ReadFixedString f 0x40
>
> bone_parent_name = ReadFixedString f 0x40
>
> m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
>
> m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
>
> m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
>
> m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
>
> tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
>
> m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
>
> m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
>
> m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
>
> m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
>
> tfm2 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]	
>
> m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
>
> m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
>
> m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
>
> m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
>
> tfm3 = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]	
>
> 
>
> newBone = bonesys.createbone	\
>
> 				  tfm.row4	\
>
> 				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
>
> 				  (normalize tfm.row3)
>
> 			newBone.name = bone_name
>
> 			newBone.width  = 0.01
>
> 			newBone.height = 0.01
>
> 			newBone.transform = tfm2
>
> 			newBone.setBoneEnable false 0
>
> 			newBone.wirecolor = yellow
>
> 			newbone.showlinks = true
>
> 			newBone.pos.controller      = TCB_position ()
>
> 			newBone.rotation.controller = TCB_rotation ()
>
> 
>
>  if (BoneParentID != -1) then
>
>  newBone.parent = BNArr[BoneParentID + 1]
>
> append BNArr newBone
>
> 
>
> )
>
> printoffset (ftell f)
>
> for a = 1 to mesh_count Do (
>
> Vert_array = #()
>
> Normal_array = #()
>
> UV_array = #()
>
> Face_array = #()
>
> BonePallet_array = #()
>
> Weight_array = #()
>
> WeightID_array = #()
>
> BoneID_array = #()
>
> used_id_array = #()
>
> for b = 1 to Mesh_Info_Array[a].type3 Do (
>
> BonePallet = (readbyte f#unsigned) + 1
>
> append BonePallet_array BonePallet
>
> )
>
> 
>
> 
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> vx = readfloat f
>
> vy = readfloat f 
>
> vz = readfloat f
>
> append Vert_array [vx,vy,vz]
>
> )
>
> printoffset (ftell f)
>
> 
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> nx = readfloat f     
>
> ny = readfloat f 
>
> nz = readfloat f
>
> append Normal_array [nx,ny,nz]
>
> )
>
> printoffset (ftell f)
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> tu = readfloat f
>
> tv = readfloat f * -1
>
> append UV_array [tu,tv,0]  
>
> )
>
> printoffset (ftell f)
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> ix = readfloat f
>
> iy = readfloat f 
>
> iz = readfloat f
>
> )
>
> printoffset (ftell f)
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> ux = readfloat f 
>
> uy = readfloat f 
>
> uz = readfloat f
>
> )
>
> printoffset (ftell f)
>
> if Mesh_Info_Array[a].type1 != 0 Do (
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> w1 = readfloat f 
>
> w2 = readfloat f 
>
> w3 = readfloat f 
>
> w4 = readfloat f
>
> append WeightID_array (weight_Info_Struct w1:w1 w2:w2 w3:w3 w4:w4)
>
> )
>
> printoffset (ftell f)
>
> for a = 1 to Mesh_Info_Array[a].vertcount do (
>
> b1 = readbyte f#unsigned
>
> b2 = readbyte f#unsigned
>
> b3 = readbyte f#unsigned
>
> b4 = readbyte f#unsigned
>
> appendIfUnique used_id_array (b1 + 1)
>
> appendIfUnique used_id_array (b2 + 1)
>
> appendIfUnique used_id_array (b3 + 1)
>
> appendIfUnique used_id_array (b4 + 1)
>
> append BoneID_array (bone_Info_Struct b1:b1 b2:b2 b3:b3 b4:b4)
>
> )
>
> printoffset (ftell f)
>
> 
>
> for i = 1 to Mesh_Info_Array[a].vertcount Do (
>
> w = (weight_data boneids:#() weights:#())
>
> maxweight = 0
>
> if(WeightID_array.w1 != 0) then
>
> 	maxweight = maxweight + WeightID_array.w1
>
> if(WeightID_array.w2 != 0) then
>
> 	maxweight = maxweight + WeightID_array.w2
>
> if(WeightID_array.w3 != 0) then
>
> 	maxweight = maxweight + WeightID_array.w3
>
> if(WeightID_array.w4 != 0) then
>
> 	maxweight = maxweight + WeightID_array.w4
>
> 
>
> if(maxweight != 0) then (
>
> 		if(WeightID_array.w1 != 0) then (
>
> 			append w.boneids (BoneID_array.b1 + 1)
>
> 			append w.weights WeightID_array[i].w1
>
> 		)
>
> 		if(WeightID_array[i].w2 != 0) then (
>
> 			append w.boneids (BoneID_array[i].b2 + 1)
>
> 			append w.weights WeightID_array[i].w2
>
> 		)
>
> 		if(WeightID_array[i].w3 != 0) then (
>
> 			append w.boneids (BoneID_array[i].b3 + 1)
>
> 			append w.weights WeightID_array[i].w3
>
> 		)
>
> 		if(WeightID_array[i].w4 != 0) then (
>
> 			append w.boneids (BoneID_array[i].b4 + 1)
>
> 			append w.weights WeightID_array[i].w4
>
> 		)		
>
> 	)
>
> append Weight_array w	
>
> )
>
> 
>
> )
>
> for b = 1 to ((Mesh_Info_Array[a].facecount) / 3) Do (
>
> f1 = ((readshort f) + 1)
>
> f2 = ((readshort f) + 1)
>
> f3 = ((readshort f) + 1)
>
> append Face_array [f1,f2,f3] --save faces to Face_array	
>
> )
>
> printoffset (ftell f)
>
> print BonePallet_array
>
> msh = mesh vertices:Vert_array faces:Face_array
>
> msh.numTVerts = UV_array.count
>
> buildTVFaces msh
>
> if used_id_array.count != BonePallet_array.count Do (
>
> for c = 1 to used_id_array.count Do (
>
> appendIfUnique BonePallet_array used_id_array[c]
>
> )
>
> )
>
> if BonePallet_array.count == 0 Do (
>
> msh.transform = (getnodebyname Mesh_Info_Array[a].name2).transform
>
> append BonePallet_array ((finditem BNArr (getnodebyname Mesh_Info_Array[a].name2)))
>
> )
>
> msh.material = meditMaterials[1]
>
> msh.name = Mesh_Info_Array[a].name1
>
> for j = 1 to UV_array.count do setTVert msh j UV_array[j]
>
> for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
>
> for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
>
> if BonePallet_array.count != 0 Do (
>
> max modify mode
>
> select msh
>
> skinMod = skin ()
>
> addModifier msh skinMod
>
> for i = 1 to BonePallet_array.count do
>
> (
>
> 	maxbone = BNArr[(BonePallet_array[i])]
>
> 	if i != BonePallet_array.count then
>
> 		skinOps.addBone skinMod maxbone 0
>
> 	else
>
> 		skinOps.addBone skinMod maxbone 1
>
> )
>
> modPanel.setCurrentObject skinMod
>
> for i = 1 to Weight_array.count do
>
> (
>
> 	w = Weight_array[i]
>
> 	bi = #()
>
> 	wv = #()
>
> 	for j = 1 to w.boneids.count do
>
> 	(
>
> 		boneid = w.boneids[j]
>
> 		weight = w.weights[j]
>
> 		append bi boneid
>
> 		append wv weight
>
> 	)	
>
> 	skinOps.ReplaceVertexWeights skinMod i bi wv
>
> )
>
> max create mode
>
> )
>
> )
>
> fclose f

Samples

http://puu.sh/bW2CC/f213503940.7z
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-03T11:33:57+00:00
- Post Title: Reign of Revolution MaxScript Help

> Reply from CriticalError
>
> after checking a lot fo files, no one opened, just a few of them,lol, noone == a few of them?
Anyway, the samples you provided have a bone count of zero thus the script has to be changed slightly:



i003023.JPG (79.5 KiB) Viewed 284 times



> and add material assign too, ok many thanks for all and hope can fix that, thanks for support it and have a nice day.well, I'm not very familar with max, the search path for texture files must be set correctly, I guess.

I didn't bother and just expanded the texname like this:

for a = 1 to texture_count do (
texname = readstring f
...
texname = "C:\Programme\Autodesk\3ds Max 2009\Scripts\R2 Samples\i003023.dds"
...
}

(This is working for the model i003023.rmb only, of course. It just picks the diffuse texture.)
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-11-26T17:39:57+00:00
- Post Title: Reign of Revolution MaxScript Help

Hello 


Here is a blender importer for animation and skinned meshes. 
It works only with Blender version 249 and Python 249.

It supports: 
-rmb - file with skinned mesh
-rab - animation file

For autotexturing:
-unpack "model.rfs" to "model" folder
-unpack "texture.rfs" to "texture" folder

If problem with game version, please send me files.
[https://ru.4game.com/r2/install/](https://ru.4game.com/r2/install/)
[Blender249[ReignOfRevolutionOnline][rab][rmb][2014-11-26].zip](https://xentaxbackup.github.io/file/8146_Blender249[ReignOfRevolutionOnline][rab][rmb][2014-11-26].zip)
## Post #4
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-11-29T17:15:44+00:00
- Post Title: Reign of Revolution MaxScript Help

> Reply from Szkaradek123
>
> Hello 


Here is a blender importer for animation and skinned meshes. 
It works only with Blender version 249 and Python 249.

It supports: 
-rmb - file with skinned mesh
-rab - animation file

For autotexturing:
-unpack "model.rfs" to "model" folder
-unpack "texture.rfs" to "texture" folder

If problem with game version, please send me files.
https://ru.4game.com/r2/install/Thank you, my friend, the script works very well, good job
