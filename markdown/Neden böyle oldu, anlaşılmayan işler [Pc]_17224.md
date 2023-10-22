## Post #1
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:08:35+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

Ben başlıyorım
KAsma yeri
MT2 gin ikasma için yapıldı
Seviyesizlere seviye getirmek içi
weight3 = readbyte f #unsigned	
weight2 = readbyte f #unsigned	
weight1 = readbyte f #unsigned	
weight4 = readbyte f #unsigned			

bone1 = readbyte f #unsigned	
bone2 = readbyte f #unsigned	
bone3 = readbyte f #unsigned	
bone4 = readbyte f #unsigned

Şimsi siz neden böyle bir şey yaptığını mesak edeceksiniz değim li
## Post #2
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:10:50+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

AA bulll
## Post #3
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:11:44+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

Çok 
Var ama nalşıl mayan 

kurna ile bb
## Post #4
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:13:05+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

import newGameLib
reload(newGameLib)
from newGameLib import *
import Blender


def section_1860(g):
	g.B(4)
	num = g.i(8)
	for m in range(num[4]):
		t=g.tell()		
		mesh.vertPosList.append(g.f(3))
		g.seek(t+24,0)
	for m in range(num[6]):
		t=g.tell()
		mesh.faceList.append(g.i(3))
		matID,unk=g.i(2)
		mesh.matIDList.append(matID)
		g.seek(t+20,0) 
	if num[3]!=0: 
		uvcoord=[]
		for m in range(num[5]):
			uvcoord.append(Vector(g.f(2)))
		for m in range(num[6]):
			id1,id2,id3=g.i(3)
			mesh.faceUVList.append([uvcoord[id1],uvcoord[id2],uvcoord[id3]])
		skin=Skin()
		for m in range(num[4]):
			count = g.i(1)[0]
			list1,list2=[],[]
			for n in range(count):
				list1.append(g.i(1)[0])
				g.f(3)
				list2.append(g.f(1)[0])
			mesh.skinIndiceList.append(list1)
			mesh.skinWeightList.append(list2)
		mesh.skinList.append(skin)	


def section_0(g):
	g.find('\x00')


def section_1863(g):
	g.i(4)
	t=g.tell()
	name=g.find('\x00')
	g.seek(t+132,0)
	type=g.B(4)
	if type==(255,255,255,0):
		mat=Mat()
		mat.ZTRANS=True
		g.seek(t+404,0)
		name=g.find('\x00')
		mat.diffuse=g.dirname+os.sep+os.path.basename(name)
		if os.path.exists(mat.diffuse)==False:
			mat.diffuse=g.dirname.split('object')[0]+os.sep+name		
		g.seek(t+876,0)
		g.seek(t+1348,0)
		g.find('\x00')
		g.seek(t+1820,0)
		name=g.find('\x00')
		mat.specular=g.dirname+os.sep+os.path.basename(name)
		if os.path.exists(mat.specular)==False:
			mat.specular=g.dirname.split('object')[0]+os.sep+name
		mesh.matList.append(mat)	


def section_656(g):
	g.B(4)
	num = g.i(4)
	for m in range(num[3]):
		t=g.tell()
		v=g.i(3)
		g.seek(t+152,0)	
		bone_parent_list.append(v[1])


def section_1861(g):	
	num = g.i(1)[0]
	for m in range(num):
		name=g.find('\x00')
		bone_name_list.append(name)


def section_1(g): 
	num = g.i(2)
	for m in range(num[1]):
		rotmatrix=Matrix(g.f(3),g.f(3),g.f(3)).resize4x4()
		posmatrix=TranslationMatrix(Vector(g.f(3)))
		bone_matrices_list.append([rotmatrix,posmatrix])


def cgfParser(filename,g):
	global mesh,skeleton
	global bone_matrices_list
	global bone_parent_list
	global bone_name_list

	global mesh

	skeleton=Skeleton()
	skeleton.name='armature'
	skeleton.ARMATURESPACE=True
	bone_matrices_list=[]
	bone_parent_list=[]
	bone_name_list=[]

	mesh=Mesh() 
	mesh.BINDSKELETON=skeleton.name

	g.word(10)
	g.H(1)
	mat_id=0
	bone_id=0
	off=g.i(2)
	g.seek(off[1],0)
	nSec = g.i(1)[0]
	off_list=[]
	for m in range(nSec):
		off_list.append([g.B(4),g.i(3)])
	for m in range(nSec):
		chunk=off_list[m][0]
		type=off_list[m][1][0]  
		off=off_list[m][1][1]
		g.seek(off,0)
		if type==0:
			section_0(g) 
		if chunk==(0,0,204,204) and type==1860: 
			section_1860(g)
		if chunk==(3,0,204,204) and type==656:
			section_656(g)
		if chunk==(5,0,204,204) and type==1861:
			section_1861(g)  
		if chunk==(18,0,204,204) and type==1:
			section_1(g)
		if chunk==(12,0,204,204) and type==1863:
			section_1863(g)
		if chunk==(13,0,204,204) and type==2089:	  
			anim_section_2089(bone_id)
			bone_id+=1

	for m in range(len(bone_name_list)):
		bone=Bone()
		bone.name=bone_name_list[m]
		bone.parentID=bone_parent_list[m]
		bone.rotMatrix=bone_matrices_list[m][0]
		bone.posMatrix=bone_matrices_list[m][1]
		skeleton.boneList.append(bone)
	skeleton.draw()	
	mesh.boneNameList=skeleton.boneNameList
	mesh.draw()	






