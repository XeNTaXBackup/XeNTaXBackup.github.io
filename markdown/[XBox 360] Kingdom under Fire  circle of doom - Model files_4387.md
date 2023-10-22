## Post #1
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-04-25T22:11:31+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

Hi all, i successfully extracted the characters data files from the game using the bms script that Chrrox has kindly posted :
[viewtopic.php?f=10&t=4361](http://forum.xentax.com/viewtopic.php?f=10&t=4361)

Here is an archive sample containing Celine's character files. 
[PC_CL.rar - 34.24MB](http://www.zshare.net/download/75379747508986a0/)
There are 4 formats types .skin, .bm, .bs and .36t
if someone can actually look at it, i will be very grateful.
Thank you.
## Post #2
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-04-28T19:12:13+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

> Reply from noazett
>
> Hi all, i successfully extracted the characters data files from the game using the bms script that Chrrox has kindly posted :
viewtopic.php?f=10&t=4361

Here is an archive sample containing Celine's character files. 
PC_CL.rar - 34.24MB
There are 4 formats types .skin, .bm, .bs and .36t
if someone can actually look at it, i will be very grateful.
Thank you.
36T = texture
.bm = model
.bs = skeleton
.ba=animation
.fxa = bone effects
.txt = collision mesh or bones related
.SKIn = materials
## Post #3
- Username: noazett
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-04-28T20:46:15+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

fxa is facial animation
## Post #4
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-04-29T20:57:11+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

thank you guys for your replies i really appreciate it. now i would like to know how to convert a bm files into an obj file. i tried to follow the instructions given in the tutorial concerning shaiya's model conversion, so I started with a small size bm file for my learning ([http://www.sendspace.com/file/jozt0m](http://www.sendspace.com/file/jozt0m)) however i still can't find the vertex section in the file's encryption.
if someone can make a converter for it that would be great, otherwise just help me understand the file structure so i can learn to do it myself.
Thx again
## Post #5
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-05-04T20:59:47+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

anyone can help me on this?
please
## Post #6
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-05-29T20:52:29+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

> Reply from noazett
>
> anyone can help me on this?
please


All of the .bm meshes do not have the same format, but all use tristripes in a similar manner.

The first part of each mesh is where the Vertex, Normal Maps, and TextureMaps are.
Some meshes store this in 40 Byte Arrays, some in 32 Byte Arrays, and some in 52 Byte Arrays, with possible additional ways.
However while the Vertexes are in standard IEEE Floating Point format, the Normal and Texture Maps are not.
After the arrays there are the tristrips that are separated by "FF FF"
## Post #7
- Username: noazett
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-05-29T20:56:10+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

I have a max script i made for this its not finished yet but it works.

```
	heapSize = 200000000 -- allow ~ 40 MB instead of just 7.5 MB. Prevents "Runtime Error: Out of scripter memory"

fname = GetOpenFileName caption:"Open Kingdom Under Fire:Circle of Doom Model File" types:"Kingdom Under Fire:Circle of Doom Model File(*.bm)|*.bm"
f = fopen fname "rb"   --open file in read only format


fn floatSwap2 f = 
(
	i = bit.floatAsInt f
	h = bit.intashex i
	while h.count < 8 do h = "0" + h
	s = (substring h 7 2) + (substring h 5 2) + (substring h 3 2) + (substring h 1 2)
	bit.intAsFloat (bit.hexasint s)
)	
fn ReadBEfloat fstream = (
return floatSwap2(readfloat fstream)
)
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

fn ReadBEword fstream = (
return (bit.swapBytes (readshort fstream #unsigned) 1 2)
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

fn ReadBEHalfFloat fstream = (
return convertTo32(ReadBEword fstream) * 2
)
 

fn ReadBElong fstream = (
long = readlong fstream
long = bit.swapBytes long 1 4
long = bit.swapBytes long 2 3
return long
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



unk1 = ReadBElong f
unk2 = ReadBElong f
unk3 = ReadBElong f
MeshCount = ReadBElong f
unk5 = ReadBElong f
unk6 = ReadBElong f
for a = 1 to MeshCount Do (
	
Vert_array = #()    --define arrays for verts, normals, UV and Faces
Normal_array = #()
UV_array = #()
Face_array = #()

Offset_start = (ReadBElong f) - 24
unk8 = ReadBElong f
unk9 = ReadBElong f
FaceType = ReadBElong f
VertCount = ReadBElong f
FaceCount = ReadBElong f
fseek f Offset_start#seek_cur
Scen_Name_Size = ReadBElong f
Scene_Name = ReadString f
Material_Name_Size = ReadBElong f
Material_Name = ReadString f
Mesh_Name_Count = ReadBElong f
Mesh_Name = Readstring f
fseek f (0xFF - Mesh_Name.count)#seek_cur
fseek f 0x34#seek_cur
Used_Textures1 = ReadBElong f
Used_Textures2 = ReadBElong f
Used_Textures3 = ReadBElong f
fseek f 0x2C#seek_cur
fseek f 0xDF2#seek_cur
PrintOffset (ftell f)
byte1 = readbyte f#unsigned
byte2 = readbyte f#unsigned
byte3 = readbyte f#unsigned
byte4 = readbyte f#unsigned
byte5 = readbyte f#unsigned
byte6 = readbyte f#unsigned
byte7 = readbyte f#unsigned
byte8 = readbyte f#unsigned
byte9 = readbyte f#unsigned
byte10 = readbyte f#unsigned
byte11 = readbyte f#unsigned
byte12 = readbyte f#unsigned
byte13 = readbyte f#unsigned
byte14 = readbyte f#unsigned
fseek f 0x3C#seek_cur
type = ReadBElong f
type1 = ReadBElong f
type2 = ReadBElong f
if type == 0x7 and type2 == 40 do (
fseek f 0x18#seek_cur
)
if type == 0x7 and type2 == 30 do (
fseek f 0x18#seek_cur
)
if type == 0x6 and type2 == 20 do (
fseek f 0x18#seek_cur
)
if type == 0x6 and type2 == 10 do (
fseek f 0xC#seek_cur
)
if type == 17 and type2 == 1 do (
fseek f 0x18#seek_cur
)
if type == 18 do (

)
PrintOffset (ftell f)
for c = 1 to VertCount Do (
if type == 18 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
)
if type == 17 and type2 == 1 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
fseek f 0x10#seek_cur
)
if type == 0x7 and type2 == 40 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
fseek f 0x18#seek_cur
)
if type == 0x7 and type2 == 30 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
fseek f 0x14#seek_cur
)
if type == 0x6 and type2 == 10 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
fseek f 0x4#seek_cur
)
if type == 0x6 and type2 == 20 do (
vx = ReadBEfloat f  --read xyz coordinates
vy = ReadBEfloat f
vz = ReadBEfloat f
nx = ReadBEfloat f 
ny = ReadBEfloat f
nz = ReadBEfloat f
tu = ReadBEHalfFloat f
tv = ReadBEHalfFloat f * -1
fseek f 0xC#seek_cur
)
append Vert_array [vx,vy,vz] --save verts to Vert_array
 --append Normal_array [nx,ny,nz]
append UV_array [tu,tv,0]
)
FaceCount2 = ReadBElong f
facestart = (ftell f)
print FaceType
if FaceType == 3 do (
for b = 1 to FaceCount2 do (
f1 = ReadBEword f + 1
f2 = ReadBEword f + 1
f3 = ReadBEword f + 1
append Face_array [f1,f2,f3]
)
)
if FaceType == 4 do (
StartDirection = -1
f1 = (ReadBEword f) + 1
f2 = (ReadBEword f) + 1  
FaceDirection = StartDirection
Do (
f3 = (ReadBEword f)
if (f3==0xFFFF) then (
f1 = (ReadBEword f) + 1
f2 = (ReadBEword f) + 1
FaceDirection = StartDirection   
) else (
f3 += 1
FaceDirection *= -1
if (f1!=f2)AND(f2!=f3)AND(f3!=f1) then (
if FaceDirection > 0 then append Face_array [f1,f2,f3]
else append Face_array [f1,f3,f2]
)
f1 = f2
f2 = f3
)  
)while (ftell f) != (facestart + (FaceCount2 * 2))
)
PrintOffset (ftell f)
fseek f 0x18#seek_cur
if type == 0x7 do (
bonecount = ReadBElong f
for i = 1 to bonecount Do (
Bone_Name_Size = ReadBElong f	
Bone_Name = readstring f
)
)
if type == 0x6 do (
bonecount = ReadBElong f
for i = 1 to bonecount Do (
Bone_Name_Size = ReadBElong f	
Bone_Name = readstring f
)
)
msh = mesh vertices:Vert_array faces:Face_array   --build mesh
msh.numTVerts = UV_array.count
buildTVFaces msh
msh.name = Mesh_Name
for j = 1 to UV_array.count  do setTVert msh j UV_array[j]
for j = 1 to Face_array.count  do setTVFace msh j Face_array[j]
for j = 1 to Normal_array.count do setNormal msh j Normal_array[j]


)

fclose f

```
## Post #8
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-05-31T20:14:42+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

Thanks furryfan for your post  i am sure this will help me a lot understanding the format now, and many thanks to you chrrox for sharing your script. Big up! as usual   
Now, i hope someone will find a way to read the textures files, but until then i've decided to post some screenshots with simple colors objects from max and show how these models are well made...seriously this game is unfortunatly underrated   

[](http://s930.photobucket.com/albums/ad150/noazett/kuf%20extact%20test/?action=view&current=celine.jpg) [](http://s930.photobucket.com/albums/ad150/noazett/kuf%20extact%20test/?action=view&current=leinhart.jpg) [](http://s930.photobucket.com/albums/ad150/noazett/kuf%20extact%20test/?action=view&current=morene.jpg)
## Post #9
- Username: AceAngel
- Rank: veteran
- Number of posts: 115
- Joined date: Mon Feb 09, 2009 12:45 am
- Post datetime: 2010-05-31T20:44:32+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

They're going to release KUF2 on PC and X360, and all the characters are going to be included as well.

So who knows? Maybe the PC version will be easier to pop open at the end of the day.
## Post #10
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2010-05-31T21:26:29+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

yes and i am looking forward to get it, it looks really promising
## Post #11
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-28T09:36:56+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

maxscript for textures, needs the 360 sdk tool to process the textures

```
/*
　　　　　　　　　　　　　　 　 ／　　　　　｀y　´　　　 　 　 　 　 　 　 　 　 　 |
　　　　　 　 　 　 　 　 　 ／　　　 　 　 , '　　　　　　　　　　 　 　 　 　 　 　 |
　　　　　　　　　 　 　 ／　　＿＿＿__/ _　　-―――――＝＝== ､＿_　　:!
　　　　 ＿＿＿__　,_.′_'"￣　 　 　 / _　　　　　　　　 　 ヾ＞'￣￣￣`ヾ、 |
　　　 ！r､――.､〉∠´　　_　　 ￣｀,'"　　　　　　　　　　／　　　　　 ／7ヘに)､
　　　　 ＼＼ イ/1｢二￣ _　　　＿__ 　 　 　 　 　 　 ／　　　　　　　| ./ .//./｢｀＼
　　　　　_｣＞`7　{｢ ﾌ￣,. -　　 ;´:i￣:: : .: . . .　　 ／　　　　 　 　 　 |∧// .| |＿〉_〉
.　 　 ／ 1「ﾌ/　　∨ ／　　　　:::::i::::::::::::::::::: : :.／　　　　　　　　　 　 >ァ'　 ヽヽ￣
　 ／ ′／ｲ′　　∨=__　　 　 ::::i!::::::::::::::: :: ,."　　　　　　　　　　 ／／ 　 　 |＼＼
. / /　 / /.′　　　 ヽ⌒　.: :. .. ::::i!:::::::::::::::〃　　　　　　　　　　／ /　　 　 　 !　 〉 〉
〈._」 　 ! :! !　　　　　　＼:: .: .:: :: :::ヽ::::::::::〃　　　　　　　　　　/　./　　　　 　 |／／
　　 　 |_｣ ! 　 　 　 　 　 ヽ:. :: ::.,:::::::＼::ｲ′　　　　　　　　　　`ｰ′　　 　 　 i／
.　　　　　 i　　　 　 　 　 　 ＼'"::::::ヽ:＼{　　　　　　　　　　　　　　　　　　　　|
　　　　　　!　　　　　　　　　 　 `.＜':;:::::::ﾍ 　 　 　 ,...　　　　　　　　　　 　 　 !
.　 　 　 　 ',　　　　　　　 　 　 　 　 ヽ::ヾ:::ヽ　,　'´　　　　　　　　　　　 　 　 l
.　　　 　 　 '　　　　　　　　　　　　　, '´` ｰ→　　　　　　　　　　　　　　　　　!
　　　　　　　 ' ,　　　　　　　　　　　　　　　y′　　　　　　　 　 　 　 　 　 　 l
　 　 　 　 　 　 ' ,　 　 　 　 　 　 　 　 　 /　　　　　　　　　　　　　　　　　　l
　　　　　 　 　 　 ＼　　　　　　　　　　　,′　　　　　　　　　　　　　　 　 　 l
　　　　　　　　 　 　 ヽ　　　　　　　　　 ,　　　　　　　　　　　　　　　　　　　! 
*/
--===========================================================================
-- fsource="N:\\_3DMODELS\\Ripped\\Circle of Doom\\mainres\\Data\\char\\PC_CL\\test\\test2\\LOD_PC_CL_0_body.36t"

mkXPR=true --dump swizzled textures as XPR
useXDK=true --Use xbox360 SDK to unswizzle textures from generated XPRs

clearlistener()
fsource = GetOpenFileName \
caption:"COD 36t to XPR" \
types: "Xbox360 Texture(*.36t)|*.36T|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
unbundler=(fpath+"UnBundler.exe")
st = timestamp() --get start time in milliseconds
clearlistener()
-- openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(
with redraw off (

texType=bit.swapBytes (readshort f #unsigned) 2 1 -- 0x01 = SpecMap |  0x02 = NormalMap |  0x03 = DiffuseMap | 0x0C = CubeMap | 
ukn1=(bit.swapBytes (bit.swapBytes (readlong f #unsigned) 1 4) 2 3)
ukn2=(bit.swapBytes (readshort f #unsigned) 2 1)

if mkXPR==true do(
createFile (fpath+fname+".xpr")
s = fopen (fpath+fname+".xpr") "ab"
write=writebyte s 0x58
write=writebyte s 0x50
write=writebyte s 0x52
write=writebyte s 0x32
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x08
write=writebyte s 0x00
write=writelong s (bit.swapBytes (bit.swapBytes (fsize-4096) 1 4) 2 3)
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x01
write=writebyte s 0x54
write=writebyte s 0x58
write=writebyte s 0x32
write=writebyte s 0x44
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x40
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x34
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x18
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writebyte s 0x00
write=writestring s fname
for x = 1 to (40-(fname.count+1)) do(
write=writebyte s 0x00
)

for x = 1 to (16*4) do(
read=readbyte f #unsigned
write=writebyte s read
)
for x = 1 to 1920 do(
write=writebyte s 0x00
)
fseek f 0x1000 #seek_set
for x = 1 to (fsize-4096) do(
read=readbyte f #unsigned
write=writebyte s read
)


)
gc()
fclose s
if useXDK==true do(
if (unbundler!=undefined) AND ((doesFileExist unbundler)==true) do(
DOSCommand ("\"\""+unbundler+"\" \""+(fpath+fname+".xpr")+"\"\"")
deleteFile (fpath+fname+".xpr")
deleteFile (fpath+fname+".xpr.rdf")
deleteFile (fpath+fname+"_1.tga")
deleteFile (fpath+fname+"_2.tga")
deleteFile (fpath+fname+"_3.tga")
deleteFile (fpath+fname+"_4.tga")
deleteFile (fpath+fname+"_5.tga")
deleteFile (fpath+fname+"_6.tga")
deleteFile (fpath+fname+"_7.tga")
deleteFile (fpath+fname+"_8.tga")
deleteFile (fpath+fname+"_9.tga")
deleteFile (fpath+fname+"_10.tga")
deleteFile (fpath+fname+"_11.tga")
deleteFile (fpath+fname+"_12.tga")
deleteFile (fpath+fname+"_miptail.tga")
    ))

--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
fclose g
fclose s
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")
```
## Post #12
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2010-12-29T19:17:45+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

here is an exporter i made a long time ago for chrroxx
[KUF_Dot36T_exporter](http://www.mediafire.com/?9or2fxuan3m4c3o)
## Post #13
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-13T18:08:54+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

Skeleton and animations are in .ba files.

```

byte[12]
dword[1]  - nAnimations
dword[nAnimations] - frames of each animation ?
dword[2]

nBones x {  - nBones or do until end file
byte[255] - bonename (255 - find \x00) 
byte[255] - parentname (255 - find \x00)
float[16] - matrix
float[16] - bone matrix
float[14] - ?
nAnimations x {
dword[1] - ?
dword[1] - nLocFrames
nLocFrames x {
dword[1] - time
float[3] - position bone
} - end locframes
dword[1] - nRotFrames 
nRotFrames x {
dword[1] - time
float[4] - rotation (quaternion qx,qy,qz,qw)
} - end rotframes
dword[1] - ?
} - end animation
} - end bones


```

[model.jpg](https://xentaxbackup.github.io/file/4063_model.jpg)
## Post #14
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-03-14T15:41:21+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

hi Szkaradek123, the script you posted above is for blender or max ? can you describe how to use it please. i'm not familiar with blender.
thank you
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-03-15T20:40:20+00:00
- Post Title: [XBox 360] Kingdom under Fire : circle of doom - Model files

Blender249 importer :
 - meshes, armature, animations, textures and materials

1. copy shadowmoy KUF_Dot36T_exporter to folder where is .blend file
2. open .blend and run script
3. in gui browse for :
-folder with .bm files
-folder with .tga or .6kt files
-.ba file 
4. click on 'SHOW WHAT BA FILE HAVE' and select 'ARMATURE' click on LOAD
5. in 3d window scale obiekt 'armature'
6. click on 'SHOW KINGDOM BM FILES' and select what you want and click on LOAD - check always console, sometimes converter stoped
7. clock on 'SHOW WHAT BA FILE HAVE' and select 'ARMATURE' and animation and click on LOAD
8. if animation is 'ugly' always select 'ARMATURE' and click on LOAD

Update:
 - fixed parenting objects without weighting to bones
 - fixed weighting some types of meshes
[import-kingdom-under-fire-2011-03-12.zip](https://xentaxbackup.github.io/file/4071_import-kingdom-under-fire-2011-03-12.zip)
## Post #16
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-03-16T09:09:50+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

many thanks Szkaradek123, you're great!
## Post #17
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-03T14:21:49+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

The contents of this post was deleted because of possible forum rules violation.
[kuf heroes.jpg](https://xentaxbackup.github.io/file/4158_kuf heroes.jpg)
## Post #18
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-04-05T08:26:19+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

The contents of this post was deleted because of possible forum rules violation.
## Post #19
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2011-04-05T14:50:10+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

Paste this.blend in folder where are .dat files (data1.dat,.....) and run script.
This create new folders data1,data2... .
[kindgdom-under-fire-heroes-dat-unpacker.zip](https://xentaxbackup.github.io/file/4166_kindgdom-under-fire-heroes-dat-unpacker.zip)
## Post #20
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2011-04-05T17:12:00+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

it works fine, thanks again Szkaradek123.
## Post #21
- Username: sunasiro99s
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 12, 2011 12:02 am
- Post datetime: 2012-01-08T03:41:59+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

Could someone please reupload KUF_Dot36T_exporter?
Please  


> Reply from shadowmoy
>
> here is an exporter i made a long time ago for chrroxx
KUF_Dot36T_exporter
## Post #22
- Username: noazett
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Dec 14, 2009 8:09 am
- Post datetime: 2012-01-08T13:51:45+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

The contents of this post was deleted because of possible forum rules violation.
## Post #23
- Username: sunasiro99s
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 12, 2011 12:02 am
- Post datetime: 2012-01-08T14:27:26+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

The contents of this post was deleted because of possible forum rules violation.
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-04-01T21:06:06+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

> Reply from shadowmoy
>
> here is an exporter i made a long time ago for chrroxx
KUF_Dot36T_exporterdoes anyone have this tool?
## Post #25
- Username: masonly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Feb 13, 2021 1:46 pm
- Post datetime: 2022-10-25T07:02:41+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

bumping. need this for ninety nine nights and have found absolutely nothing.

I've tried writing my own texture exporter but the format is too confusing (I can't tell if it's packed or just swizzled)
## Post #26
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-10-25T07:11:51+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

The ninety nine nights texture tool is still online.
Also, the textures for this game are slightly different in format from ninety nine nights, but only in one part of the header.
I was able to convert them with the ninety nine nights texture tool by aligning the data in the same way. I have tried that before.

From memory, I believe there was a discrepancy of about 4 bytes in the area where the image size is written.
I also remember that I added 4 bytes of 0x00 to the data that followed because there was also a discrepancy.
I don't have the file anymore, so I can't check, but it can be converted with the N3 tool with a little modification.
## Post #27
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2022-10-25T08:50:45+00:00
- Post Title: Re: [XBox 360] Kingdom under Fire : circle of doom - Model f

Dunno if it can help. I remember using this (attachment) autodesk script to get the textures, but you need the xbox 360 SDK. Can't event remember where i got this from but most likely from some thread in here.
[KUF.7z](https://xentaxbackup.github.io/file/22959_KUF.7z)
