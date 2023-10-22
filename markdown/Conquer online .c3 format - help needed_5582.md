## Post #1
- Username: Shinokaze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 18, 2010 6:01 pm
- Post datetime: 2010-12-19T12:06:57+00:00
- Post Title: Conquer online .c3 format - help needed

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: pao com ovo
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-19T14:20:23+00:00
- Post Title: Conquer online .c3 format - help needed

Here you go this should work i tried it on a lot of meshes and they all seemed to work. I am not sure what you will learn from this they are very low polly and look like collision meshes.
3ds max script.


```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = getOpenFileName \ 
caption:"Open C3 Model File" \
types:"C3 Model File(*.c3)|*.c3" \
historyCategory:"C3ObjectPresets"
f = fopen fname "rb"

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
 	fn convertTo32 input16 = (
 		inputAsInt = input16
 		sign = bit.get inputAsInt 16
 		exponent = (bit.shift (bit.and inputAsInt (bit.hexasint "7C00")) -10) as integer - 16
 		fraction = bit.and inputAsInt (bit.hexasint "03FF")
 		if sign==true then sign = 1 else sign = 0
 		exponentF = exponent + 127
 		--Ouput 32 bit integer representing a 32 bit float
 		outputAsFloat = bit.or (bit.or (bit.shift fraction 13) (bit.shift exponentF 23)) (bit.shift sign 31)
 		--Output Check	
 		return bit.intasfloat outputasfloat
 	)

fn ReadHalfFloat fstream = (
return convertTo32(Readshort fstream)
)
maxlen=(getfilesize fname)

Magic1 = ReadFixedString f 0x10
Magic2 == "PHY"
do (
Magic2 = ReadFixedString f 0x3
Magic = readbyte f#unsigned
SectSize = readlong f
test = (ftell f)
nsize = readlong f
MeshName = ReadFixedString f nsize
null = readlong f
vertcount = readlong f
null = readlong f

Vert_array = #()
UV_array = #()
Face_array = #()
if magic == 0x20 Do (
for a = 1 to vertcount Do (
vx = readfloat f 
vy = readfloat f
vz = readfloat f
fseek f 0x24#seek_cur
tu = (readfloat f) * 1
tv = (readfloat f) * -1
fseek f 0x14#seek_cur
append Vert_array [vx,vz,vy]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)	
)
if magic == 0x34 Do (
for a = 1 to vertcount Do (
vx = readfloat f 
vy = readfloat f
vz = readfloat f
tu = (readfloat f) * 1
tv = (readfloat f) * -1
fseek f 0x14#seek_cur
append Vert_array [vx,vz,vy]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
)
if magic == 0x33 Do (
for a = 1 to vertcount Do (
vx = readfloat f 
vy = readfloat f
vz = readfloat f
tu = (readfloat f) * 1
tv = (readfloat f) * -1
fseek f 0x20#seek_cur
append Vert_array [vx,vz,vy]
--append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
)

FaceCount = readlong f
null = readlong f
for a = 1 to FaceCount Do (
f1 = (readshort f) + 1
f2 = (readshort f) + 1
f3 = (readshort f) + 1
append Face_array [f1,f2,f3] --save faces to Face_array
)

msh = mesh vertices:Vert_array faces:Face_array
msh.numTVerts = UV_array.count
buildTVFaces msh
for j = 1 to UV_array.count     do setTVert  msh j UV_array[j]
for j = 1 to Face_array.count   do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]
printoffset (ftell f)
fseek f (test + SectSize)#seek_set
printoffset (ftell f)
Magic2 = ReadFixedString f 0x3
fseek f -3#seek_cur
) while Magic2 == "PHY" 
fclose f     --close file
actionMan.executeAction 0 "311"  -- Tools: Zoom Extents All Selected

```

[horse.png](https://xentaxbackup.github.io/file/3699_horse.png)
## Post #3
- Username: Shinokaze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 18, 2010 6:01 pm
- Post datetime: 2010-12-20T00:13:13+00:00
- Post Title: Conquer online .c3 format - help needed

wow, great work chrrox! Thank you for taking the time to decode this format for me.
I know it will be very educational and hopfully useful for others as well.

I don't have max unfortunately would it be possible to rewrite an importer for blender?
Thanks you again, I appreciate your help very much! and sorry for this other small request.
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-20T00:52:04+00:00
- Post Title: Conquer online .c3 format - help needed

The format was fairly basic. I do not know how to code for blender sorry ma-bee some can help you there.
## Post #5
- Username: Shinokaze
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Dec 18, 2010 6:01 pm
- Post datetime: 2010-12-20T16:16:14+00:00
- Post Title: Conquer online .c3 format - help needed

hello again chrrox, Ive gone ahead and downloaded the latest trial version of max after playing around with it for a few minutes I'm able to open and run a script but after selecting the .c3 file I wish to open it comes back with these error message.


```
--Runtime error; buildTVFaces; mesh has no texture verticels - $Ditable_Mesh:Objec001 @ [0.000000,0.000000,.000000]
```


```
--No'+' fuction for underfinded
```


Is it max 2011? if so ill have to test my script with it max 2011 can be very picky with spaces and other things.
also make sure the file you want to import contains a mesh alot of the files you posted were just animations.
## Post #6
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-12-23T17:08:41+00:00
- Post Title: Conquer online .c3 format - help needed

Shinokaze,

The posted script does not like all .c3 files.


I added the .c3 loader module to my program and I released the 3D Object Converter 4.433 update package now.
[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)

Please install the v4.40 or use the v4.40 portable version.
After that you must upgrade to the latest version (v4.433) using the Help/Check for updates... function.