def section_2089(g):
	num=g.i(2)
	abone=ActionBone()
	framecountlist.append(num[0])
	for m in range(num[0]):
		t=g.tell()
		time = int(g.i(1)[0]/160)
		pos=g.f(3)
		rot=g.f(4)
		rot=Quaternion(rot[3],rot[0],rot[1],rot[2]).toMatrix().invert()
		matrix = Matrix()		   
		matrix[0][:3] = rot[0]
		matrix[1][:3] = rot[1]
		matrix[2][:3] = rot[2]
		matrix[3][:3] = pos
		abone.posFrameList.append(time)
		abone.rotFrameList.append(time)
		abone.posKeyList.append(TranslationMatrix(Vector(pos)))
		abone.rotKeyList.append(rot.resize4x4())
		#abone.matrixframelist.append(time) 
		#abone.matrixkeylist.append(matrix)
		g.seek(t+32)
	action.boneList.append(abone)

def caf_parser(filename,g):
	global bone_name_list
	global action
	global framecountlist
	framecountlist=[]

	action=Action()
	action.skeleton='armature'
	action.BONESPACE=True
	action.BONESORT=True

	bone_name_list=[]

	g.word(10)
	g.H(1)
	off=g.i(2)
	g.seek(off[1],0)
	nSec = g.i(1)[0]
	off_list=[]
	for m in range(nSec):
		off_list.append([g.B(4),g.i(3)])
	for m in range(nSec):
		chunk=off_list[m][0]
		type=off_list[m][1][0]  
		off=off_list[m][1][1]
		g.seek(off)
		if chunk==(5,0,204,204) and type==1861:section_1861(g) 
		if chunk==(13,0,204,204) and type==2089:section_2089(g)
	for m in range(len(action.boneList)):
		abone=action.boneList[m]
		abone.name=bone_name_list[m]
	action.framecount=max(framecountlist)
	action.draw()	
	action.setContext()				




def Parser():
	filename=input.filename
	ext=filename.split('.')[-1].lower()

	if ext=='cgf':
		file=open(filename,'rb')
		g=BinaryReader(file)
		cgfParser(filename,g)
		file.close()

	if ext=='caf':
		file=open(filename,'rb')
		g=BinaryReader(file)
		caf_parser(filename,g)
		file.close()

def openFile(flagList):
	global input,output
	input=Input(flagList)
	output=Output(flagList)
	parser=Parser()

Blender.Window.FileSelector(openFile,'import','cgf - skeleton mesh,caf - animation file')
## Post #5
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:13:55+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

Böylesi daha iyiymiş 

