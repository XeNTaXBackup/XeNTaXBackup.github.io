## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-14T10:17:24+00:00
- Post Title: Bad Company 2 Mesh importer

So I`m building this mesh importer for BFBC2 and run into an issue with UV`s 
don`t understand what`s throwing it off. This seems to execute just fine,
                        mesh1 = mesh vertices:Vert_Positions_array faces:Face_array
			mesh1.numTVerts = Vert_Diffuse_array.count
			buildTVFaces mesh1	

 but I get 1023 dead verts (out of 1024) in channel info.


Here is the script, texture map and mesh file I`m reading from.
[https://dl.dropboxusercontent.com/u/881 ... a.meshdata](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/Raven_Mesh_lod0_data.meshdata)
[https://dl.dropboxusercontent.com/u/881 ... cache_.dds](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/_temp_cache_.dds)
[https://dl.dropboxusercontent.com/u/881 ... 81.1%29.ms](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/Bad%20Company%202%20mesh%20Importer%281.1%29.ms)

Anyone have suggestions how to fix my UV`s?
Thanks guys ;]
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-08-14T11:13:20+00:00
- Post Title: Bad Company 2 Mesh importer

You have to add this after the buildTVFaces line:

```
for j = 1 to Face_array.count do setTVFace mesh1 j Face_array[j]
```
## Post #3
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-14T11:20:11+00:00
- Post Title: Bad Company 2 Mesh importer

> Reply from barti
>
> You have to add this after the buildTVFaces line:
Code: Select allfor j = 1 to Vert_Diffuse_array.count do setTVert mesh1 j Vert_Diffuse_array[j]
for j = 1 to Face_array.count do setTVFace mesh1 j Face_array[j]
Omg how did I miss this  
Thanks bud it works now ;]
## Post #4
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-15T20:01:15+00:00
- Post Title: Bad Company 2 Mesh importer

Ok I`ve run into another issue. There are only three static offsets in the header that I can understand 
It`s #1 ObjectType    = @ 0x01 (UBYTE)
      #2 ObjectCount   = @ 0x06 (UBYTE)
      #3 ObjectName    = @ 0x07  (ASCII)
There rest seems to be dependent on number of strings and string lenghts.
Now most of the data seems to have static positions just after the strings "ObjectName" like ObjectTriangleCount is ObjectName.count+1(uint16),
ObjectVertexCount is ObjectName.count+5(uint16), ObjectVertexStride is ObjectName.count+17(UByte). While I can import one object just fine my problems start when there are more than one in the file .As I cannot find any values that would define spacing between the strings or start and end positions. Any suggestions how to tackle this would be greatly appreciated ;]

