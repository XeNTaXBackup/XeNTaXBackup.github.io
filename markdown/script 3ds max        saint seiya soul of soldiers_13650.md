## Post #1
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2015-12-10T09:59:15+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

script import / export saint seiyas games of models PS3 / PC

please someone could convert this script  Blender 249
to run in 3ds max

SCRIPT

```
from newGameLib import *
import Blender	


def embParser(filename,g):
	g.endian='>'	
	name=g.word(4)
	v0=g.h(4)
	v1=g.i(5)	
	g.seek(v1[3])
	t0=g.tell()	
	texDir=g.dirname+os.sep+g.basename.split('.')[0]+'_files'
	try:os.makedirs(texDir)
	except:pass
	
	for id0 in range(v1[0]):
		t1=g.tell()
		v2=g.i(2)
		t2=g.tell()
		g.seek(t1+v2[0])
		v3=g.B(8)
		v4=g.H(20)
		w,h=v4[12],v4[13]
		g.seek(t1+v2[0]+128)		
		img=imageLib.Image()
		img.name=texDir+os.sep+str(id0)+'.dds'
		img.szer=w
		img.wys=h		
		if v4[8]==34817:img.format='DXT5'		
		elif v4[8]==34305:img.format='DXT1'
		elif v4[8]==34828:img.format='DXT5'
		elif v4[8]==34825:img.format='DXT5'
		else:print 'unknow format',v4[8]		
		img.data=g.read(v2[1]-128)
		g.seek(t2)
		img.draw()


def emoParser(filename,g):
	g.endian='>'
	skeleton=Skeleton()
	skeleton.BONESPACE=True
	skeleton.NICE=True	
	
	t0=g.tell()
	name=g.word(4) 
	v0=g.h(4)
	v1=g.i(3)
	
	g.seek(t0+v1[1])
	A=g.H(4)+g.i(14)
	g.seek(t0+v1[1]+A[4])
	for m in range(A[0]):
		bone=Bone()
		t=g.tell()
		B=g.h(8)
		bone.parentID=B[0]
		bone.matrix=Matrix4x4(g.f(16))
		g.seek(t+80)
		skeleton.boneList.append(bone)
	for m in range(A[0]):g.seek(8,1)			
	for m in range(A[0]):
		bone=skeleton.boneList[m]
		offset=g.i(1)[0]
		t=g.tell()
		g.seek(t0+v1[1]+offset)
		bone.name=g.find('\x00')
		g.seek(t)
	skeleton.draw()
	texDir=g.dirname+os.sep+g.basename.split('.')[0]+'_files'
	
	
	g.seek(t0+v1[0])
	t1=g.tell()
	v1=g.H(4)
	v2=g.i(v1[0])
	
	modelID=ParseID()
	
	for id in range(v1[0]):	
		g.seek(t1+v2[id])
		t2=g.tell()
		v3=g.H(2)
		v4=g.i(v3[0])	
		for id0 in range(v3[0]):
			if v4[id0]!=0:
				g.seek(t2+v4[id0])
				t3=g.tell()
				name=g.word(4)
				v5=g.h(2)
				v6=g.i(v5[1])
				for id1 in range(v5[1]):
					mesh=Mesh()
					matList=[]
					if v3[0]>1:mesh.name=str(modelID)+'-mdl-'+str(id)+'-mrph-'+str(id0)+'-'+str(id1)
					else:mesh.name=str(modelID)+'-mdl-'+str(id)+'-'+str(id0)+'-'+str(id1)
					g.seek(t3+v6[id1])  
					t4=g.tell()
					v7=g.H(4)
					v8=g.i(2),g.H(2),g.i(1)+g.H(2)+g.i(1)
					g.f(3)
					g.f(3)
					g.f(3)
					g.f(3)
					v9=g.i(v7[2])
					for id2 in range(v7[2]):
						g.seek(t4+v9[id2])
						v11=g.H(2)				
						mat=Mat()
						for id3 in range(v11[0]):
							a,b=g.H(2)
							'-'*20,a,b,g.f(2)
							if id3==0:
								mat.diffuse=texDir+os.sep+str(a)+'.dds'
						matList.append(mat)	
						
						
						
					g.seek(t4+v8[2][0])
					for id2 in range(v8[1][0]):
						t5=g.tell()
						mesh.vertPosList.append(g.f(3))
						g.seek(t5+24)
						mesh.vertUVList.append(g.f(2))
						if v8[1][1]==52:
							g.seek(4,1)	
							i1,i2,i3,i4=g.B(4)
							mesh.skinIndiceList.append([i4,i3,i2,i1])
							w1,w2,w3=g.f(3)
							w4=1.0-(w1+w2+w3)
							mesh.skinWeightList.append([w1,w2,w3,w4])
						if v8[1][1]==64:
							g.seek(16,1)
							i1,i2,i3,i4=g.B(4)
							mesh.skinIndiceList.append([i4,i3,i2,i1])
							w1,w2,w3=g.f(3)
							w4=1.0-(w1+w2+w3)
							mesh.skinWeightList.append([w1,w2,w3,w4])
						g.seek(t5+v8[1][1])
						mesh.skinIDList.append([0]*v8[2][2])
						
					g.seek(t4+v8[2][3])				
					v10=g.i(v8[2][2])
					edgeFlag=0
					for id2 in range(v8[2][2]):
						mat=Mat()
						mat.TRISTRIP=True
						faceslist=[]
						if v10[id2]!=0:						
							g.seek(t4+v10[id2])
							g.f(4)
							v11=g.H(3)	
							matID=v11[0]
							if matID<len(matList):mat.diffuse=matList[matID].diffuse
							name=g.word(32)
							if name=='EDGE':edgeFlag=1
							mat.name=name+'-'+str(id)+'-'+str(id0)+'-'+str(id1)
							mat.IDStart=len(mesh.indiceList)
							mat.IDCount=v11[1]
							indiceList=g.H(v11[1])
							mesh.indiceList.extend(indiceList)
							mesh.matList.append(mat)
							skin=Skin()						
							skin.boneMap=g.H(v11[2])
							for indice in indiceList:
								mesh.skinIDList[indice][id2]=1
							g.i(1)
							mesh.skinList.append(skin)	
					
					if edgeFlag==0:
						mesh.boneNameList=skeleton.boneNameList
						mesh.BINDSKELETON=skeleton.name
						mesh.draw()
	
def Parser():	
	filename=input.filename
	print
	print filename
	print 
	ext=filename.split('.')[-1].lower()	
	
	if ext=='emb':
		file=open(filename,'rb')
		g=BinaryReader(file)
		embParser(filename,g)
		file.close()
	
	if ext=='emo':
		file=open(filename,'rb')
		g=BinaryReader(file)
		emoParser(filename,g)
		file.close()
 
def openFile(flagList):
	global input,output
	input=Input(flagList)
	output=Output(flagList)
	parser=Parser()
	
Blender.Window.FileSelector(openFile,'import','Saint Seiya Brave Soldier PS3 files: *emo - model, *.emb - textures')
```
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-12-10T12:56:56+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