```
reload(newGameLib)
from newGameLib import *
import Blender

			
def section_1860(g):
	g.B(4)
	num = g.i(8)
	for m in range(num[4]):
		t=g.tell()		
		mesh.vertPosList.append(g.f(3))
		g.seek(t+24,0)
	for m in range(num[6]):
		t=g.tell()
		mesh.faceList.append(g.i(3))
		matID,unk=g.i(2)
		mesh.matIDList.append(matID)
		g.seek(t+20,0) 
	if num[3]!=0: 
		uvcoord=[]
		for m in range(num[5]):
			uvcoord.append(Vector(g.f(2)))
		for m in range(num[6]):
			id1,id2,id3=g.i(3)
			mesh.faceUVList.append([uvcoord[id1],uvcoord[id2],uvcoord[id3]])
		skin=Skin()
		for m in range(num[4]):
			count = g.i(1)[0]
			list1,list2=[],[]
			for n in range(count):
				list1.append(g.i(1)[0])
				g.f(3)
				list2.append(g.f(1)[0])
			mesh.skinIndiceList.append(list1)
			mesh.skinWeightList.append(list2)
		mesh.skinList.append(skin)	
	
	
def section_0(g):
	g.find('\x00')


def section_1863(g):
	g.i(4)
	t=g.tell()
	name=g.find('\x00')
	g.seek(t+132,0)
	type=g.B(4)
	if type==(255,255,255,0):
		mat=Mat()
		mat.ZTRANS=True
		g.seek(t+404,0)
		name=g.find('\x00')
		mat.diffuse=g.dirname+os.sep+os.path.basename(name)
		if os.path.exists(mat.diffuse)==False:
			mat.diffuse=g.dirname.split('object')[0]+os.sep+name		
		g.seek(t+876,0)
		g.seek(t+1348,0)
		g.find('\x00')
		g.seek(t+1820,0)
		name=g.find('\x00')
		mat.specular=g.dirname+os.sep+os.path.basename(name)
		if os.path.exists(mat.specular)==False:
			mat.specular=g.dirname.split('object')[0]+os.sep+name
		mesh.matList.append(mat)	

	
def section_656(g):
	g.B(4)
	num = g.i(4)
	for m in range(num[3]):
		t=g.tell()
		v=g.i(3)
		g.seek(t+152,0)	
		bone_parent_list.append(v[1])

		
def section_1861(g):	
	num = g.i(1)[0]
	for m in range(num):
		name=g.find('\x00')
		bone_name_list.append(name)

		
def section_1(g): 
	num = g.i(2)
	for m in range(num[1]):
		rotmatrix=Matrix(g.f(3),g.f(3),g.f(3)).resize4x4()
		posmatrix=TranslationMatrix(Vector(g.f(3)))
		bone_matrices_list.append([rotmatrix,posmatrix])
	
	
def cgfParser(filename,g):
	global mesh,skeleton
	global bone_matrices_list
	global bone_parent_list
	global bone_name_list
	
	global mesh
	
	skeleton=Skeleton()
	skeleton.name='armature'
	skeleton.ARMATURESPACE=True
	bone_matrices_list=[]
	bone_parent_list=[]
	bone_name_list=[]
	
	mesh=Mesh() 
	mesh.BINDSKELETON=skeleton.name

	g.word(10)
	g.H(1)
	mat_id=0
	bone_id=0
	off=g.i(2)
	g.seek(off[1],0)
	nSec = g.i(1)[0]
	off_list=[]
	for m in range(nSec):
		off_list.append([g.B(4),g.i(3)])
	for m in range(nSec):
		chunk=off_list[m][0]
		type=off_list[m][1][0]  
		off=off_list[m][1][1]
		g.seek(off,0)
		if type==0:
			section_0(g) 
		if chunk==(0,0,204,204) and type==1860: 
			section_1860(g)
		if chunk==(3,0,204,204) and type==656:
			section_656(g)
		if chunk==(5,0,204,204) and type==1861:
			section_1861(g)  
		if chunk==(18,0,204,204) and type==1:
			section_1(g)
		if chunk==(12,0,204,204) and type==1863:
			section_1863(g)
		if chunk==(13,0,204,204) and type==2089:	  
			anim_section_2089(bone_id)
			bone_id+=1
		
	for m in range(len(bone_name_list)):
		bone=Bone()
		bone.name=bone_name_list[m]
		bone.parentID=bone_parent_list[m]
		bone.rotMatrix=bone_matrices_list[m][0]
		bone.posMatrix=bone_matrices_list[m][1]
		skeleton.boneList.append(bone)
	skeleton.draw()	
	mesh.boneNameList=skeleton.boneNameList
	mesh.draw()	
	
						
		

		
				
def section_2089(g):
	num=g.i(2)
	abone=ActionBone()
	framecountlist.append(num[0])
	for m in range(num[0]):
		t=g.tell()
		time = int(g.i(1)[0]/160)
		pos=g.f(3)
		rot=g.f(4)
		rot=Quaternion(rot[3],rot[0],rot[1],rot[2]).toMatrix().invert()
		matrix = Matrix()		   
		matrix[0][:3] = rot[0]
		matrix[1][:3] = rot[1]
		matrix[2][:3] = rot[2]
		matrix[3][:3] = pos
		abone.posFrameList.append(time)
		abone.rotFrameList.append(time)
		abone.posKeyList.append(TranslationMatrix(Vector(pos)))
		abone.rotKeyList.append(rot.resize4x4())
		#abone.matrixframelist.append(time) 
		#abone.matrixkeylist.append(matrix)
		g.seek(t+32)
	action.boneList.append(abone)
		
def caf_parser(filename,g):
	global bone_name_list
	global action
	global framecountlist
	framecountlist=[]
			
	action=Action()
	action.skeleton='armature'
	action.BONESPACE=True
	action.BONESORT=True
	
	bone_name_list=[]

	g.word(10)
	g.H(1)
	off=g.i(2)
	g.seek(off[1],0)
	nSec = g.i(1)[0]
	off_list=[]
	for m in range(nSec):
		off_list.append([g.B(4),g.i(3)])
	for m in range(nSec):
		chunk=off_list[m][0]
		type=off_list[m][1][0]  
		off=off_list[m][1][1]
		g.seek(off)
		if chunk==(5,0,204,204) and type==1861:section_1861(g) 
		if chunk==(13,0,204,204) and type==2089:section_2089(g)
	for m in range(len(action.boneList)):
		abone=action.boneList[m]
		abone.name=bone_name_list[m]
	action.framecount=max(framecountlist)
	action.draw()	
	action.setContext()				
						
				
		
			
def Parser():
	filename=input.filename
	ext=filename.split('.')[-1].lower()
	
	if ext=='cgf':
		file=open(filename,'rb')
		g=BinaryReader(file)
		cgfParser(filename,g)
		file.close()
		
	if ext=='caf':
		file=open(filename,'rb')
		g=BinaryReader(file)
		caf_parser(filename,g)
		file.close()
 
def openFile(flagList):
	global input,output
	input=Input(flagList)
	output=Output(flagList)
	parser=Parser()
	
Blender.Window.FileSelector(openFile,'import','cgf - skeleton mesh,caf - animation file') 
```
## Post #6
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:16:29+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```

	local HInfo = undefined

	button loaddff "Import DFF" width:120 --offset:[-1,-3]
	button loadifp "Load IFP" width:120 offset:[-1,-3]
	label lbl1 "Anim. File:" align:#left
	label lbl2 "Total Animation:" align:#left
	label lbl3 "Internal Name:" align:#left
	listbox AnimList height:10
	button RecOrg "M" width:17 align:#left tooltip:"Record Origin
```
## Post #7
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:16:51+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
			sliderTime = 0
			for i = 1 to $selection.count do (
				deletekeys $selection[i].pos.controller
				deletekeys $selection[i].rotation.controller
				deletekeys $selection[i].scale.controller
				try (
					tp 					= readvalue ((getUserProp $selection[i] "OrgRot") as stringstream)
					tpW					= getUserProp $selection[i] "OrgRotW"
					$selection[i].rotation = (quat tp.x tp.y tp.z tpW)
					$selection[i].scale	= readvalue ((getUserProp $selection[i] "Orgscl") as stringstream)
					$selection[i].pos	= readvalue ((getUserProp $selection[i] "OrgPos") as stringstream)
				) catch (RecOrg.text = "M")
			)--end for i	
