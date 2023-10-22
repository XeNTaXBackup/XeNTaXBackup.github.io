## Post #1
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-28T13:14:03+00:00
- Post Title: Farming Simulator 14 (Android) .p3d - Normals Help

Hello,
I've been playing Farming Simulator 14 on Android recently, and I've decided to make a MaxScript importer, just for fun because the format is very basic. But, I can't get the normals to import correctly. Some help would be appreciated.

Samples: [https://www.sendspace.com/file/88kxbp](https://www.sendspace.com/file/88kxbp)

MaxScript:

```
types:"Farming Simulator 14 Android / iOS (.p3d)|*.p3d|"

if fP3D != undefined then (
	f = fopen fP3D "rb"
	clearlistener()

	if (readlong f) != 1 do messageBox "Wrong p3d file."

	max modify mode -- open mod panel for edit_normals to work
	cui.expertModeOn() --hide panel for faster processing

	vArr=#()
	nArr=#()
	tArr=#()
	fArr=#()

	vertCnt = readlong f
	faceCnt = readlong f
	for x = 1 to vertCnt do
	(
		vx=readfloat f; vy=readfloat f; vz=readfloat f
		nf=readshort f -- some kind of a factor?
		nx=readshort f #signed / 255
		ny=readshort f #signed / 255
		nz=readshort f #signed / 255
		tu=readfloat f; tv=readfloat f
		append vArr[-vx,vz,vy]
		-- normals are temporarily disabled, extracted values are incorrect
		--append nArr[-nx,nz,ny]
		append tArr[tu,1-tv,0]
	)

	for x = 1 to faceCnt/3 do
	(
		fa=readshort f #unsigned+1
		fb=readshort f #unsigned+1
		fc=readshort f #unsigned+1
		append fArr[fa,fb,fc]
	)

	msh = mesh vertices:vArr faces:fArr
	msh.numTVerts = tArr.count
	buildTVFaces msh
	msh.name= getFilenameFile fP3D
	--convertTo msh PolyMeshObject
	for j = 1 to tArr.count do setTVert msh j tArr[j]
	for j = 1 to fArr.count do setTVFace msh j fArr[j]

	--set smoothing group of all faces to 1 to get one normal per vertex
	for face = 1 to msh.numfaces do setFaceSmoothGroup msh face 1
	--set normals via edit normals modifier
	select msh
	addmodifier msh (Edit_Normals ()) ui:off
	msh.Edit_Normals.MakeExplicit selection:#{1..nArr.count}
	EN_convertVS = msh.Edit_Normals.ConvertVertexSelection
	EN_setNormal = msh.Edit_Normals.SetNormal
	normID = #{}
	--apply normals
	for v = 1 to nArr.count do
	(
		free normID
		EN_convertVS #{v} &normID
		for id in normID do EN_setNormal id nArr[v]
	)
	collapseStack msh
			
--	for i = 1 to nArr.count do print nArr[i]
	cui.expertModeOff()
	max select none
	max tool zoomextents all
	max tool zoomextents all

	gc()
	fclose f 
) else (
	clearlistener()
)
```


Thanks in advance.
