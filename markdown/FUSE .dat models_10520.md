## Post #1
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2013-06-16T10:56:18+00:00
- Post Title: FUSE .dat models

Hello everyone! I'm stuck with Fuse model format, and really need help from experienced ones   Whatever I do I can't figure out and import vertices right. Resulted mesh looks awful, twisted in a box shape. Lower half of face appears to be above of upper and so on. Could someone check out this sample and help me with some advice? Thanks in advance.
[fuse_dalton_head.7z](https://xentaxbackup.github.io/file/6472_fuse_dalton_head.7z)
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2013-06-22T16:45:57+00:00
- Post Title: FUSE .dat models

i had a look out of sport, but can't import all the sub meshes.. the game doesnt appeal to me, so I left it as is. on the 3 samples I had it seems to import the first sub mesh fine.

```
caption:"Open .mdl from Mesh folder" \
types:"FUSE (*.mdl)|*.mdl" \
historyCategory:"FUSEObjectPresets"


-- fname = "D:\\MaxScripts\\tib\\fuse\\dalton_head.mdl"

f = fopen fname "rb"
clearlistener()
fscale=1000
global mdl
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
return convertTo32(ReadBEword fstream)
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

fn readBEshort fstream = (
short = readshort fstream #unsigned
short = bit.swapBytes short 1 2
return short
)
fn ReadBEfloat fstream = 
	(
	bit.intAsFloat (bit.swapBytes (bit.swapBytes (readlong fstream #unsigned) 1 4) 2 3)
)
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

fn buildObj = (
	if mdl.position!=undefined and mdl.position.count!=0 do (
		msh = mesh vertices:mdl.position faces:mdl.faces
		msh.numTVerts = mdl.texture.count
		buildTVFaces msh
		for j = 1 to mdl.texture.count do setTVert msh j mdl.texture[j]
		for j = 1 to mdl.faces.count do setTVFace msh j mdl.faces[j]
		msh.displayByLayer = false
		msh.backfacecull = on
		msh.wirecolor = random (color 0 0 0) (color 255 255 255)
		convertTo msh PolyMeshObject
		)
	)

struct header (
	magic = ReadBElong f,
	unk001 = ReadBElong f, -- fourCC, Hash Code?
	filesize = ReadBElong f,
	count = ReadBEword f,
	unk002 = ReadBEword f
	)
struct data_entry (
	unk001 = ReadBElong f, -- fourCC, Hash Code?
	offset = ReadBElong f,
	size = ReadBElong f
	)
struct mesh_entry (
	unk001 = ReadBElong f,
	unk002 = [(ReadBEfloat f),(ReadBEfloat f),(ReadBEfloat f)],
	unk003 = [(ReadBEfloat f),(ReadBEfloat f),(ReadBEfloat f)],
	unk004 = ReadBEword f,
	unk005 = ReadBEword f,
	unk006 = ReadBEword f,
	vert_pos = ReadBElong f,
	face_pos = ReadBElong f,
	num_faces = ReadBEword f,
	num_verts = ReadBEword f,
	unk013 = ReadBEword f,
	unk014 = ReadBEword f, -- constant 0x4248
	unk015 = ReadBEword f,
	unk016 = ReadBEword f,
	unk017 = ReadBEword f,
	unk018 = ReadBEword f,
	unk019 = ReadBEword f,
	unk020 = ReadBEfloat f
	)
struct geo (
	position=#(),
	texture=#(),
	faces=#()	
	)


if f!=undefined then(
mdl = geo()
hdr = header()
if hdr.magic == 0x44415431 do (
files = #()
strings = #()
meshes = #()
num_objs = 0

for i = 1 to hdr.count do (
	files[i] = data_entry()
	)

str = "";do (
	if str!="" do (
		append strings str
		)
	str=readstring f
	) while str!=""


for m in files do (
		case m.unk001 of (
			(2027539422):( -- mesh enties
			fseek f m.offset #seek_set
			do (
				mshentry = mesh_entry()
				if mshentry.unk014==0x4248 do (
					append meshes mshentry
					)
				) while mshentry.unk014==0x4248
			num_objs = 1 --meshes.count
			)
		)
	)

for m in files do (
-- 	print m.unk001
	case m.unk001 of (
		(-1450449253):( -- verts
			delete $*
			fseek f m.offset #seek_set
			for x = 1 to num_objs do (
				format "Verts @ 0x%\n" ((bit.intAsHex(ftell f))as string)
				for v = 1 to meshes[x].num_verts do (
					getPos = ftell f + 16
					vx = (ReadBEword f) / 65535.0
					vy = (ReadBEword f) / 65535.0
					vz = (ReadBEword f) / 65535.0
					if vx>0.5 do vx-=1
					if vy>0.5 do vy-=1
					if vz>0.5 do vz-=1
					append mdl.position ([vx,vz,vy]*fscale)
					fseek f getPos #seek_set
					)
				getPos = ftell f
				check = 0
				do (
					check += readlong f #unsigned
					check += readlong f #unsigned
					check += readlong f #unsigned
					check += readlong f #unsigned
					) while check==0
				fseek f -16 #seek_cur
				)
			)
		(385071640):( -- uvs
			fseek f m.offset #seek_set
			for x = 1 to num_objs do (
				for v = 1 to meshes[x].num_verts do (
					append mdl.texture [(ReadBEHalfFloat f),(ReadBEHalfFloat f),0]
				)
			)
			)
		(140084797):( -- faces
			addon = 1
			fseek f m.offset #seek_set
			for x = 1 to num_objs do (
				for v = 1 to (meshes[x].num_faces/3) do (
					fa=ReadBEword f + addon
					fb=ReadBEword f + addon
					fc=ReadBEword f + addon
					append mdl.faces [fa,fc,fb] 
					)
				addon+=meshes[x].num_verts
				)
			)
		)
	)

buildObj()

)
format "Last Read @ 0x%\n" ((bit.intAsHex(ftell f))as string)
)else(print "aborted?")
fclose f
```