```
## Post #8
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:17:26+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
		if (AnimList.selection != 0)AND($selection.count >0) then (
			OK2Append = false
			if (tyVC.checked == true)AND(AnimInfo[3] == 0x4B504E41) then OK2Append = true
			if (tySA.checked == true)AND(AnimInfo[3] == 0x33504E41) then OK2Append = true
			if OK2Append == false then (
            	messagebox "You can not replace DIFFERENT FORMAT\nin animation IFP file." title: "IFP Format Error"
            	--format "%\n" AnimInfo[3] 
			) else (

				for obj in $selection where (getUserProp obj "BoneID") == undefined do deselect obj

				try (	--undefined*undefined
					Sname = (getFilenamePath ifpname) + "ttemp.bin"
					format "\nReplace Anime: % at [%]\n" AnimList.selected AnimInfo[2][AnimList.selection]
					ff = fopen Sname "wb"
					f = fopen ifpname "rb"
					fseek f 0 #seek_end
					edf = ftell f
					fseek f 0 #seek_set
					for i = 1 to AnimInfo[2][AnimList.selection] do (
						writebyte ff (readByte f)
					)--end for i
```


```
f = fopen ifpname "rb"
```
## Post #9
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:17:46+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
		if $selection.count >0 then (

			rult = resetPost $selection slidertime
			if rult == false then RecOrg.text = "M"

			f = fopen ifpname "rb"
			fseek f AnimInfo[2][AnimList.selection] #seek_set

			format "\nAnime: % at [%]\n" AnimList.selected (ftell f)
			
			ApplyAnim f ($selection as array) skipPos.checked slidertime AnimInfo[3]
		
			fclose f
			gc()
		)
	)--end on apyAnim
```
## Post #10
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:18:15+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

Ben bil yormuyum sanıyor sun çırak 

```
		if (AnimList.selection > 0)AND($selection.count >0) then (

			rult = resetPost $selection slidertime
			if rult == false then RecOrg.text = "M"

			f = fopen ifpname "rb"
			fseek f AnimInfo[2][AnimList.selection] #seek_set

			format "\nAnime: % at [%]\n" AnimList.selected (ftell f)
			
			ApplyAnim f ($selection as array) skipPos.checked slidertime AnimInfo[3]
		
			fclose f
			gc()
		)
	)--end on apyAnim
```
## Post #11
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:19:03+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

Yaln diyen nin ben simdi var ya

Nosul son sonu ad erecek

```
	label l1 "GTA IFP IO V1.1"
	label l1a "   - for both Max/GMax" align:#left
	label l2 "" 
	label l3 "by Kam" align:#left across:2
	label l4 "14Oct05" align:#right
	label l5 "kam.lai@ntlworld.com"
	label l6 " "
	label l7 "**Important GMax User**"
	label l8 "- You need copy/paste all" align:#left
	label l9 "  text from listener and edit" align:#left
	label lA "  the ifp text (from dumper)."	align:#left
	label lb "- Use T2B.exe to convert it."