here are my current files
hexworkshop .hbk file for  "Raven_Mesh_lod0_data.meshdata" [https://dl.dropboxusercontent.com/u/881 ... ven%29.hbk](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/BadCompany2%28Raven%29.hbk)
hexworkshop .hbk file for "Parrot_01_Mesh_lod0_data.meshdata" [https://dl.dropboxusercontent.com/u/881 ... rot%29.hbk](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/BadCompany2%28Parrot%29.hbk)

maxscript: [https://dl.dropboxusercontent.com/u/881 ... 81.2%29.ms](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/Bad%20Company%202%20mesh%20Importer%281.2%29.ms)
file with a single object: [https://dl.dropboxusercontent.com/u/881 ... a.meshdata](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/Raven_Mesh_lod0_data.meshdata)
file with two objects: [https://dl.dropboxusercontent.com/u/881 ... a.meshdata](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Mesh%20Importer/Parrot_01_Mesh_lod0_data.meshdata)

maybe this will be of some help [https://dl.dropboxusercontent.com/u/881 ... nction.gif](https://dl.dropboxusercontent.com/u/88155050/BFBC2/Mesh%20Research/Null_Terminated_String_Function.gif)
## Post #5
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-17T21:07:20+00:00
- Post Title: Bad Company 2 Mesh importer

No suggestions
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-18T08:52:39+00:00
- Post Title: Bad Company 2 Mesh importer

well, that's some work, you know?  
(Your mix of reading from mfile and sfile is a little bit confusing.)

I modified your script (for reading the header after @0007 I used mfile only).
It works with the parrot now (first submesh only) and there are some weird faces. Didn't check this in depth, no time, sry.



Parrot.JPG (36.75 KiB) Viewed 190 times



You can use that modified script for the raven, too.
But you'll have to change this line:
fseek mfile 22#seek_cur -- 21 for the raven!

and to delete this one:
fseek mfile 71439#seek_set	 -- delete this line for the raven!

It's up to you how to solve this "22/21" issue to make the script useable for both single and multi mesh files.
Also a loop for getting the submeshes has to be built in.
Keep in mind that for the parrot the VertexStride of the 2nd submesh seems to be 32? 

Also to be checked whether ObjectPrimitiveCount always having the same value or needs an array, too.

```
	fn readHalfFloat fstream = (
	    hf=readshort fstream #unsigned
	    sign = bit.get hf 16
	    exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
	    fraction = bit.and hf (bit.hexasint "03FF")
	    if sign==true then sign = 1 else sign = 0
	    exponentF = exponent + 127
	    outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
	    (bit.shift exponentF 23)) (bit.shift sign 31)
	    return bit.intasfloat outputasfloat*2
	    )		
		
	clearlistener()

	meshdata_filename = getOpenFileName caption:"Import meshdata File" types:"meshdataFile (*.meshdata)|*.meshdata|All Files (*.*)|*.*"
	if meshdata_filename != undefined then mFile = fopen meshdata_filename "rb"
	sfile=openfile meshdata_filename mode:"r+"													
	
	Vert_Positions_array=#()
	Vert_Tangents_array=#()
	Vert_BiNormals_array=#()
	Vert_Diffuse_Array=#()
	Vert_Normal_Array=#()
	Vert_Bone_Indices_array=#()
	Vert_Blend_Weights_Array=#()
	Face_array=#()
	BoneIndexSameBool=false
	
	model_Scale = 39
	
	ObjectType = "ObjectType " + readbyte mfile as string
	ObjectCountOffset = fseek mfile 6 #seek_set
	--ObjectCount = "ObjectCount " + readbyte mfile as string
	ObjectCount = readbyte mfile
	ObjectNameOffset = seek sfile 7		

	ObjectVertCount= #()
	VertexStride= #()
	for i = 1 to ObjectCount do
	(
		ObjectName= readString mfile --read zero terminated string
		ObjectPrimitiveCount = readshort mfile
		unk1 =  readshort mfile          -- high word of ObjectPrimitiveCount?
		ObjectVertCount[i] =  readlong mfile
		fseek mfile 8#seek_cur
		VertexStride[i] = readbyte mfile
		fseek mfile 37#seek_cur
		format "%, %, %, %\n" ObjectName ObjectPrimitiveCount ObjectVertCount[i] VertexStride[i]
	) 
	fseek mfile 22#seek_cur	-- 21 for the raven!
	FaceIndiceCount =((readlong mfile)/2)	
	unk2 = readlong mfile
	addr= ftell mfile
	format "fIndCount: % addr: %\n" FaceIndiceCount addr
	--In this section the script reads out data from VertexBlock and appends it to arrays

		for vb_read_array = 1 to ObjectVertCount[1] do	    
		(
			--Read vertex positions	
			try(	
				vpx =  readhalffloat mfile 
				vpy =  readhalffloat mfile 
				vpz =  readhalffloat mfile 
				--format "% % %\n" vpx vpy vpz
				for i = 1 to 38 do readbyte mfile  
					ftell mfile
				if
				
					vpx != Undefined and vpy!=undefined and vpz!=undefined do
					(
						append Vert_Positions_array [(vpx*model_scale),(vpy*model_scale),(vpz*model_scale)]
					)
				)
			catch 
				if vb_read_array == 1 do 
					(print"Vert_Positions error" 
					messagebox "Vert_Positions error")
			--Read diffuse UV coordinates
			try(
				v_diff_U = ReadHalfFloat mfile 
				v_diff_V = ReadHalfFloat mfile 
				if 
				
					v_diff_U !=Undefined and v_diff_V!=Undefined do
					(
					append Vert_diffuse_Array [v_diff_U,v_diff_V,0]
					)
				)
			catch 
				if vb_read_array == 1 do print"Vert_diffuse error"			
		)


	--Read face indices
	fseek mfile 71439#seek_set					-- delete this line for the raven!
	print ("Position before f-indice`s "+((ftell mFile)as string))	
		for x = 1 to ((FaceIndiceCount/3)) do
			(
				fa=readshort mFile #unsigned+1
				fb=readshort mFile #unsigned+1
				fc=readshort mFile #unsigned+1
				--format "% % %\n" fa fb fc
				append Face_array[fa,fb,fc]
			)
			
			
			--Build Mesh From Arrays
				mesh1 = mesh vertices:Vert_Positions_array faces:Face_array
				mesh1.numTVerts = Vert_Diffuse_array.count
				mesh1.name = objectname
				
				meshop.setNumMaps mesh1 3 keep:false
				channelInfo.Dialog ()	
				channelInfo.NameChannel mesh1 3 1 "Diffuse"
				channelInfo.NameChannel mesh1 3 2 "Normal"
					
				buildTVFaces mesh1	
				meshop.setMapSupport mesh1 1 true
				meshop.setMapSupport mesh1 2 true	
				for j = 1 to Vert_Diffuse_array.count  do  meshop.setMapVert mesh1 1 j Vert_Diffuse_array[j] 
	 			for j = 1 to Face_array.count do meshop.setMapFace mesh1 1 j Face_array[j] 	
					
				for j = 1 to Vert_Normal_array.count  do  meshop.setMapVert mesh1 2 j Vert_Normal_array[j] 
	 			for j = 1 to Face_array.count do meshop.setMapFace mesh1 2 j Face_array[j] 	
					
				mesh1.name = objectname

				
				--flip UV`s, apply material/name, add checker map to the diffuse map.
				select mesh1
				modPanel.addModToSelection (UVW_Xform ()) ui:on

				mesh1.modifiers[#UVW_Xform].V_Flip = 1
				maxOps.CollapseNode mesh1 off	
				modPanel.addModToSelection (UVW_Xform ()) ui:on	
				mesh1.modifiers[#UVW_Xform].Map_Channel = 2
				mesh1.modifiers[#UVW_Xform].V_Flip = 1				

				maxOps.CollapseNode mesh1 off	
				mesh1.material = standardMaterial()
				mesh1.material.name = objectname
				mesh1.material.showInViewport = on		
				
			
			
			
			
			
			
			
			
			rotate mesh1(angleaxis 90 [1,0,0])	

			Vert_Diffuse_array[1024]
			
			fclose mfile
			fclose sfile

```
## Post #7
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-08-20T20:06:50+00:00
- Post Title: Bad Company 2 Mesh importer

Thanks shakotay for that, I appreciate it. I have pushed on quite a bit but the game files seems to be a lot messier that fb2 or fb3. I`ll see if I can get it working.
## Post #8
- Username: Humm08
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Aug 24, 2014 3:23 pm
- Post datetime: 2014-08-24T07:34:00+00:00
- Post Title: Bad Company 2 Mesh importer

thanks dainazinas and shakotay2 for the script

o.o
## Post #9
- Username: DyordsTheBell
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 07, 2023 8:21 pm
- Post datetime: 2023-04-07T12:48:52+00:00
- Post Title: Bad Company 2 Mesh importer

> Reply from dainazinas ↑Sat Aug 16, 2014 4:01 am at Sat Aug 16, 2014 4:01 am
>
> 
Ok I`ve run into another issue. There are only three static offsets in the header that I can understand 
It`s #1 ObjectType    = @ 0x01 (UBYTE)
      #2 ObjectCount   = @ 0x06 (UBYTE)
      #3 ObjectName    = @ 0x07  (ASCII)
There rest seems to be dependent on number of strings and string lenghts.
Now most of the data seems to have static positions just after the strings "ObjectName" like ObjectTriangleCount is ObjectName.count+1(uint16),
ObjectVertexCount is ObjectName.count+5(uint16), ObjectVertexStride is ObjectName.count+17(UByte). While I can import one object just fine my problems start when there are more than one in the file .As I cannot find any values that would define spacing between the strings or start and end positions. Any suggestions how to tackle this would be greatly appreciated ;]

here are my current files
hexworkshop .hbk file for  "Raven_Mesh_lod0_data.meshdata" https://dl.dropboxusercontent.com/u/881 ... ven%29.hbk
hexworkshop .hbk file for "Parrot_01_Mesh_lod0_data.meshdata" https://dl.dropboxusercontent.com/u/881 ... rot%29.hbk

maxscript: https://dl.dropboxusercontent.com/u/881 ... 81.2%29.ms
file with a single object: https://dl.dropboxusercontent.com/u/881 ... a.meshdata
file with two objects: https://dl.dropboxusercontent.com/u/881 ... a.meshdata

maybe this will be of some help https://dl.dropboxusercontent.com/u/881 ... nction.gif

Does these download links are still working. Can anyone re-post the files, including the max script for download please.....
