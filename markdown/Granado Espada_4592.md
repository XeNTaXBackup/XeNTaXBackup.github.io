## Post #1
- Username: omfgpota
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-12T11:57:48+00:00
- Post Title: Granado Espada

Here is a max script to load them into 3ds max with bones.
If someone wants to help me figure out the weighting ill add it to the max script.

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = GetOpenFileName caption:"Open Granado Espada Model File" types:"Granado Espada Model File(*.lma)|*.lma"
f = fopen fname "rb"   --open file in read only format


fn PrintOffset Var =
(
	local Var = Var
print ("This is the offset 0x" + (bit.intAsHex Var) as string)
	Var
)
fn PrintCount Var =
(
	local Var = Var
print ("This is the Count 0x" + (bit.intAsHex Var) as string)
	Var
)

fn Readword fstream = (
return readshort fstream #unsigned
)

fn ReadFixedString bstream fixedLen =
(
	local str = ""
	for i = 1 to fixedLen do
	(
		str += bit.intAsChar (ReadByte bstream #unsigned)
	)
	str
)

struct Mesh_Info_Struct
(
	Mesh_Name,vertstart,vertend,vertcount,facecount
)
struct Offset_Info_Struct
(
	Section_Start,Vert_Start,Face_Start,vertsize
)
total_size = getFileSize fname
print total_size
idstring = readlong f
id1 = readbyte f#unsigned
id2 = readbyte f#unsigned
id3 = readbyte f#unsigned
Type_0_offset_array =#()
Type_1_offset_array =#()
Type_2_offset_array =#()
Type_3_offset_array =#()
Type_3_2_offset_array =#()
Type_4_offset_array =#()
Type_5_offset_array =#()
Type_6_offset_array =#()
Type_7_offset_array =#()
Mesh_Name_array =#()
do (
type = readlong f
size = readlong f
type2 = readlong f
print type
print size
print type2
printoffset (ftell f)
if type == 0 do (

append Type_0_offset_array (ftell f)

)
if type == 1 do (
append Type_1_offset_array (ftell f)
)
if type == 2 do (
append Type_2_offset_array (ftell f)
)
if type == 3 do (
if type2 == 2 do (
append Type_3_offset_array (ftell f)
)
if type2 == 10000 do (
append Type_3_2_offset_array (ftell f)
)
)
if type == 4 do (
append Type_4_offset_array (ftell f)
)
if type == 5 do (
append Type_6_offset_array (ftell f)
)
if type == 6 do (
append Type_6_offset_array (ftell f)
)
if type == 7 do (
append Type_7_offset_array (ftell f)
)
fseek f size #seek_cur
)while (ftell f) != total_size
print Type_0_offset_array.count
print Type_1_offset_array.count
print Type_2_offset_array.count
print Type_3_offset_array.count
print Type_4_offset_array.count
print Type_5_offset_array.count
print Type_6_offset_array.count
print Type_7_offset_array.count

for a = 1 to Type_0_offset_array.count  do (
fseek f Type_0_offset_array[a]#seek_set
bone_name = readstring f
print bone_name
if isvalidnode (getNodeByName bone_name) != true then (
fseek f (0x28 - (bone_name.count + 1))#seek_cur
bone_parent = readstring f
if bone_parent != "" do (
fseek f (0x28 - (bone_parent.count + 1))#seek_cur
)
if bone_parent == "" do (
fseek f 0x27 #seek_cur
)
print (getNodeByName bone_name)
if (getNodeByName bone_name) != "undefined" do (
fseek f 0x28#seek_cur
m11 = readfloat f; m12 = readfloat f; m13 = readfloat f; m14 = readfloat f
m21 = readfloat f; m22 = readfloat f; m23 = readfloat f; m24 = readfloat f
m31 = readfloat f; m32 = readfloat f; m33 = readfloat f; m34 = readfloat f
m41 = readfloat f; m42 = readfloat f; m43 = readfloat f; m44 = readfloat f
tfm = matrix3 [m11,m12,m13] [m21,m22,m23] [m31,m32,m33] [m41,m42,m43]
	newBone = bonesys.createbone	\
				  tfm.row4	\
				  (tfm.row4 + 0.01 * (normalize tfm.row1)) \
				  (normalize tfm.row3)
			newBone.name   = bone_name
			newBone.width  = 0.3
			newBone.height = 0.3
			newBone.transform = inverse tfm
			newBone.wirecolor = yellow
			newbone.showlinks = true
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()
			newBone.name   = bone_name
			newBone.width  = 0.3
			newBone.height = 0.3
			newBone.setBoneEnable false 0
			newBone.pos.controller      = TCB_position ()
			newBone.rotation.controller = TCB_rotation ()

 if (bone_parent != "") then (
 newBone.parent = getNodeByName bone_parent
 )
 )
)
)
for a = 1 to Type_7_offset_array.count do (
fseek f Type_7_offset_array[a]#seek_set
Mesh_name = readstring f
fseek f (0x28 - (Mesh_name.count + 1))#seek_cur
if Mesh_name != "env_normal" do (

append Mesh_Name_array Mesh_name 
)
print Mesh_name
print "-----------------"
)
for a = 1 to Type_4_offset_array.count do (
fseek f Type_4_offset_array[a]#seek_set
fseek f -8#seek_cur
tsize = readlong f
t2 = readlong f
unk01 = readlong f
t4_count = (tsize / 9)
for b = 1 to t4_count do (
type = readbyte f#unsigned
bone_id = readlong f
weight = readfloat f
printoffset type
print bone_id
print weight
	print "----------"
	
)
printoffset (ftell f)
)

for a = 1 to Type_3_offset_array.count do (
fseek f Type_3_offset_array[a]#seek_set
	
unk01 = readlong f
unk02 = readlong f
unk03 = readlong f
unk04 = readlong f
Mesh_Count = readlong f
unk06 = readlong f
for c = 1 to Mesh_Count do (
unk07 = readlong f
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()	

Fcount = (readlong f) / 3
Vcount = readlong f
for i = 1 to Vcount do (   --* number of verts count
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
        --since UV in Max are in point3 format, so we add 0 for z value
nx = readlong f    --read Normal ??
ny = readlong f
nz = readlong f
--append Normal_array [nx,ny,nz] --save normals to Normal_array
tu = readfloat f     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
b1 = readlong f
)

for k = 1 to Fcount do (
f1 = (readlong f) + 1  --read face indices, games are start form 0, but Max start from 1
f2 = (readlong f) + 1  --so we add 1 to each index
f3 = (readlong f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)

msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = Mesh_Name_array[a]
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
)	
)


for a = 1 to Type_3_2_offset_array.count do (
fseek f Type_3_2_offset_array[a]#seek_set
	
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()	

unk01 = readlong f
unk02 = readlong f
unk03 = readlong f
unk04 = readlong f
unk05 = readlong f
unk06 = readbyte f
Mesh_Name = readstring f
fseek f (0x107 - (Mesh_name.count + 1))#seek_cur

Fcount = (readlong f) / 3
Vcount = readlong f
for i = 1 to Vcount do (   --* number of verts count
vx = readfloat f     --read xyz coordinates
vy = readfloat f
vz = readfloat f
append Vert_array [vx,vy,vz] --save verts to Vert_array
        --since UV in Max are in point3 format, so we add 0 for z value
nx = readlong f    --read Normal ??
ny = readlong f
nz = readlong f
--append Normal_array [nx,ny,nz] --save normals to Normal_array
tu = readfloat f     --read UV float value
tv = (readfloat f) * -1 
append UV_array [tu,tv,0]  --save UVs to UV_array
b1 = readfloat f 
b2 = readfloat f 
b3 = readfloat f 
)

for k = 1 to Fcount do (
f1 = (readlong f) + 1  --read face indices, games are start form 0, but Max start from 1
f2 = (readlong f) + 1  --so we add 1 to each index
f3 = (readlong f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)

msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = Mesh_Name
for j = 1 to UV_array.count do setTVert msh j UV_array[j]
for j = 1 to Face_array.count do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
	
)
fclose f



```
## Post #2
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-06-14T11:19:09+00:00
- Post Title: Granado Espada

that is pure coolness chrrox
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-06-29T15:29:10+00:00
- Post Title: Granado Espada

look at :
line 167-179
line 231
line 261
[import with weight.rar](https://xentaxbackup.github.io/file/3181_import with weight.rar)
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-30T02:02:42+00:00
- Post Title: Granado Espada

Thanks I will try this as soon as i can.
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2010-07-11T15:32:43+00:00
- Post Title: Granado Espada

The contents of this post was deleted because of possible forum rules violation.
[image.jpg](https://xentaxbackup.github.io/file/3227_image.jpg)
## Post #6
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2010-11-21T20:36:34+00:00
- Post Title: Granado Espada

Nice work chrrox. Thanks.
## Post #7
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-01-28T19:40:06+00:00
- Post Title: Granado Espada

The contents of this post was deleted because of possible forum rules violation.


Upadate: 2014-07-01

[http://www.mediafire.com/download/82wha ... BPC%5D.zip](http://www.mediafire.com/download/82wha658q4i7dg8/GranadoEspada%5BPC%5D.zip)
## Post #8
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2011-04-08T22:52:06+00:00
- Post Title: Granado Espada

Havent had the chance to try this plugin until now but just wanted to say it works great  Are you planning animations to?
## Post #9
- Username: almondega
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Jan 03, 2010 6:39 am
- Post datetime: 2011-04-17T14:31:18+00:00
- Post Title: Granado Espada

Wow!

Animations support would be amazing.
## Post #10
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2011-04-26T10:18:29+00:00
- Post Title: Granado Espada

to Szkaradek123 
Your script (import with weight.rar [2.32 KiB]) is incorrect. Some language mistakes (((
## Post #11
- Username: gv2mancia
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jun 16, 2011 10:10 pm
- Post datetime: 2011-11-22T13:49:34+00:00
- Post Title: Granado Espada

could you update the 3dsmax script that import with weight please?

Thanks chroxx and Szkaradek123 so much
## Post #12
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2012-05-15T22:48:58+00:00
- Post Title: Granado Espada

> Reply from Szkaradek123
>
> look at :
line 167-179
line 231
line 261

Hate to bring up a closed topic but I keep getting a maxscript filein exception error when I try this with 2012.
Where could I get the fix for this?
## Post #13
- Username: zdsmdbh
- Rank: n00b
- Number of posts: 19
- Joined date: Wed Nov 13, 2013 10:03 am
- Post datetime: 2014-04-30T12:53:07+00:00
- Post Title: Granado Espada

Sorry to bump this old topic
Model there are really nice,hope somebody will realease a script with weight
Here's some sample files
[http://1drv.ms/1hRHOlY](http://1drv.ms/1hRHOlY)

Thanks
## Post #14
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-02T22:02:09+00:00
- Post Title: Granado Espada

> Reply from Szkaradek123 ↑Sat Jan 29, 2011 3:40 am at Sat Jan 29, 2011 3:40 am
>
> 
The contents of this post was deleted because of possible forum rules violation.


Upadate: 2014-07-01

http://www.mediafire.com/download/82wha ... BPC%5D.zip

. Does this still work? 

I tried using the old blender  script. I couldn’t get it to work :/. Can someone update it?^^
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-03T15:13:58+00:00
- Post Title: Granado Espada

No update required when using script in zip as of Fri Jan 28, 2011 8:40 pm.

It's works as expectend in case you use blender 2.49b. (Other version DON'T do. Was mentioned in nearly every thread where Mariusz presented his scripts.)
.



npc_angie_set1-lma.jpg (123.38 KiB) Viewed 120 times
## Post #16
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-03T18:59:24+00:00
- Post Title: Re: Granado Espada

> Reply from shakotay2 ↑Wed Aug 03, 2022 11:13 pm at Wed Aug 03, 2022 11:13 pm
>
> 
No update required when using script in zip as of Fri Jan 28, 2011 8:40 pm.

It's works as expectend in case you use blender 2.49b. (Other version DON'T do. Was mentioned in nearly every thread where Marius presented his scripts.)
.
npc_angie_set1-lma.jpg

How do i even use the script
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-03T20:07:02+00:00
- Post Title: Re: Granado Espada

Load Blender249-GranadoEspadaImporter-2014-07-01.blend into blender 2.49b.
Then (with the cursor in the left script (Text) window) press Alt-p.

Select a lma - geometry file, then press import button.
## Post #18
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-08-05T15:57:51+00:00
- Post Title: Re: Granado Espada

> Reply from shakotay2 ↑Wed Aug 03, 2022 11:13 pm at Wed Aug 03, 2022 11:13 pm
>
> 
It's works as expectend in case you use blender 2.49b
I adapted the plugin for Noesis. while many have problems with the old Blender. 

> Reply from Brekkez ↑Wed Aug 03, 2022 6:02 am at Wed Aug 03, 2022 6:02 am
>
> 
Can someone update it?^^
try with it

[fmt_lma.zip](https://xentaxbackup.github.io/file/22591_fmt_lma.zip)
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-05T16:39:51+00:00
- Post Title: Re: Granado Espada

> Reply from Durik256 ↑Fri Aug 05, 2022 11:57 pm at Fri Aug 05, 2022 11:57 pm
>
> I adapted the plugin for Noesis.Yeah, cool! 

> while many have problems with the old Blender.There's some dozens of Mariusz' blender 2.49b scripts and most of them handle animations. (And usually they do work with the format versions they were created for.)
Once you're familiar with alt-p they work like a charm.  

But yes, maybe it's time to "convert" them to Noesis.
## Post #20
- Username: hiera0035
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 06, 2022 4:17 am
- Post datetime: 2022-08-05T21:24:13+00:00
- Post Title: Re: Granado Espada

> Reply from shakotay2 ↑Sat Aug 06, 2022 12:39 am at Sat Aug 06, 2022 12:39 am
>
> 
Durik256 wrote: ↑Fri Aug 05, 2022 11:57 pmI adapted the plugin for Noesis.Yeah, cool! 
 while many have problems with the old Blender.  There's some dozens of Mariusz' blender 2.49b scripts and most of them handle animations. (And usually they do work with the format versions they were created for.)
Once you're familiar with alt-p they work like a charm.  

But yes, maybe it's time to "convert" them to Noesis.

Hi i know this is entirely different from the post but 

I'm importing to view LMA files through 3d object converter
and manage to load it's texture and export it through .obj for blender
but when i load it on blender its just a tiny dot. any idea what seems to be the issue?
i saw on the internet that its a scaling issue but i tried to reduce/increase it size its still the same.

also is it possible to merge all the body part to 1 LMA file?
## Post #21
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-07T17:28:50+00:00
- Post Title: Re: Granado Espada

> Reply from hiera0035 ↑Sat Aug 06, 2022 5:24 am at Sat Aug 06, 2022 5:24 am
>
> 
shakotay2 wrote: ↑Sat Aug 06, 2022 12:39 am
Durik256 wrote: ↑Fri Aug 05, 2022 11:57 pmI adapted the plugin for Noesis.Yeah, cool! 
 while many have problems with the old Blender.  There's some dozens of Mariusz' blender 2.49b scripts and most of them handle animations. (And usually they do work with the format versions they were created for.)
Once you're familiar with alt-p they work like a charm.  

But yes, maybe it's time to "convert" them to Noesis.


Hi i know this is entirely different from the post but 

I'm importing to view LMA files through 3d object converter
and manage to load it's texture and export it through .obj for blender
but when i load it on blender its just a tiny dot. any idea what seems to be the issue?
i saw on the internet that its a scaling issue but i tried to reduce/increase it size its still the same.

also is it possible to merge all the body part to 1 LMA file?

The old method works fine. Save it as .blend and open it up in a newer version of blender  

I made this using the old blender.

> Reply from Durik256 ↑Fri Aug 05, 2022 11:57 pm at Fri Aug 05, 2022 11:57 pm
>
> 
shakotay2 wrote: ↑Wed Aug 03, 2022 11:13 pm
It's works as expectend in case you use blender 2.49b

I adapted the plugin for Noesis. while many have problems with the old Blender. 
Brekkez wrote: ↑Wed Aug 03, 2022 6:02 am
Can someone update it?^^

try with it

amazing. Is it possible make it work on all lma files?, opening any other lma’s will result in the same error message 


Uploaded a Sample file
[barrack02_chair01_00.rar](https://xentaxbackup.github.io/file/22599_barrack02_chair01_00.rar)
## Post #22
- Username: hiera0035
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 06, 2022 4:17 am
- Post datetime: 2022-08-09T19:44:43+00:00
- Post Title: Re: Granado Espada

> Reply from Brekkez ↑Mon Aug 08, 2022 1:28 am at Mon Aug 08, 2022 1:28 am
>
> 
hiera0035 wrote: ↑Sat Aug 06, 2022 5:24 am
shakotay2 wrote: ↑Sat Aug 06, 2022 12:39 am
Yeah, cool!  
There's some dozens of Mariusz' blender 2.49b scripts and most of them handle animations. (And usually they do work with the format versions they were created for.)
Once you're familiar with alt-p they work like a charm.  

But yes, maybe it's time to "convert" them to Noesis.


Hi i know this is entirely different from the post but 

I'm importing to view LMA files through 3d object converter
and manage to load it's texture and export it through .obj for blender
but when i load it on blender its just a tiny dot. any idea what seems to be the issue?
i saw on the internet that its a scaling issue but i tried to reduce/increase it size its still the same.

also is it possible to merge all the body part to 1 LMA file?





Hi, i'm trying the old way but when i'm launching the script on 2.49B there's a error showing and the script wont play. perhaps can u provide a step by step on how it works?
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-09T20:06:08+00:00
- Post Title: Re: Granado Espada

> Reply from shakotay2 ↑Thu Aug 04, 2022 4:07 am at Thu Aug 04, 2022 4:07 am
>
> In case it doesn't work for you provide a decent description (what did you do exactly, which lma file did you try, which was the error message, screenshots). Have a look at the blender console window which opens additional to the blender gui.

For the chair sample further analysis is required (barrack02_chair01_00\barrack02_chair01_00.lma):

Traceback (most recent call last):
  File "GranadoEspada.py", line 131, in openFile
  File "GranadoEspada.py", line 67, in lmaParser
IndexError: list index out of range

-------------------

Format of static mesh is quite simple, though:
.



barrack02_chair01_00-lma.jpg (112.61 KiB) Viewed 232 times
## Post #24
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-09T23:16:34+00:00
- Post Title: Re: Granado Espada

I opened the chair file the same way i opened the characters lma.. And i got the error message ^ in my previous post .  Idk Why the rest of then dont work though
## Post #25
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-10T04:35:15+00:00
- Post Title: Re: Granado Espada

> Reply from Brekkez ↑Wed Aug 10, 2022 7:16 am at Wed Aug 10, 2022 7:16 am
>
> 
I opened the chair file the same way i opened the characters lma.. And i guy the error message ^ in my previous post .  Idk Why the rest of then dont work thoughPrimary aim of that script was not to handle static meshes, obviously. It was designed to work with character meshes, I guess. Including the bones, so no time for complaining, is it?
## Post #26
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-10T08:26:51+00:00
- Post Title: Re: Granado Espada

> Reply from shakotay2 ↑Wed Aug 10, 2022 12:35 pm at Wed Aug 10, 2022 12:35 pm
>
> 
Brekkez wrote: ↑Wed Aug 10, 2022 7:16 am
I opened the chair file the same way i opened the characters lma.. And i guy the error message ^ in my previous post .  Idk Why the rest of then dont work though
Primary aim of that script was not to handle static meshes, obviously. It was designed to work with character meshes, I guess. Including the bones, so no time for complaining, is it?
## Post #27
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-10T18:13:12+00:00
- Post Title: Re: Granado Espada

@Brekkez: feel free to upload another static model. Chances are high that I can integrate them into my Make_H2O project.
## Post #28
- Username: Brekkez
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Oct 06, 2016 12:56 am
- Post datetime: 2022-08-11T23:47:22+00:00
- Post Title: Re: Granado Espada

here's a random static lma
[bedel_basic_tower_001.rar](https://xentaxbackup.github.io/file/22628_bedel_basic_tower_001.rar)
## Post #29
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-12T19:01:37+00:00
- Post Title: Re: Granado Espada

Here's a tiny tool. Tested with few static mesh .lma samples only. Can handle multiple sub meshes now.
.


 GranadoEsp_multi_mesh.zip
(72.15 KiB) Downloaded 20 times



Close the app before accessing Makeobj_log.obj.
Further sub meshes, if any, located in the .lma directory (in case it's different from the app's dir.)

For some models (which lack a signature the tool relies on) still  one mesh is extracted only, bedel_basic_tower_001.lma for example.
## Post #30
- Username: GranadoEspadaFan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 28, 2022 3:36 am
- Post datetime: 2022-08-16T07:27:43+00:00
- Post Title: Re: Granado Espada

I have source code for GE and models, possible to make a converter from obj to lma and vice versa if I hand out source?
## Post #31
- Username: GranadoEspadaFan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 28, 2022 3:36 am
- Post datetime: 2022-08-16T07:32:13+00:00
- Post Title: Re: Granado Espada

Please take a look there is importers source for Maya and 3DStudio
[https://pixeldrain.com/u/575BFuYN](https://pixeldrain.com/u/575BFuYN)
## Post #32
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-08-30T09:17:00+00:00
- Post Title: Re: Granado Espada

> Reply from GranadoEspadaFan ↑Tue Aug 16, 2022 3:27 pm at Tue Aug 16, 2022 3:27 pm
>
> 
I have source code for GE and models, possible to make a converter from obj to lma and vice versa if I hand out source?Suiting MAXSDK required for compiling the source. Otherwise the source (export.cpp for example) only could help providing some lma specs.

Converter "obj to lma"? Hard to achieve. (Count the threads labled with "obj to [any]_3D_format conversion", you won't find too many.)

edit: updated the tool here

> Reply from shakotay2 ↑Sat Aug 13, 2022 3:01 am at Sat Aug 13, 2022 3:01 am
>
> to handle multiple sub meshes of static meshes, if any.
.



GranadoEspada_multi_mesh.jpg (31.78 KiB) Viewed 67 times