```
## Post #12
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:20:44+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
        symbols = ":,'\" +-*!?;./="
        table = str.maketrans(symbols, "_" * len(symbols))
        enum = gname.upper().translate(table).replace("__", "_")
        return enum

    Fundementally broken versioning system
```
## Post #13
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:21:15+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
hex(self.data._version_value_._value)[4:]),0)).zfill(2)x
```
## Post #14
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:21:40+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
    # due to invalid settings
    b_scene = bpy.context.scene
    nif_ver_hex = b_scene.niftools.nif_version
    for gname in NifFormat.games:
        gname_trans = self.get_game_to_trans(gname)
        if gname_trans == self.properties.game:
            if nif_ver_hex not in NifFormat.games[gname]:
                raise nif_utils.NifError(
                "Version for export not found: %s"
                % str(nif_ver_hex))
            break
x(self.data._version_value_._value)),0)).zfill(2)
        nif_ver_hex_2 = str(int('0x{0:.2}'.format(
                        hex(self.data._version_value_._value)[4:]),0)).zfill(2)
        nif_ver_hex_3 = str(int('0x{0:.2}'.format(
                        hex(self.data._version_value_._value)[6:]),0)).zfill(2)
        nif_ver_hex_4 = str(int('0x{0:.2}'.format(
                        hex(self.data._version_value_._value)[8:]),0)).zfill(2)
```
## Post #15
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:22:00+00:00
- Post Title: Neden böyle oldu, anlaşılmayan işler [Pc]

```
        """Initialize and load configuration."""
        # initialize all instance variables
        self.guiElements = {} # dictionary of gui elements (buttons, strings, sliders, ...)
        self.gui_events = []   # list of events
        self.gui_event_ids = {} # dictionary of event ids
        self.config = {}      # configuration dictionary
        self.target = None    # import or export
        self.callback = None  # function to call when config gui is done
        self.texpathIndex = 0
        self.texpathCurrent = ''
```
## Post #16
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:22:32+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
27 0a 20 20 20 20 64 65 66 20 67 65 74 5f 67 61
6d 65 5f 74 6f 5f 74 72 61 6e 73 28 73 65 6c 66
2c 20 67 6e 61 6d 65 29 3a 0a 20 20 20 20 20 20
20 20 73 79 6d 62 6f 6c 73 20 3d 20 22 3a 2c 27
5c 22 20 2b 2d 2a 21 3f 3b 2e 2f 3d 22 0a 20 20
20 20 20 20 20 20 74 61 62 6c 65 20 3d 20 73 74
72 2e 6d 61 6b 65 74 72 61 6e 73 28 73 79 6d 62
6f 6c 73 2c 20 22 5f 22 20 2a 20 6c 65 6e 28 73
79 6d 62 6f 6c 73 29 29 0a 20 20 20 20 20 20 20
20 65 6e 75 6d 20 3d 20 67 6e 61 6d 65 2e 75 70
70 65 72 28 29 2e 74 72 61 6e 73 6c 61 74 65 28
74 61 62 6c 65 29 2e 72 65 70 6c 61 63 65 28 22
5f 5f 22 2c 20 22 5f 22 29 0a 20 20 20 20 20 20
20 20 72 65 74 75 72 6e 20 65 6e 75 6d 0a 0a 20
20 20 20 46 75 6e 64 65 6d 65 6e 74 61 6c 6c 79
20 62 72 6f 6b 65 6e 20 76 65 72 73 69 6f 6e 69
6e 67 20 73 79 73 74 65 6d 0a 20 20 20 20 64 65
66 20 68 65 78 5f 74 6f 5f 64 65 63 28 73 65 6c
66 2c 20 6e 69 66 5f 76 65 72 5f 68 65 78 29 3a
0a 20 20 20 20 20 20 20 20 0a 20 20 20 20 20 20
20 20 6e 69 66 5f 76 65 72 5f 68 65 78 5f 31 20
3d 20 73 74 72 28 69 6e 74 28 27 7b 30 3a 2e 34
7d 27 2e 66 6f 72 6d 61 74 28 0a 20 20 20 20 20
20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
20 20 20 68 65 78 28 73 65 6c 66 2e 64 61 74 61

```
## Post #17
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:23:00+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
2e 5f 76 61 6c 75 65 29 29 2c 30 29 29 2e 7a 66
69 6c 6c 28 32 29 0a 20 20 20 20 20 20 20 20 6e
69 66 5f 76 65 72 5f 68 65 78 5f 32 20 3d 20 73
74 72 28 69 6e 74 28 27 30 78 7b 30 3a 2e 32 7d
27 2e 66 6f 72 6d 61 74 28 0a 20 20 20 20 20 20
20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
20 20 68 65 78 28 73 65 6c 66 2e 64 61 74 61 2e
5f 76 65 72 73 69 6f 6e 5f 76 61 6c 75 65 5f 2e
5f 76 61 6c 75 65 29 5b 34 3a 5d 29 2c 30 29 29
2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20 20 20 20

```
## Post #18
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:24:12+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
        """Run the config gui."""
        self.target = target     # import or export
        self.callback = callback # function to call when config gui is done
