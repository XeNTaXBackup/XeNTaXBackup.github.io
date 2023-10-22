## Post #1
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-09-08T04:25:18+00:00
- Post Title: Railway Empires Train Engine models

So I successfully unpacked the .fuk files of the Railway Empire game, because I absolutely love classic steam locomotives from the early days of trains, and this game has fantastic reproductions of them all. The game uses the Gaming Mind Studios Kalypso engine, the QuickBMS script can be found here: [http://aluigi.altervista.org/bms/gaming ... os_fuk.bms](http://aluigi.altervista.org/bms/gaming_mind_studios_fuk.bms)

Thanks to Luigi for putting that together for us!
His script successfully unpacked the .fuk compressed game files, which created a complete file structure with names and everything. I'd like to propose that we figure out this game's model format, because I don't recognize it, and I  haven't found any tools through my research that can open them. It doesn't help that Google search doesn't work well with vague search terms, such as "Railway Empire 3d models" etc etc.

So the game file structure and naming system is very simple, and it was easy to find all the files in each folder for each locomotive. I've put together a sample pack of the files for the Iron Duke locomotive for anyone interested to take a look at: [https://sta.sh/027em6yb0ene](https://sta.sh/027em6yb0ene)

Is anyone else interested in this game or its models?

EDIT: I've attached screenshots of the file structure for your reference.



Capture.PNG (32.65 KiB) Viewed 222 times
## Post #2
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-09-27T22:44:13+00:00
- Post Title: Railway Empires Train Engine models

Ok, since my post got magically zero responses, I'll throw some money at the problem, hopefully that helps grease the gears. 

I'm willing to pay anyone who helps me do what I asked a decent chunk of cash for their assistance, in US dollars.
## Post #3
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2020-09-28T17:08:23+00:00
- Post Title: Railway Empires Train Engine models

The link to the sample files does not work.
## Post #4
- Username: Joschka
- Rank: mega-veteran
- Number of posts: 286
- Joined date: Fri Aug 09, 2019 10:51 pm
- Post datetime: 2020-09-28T17:28:19+00:00
- Post Title: Railway Empires Train Engine models

Took a very quick look at the samples, vertices positions and UVs seem easy to get. Indices are obviously in the .ibuf files but had no time to see how they work.



Capture.PNG (83.67 KiB) Viewed 198 times



Here's the wip noesis script that I did real quick 

```
import os

def registerNoesisTypes():
	handle = noesis.register("train",".vbuf")
	noesis.setHandlerTypeCheck(handle, CheckType)
	noesis.setHandlerLoadModel(handle, LoadModel)	
	return 1
	
def CheckType(data):
	bs = NoeBitStream(data)
	if len(data) < 16:
		print("Invalid file, too small")
		return 0
	return 1

def LoadModel(data, mdlList):
	
	ctx = rapi.rpgCreateContext()
	bs = NoeBitStream(data)
	bs.setEndian(NOE_LITTLEENDIAN)
	dir = rapi.getDirForFilePath(rapi.getInputName())
	vBufFiles = [f for f in os.listdir(dir) if os.path.isfile(os.path.join(dir, f)) and f.endswith(".vbuf")]
	iBufFiles = [f for f in os.listdir(dir) if os.path.isfile(os.path.join(dir, f)) and f.endswith(".ibuf")]
	
	
	opcode = bs.readUInt()
	bs.readBytes(0x18 if opcode==4 else 0x24 if opcode==6 else 0)
	stride = bs.readUInt()
	bufferSize = bs.readUInt()
	vbuffer = bs.readBytes(bufferSize)
		
	rapi.rpgBindPositionBuffer(vbuffer, noesis.RPGEODATA_HALFFLOAT,stride)
	if stride == 0x24:
		rapi.rpgBindUV1BufferOfs(vbuffer, noesis.RPGEODATA_FLOAT,stride,20)
		
	rapi.rpgCommitTriangles(None, noesis.RPGEODATA_USHORT, bufferSize//36, noesis.RPGEO_POINTS, 1)
	try:
		mdl = rapi.rpgConstructModel()
	except:
		mdl = NoeModel()
	mdlList.append(mdl)
	
	return 1
```


No need for money or anything. 
Probably don't expect me to finish the job, I'm quite busy with my own projects, good luck.
## Post #5
- Username: kingfisher13
- Rank: veteran
- Number of posts: 83
- Joined date: Tue Jul 27, 2010 2:32 am
- Post datetime: 2020-10-01T22:00:43+00:00
- Post Title: Railway Empires Train Engine models

Thanks for your help, hopefully someone can take your script and finish it. Also, Karpati the link does work, it hasn't been taken down, and I just opened it myself a few minutes ago to make sure. 

Again, I'm offering a decent chunk of money via Paypal to anyone willing to work on this project.
## Post #6
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-19T18:39:17+00:00
- Post Title: Railway Empires Train Engine models

if anyone has a second or know scripting i was hoping to update this script so it reads faces properly. anyone out there able to help ?
I was able to do many of them manually but i see this script can pull verts just not faces. anyone able to help me ?
[](https://ibb.co/Th4jmNv)
I dont know scripting or i would attempt it myself. I tried to add face data but no idea what im doing.

Samples
[https://drive.google.com/file/d/1tJi8fn ... sp=sharing](https://drive.google.com/file/d/1tJi8fn0GsKu_BpN8zAzglb1C_cY8jWpZ/view?usp=sharing)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-19T22:54:26+00:00
- Post Title: Railway Empires Train Engine models

loco_0660oldmaude0.model: seems there's a problem with the face indices.

What's the name of that model which worked for you?
## Post #8
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-22T20:18:02+00:00
- Post Title: Railway Empires Train Engine models

> Reply from shakotay2 ↑Sun Feb 20, 2022 6:54 am at Sun Feb 20, 2022 6:54 am
>
> 
loco_0660oldmaude0.model: seems there's a problem with the face indices.
seems to be (ib0).ibuf have faces for all 3 models: (vb0, vb1, vb2).vbuf   
for loco_0660oldmaude0.model.vb0.vbuf:
offset 5 >> indices count 179607 >> face 59869
(maybe even less)



loco_0660oldmaude0.png (68.82 KiB) Viewed 128 times
## Post #9
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2022-02-28T00:21:42+00:00
- Post Title: Railway Empires Train Engine models

Very nice this one has been brutal i haven't found anyone to get the mesh to parse properly.
## Post #10
- Username: Plokman
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 02, 2022 10:31 am
- Post datetime: 2022-05-02T02:39:09+00:00
- Post Title: Railway Empires Train Engine models

Oh my I do hope this moves along to include a setup for Blender, I love the engines in the game but the locomotive Dragon is one I want to see in modeling mode. Not to change it but to help me model a locomotive of the same class, B&O Memnon! Anyone know how to get STL files now?
## Post #11
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-07-28T02:16:35+00:00
- Post Title: Railway Empires Train Engine models

> Reply from Plokman ↑Mon May 02, 2022 10:39 am at Mon May 02, 2022 10:39 am
>
> 
Oh my I do hope this moves along to include a setup for Blender
it's train time  
[*.model, *.ibuf, *.vbuf]

[fmt_model_train.zip](https://xentaxbackup.github.io/file/22565_fmt_model_train.zip)
