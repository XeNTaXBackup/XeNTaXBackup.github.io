## Post #1
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2018-10-17T03:12:42+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

I checked the file and it looks compressed. Any way to decompress these files for editing these models?

[https://mega.nz/#!nw5TzIyK!l1Vv7r1Lzs3S ... t8uD_qgSXo](https://mega.nz/#!nw5TzIyK!l1Vv7r1Lzs3SUAUpxwYrbjxOyDTEzWWL7t8uD_qgSXo)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-17T12:01:12+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

The used algorithm seems to be LZO.
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-17T12:28:32+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

Got it. It's lzo1x.
Use this BMS script to decompress the files.
[BBADecompressor.zip](https://xentaxbackup.github.io/file/15040_BBADecompressor.zip)
## Post #4
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2018-10-17T13:52:20+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

> Reply from Bigchillghost
>
> Got it. It's lzo1x.
Use this BMS script to decompress the files.
Thanks, but now that they are uncompressed, what programs should i use to open them and convert them to useable formats?

[https://mega.nz/#!6hRyVaTC!r0-Icffj3dS3 ... 3XYVfp9iNQ](https://mega.nz/#!6hRyVaTC!r0-Icffj3dS3cTyPvUdfL00kYfJtRHdHr3XYVfp9iNQ)
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-17T19:41:18+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

> Reply from MarioSonicU
>
> Thanks, but now that they are uncompressed, what programs should i use to open them and convert them to useable formats?Who knows?
My idea is to use hex2obj for getting point clouds in a first step but you need to understand the idea and have patience:



Holly.jpg (82.72 KiB) Viewed 114 times
## Post #6
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2018-10-18T14:07:44+00:00
- Post Title: Black & Bruised (NGC) - .mdl mesh and .ani motion files

I have luck to get faces , but not for uv and rest.

[http://www.mediafire.com/view/igaja2rla ... norama.jpg](http://www.mediafire.com/view/igaja2rlazjb3m4/Panorama.jpg)


```
from newGameLib import *
import Blender	


def indicesToFaces(indicesList):
	StartDirection = -1
	id=0
	f1 = indicesList[id]
	id+=1
	f2 = indicesList[id]
	FaceDirection = StartDirection
	faceList=[]
	while(True):
		id+=1
		f3 = indicesList[id]
		FaceDirection *= -1
		if (f1!=f2) and (f2!=f3) and (f3!=f1):
			if FaceDirection > 0:faceList.append([(f1),(f2),(f3)])
			else:faceList.append([(f1),(f3),(f2)])
		f1 = f2
		f2 = f3
		if id==len(indicesList)-1:break
	return 	faceList
			
def mdlParser(filename,g):
	
	
	g.endian='>'
	while(True):
		A=g.i(2)
		if A[1]==0:break
		t=g.tell()
		g.word(16)
		if A[0]==2:#mesh section, 1-image section
			B=g.i(5)
			g.word(16)
			g.word(16)
			g.word(16)
			mesh=Mesh()			
			off=g.tell()
			g.seek(t+B[1])
			for m in safe(B[0]):
				mesh.vertPosList.append(g.short(3))
				mesh.vertNormList.append(g.short(3))
				mesh.vertUVList.append([])
			g.seek(off)			
			for m in safe(B[2]):
				C=g.i(19)
				tm=g.tell()
				g.seek(t+C[16])
				while(True):
					flag=g.B(1)[0]
					if flag==152:
						count=g.H(1)[0]
						for n in safe(count):
							index1,index2=g.H(2)
							u,v=g.B(1)[0],g.B(1)[0]
							mesh.vertUVList[index1]=[u,v]
					if g.tell()==t+C[15]+C[16]:break
				g.seek(t+C[18])
				while(True):
					flag=g.B(1)[0]
					if flag==152:
						list=g.H(g.H(1)[0])
						faces=indicesToFaces(list)
						mesh.faceList.extend(faces)
					if g.tell()==t+C[18]+C[17]:break
				g.seek(tm)	
			mesh.draw()			
		g.seek(t+A[1])
	g.debug=True
	g.tell()
	
def Parser(filename):
	sys=Sys(filename)
	if sys.ext=='ucp':sys.parseFile(mdlParser,'rb',log=0)
 
	
Blender.Window.FileSelector(Parser,'import','*.ucp files')
```


Here is a model of Holly.
I you want  to import models use installed Blender version 2.4.9b
[http://download.blender.org/release/Ble ... indows.exe](http://download.blender.org/release/Blender2.49b/blender-2.49b-windows.exe)
[Blender249[BlackAndBruised][NGC][ucp][2018-10-18].7z](https://xentaxbackup.github.io/file/15047_Blender249[BlackAndBruised][NGC][ucp][2018-10-18].7z)