```
## Post #19
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:25:05+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

Gerk siz ben siz neden böyle bil gisiz 

```
2e 5f 76 61 6c 75 65 29 29 2c 30 29 29 2e 7a 66
69 6c 6c 28 32 29 0a 20 20 20 20 20 20 20 20 6e
69 66 5f 76 65 72 5f 68 65 78 5f 32 20 3d 20 73
74 72 28 69 6e 74 28 27 30 78 7b 30 3a 2e 32 7d
27 2e 66 6f 72 6d 61 74 28 0a 20 20 20 20 20 20
20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
20 20 68 65 78 28 73 65 6c 66 2e 64 61 74 61 2e
5f 76 65 72 73 69 6f 6e 5f 76 61 6c 75 65 5f 2e
5f 76 61 6c 75 65 29 5b 34 3a 5d 29 2c 30 29 29
2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20 20 20 20
65 78 5f 32 20 2b 20 22 2e 22 20 2b 20 6e 69 66
5f 76 65 72 5f 68 65 78 5f 33 20 2b 20 22 2e 22
20 2b 20 6e 69 66 5f 76 65 72 5f 68 65 78 5f 34
29 0a 20 20 20 20 20 20 20 20 0a 20 20 20 20 20
20 20 20 72 65 74 75 72 6e 20 6e 69 66 5f 76 65
72 5f

```
## Post #20
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:25:41+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

Noeee 


Neden böy le

```
2e 5f 76 61 6c 75 65 29 29 2c 30 29 29 2e 7a 66
69 6c 6c 28 32 29 0a 20 20 20 20 20 20 20 20 6e
69 66 5f 76 65 72 5f 68 65 78 5f 32 20 3d 20 73
74 72 28 69 6e 74 28 27 30 78 7b 30 3a 2e 32 7d
27 2e 66 6f 72 6d 61 74 28 0a 20 20 20 20 20 20
20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
20 20 68 65 78 28 73 65 6c 66 2e 64 61 74 61 2e
5f 76 65 72 73 69 6f 6e 5f 76 61 6c 75 65 5f 2e
5f 76 61 6c 75 65 29 5b 34 3a 5d 29 2c 30 29 29
2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20 20 20 20
65 78 5f 32 20 2b 20 22 2e 22 20 2b 20 6e 69 66
5f 76 65 72 5f 68 65 78 5f 33 20 2b 20 22 2e 22
20 2b 20 6e 69 66 5f 76 65 72 5f 68 65 78 5f 34
29 0a 20 20 20 20 20 20 20 20 0a 20 20 20 20 20
20 20 20 72 65 74 75 72 6e 20 6e 69 66 5f 76 65
72 5f 20 20 6e 69 66 5f 76 65 72 5f 64 65 63 5f
33 20 3d 20 68 65 78 28 69 6e 74 28 6e 69 66 5f
76 65 72 5f 64 65 63 5f 33 2c 20 31 30 29 29 5b
32 3a 5d 2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20
20 20 20 20 20 6e 69 66 5f 76 65 72 5f 64 65 63
5f 34 20 3d 20 68 65 78 28 69 6e 74 28 6e 69 66
5f 76 65 72 5f 64 65 63 5f 34 2c 20 31 30 29 29
5b 32 3a 5d 2e 7a 66 69 6c 6c 28 32 29 0a 20 20
20 20 20 20 20 20 6e 69 66 5f 76 65 72 5f 68 65
78 20 3d 20 69 6e 74 28 0a 20 20 20 20 20 20 20
20 20 20 20 20 28 6e 69 66 5f 76 65 72 5f 64 65
63 5f 31 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 32 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 33 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 34 29 2c 20 31 36 29 0a