Hi,
first of all: why not tell whose script is it? From here: [viewtopic.php?f=16&t=13363&start=15](http://forum.xentax.com/viewtopic.php?f=16&t=13363&start=15)

2ndly: use code tags 
```
...whatever code...
```
to present code

3rdly: very unlikely that someone will take over this tasks 'cause there are working python scripts already

4thly: did you try out the script from Watcher for blender versions > 2.49b?

5thly: don't you like blender?  (rhetorical question)
## Post #3
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2015-12-10T13:15:47+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

sorry if I made a mistake
friend I work better with 3ds max
and no longer use blender makes  long time
thank you for answering the topic


you do not know of a script can export the same que saint seiya  models files  emo, emb   for 3ds max
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-12-10T19:45:14+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

> Reply from adam0000
>
> sorry if I made a mistake
i am new on the site
friend I work better with 3ds max
and no longer use blender makes  long time
thank you for answering the topic


you do not know of a script can export the same que saint seiya  models files  emo, emb   for 3ds max

Blender 2.49 has an fbx exporter, import the mesh you want and export it to fbx. If you have any problem in 3ds max, re-export the fbx to fbx again with noesis.

[https://www.youtube.com/watch?v=tNyGFBM--9c](https://www.youtube.com/watch?v=tNyGFBM--9c)
## Post #5
- Username: adam0000
- Rank: n00b
- Number of posts: 16
- Joined date: Thu Jul 23, 2015 6:34 am
- Post datetime: 2016-05-23T03:56:26+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

Thanks to all who responded
## Post #6
- Username: Darkhowlings
- Rank: mega-veteran
- Number of posts: 185
- Joined date: Mon Sep 01, 2014 3:33 pm
- Post datetime: 2016-07-05T16:56:04+00:00
- Post Title: script 3ds max        saint seiya soul of soldiers

Not for revive this, but they something odd if you try to open the models of the PC version of the game.
Actually it doesn't open on Blender always coming with an error message.

But why not made a Noesis plugging instead? on that way it can be convert for user of Blender, 3D Max and even Cinema 4D
