## Post #1
- Username: GoodFace
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-01T22:54:53+00:00
- Post Title: Martial Empires / Seven Souls

Here is a max script to import models with bones and weights it will also attempt to apply a texture tho it does not work every time.
part of the texture id is a value near the start of the file but i got bored trying to figure out how the other half worked so this will have to do.

[7souls.rar](https://xentaxbackup.github.io/file/4146_7souls.rar)
## Post #2
- Username: jaden
- Rank: mega-veteran
- Number of posts: 209
- Joined date: Sat Feb 05, 2011 8:41 am
- Post datetime: 2011-04-01T23:29:37+00:00
- Post Title: Martial Empires / Seven Souls

wow great stuff chrrox
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T15:54:16+00:00
- Post Title: Martial Empires / Seven Souls

Thanks for the script chrrox. I'm tried your script on max 2008, but it wont importing skin modifier, why this happen?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T18:17:35+00:00
- Post Title: Martial Empires / Seven Souls

what error do you get?
also the directory must be correct for it to see the bones

say you use the bms script you will get the folder
char
you must have the meshes in

char\mesh

and the bones in

char\bind
## Post #5
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T18:36:06+00:00
- Post Title: Martial Empires / Seven Souls

> Reply from chrrox
>
> what error do you get?
also the directory must be correct for it to see the bones

say you use the bms script you will get the folder
char
you must have the meshes in

char\mesh

and the bones in

char\bind
yes, i checked the script and my folders, everithing is fine, and i sucsesfully importing meshes and skeleton but without skin modifier, and no errors
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T18:57:32+00:00
- Post Title: Martial Empires / Seven Souls

does this add a skin modifier in max 2008
select  a mesh and then run this script does it add a skin modifier?

skinMod = skin ()
addModifier $ skinMod
## Post #7
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T19:00:57+00:00
- Post Title: Martial Empires / Seven Souls

> Reply from chrrox
>
> does this add a skin modifier in max 2008
select  a mesh and then run this script does it add a skin modifier?

skinMod = skin ()
addModifier $ skinMod
yes, it does
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T19:07:35+00:00
- Post Title: Martial Empires / Seven Souls

I have no idea then you can try 2010 thats what i use.
if its not giving errors i can not say why it wont add a skin modifier.
## Post #9
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-02T20:28:51+00:00
- Post Title: Martial Empires / Seven Souls

> Reply from chrrox
>
> I have no idea then you can try 2010 thats what i use.
if its not giving errors i can not say why it wont add a skin modifier.
ok, i installed 2011 x32 version, and every time getting same error:

```
-- In line: f = fopen fname "rb"
```
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-02T20:40:51+00:00
- Post Title: Martial Empires / Seven Souls

this should work in 2011
2011 just hates comments and spaces its annoying that's all that is changed.
[7souls.rar](https://xentaxbackup.github.io/file/4152_7souls.rar)
## Post #11
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-03T04:33:39+00:00
- Post Title: Martial Empires / Seven Souls

> Reply from chrrox
>
> this should work in 2011
2011 just hates comments and spaces its annoying that's all that is changed.
thanks, now script can loading models and sometimes bones, but it cause me an error at the line 317 (select msh)

add: same error for 2010 3ds max
## Post #12
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-04-03T12:33:01+00:00
- Post Title: Martial Empires / Seven Souls

I think its your language you might want to try copying the max script and pasting it into a new one.
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-04-03T13:11:35+00:00
- Post Title: Martial Empires / Seven Souls

> Reply from chrrox
>
> I think its your language you might want to try copying the max script and pasting it into a new one.
i checked all your words: on 2 PC with diffrent system languages and with several 3ds maxs, also i copied script to new one and nothing!

p.s.: it's strange, because all of your scripts before work perfectly on my PC, only this two working in strange way
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2011-05-26T20:25:52+00:00
- Post Title: Martial Empires / Seven Souls

some progress of my problem, and also solution

if you have a problem with importing weights, just import first *.msh file (g200002620.msh) and evaluate next command:

```
select msh
skinMod = skin ()
addModifier msh skinMod
```

then Resting your max and after that you can loading any "7 Souls" model you want

p.s.: after reloading max you need repeat this operation, don't know why this happen, but now it's only one solution
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-07T02:29:52+00:00
- Post Title: Martial Empires / Seven Souls

What are the bsb files?
I opened them in hex and it looks like it was done in .max, but couldn't import it. So maybe it being done in max doesn't mean anything.

This file is called "prop_1024.bsb"



The name of the bsb is the same as the name of the max in the file.
The textures that are references are stored in another folder called "textures" and were dumped by the bms.

Ok, I know what they might be (environment objects like architecture and walls and trees and stuff based on the filename) lol.

Here are some samples
[bsb.7z](https://xentaxbackup.github.io/file/4298_bsb.7z)
## Post #16
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-06-16T07:45:40+00:00
- Post Title: Re: Martial Empires / Seven Souls

thanks a lot for the great support but I get problem when try import in MAX 9,2009,2010.
[Sin título.jpg](https://xentaxbackup.github.io/file/4337_Sin título.jpg)
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T18:06:58+00:00
- Post Title: Re: Martial Empires / Seven Souls

Here's my guess so far for some BSB files (samples were less than 10 kb)
From the filenames, it appears they contain scenery assets like trees stones and architectures. I don't know what some of the floats could represent. The extent of my knowledge so far is limited to coords, faces, UV's, and normals. Transformations, weights, bones, material properties, and so on are out of my reach.

A couple files already don't follow what I have so far. Probably some of the unknowns explain this.

Works for a couple bsb's, fails for a lot of others. At least I know I'm getting somewhere.

"tree_0124.bsb"

[http://i.imgur.com/EcN3j.jpg](http://i.imgur.com/EcN3j.jpg)

EDIT: can load more bsb's now:

[http://i.imgur.com/gLskE.jpg](http://i.imgur.com/gLskE.jpg)

Note1: there may be multiple meshes in a single bsb file. Still looking for the mesh count.
note2: there are two different vertsizes: 56 and 44. Haven't found when they occur. "prop_ex01.bsb" contains vertsize 44 while most others contain vertsize 56

Note3: Not all materials use mask and normal textures (not sure what they're for). There doesn't appear to be any way to figure this out beforehand. We can probably take advantage of the charCount, knowing that there should be at least 5 characters to qualify as a texture name, but it could just as easily be a model with many materials that don't use masks or normal texture..

Note4: the material section really is odd. There are a couple odd ones out that I just can't seem to figure out the pattern. It almost looks as if some of them have multiple material sections...

Note5: although it parses large files successfully, the face count is way off. Not sure why.

```
dword ??? (seems to determine vertsize. If 8, then vertsize 44, else vertsize 56)
dword charCount
charCount model_name.max (maybe there's significance that it is done in max?)

dword_4 ??? 
byte ??? (just to get it to work)
dword ???
dword material_sections
struct mat_section {
   dword section_number
   float_9 ??? 
   dword num_materials (in this section)
   IF dword == 0
      dword charCount
      charCount "NULL"
   ELSE
      struct material { (does not always follow this format)
         dword material_number
         dword charCount
         charCount texture_name
         dword charCount
         charCount texture_mask_name
         dword charCount
         charCount texture_normal_name
      }
   ENDIF
}

dword num_meshes
dword unk

IF unk == 1
   dword_28 ???
ELSE
   dword_9 ???
   dword charCount
   charCount unknownProperty
   dword_9 ???
ENDIF

struct mesh {
   dword charCount
   charCount meshName (?)
   dword charCount
   charCount "property name"
   byte ???
   dword charCount
   charCount "Editable poly"
   dword_3 ???
   byte ???
   dword charCount
   charCount lightingMap
   byte ???

   dword_3 ???
   struct ??? {
      3 * float_16 ???
   }
   byte ???
   dword_10 ???

   dword num_vertices
   struct vertex {
      float_3 x,y,z
      float_11 ??? (might not all be float)
   }
   dword ??? (this value is important, because num_faces is only correct when it is == 1)
   dword num_faces
   struct face {
      word_3 f1, f2, f3
   }
}
[...maybe some more..]

```
## Post #18
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-06-30T23:48:06+00:00
- Post Title: Re: Martial Empires / Seven Souls

This thing looks like it has multiple material sections o.O

Is that common in 3D objects? If not, what could it represent (besides...corrupt data)

I might treat the first number in the highlighted section as "# material sections" and then do a loop over that. That's pretty much one of the main issues for small files

EDIT: that definitely does seem to be the number of material sections. I don't know what that means.
## Post #19
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-09T18:29:11+00:00
- Post Title: Re: Martial Empires / Seven Souls

nobody can give me a hand with it? what is wrong in script? I try with 2 scripts post chrox for Max 9 and 2010 and don't work -.-

Error: 

```

"201112600"
"C:\Users\Enzo\Des"
"C:\Users\Enzo\Destexture\diffuse\4201112600.dds"
"C:\Users\Enzo\Desbind\g0.bnd"
"BoneFile_0"
39639
39639
-- Error occurred during fileIn in <File:C:\Program Files\Autodesk\3ds Max 9\stdplugs\stdscripts\7souls.ms>
>> MAXScript Auto-load Script Error - C:\Program Files\Autodesk\3ds Max 9\stdplugs\stdscripts\7souls.ms Exception: -- Unable to convert: undefined to type: FileName <<

```


Script

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = GetOpenFileName caption:"Open 7 Souls Model File" types:"7 Souls Model File(*.msh)|*.msh"
f = fopen fname "rb"   --open file in read only format
base = getFilenamePath fname
basefile = getFilenameFile fname -- returns: "myImage.jpg"
basefile = substring basefile 3 (basefile.count - 2)
ss = substring base 1 (base.count - 5) -- returns "rof"
print basefile
print ss
DiffuseTex = (ss + "texture\diffuse\4" + basefile + ".dds")

print DiffuseTex
fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)

struct weight_data
(
	boneids,weights
)

Vert_array = #()
Normal_array = #()
UV_array = #()
Face_Array = #()
Weight_array = #()
VertID_array = #()

idstring2 = ReadFixedString  f 4
if idstring2 != "MESH" do (
BoneFile = readlong f
Skelleton = (ss + "bind\g" + (BoneFile as string) + ".bnd")
print Skelleton
print ("BoneFile" + "_" + (BoneFile as string))
Mesh_Name_Size = readlong f
Mesh_Name = ReadFixedString  f Mesh_Name_Size
vertcount = readlong f
facecount = readlong f
weightcount = readlong f
weightcount2 = readlong f
for i = 1 to vertcount do (
vx = readfloat f      --read xyz coordinates
vy = readfloat f 
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f * -1	
append Vert_array [vx,vy,vz] --save verts to Vert_array
append UV_array [tu,tv,0]
append Normal_array [nx,ny,nz]
)
facedirection = 1
for i = 1 to facecount  do (
f1 = readlong f + 1
f2 = readlong f + 1
f3 = readlong f + 1
append Face_array [f1,f2,f3]
)
for i = 1 to weightcount do (
boneids = ((readlong f) + 1)
VertID = ((readlong f) + 1)
weights = readfloat f
v2 = readlong f
w2 = readfloat f
v3 = readlong f
w3 = readfloat f
v4 = readlong f
w4 = readfloat f
append Weight_array (weight_data boneids:boneids weights:weights)
append VertID_array VertID
)
for i = 1 to weightcount2 do (
bone1 = readlong f
VertID = ((readlong f) + 1)
weight1 = readfloat f
w = (weight_data boneids:#() weights:#())
			w1 = weight1 as float
			append w.boneids (bone1+1)
			append w.weights (w1)
v2 = readlong f
w2 = readfloat f
v3 = readlong f
w3 = readfloat f
v4 = readlong f
w4 = readfloat f
append Weight_array w
append VertID_array VertID
)
print (ftell f)
msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
meditMaterials[1] = Standardmaterial ()
msh.material = meditMaterials[1]
meditMaterials[1].diffuseMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap.monoOutput = 1
msh.name = Mesh_Name
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
print (ftell f)
usedbones_array = #()
if idstring2 == "MESH" do (
mcount = readlong f
mid = readlong f
BoneFile = readlong f
Skelleton = (ss + "bind\g" + (BoneFile as string) + ".bnd")
print Skelleton
print ("BoneFile" + "_" + (BoneFile as string))
Mesh_Name_Size = readlong f
Mesh_Name = ReadFixedString  f Mesh_Name_Size
vertcount = readlong f
facecount = readlong f
for i = 1 to vertcount do (

vx = readfloat f      --read xyz coordinates
vy = readfloat f 
vz = readfloat f
nx = readfloat f
ny = readfloat f
nz = readfloat f
tu = readfloat f
tv = readfloat f * -1
if mcount == 2 Do (
fseek f 0x10#seek_cur
)
Bone1 = readbyte f#unsigned
Bone2 = readbyte f#unsigned
Bone3 = readbyte f#unsigned
Bone4 = readbyte f#unsigned
weight1 = readfloat f
weight2 = readfloat f
weight3 = readfloat f
weight4 = readfloat f

w = (weight_data boneids:#() weights:#())
maxweight = 0
if(Bone1 != 0) then
	maxweight = maxweight + weight1
if(Bone2 != 0) then
	maxweight = maxweight + weight2
if(Bone3 != 0) then
	maxweight = maxweight + weight3
if(Bone4 != 0) then
	maxweight = maxweight + weight4

if(maxweight != 0) then (
		if(weight1 != 0) then (
			w1 = weight1 as float
			append w.boneids (bone1 + 1)
			append w.weights w1
		)
		if(weight1 != 0) then (
			w2 = weight2 as float
			append w.boneids (bone2 + 1)
			append w.weights w2
		)
		if(weight1 != 0) then (
			w3 = weight3 as float
			append w.boneids (bone3 + 1)
			append w.weights w3
		)
		if(weight1 != 0) then (
			w4 = weight4 as float
			append w.boneids (bone4 + 1)
			append w.weights w4
		)		
	)
append Weight_array w
append Vert_array [vx,vy,vz] --save verts to Vert_array
append UV_array [tu,tv,0]
append Normal_array [nx,ny,nz]
)
if mcount == 2 Do (
usedbones = readbyte f#unsigned
for a = 1 to usedbones do (
bid = readbyte f#unsigned + 1
append usedbones_array bid
)
)
facedirection = 1
if mcount == 2 Do (
for i = 1 to facecount  do (
f1 = readshort f + 1
f2 = readshort f + 1
f3 = readshort f + 1
append Face_array [f1,f2,f3]
)
)
if mcount == 1 Do (
for i = 1 to facecount  do (
f1 = readlong f + 1
f2 = readlong f + 1
f3 = readlong f + 1
append Face_array [f1,f2,f3]
)
)
print (ftell f)
msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
meditMaterials[1] = Standardmaterial ()
msh.material = meditMaterials[1]
meditMaterials[1].diffuseMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap = Bitmaptexture fileName:DiffuseTex
meditMaterials[1].opacityMap.monoOutput = 1
msh.name = Mesh_Name
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)
actionMan.executeAction 0 "63508"

fclose f
f = fopen Skelleton "rb"
idstring = ReadFixedString f 4
BNArr = #()
if idstring != "BIND" Do (
nsize = readlong f
skelname = ReadFixedString f nsize
bonecount = readlong f
for a = 1 to bonecount Do (
boneid = readlong f + 1
boneparent = readlong f + 1
f1 = readfloat f
f2 = readfloat f
f3 = readfloat f
f4 = readfloat f
f5 = readfloat f
f6 = readfloat f
f7 = readfloat f
tfm = (quat f4 f5 f6 (f7 * -1)) as matrix3
tfm.row4 = [f1,f2,f3]
if isvalidnode (getNodeByName (a as string)) != true then (
if (boneparent != boneid) do (
tfm = tfm * BNArr[boneparent].objecttransform
 )	
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = (a as string)
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (boneparent != 0) then
 newBone.parent = BNArr[boneparent]
append BNArr newBone
)
)
)

if idstring == "BIND" Do (
fseek f 0x8#seek_cur
nsize = readlong f
skelname = ReadFixedString f nsize
bcount1 = readbyte f#unsigned
bcount2 = readbyte f#unsigned
bonecount  = (bcount1 + bcount2)
for a = 1 to bonecount Do (
boneid = readlong f + 1
boneparent = readlong f + 1
f1 = readfloat f
f2 = readfloat f
f3 = readfloat f
f4 = readfloat f
f5 = readfloat f
f6 = readfloat f
f7 = readfloat f
null = readbyte f#unsigned
tfm = (quat f4 f5 f6 (f7 * -1)) as matrix3
tfm.row4 = [f1,f2,f3]
if isvalidnode (getNodeByName (a as string)) != true then (
if (boneparent != boneid) do (
tfm = tfm * BNArr[boneparent].objecttransform
 )	
newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name = (a as string)
			newBone.width  = 0.01
			newBone.height = 0.01
			newBone.transform = tfm
			newBone.setBoneEnable false 0
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
 if (boneparent != 0) then
 newBone.parent = BNArr[boneparent]
append BNArr newBone
)
)
)
max modify mode
print idstring
if idstring2 != "MESH" do (

select msh
skinMod = skin ()
addModifier msh skinMod
for i = 1 to BNArr.count do
(
	maxbone = getnodebyname BNArr[i].name
	if i != BNArr.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
for i = 1 to Weight_array.count do
(
	skinOps.SetVertexWeights skinMod VertID_array[i] Weight_array[i].boneids Weight_array[i].weights
)
)

if idstring2 == "MESH" do (
if mcount == 2 Do (
BNArr = #()
for a = 1 to usedbones_array.count do (
append BNArr (getnodebyname (usedbones_array[a] as string))
)
)
select msh
skinMod = skin ()
addModifier msh skinMod
for i = 1 to BNArr.count do
(
	maxbone = getnodebyname BNArr[i].name
	if i != BNArr.count then
		skinOps.addBone skinMod maxbone 0
	else
		skinOps.addBone skinMod maxbone 1
)
modPanel.setCurrentObject skinMod
for i = 1 to Weight_array.count do
(
	w = Weight_array[i]
	bi = #()
	wv = #()
	for j = 1 to w.boneids.count do
	(
		boneid = w.boneids[j]
		weight = w.weights[j]
		append bi boneid
		append wv weight
	)	
	skinOps.ReplaceVertexWeights skinMod i bi wv
)
)

max create mode
max zoomext sel all
fclose f
```
## Post #20
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-09T18:43:33+00:00
- Post Title: Re: Martial Empires / Seven Souls

it cant find one of the files mentioned there.
## Post #21
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-09T18:52:50+00:00
- Post Title: Re: Martial Empires / Seven Souls

> Reply from chrrox
>
> it cant find one of the files mentioned there.yes I know g0.bnd are is bone I think, but in folder are not files with this name just .msh for weapons, and for characters in another folder called bindd are bnd files but for characters not for weapon  so what I do wrong man, can you tell me? because when get this error the model are imported there, but when try import another need restart max
## Post #22
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-09T19:16:25+00:00
- Post Title: Re: Martial Empires / Seven Souls

Well, it does say the script is to import models with bones and weights.
Though, one can assume the format is similar for unskinned models so one might use chrrox's script as reference.
## Post #23
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-09T19:21:44+00:00
- Post Title: Re: Martial Empires / Seven Souls

> Reply from finale00
>
> Well, it does say the script is to import models with bones and weights.
Though, one can assume the format is similar for unskinned models so one might use chrrox's script as reference.I don't know really what I do wrong guys, this make me crazy T_T
## Post #24
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-09T19:27:01+00:00
- Post Title: Re: Martial Empires / Seven Souls

I mean, you won't be able to load weapons because as you've pointed out, they don't have certain files
## Post #25
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2011-07-09T19:46:46+00:00
- Post Title: Re: Martial Empires / Seven Souls

> Reply from finale00
>
> I mean, you won't be able to load weapons because as you've pointed out, they don't have certain filesI get error with all files, just show a example with weapons but characters have bones and files are there can't get too, anyway thanks for reply
## Post #26
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-17T04:38:25+00:00
- Post Title: Re: Martial Empires / Seven Souls

Finale the Chroxxx script have trobles and not work fine, maybe u can made one for Noesis man? thanks.
## Post #27
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-17T04:49:02+00:00
- Post Title: Re: Martial Empires / Seven Souls

Needs samples.
Someone should put together a sample repository where all samples go so I can just go there for samples.

EDIT: well, here's the start of it since I don't have textures or the associated skeleton file

[https://www.dropbox.com/sh/7stlpd4qvkq3 ... uls_msh.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/qrKmKY-2UP/fmt_SevenSouls_msh.py)



Note that the file check ASSUMES the filename is the original filename, because the first 4 bytes is an integer equal to the number on that file.

I also noticed that I posted some bsb samples for the map assets, so I looked at it again with those samples:

[https://www.dropbox.com/sh/7stlpd4qvkq3 ... uls_bsb.py](https://www.dropbox.com/sh/7stlpd4qvkq3096/14yVnO6Jo4/fmt_SevenSouls_bsb.py)

Does not load the entire model yet, since one mesh struct seems different from another.
I don't actually know what that "extra" mesh after the first mesh is. It looks like the first mesh is enough for most purposes

Textures don't look right (UV is a big mess).
Maybe I'm not reading the right ones.
## Post #28
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-17T08:08:23+00:00
- Post Title: Re: Martial Empires / Seven Souls

This man made the plugin in 10 minutes for Noesis,   , Thanks finale its a greath job.
Tomorrow i startmade a game samples repository.
## Post #29
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-17T20:54:30+00:00
- Post Title: Re: Martial Empires / Seven Souls

Chrrox already wrote the maxscript so the format just needs to be parsed in a different language.
## Post #30
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-18T01:56:58+00:00
- Post Title: Re: Martial Empires / Seven Souls

msh script updated. Changed the file check to remove all non-digit characters rather than assume the format of the string. Now it should correctly check any of the msh files. After looking at how the data is stored, my plan is to have you copy all of the textures, in their original folders (normal, mask, texture) into the mesh folder. Then I can just assume that's where they are.

The mesh-texture assignment is stored in the "texture-info.txt" file. It is huge, and contains information for all meshes in that particular folder. I'm looking for a way to avoid having to keep selecting that file again and again whenever you want to view a new model.

bsb script updated.
Figured out where the mesh count is, and what the extra stuff at the end is also ("extra meshes" apparently)

It looks like all of the map assets such as buildings, dungeons, and basically entire cities/villages are stored across several bsb files.

Still some files with unknown mesh structs though.
Each vertex is 56 bytes. Some of these meshes would say they have 20 vertices, and so you read 20 vertices. Then they might have another 400k bytes of unknown floats, followed by say 36 faces.

Not sure what those random chunks of bytes are.





Attached two such examples that are breaking the script
[test.7z](https://xentaxbackup.github.io/file/5582_test.7z)
## Post #31
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-18T05:55:16+00:00
- Post Title: Re: Martial Empires / Seven Souls

Thanks finale, i little confused i open the textureinfo.txt inside of the folder Martial Empires\vfs\char\texture and i get a list but all the rows are same i cant found the rerence for meshes, this its the textures names but i cant see for wath model are each texture, since the models have diferent numbers but all start with g2 like g200002620.msh.

Texture Info ID	Diffuse Map  	Mask Map	  Color Map	         Normal Map		
402100200	       402100200	      m402100200	 c402100200	n402100200					
402100201	       402100201	      m402100201	 c402100201	n402100201					
402100300	       402100300	      m402100300	 c402100300	n402100300

EDIT: ok i found wath happend, if u delete the 2 first characters of the Texture info ID u get the name of the mesh asigned to this texture.
Like Texture ID 402100200 = 2100200 (mesh name)
      Texture ID 402100201 = 2100201 (mesh name)
## Post #32
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-18T06:25:33+00:00
- Post Title: Re: Martial Empires / Seven Souls

Ya, that's how it works. Pretty interesting way to store data lol
## Post #33
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-07-18T19:48:01+00:00
- Post Title: Re: Martial Empires / Seven Souls

Plugin its working perfect now, thanks Finale its a greath job.
## Post #34
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-07-22T01:50:23+00:00
- Post Title: Re: Martial Empires / Seven Souls

is there a way to get the textures to show on the LOS models in noesis?  i extracted all textures but it won't show. or maybe i'm missing something.

Here's an example:
## Post #35
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-07-22T17:43:02+00:00
- Post Title: Re: Martial Empires / Seven Souls

You have to load the texture-info file, but I don't want to have to load it everytime you view a model since it's a large file so I didn't write code to auto-assign.

You can manually assign textures if you want.
## Post #36
- Username: inspiredgurl
- Rank: advanced
- Number of posts: 46
- Joined date: Tue Nov 01, 2011 5:07 am
- Post datetime: 2012-07-23T00:27:25+00:00
- Post Title: Re: Martial Empires / Seven Souls

Thanks for the reply finale.  I didn't know noesis could load txt files, cool! I found a post of yours discussing about how to use the texture info file: [viewtopic.php?f=33&t=4582&start=1080](http://forum.xentax.com/viewtopic.php?f=33&t=4582&start=1080)


i don't mean to sound slow, but idk how to get noesis to find the textureinfo file. is there an option i'm missing that loads it, maybe?
## Post #37
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-28T18:55:20+00:00
- Post Title: Re: Martial Empires / Seven Souls

Hello comrades, i need some help to get the mesh from the VFS 

-----
My case is:

>> Extracted contain of chars.vfs using cmd (offzip.exe -a chars.vfs "C:\Samples" 0)

>> The extracted data extension is (.dat)

-----

At this point im stuck, how do i obtain the mesh files from those file.dat?


Please could somebody help ?
## Post #38
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-29T09:01:58+00:00
- Post Title: Re: Martial Empires / Seven Souls

Hello again,

Finally i found the way to extract correctly those files.

Isnt using offzip, i used QuickBMS with this script:
---------------
#quickbms script
#from chrrox and aluigi
open FDDE VFS 0
open FDDE INF 1

get id longlong 1
get files long 1
goto 0x48 1
for i = 0 < files
    getdstring name 0xD8 1
    get ZIPPED long 1
    get DUMMY long 1
    get offset longlong 1
    get zsize longlong 1
    get size longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    get TIMESTAMP longlong 1
    if ZIPPED == 0
        log name offset zsize
    else
        clog name offset zsize size
    endif
next i
---------------

Thanks anyway
## Post #39
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-29T14:14:10+00:00
- Post Title: Re: Martial Empires / Seven Souls

Hello to open every mesh only need modify the script and put this line:

```
select msh
skinMod = skin ()
addModifier msh skinMod

```


On the x2 parts where can find the "select msh"
## Post #40
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-08-29T22:14:05+00:00
- Post Title: Re: Martial Empires / Seven Souls

> Reply from Keygen
>
> Hello to open every mesh only need modify the script and put this line:
Code: Select allmsh = $s_*
select msh
skinMod = skin ()
addModifier msh skinMod


On the x2 parts where can find the "select msh"very interesting mate, but you can upload the full maxscript file attached here? really this would be great mate, many thanks for the discover thing.
## Post #41
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-30T10:44:29+00:00
- Post Title: Re: Martial Empires / Seven Souls

> Reply from CriticalError
>
> Keygen wrote:Hello to open every mesh only need modify the script and put this line:
Code: Select allmsh = $s_*
select msh
skinMod = skin ()
addModifier msh skinMod


On the x2 parts where can find the "select msh"


very interesting mate, but you can upload the full maxscript file attached here? really this would be great mate, many thanks for the discover thing.

Sure , here is
[7souls.zip](https://xentaxbackup.github.io/file/9654_7souls.zip)
## Post #42
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-30T10:46:15+00:00
- Post Title: Re: Martial Empires / Seven Souls

We need new script that able us to import .msh without bones , 

it crash on main characters so i cant obtain the warrior or the others models,

Somebody could help on this?

[](http://subefotos.com/ver/?f989dc557d4e7552d5660076d053a438o.png)

I tried use Noesis, it doesnt work to me.

I couldnt modify the script to ignore the error, would be good make a new script that import every mesh.
## Post #43
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-08-30T12:35:26+00:00
- Post Title: Re: Martial Empires / Seven Souls

Okey comrades, get ready to enjoy

i modify the script and the result is this:

[](http://subefotos.com/ver/?1167a01208e37a557ddd17573c8a283fo.png)


Here is the new script:
[7souls2.zip](https://xentaxbackup.github.io/file/9656_7souls2.zip)
## Post #44
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-09-03T13:16:37+00:00
- Post Title: Re: Martial Empires / Seven Souls

Somebody know a way to open the map files?


I want to do a mod in GTA with 7souls Maps


Thanks
## Post #45
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-09-03T13:23:02+00:00
- Post Title: Re: Martial Empires / Seven Souls

you can upload samples or just remake a new topic for map files, because this one is to old and no one check them.
## Post #46
- Username: Keygen
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 29, 2015 2:36 am
- Post datetime: 2015-09-06T16:55:15+00:00
- Post Title: Re: Martial Empires / Seven Souls

Here is the new POST: 


[viewtopic.php?f=16&t=13279](http://forum.xentax.com/viewtopic.php?f=16&t=13279)


Please check it out, if somebody know how open weapons and maps share it in that POST