```
## Post #21
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:26:33+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

ÇOK bok muhabbet ker ler bunlar neden 

```
2e 5f 76 61 6c 75 65 29 29 2c 30 29 29 2e 7a 66
69 6c 6c 28 32 29 0a 20 20 20 20 20 20 20 20 6e
69 66 5f 76 65 72 5f 68 65 78 5f 32 20 3d 20 73
74 72 28 69 6e 74 28 27 30 78 7b 30 3a 2e 32 7d
27 2e 66 6f 72 6d 61 74 28 0a 20 20 20 20 20 20
20 20 20 20 20 20 20 20 20 20 20 20 20 20 20 20
20 20 68 65 78 28 73 65 6c 66 2e 64 61 74 61 2e
5f 76 65 72 73 69 6f 6e 5f 76 61 6c 75 65 5f 2e
5f 76 61 6c 75 65 29 5b 34 3a 5d 29 2c 30 29 29
2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20 20 20 20
65 78 5f 32 20 2b 20 22 2e 22 20 2b 20 6e 69 66
5f 76 65 72 5f 68 65 78 5f 33 20 2b 20 22 2e 22
20 2b 20 6e 69 66 5f 76 65 72 5f 68 65 78 5f 34
29 0a 20 20 20 20 20 20 20 20 0a 20 20 20 20 20
20 20 20 72 65 74 75 72 6e 20 6e 69 66 5f 76 65
72 5f 20 20 6e 69 66 5f 76 65 72 5f 64 65 63 5f
33 20 3d 20 68 65 78 28 69 6e 74 28 6e 69 66 5f
76 65 72 5f 64 65 63 5f 33 2c 20 31 30 29 29 5b
32 3a 5d 2e 7a 66 69 6c 6c 28 32 29 0a 20 20 20
20 20 20 20 20 6e 69 66 5f 76 65 72 5f 64 65 63
5f 34 20 3d 20 68 65 78 28 69 6e 74 28 6e 69 66
5f 76 65 72 5f 64 65 63 5f 34 2c 20 31 30 29 29
5b 32 3a 5d 2e 7a 66 69 6c 6c 28 32 29 0a 20 20
20 20 20 20 20 20 6e 69 66 5f 76 65 72 5f 68 65
78 20 3d 20 69 6e 74 28 0a 20 20 20 20 20 20 20
20 20 20 20 20 28 6e 69 66 5f 76 65 72 5f 64 65
63 5f 31 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 32 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 33 20 2b 20 6e 69 66 5f 76 65 72 5f 64 65
63 5f 34 29 2c 20 31 36 29 0a 7d 20 23 20 64 69
63 74 69 6f 6e 61 72 79 20 6f 66 20 67 75 69 20
65 6c 65 6d 65 6e 74 73 20 28 62 75 74 74 6f 6e
73 2c 20 73 74 72 69 6e 67 73 2c 20 73 6c 69 64
65 72 73 2c 20 2e 2e 2e 29 0a 20 20 20 20 20 20
20 20 73 65 6c 66 2e 67 75 69 5f 65 76 65 6e 74
73 20 3d 20 5b 5d

```

def draw_y_sep(self):
        """Vertical skip."""
        self.yPos -= self.YLINESEP
## Post #22
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:27:24+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
        heapSize = 2000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"
```
## Post #23
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:28:24+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

New


Oyun neasıl parçalan mas Bunu göstereceğim şimdi sziize

```
caption:"Open .bones from Bones folder" \
types:"Shadow of Mordor Bones (*.Kemil AMK)|*.skel" \
historyCategory:"LOTR_SOMObjectPresets"
g = fopen gname "rb"		
fname = getOpenFileName \
caption:"Open .mesh from Mesh folder" \
types:"Shadow of Mordor Models (*.Kafes amk)|*.mesh" \
historyCategory:"LOTR_SOMObjectPresets"
f = fopen fname "rb"
```
## Post #24
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:29:02+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

AAAA Moder Kelimesi geçti 

