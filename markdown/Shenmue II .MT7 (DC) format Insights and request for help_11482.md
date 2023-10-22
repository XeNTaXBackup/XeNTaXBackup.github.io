## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2014-05-03T18:48:17+00:00
- Post Title: Shenmue II *.MT7 (DC) format: Insights and request for help

Hello there, I've been trying to find someone who knows about hacking 3D in order to extract and inject models on the game Shenmue II for Dreamcast (And maybe the XBOX version as well). Some months ago I finally found the guy, but he's been really busy at this time and cannot continue this work at the moment.

So, first warning: I take no credit for the following material. The credit goes to SkyBladeCloud and he should be credited whenever someone else uses or develops this material.

I sent him some files that I needed to modify for retranslation purposes (I have to change vertices and UV positions). So the following MAXScript code only works on the following file: SCENE\XX\MODEL\SIGNBD\WT001M0G.MT7. I can't place that file publicly because of this forum's rules. (PM me for further models)

So, here's the MAXScript:

```

fname = getOpenFileName \ 
caption:"3D Model" \
types:"3D Model (*.*)|*.*" \
historyCategory:"3D Model"
f = fopen fname "rb"

Skel = #()

fn ReadFixedString bstream fixedLen = (
   local str =""
   for i=1 to fixedLen do (
      str+=bit.intAsChar (ReadByte bstream #unsigned)
   )
   str
)

fn readMeshSmall f =
(
	Vertices = #()
	TexCoords = #()
	Weights = #()
	Faces = #()
	
	type = readlong f
	vertexNum = readlong f
	
	print vertexnum
	
	for i = 1 to vertexNum do
	(
		x = readfloat f
		y = readfloat f
		z = readfloat f
		
		vertex = point3 x y z
		Vertices[i] = vertex
		
		boneIndex = readlong f
		unk = readlong f		
		weight = readfloat f

		u = readfloat f
		v = 1 - readfloat f
		
		texcoord = point3 u v 0
		TexCoords[i] = texcoord
		
		print texcoord
	)

	for i = 1 to (vertexNum - 2) by 1 do
		(
			x = i
			if(mod i 2 == 1) then
				(
				y = i + 1
				z = i + 2
			)
			else
			(
				y = i + 2
				z = i + 1
			)				
			face = point3 x y z
			append Faces face
		)

	msh = mesh vertices:Vertices faces:Faces tverts:TexCoords
		
	mmesh = msh.mesh
	buildTVFaces mmesh
	for i = 1 to mmesh.numfaces do
	(
		setTVFace mmesh i (getFace mmesh i)
	)
)

fn readBlock f numChunks offset =
(
	fseek f offset #seek_set
	
	for i = 1 to numChunks do
	(
			readMeshSmall f
	)
	
)

readBlock f 0x22 0x120
print "------------"
readBlock f 0x1c 0x1380
print "------------"
readBlock f 1 0x22b0

fclose f
```


And here's the ending result (Once I've added materials and changed the material channels):


So, here's some notes:
 - The files with the MT7 extension are actually packages that contain models as well as textures (either in PVR or DDS format). There's a subformat hidden in other files (.PKF and .PKS, those can be extracted easily thanks to Sizious' tools) that's probably just the model part of these MT7 files.
 - There's some "strange bytes" that are not developed yet. I don't know what that means.
 - This thing probably lacks bone structures.

If anyone can help us finish the importer and create an exporter, I'll be very thankful to him.