```
	(
	hf=readshort fstream
	sign = bit.get hf 16
	exponent = (bit.shift (bit.and hf (bit.hexasint "7C00")) -10) as integer - 16
	fraction = bit.and hf (bit.hexasint "03FF")
	if sign==true then sign = 1 else sign = 0
	exponentF = exponent + 127
	outputAsFloat = bit.or (bit.or (bit.shift fraction 13) \
	(bit.shift exponentF 23)) (bit.shift sign 31)
	return bit.intasfloat outputasfloat*2
```
## Post #25
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:29:21+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
BName=readstring g
Position=ftell g
NameEnd_00=readbyte g
if NameEnd_00!=0 then fseek g (Position) #seek_set
if NameEnd_00==0 then (
fseek g (0x0) #seek_cur
```
## Post #26
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:30:46+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
fseek g (BoneStart+BoneNameOff) #seek_set
BoneName=readstring g
fseek g (PosBEnd) #seek_set
append BoneNameArray BoneName
	
tfm = (quat c11 c12 c13 c14) as matrix3
tfm.row4 = [c21,c22,c23]
)	

fclose g
	
fseek f 0xC #seek_set
MshCount=readlong f
SData=readlong f
Unk00=readlong f
MeshOff=readlong f
SizeBoneId=readlong f
Count00=readlong f
```
## Post #27
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:32:13+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
getPos = ftell f + 4
fseek f getPos #seek_set			
```
## Post #28
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:32:28+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```

PosBoneMap=ftell f		
fseek f (SizeBoneId) #seek_cur
MeshCount00=readlong f
fseek f (0x8) #seek_cur

```
## Post #29
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:32:45+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
	
MeshStartPos=ftell f

fseek f (MeshOff) #seek_cur
```
## Post #30
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:33:04+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

> Reply from TSelman61X
>
> Code: Select allPrint ("Start @ 0x"+((bit.intAsHex(ftell f))as string))

PosBoneMap=ftell f		
fseek f (SizeBoneId) #seek_cur
MeshCount00=readlong f
fseek f (0x8) #seek_cur

```
getPos = ftell f + 4
fseek f getPos #seek_set			
)	
for a = 1 to Count01 do (
getPos = ftell f + 4
fseek f getPos #seek_set			
)
for a = 1 to DataCountId do (
BoneId=readbyte f#unsigned	
)
for a = 1 to CountShort do (
BoneId=readshort f#unsigned	
)	
for a = 1 to Count20 do (
getPos = ftell f + 20
fseek f getPos #seek_set			
)	
for a = 1 to Count12 do (
getPos = ftell f + 12
fseek f getPos #seek_set			
)	

Print ("Start @ 0x"+((bit.intAsHex(ftell f))as string))

PosBoneMap=ftell f		
fseek f (SizeBoneId) #seek_cur
MeshCount00=readlong f
fseek f (0x8) #seek_cur

Print ("End @ 0x"+((bit.intAsHex(ftell f))as string))	
	
MeshStartPos=ftell f

fseek f (MeshOff) #seek_cur
```
## Post #31
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:34:45+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
Null= readlong f
VertexCount = readlong f
UnkOff01 = readlong f
UnkOff02 = readlong f	
FaceCount = readlong f	
MShdId= readlong f
UsedBones=readlong f	
UsedBonesStart=readlong f	
VertexId = readlong f	
VertexEnd = readlong f	
```
## Post #32
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:35:12+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
      if(weight1 != 0) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights (w1/255.0)
      )
      if(weight2 != 0) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights (w2/255.0)
      )
      if(weight3 != 0) then (
         w3 = weight3 as float
         append w.boneids (bone3 + 1)
         append w.weights (w3/255.0)
      )
      if(weight4 != 0) then (
         w4 = weight4 as float
         append w.boneids (bone4 + 1)
        append w.weights (w4/255.0)
      )      
   )
   

if(maxweight != 0) then (
      if(weight1 != 0) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights (w1/255.0)
      )
      if(weight2 != 0) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights (w2/255.0)
append Weight_array w	
fseek f getPos #seek_set
append vertArray [-vx,-vz,vy]
append UV_array [tu,tv,0]	
)		
```
## Post #33
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:36:28+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
weight2 = readbyte f #unsigned	
weight1 = readbyte f #unsigned	
weight4 = readbyte f #unsigned			
	
bone1 = readbyte f #unsigned	
bone2 = readbyte f #unsigned	
bone3 = readbyte f #unsigned	
bone4 = readbyte f #unsigned
```
## Post #34
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:37:00+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

Ynalış mı var burda 

```
      if(weight1 != 0) then (
         w1 = weight1 as float
         append w.boneids (bone1 + 1)
         append w.weights (w1/255.0)
      )
      if(weight2 != 0) then (
         w2 = weight2 as float
         append w.boneids (bone2 + 1)
         append w.weights (w2/255.0)
      )
      if(weight3 != 0) then (
         w3 = weight3 as float
         append w.boneids (bone3 + 1)
         append w.weights (w3/255.0)
      )
      if(weight4 != 0) then (
         w4 = weight4 as float
         append w.boneids (bone4 + 1)
        append w.weights (w4/255.0)
      )      
   )
```
## Post #35
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:37:25+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
LongCheck00=readlong f
if LongCheck00!=0 then fseek f VEndPos00 #seek_set
if LongCheck00==0 then (
VEndPos01=ftell f
LongCheck01=readlong f
if LongCheck01!=0 then fseek f VEndPos01 #seek_set
if LongCheck01==0 then (
fseek f 0x8 #seek_cur	
VEndPos02=ftell f
LongCheck02=readlong f
if LongCheck02==0 then fseek f 0x0 #seek_cur
if LongCheck02!=0 then fseek f VEndPos02 #seek_set
)
if LongCheck01!=0 then fseek f VEndPos01 #seek_set	
)
```
## Post #36
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:37:49+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

KOOOOOOOt  
nedne böyle oluyor ki

```
fa=readshort f #unsigned +1
fb=readshort f #unsigned +1
fc=readshort f #unsigned +1
append faceArray [fc,fb,fa]	
)	
```
## Post #37
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:38:29+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

```
msh.numTVerts = UV_array.count
msh.name=("LOTR_MODEL_"+i as string)	
buildTVFaces msh
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to faceArray.count do setTVFace msh j faceArray[j]
msh.displayByLayer = false
msh.backfacecull = false
msh.wirecolor = (color 230 200 210)

```
## Post #38
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:38:56+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

İnsan mesak ediyor.

```
max modify mode
```
## Post #39
- Username: TSelman61X
- Rank: mega-veteran
- Number of posts: 252
- Joined date: Mon Feb 13, 2017 4:09 pm
- Post datetime: 2017-11-03T07:39:30+00:00
- Post Title: Re: Neden böyle oldu, anlaşılmayan işler [Pc]

Burda bititriyorum 
> Fin
