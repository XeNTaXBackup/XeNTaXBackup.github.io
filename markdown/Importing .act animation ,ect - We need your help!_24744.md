## Post #1
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-17T19:47:46+00:00
- Post Title: Importing .act animation ,ect - We need your help!

Hello
i need help to import that files 
.act file, .ect file it's from league of angels 3
can anyone help me to make noesis script to import these files ?

[s3d_act1_unpacked.rar](https://xentaxbackup.github.io/file/21225_s3d_act1_unpacked.rar)
## Post #2
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-18T08:54:19+00:00
- Post Title: Importing .act animation ,ect - We need your help!

up
## Post #3
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-19T21:45:40+00:00
- Post Title: Importing .act animation ,ect - We need your help!

up
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-19T22:31:22+00:00
- Post Title: Importing .act animation ,ect - We need your help!

You may bump as much as you want, nothing will happen.  
Because
nobody starts with animations
never.
Usually you start with the mesh (and weights, if any), then the skeleton, and after that, maybe, you care for the anims.

Just my two cents.

edit: aah, see, here's your concerning models thread:

> Reply from masrawy2 ↑Thu Nov 04, 2021 12:43 am at Thu Nov 04, 2021 12:43 am
>
> 
Maybe present your result using the tool mentioned there?

> Reply from masrawy2 ↑Wed Nov 17, 2021 7:21 pm at Wed Nov 17, 2021 7:21 pm
>
> the game has changed the files 
I can't find the main filesAs long as this issue isn't solved (is it?) it makes no sense to take care for the skeleton.
## Post #5
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-19T23:46:51+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from shakotay2 ↑Sat Nov 20, 2021 6:31 am at Sat Nov 20, 2021 6:31 am
>
> 
You may bump as much as you want, nothing will happen.  
Because
nobody starts with animations
never.
Usually you start with the mesh (and weights, if any), then the skeleton, and after that, maybe, you care for the anims.

Just my two cents.

edit: aah, see, here's your concerning models thread:
masrawy2 wrote: ↑Thu Nov 04, 2021 12:43 am
Maybe present your result using the tool mentioned there?
masrawy2 wrote: ↑Wed Nov 17, 2021 7:21 pmthe game has changed the files 
I can't find the main filesAs long as this issue isn't solved (is it?) it makes no sense to take care for the skeleton.

this script supports the mesh + bones but I can't support the animation
I'm a noob in hex I can't find the right offset 

joscha helped me but i can't understand all things 
that the main script

```
from inc_noesis import *

def registerNoesisTypes():
	handle = noesis.register("GTArcade", ".s3d")
	noesis.setHandlerTypeCheck(handle, noepyCheckType)
	noesis.setHandlerLoadModel(handle, noepyLoadModel)
	#noesis.logPopup()
	return 1

#check if it's this type based on the data
def noepyCheckType(data):
	if len(data) < 0x80:
		return 0
	bs = NoeBitStream(data)
	Len = bs.readShort() + 1
	Tag = noeStrFromBytes(bs.readBytes(Len), "ASCII")
	if Tag != 's3dMesh':
		return 0
	return 1

#load the model
def noepyLoadModel(data, mdlList):
	#noesis.logPopup()
	bs = NoeBitStream(data)
	Len = bs.readShort() + 5
	bs.seek(Len, NOESEEK_REL)
	
	# bone info
	boneCount = bs.readInt()
	bs.seek(4, NOESEEK_REL)
	bones = []
	matList = []
	for i in range(0, boneCount):
		NameLen = bs.readShort() + 1
		boneName = noeStrFromBytes(bs.readBytes(NameLen), "ASCII")
		bonePIndex = bs.readInt()
		tran = NoeVec3.fromBytes(bs.readBytes(12))
		rot = NoeQuat3.fromBytes(bs.readBytes(12)).toQuat()
		boneMat = rot.toMat43()
		boneMat[3] = tran
		bones.append( NoeBone(i, boneName, boneMat, None, bonePIndex) )
		matList.append(boneMat)
	
	# meshes
	Len = bs.readShort() + 1
	meshName = noeStrFromBytes(bs.readBytes(Len), "ASCII")
	Vcount = bs.readInt()
	PositionIdx = []
	WeightNum = []
	TexCoords = []
	
	for i in range(0, Vcount):
		bs.seek(4, NOESEEK_REL)
		TexCoords.append(NoeVec3([bs.readFloat(),bs.readFloat(), 0.0]))
		PositionIdx.append(bs.readInt())
		WeightNum.append(bs.readInt())
	TrixCount = bs.readInt()
	PolygonIndex = []
	for i in range(0, TrixCount):
		bs.seek(4, NOESEEK_REL)
		for j in range(0, 3):
			PolygonIndex.append(bs.readInt())
	WeightCount = bs.readInt()
	Positions = []
	blockStart = bs.tell()
	vertWeightList = []
	for i in range(0, Vcount):
		Offset = blockStart + PositionIdx[i]*0x18
		bs.seek(Offset, NOESEEK_ABS)
		rlt = NoeVec3([0.0,0.0,0.0])
		bindBoneNum = WeightNum[i]
		boneIDs = [0]*bindBoneNum
		boneWeights = [0.0]*bindBoneNum
		for j in range(0, bindBoneNum):
			bs.seek(4, NOESEEK_REL)
			boneID = bs.readInt()
			weight = bs.readFloat()
			boneIDs[j] = boneID
			boneWeights[j] = weight
			coord = NoeVec3.fromBytes(bs.readBytes(12))
			rlt += matList[boneID]*coord*weight
		Positions.append(rlt)
		vertWeightList.append(NoeVertWeight(boneIDs, boneWeights))
	
	meshes = []
	
	mesh = NoeMesh(PolygonIndex, Positions, meshName, meshName)
	mesh.setUVs(TexCoords)
	mesh.weights = vertWeightList
	meshes.append(mesh)
	
	mdl = NoeModel(meshes)
	mdl.setBones(bones)
	mdlList.append(mdl)
	rapi.setPreviewOption("setAngOfs", "0 -90 0")
	
	return 1


```


I'm not sure if my code is going right or not but right away i got this problem and i my knowledge is not good I don't how I can found the 
boneName ,or boneIndex,bonePName,bonePIndex
it's so hard 
so i need someone professional to help me or even paid one haha (i got some scammer to need a money y but no one was good )


 s3d_act1_unpacked.rar
(160.39 KiB) Downloaded 12 times
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-20T07:44:23+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from masrawy2 ↑Thu Nov 18, 2021 11:06 pm at Thu Nov 18, 2021 11:06 pm
>
> 
Hello Bigchillghost could you support animation files please
Is it too much to ask for a little gratitude to the author before you ask for something more?

And it'd be nice if you just put a link to the original post instead of redistributing the whole damn script here. And maybe ask the author for permission first before you decided to remove the ownership claim and publish your modified version of the script.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-20T07:58:06+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from Bigchillghost ↑Sat Nov 20, 2021 3:44 pm at Sat Nov 20, 2021 3:44 pm
>
> 
Is it too much to ask for a little gratitude to the authorDone. 

> Reply from Bigchillghost ↑Sat May 22, 2021 1:08 am at Sat May 22, 2021 1:08 am
>
>
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-20T09:09:35+00:00
- Post Title: Importing .act animation ,ect - We need your help!

@masrawy2: I'd suggest to start with getting bonenames/skeleton data:

```
                            FFFFFFFF is -1 (signed)
boneid 
      offs   Name           parent boneID     Translation (3 floats),     Euler angles in radians (3 floats)
      
#  0   16: BoneRoot        FF FF FF FF   0.000000 0.000000 0.000000,  -0.000437 -0.000437 -0.000437 
#  1   3d: Bip01           00 00 00 00   -0.000948 -1.764057 43.128025,  0.000000 0.000000 0.707106 
#  2   61: Bip01 Footsteps 01 00 00 00   -0.000948 -1.764057 0.024066,  0.000000 0.000000 0.000000 
#  3   8f: Bip01 Pelvis    01 00 00 00   -0.000948 -1.764057 43.128025,  -0.707107 0.000155 -0.707107 
#  4   ba: Bip01 Spine     03 00 00 00   -0.000568 -1.766114 50.923256,  0.707107 0.000700 0.707107 
#  5   e4: Bip01 Spine1    04 00 00 00   -0.000568 -1.760997 54.482403,  0.707107 0.000294 0.707106 
#  6  10f: Bip01 Neck      05 00 00 00   0.006329 -0.580836 60.397083,  0.707081 -0.000124 0.707133 
#  7  138: Bip01 Head      06 00 00 00   0.006048 -0.580849 64.198586,  0.706554 -0.027965 0.706554 

#  8  161: Bip01 Xtra15        07 00 00 00   0.021098 1.000165 68.871902,  -0.046604 -0.710018 -0.046936 
#  9  18c: Bip01 Xtra1502      08 00 00 00   -0.047363 1.709546 63.510803,  -0.013489 -0.711419 -0.014236 
#  a  1b9: Bip01 Xtra16        07 00 00 00   2.587241 -0.765083 66.505539,  -0.676253 0.076061 0.717271 
#  b  1e4: Bip01 Xtra1602      0A 00 00 00   2.398893 -2.231949 62.120346,  -0.636353 0.151860 0.692290 
#  c  211: Bip01 Xtra16Opp     07 00 00 00   -2.258046 -0.910697 66.291428,  -0.707303 0.183208 0.681943 
#  d  23f: Bip01 Xtra16Opp02   0C 00 00 00   -2.244474 -2.317387 61.882317,  -0.594421 0.334310 0.717189 

#  e  26f: Bip01 L Clavicle    06 00 00 00   0.863973 -0.445698 60.817902,  0.002627 -0.184419 -0.011840 
#  f  29e: Bip01 L UpperArm    0E 00 00 00   4.506853 -0.358493 59.400368,  -0.043440 -0.466365 0.002092 
# 10  2cd: Bip01 L Forearm     0F 00 00 00   9.669111 -0.022056 51.869217,  -0.020251 -0.467946 0.045919 
# 11  2fb: Bip01 L Hand        10 00 00 00   15.699640 -0.693162 42.922112,  0.567618 -0.426547 -0.346469 
# 12  326: Bip01 L Finger0     11 00 00 00   15.332962 -2.218412 40.016575,  -0.175609 -0.684052 0.015997 
# 13  354: Bip01 L Finger1     11 00 00 00   17.315987 -0.801132 40.241142,  0.418158 -0.573964 -0.510850 
# 14  382: Bip01 Xtra14        0E 00 00 00   4.812204 -0.370431 58.407642,  -0.680965 0.178353 -0.173399 
# 15  3ad: Bip01 Xtra18        14 00 00 00   4.963945 -3.192603 57.692291,  0.701809 0.015671 -0.712103 
# 16  3d8: Bip01 R Clavicle    06 00 00 00   -0.909309 -0.444540 60.931591,  -0.011837 -0.982773 0.002626 
# 17  407: Bip01 R UpperArm    16 00 00 00   -4.552193 -0.357356 59.514072,  0.002093 -0.883523 -0.043441 
# 18  436: Bip01 R Forearm     17 00 00 00   -9.714451 -0.020934 51.982922,  0.045920 -0.882331 -0.020252 
# 19  464: Bip01 R Hand        18 00 00 00   -15.744982 -0.692056 43.035816,  -0.346468 -0.613048 0.567617 
# 1a  48f: Bip01 R Finger0     19 00 00 00   -15.378299 -2.217305 40.130280,  0.015998 -0.707799 -0.175610 
# 1b  4bd: Bip01 R Finger1     19 00 00 00   -17.361326 -0.800030 40.354847,  -0.510850 -0.484501 0.418158 
# 1c  4eb: WeaponBone_R        19 00 00 00   -31.231375 -5.584585 47.558403,  -0.000211 0.707107 0.000527 

# 1d  516: Bip01 Xtra01        05 00 00 00   -1.647468 1.670221 56.412884,  -0.262377 0.241227 -0.884832 
# 1e  541: Bip01 Xtra0102      1D 00 00 00   -12.722528 8.244953 66.309448,  -0.489579 0.381357 -0.760888 
# 1f  56e: Bip01 Xtra0103      1E 00 00 00   -17.845085 7.294302 76.474953,  0.159470 0.187952 -0.966870 
# 20  59b: Bip01 Xtra0104      1F 00 00 00   -42.756645 12.303156 68.976685,  -0.425657 -0.222750 0.872873 
# 21  5c8: Bip01 Xtra03Opp     1F 00 00 00   -18.735107 8.473495 76.262909,  -0.100796 -0.880305 -0.235425 
# 22  5f6: Bip01 Xtra02Opp     1E 00 00 00   -18.515348 8.971450 75.518127,  -0.252030 -0.770105 -0.153874 
# 23  624: Bip01 Xtra01Opp     05 00 00 00   1.646254 1.670170 56.412872,  0.883769 0.303188 0.261517 
# 24  652: Bip01 Xtra01Opp02   23 00 00 00   12.674755 8.322956 66.309273,  0.760219 0.192229 0.488224 
# 25  682: Bip01 Xtra01Opp03   24 00 00 00   17.804045 7.408508 76.474701,  0.966628 0.069797 -0.160139 
# 26  6b2: Bip01 Xtra01Opp04   25 00 00 00   42.679497 12.593173 68.976067,  0.873167 -0.082307 -0.426448 
# 27  6e2: Bip01 Xtra03        25 00 00 00   18.685713 8.593958 76.262650,  -0.234012 -0.400183 -0.103904 
# 28  70d: Bip01 Xtra02        24 00 00 00   18.462437 9.090346 75.517868,  -0.151876 -0.566002 -0.254748 

# 29  738: Bip01 L Thigh       04 00 00 00   3.702247 -1.764064 43.128021,  -0.702770 0.014358 0.711090 
# 2a  764: Bip01 L Calf        29 00 00 00   3.511924 -2.463981 26.891708,  0.702808 0.012341 -0.711188 
# 2b  78f: Bip01 L Foot        2A 00 00 00   3.287067 -1.841629 7.978912,  -0.706871 -0.018260 0.706871 
# 2c  7ba: Bip01 L Toe0        2B 00 00 00   3.549112 -6.034278 0.024066,  -0.512745 0.486921 0.486922 

# 2d  7e5: Bip01 R Thigh       04 00 00 00   -3.702247 -1.764054 43.128029,  -0.711090 0.016090 0.702770 
# 2e  811: Bip01 R Calf        2D 00 00 00   -3.511925 -2.463970 26.891716,  0.711188 0.010926 -0.702808 
# 2f  83c: Bip01 R Foot        2E 00 00 00   -3.287073 -1.841617 7.978920,  0.706871 -0.018259 -0.706871 
# 30  867: Bip01 R Toe0        2F 00 00 00   -3.549107 -6.034267 0.024074,  -0.486922 0.512744 0.512744 

# 31  892: Bip01 Xtra04        03 00 00 00   4.478276 0.134184 48.760891,  -0.214751 -0.699014 0.004851 
# 32  8bd: Bip01 Xtra0402      31 00 00 00   4.801251 4.345961 35.023857,  -0.171687 -0.712663 0.099496 
# 33  8ea: Bip01 Xtra0403      32 00 00 00   4.387856 5.618522 23.558163,  -0.164868 -0.709572 0.106357 
# 34  917: Bip01 Xtra05        03 00 00 00   -2.444300 -0.890149 49.430538,  0.008940 -0.777851 -0.336429 
# 35  942: Bip01 Xtra0502      34 00 00 00   -5.915920 1.835995 42.806335,  0.028890 -0.770518 -0.319377 
# 36  96f: Bip01 Xtra06        03 00 00 00   5.535710 -4.197754 48.412014,  -0.664692 -0.399085 0.456349 
# 37  99a: Bip01 Xtra07Opp     03 00 00 00   -4.125438 -3.721994 48.791866,  0.361163 -0.503983 -0.677991 
# 38  9c8: Bip01 Xtra07Opp02   37 00 00 00   -9.775633 -1.450345 37.036144,  0.447794 -0.431430 -0.686761 
# 39  9f8: Bip01 Xtra07Opp03   38 00 00 00   -13.249603 -0.001810 26.665604,  0.569634 -0.289463 -0.717331 
# 3a  a28: Bip01 Xtra07OppOpp  03 00 00 00   4.133063 -3.705759 48.791859,  -0.678611 -0.393763 0.361949 
# 3b  a59: Bip01 Xtra07OppOpp02 3A 00 00 00   9.790490 -1.451868 37.036194,  -0.687352 -0.375362 0.448467 
# 3c  a8c: Bip01 Xtra07OppOpp03 3B 00 00 00   13.269097 -0.014253 26.665693,  -0.717769 -0.276657 0.570083 
# 3d  abf: Bip01 Xtra09        03 00 00 00   -0.577944 -5.403793 48.250893,  -0.671830 0.152429 0.714684 
# 3e  aea: Bip01 Xtra10        03 00 00 00   3.357864 -0.795190 49.607738,  -0.495449 -0.470843 0.292591 
# 3f  b15: Bip01 Xtra1002      3E 00 00 00   8.428974 0.193863 37.486641,  -0.447211 -0.495437 0.407195 

```


edit: crazy, seems I missed something (again, need a break  )
.



hero_003_skel.png (60.29 KiB) Viewed 283 times

(reminder for me: add "Bip01 Prop1")
## Post #9
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-20T15:52:30+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from Bigchillghost ↑Sat Nov 20, 2021 3:44 pm at Sat Nov 20, 2021 3:44 pm
>
> 
masrawy2 wrote: ↑Thu Nov 18, 2021 11:06 pm
Hello Bigchillghost could you support animation files please  

Is it too much to ask for a little gratitude to the author before you ask for something more?

And it'd be nice if you just put a link to the original post instead of redistributing the whole damn script here. And maybe ask the author for permission first before you decided to remove the ownership claim and publish your modified version of the script.

I'm so sorry Bigchillghost I'm new here and I don't have much knowledge about this stuff and I really appreciate your great effort in creating such a script
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-21T19:08:23+00:00
- Post Title: Importing .act animation ,ect - We need your help!

I checked std.act in the hope it were simple, but seems it is not:

the size of frame blocks is not constant:
no, start address (blocksize:, rest is blocksize modulo 16), rest means remainder  
---------------------------------------------------------------------
As you can see remainder is not always zero, not even constant, so I have no idea.
(block number no might be 1 too big)

Usually you have translation and rotation frames. I assume they use interpolation, that's why blocks are of different sizes.

1 0xc34 (60: 3 *16, rest: 12)
2 0xc7c (92: 5 *16, rest: 12)
3 0xce0 (208: 13 *16, rest: 0)
4 0xdb8 (156: 9 *16, rest: 12)
5 0xe60 (16: 1 *16, rest: 0)

6 0xe78 (424: 26 *16, rest: 8 )
7 0x1028 (88: 5 *16, rest: 8 )
8 0x1088 (16: 1 *16, rest: 0)

"Bip 01 Pelvis"
9 0x10a0 (452: 28 *16, rest: 4)
10 0x1270 (92: 5 *16, rest: 12)
11 0x12d4 (208: 13 *16, rest: 0)
12 0x13ac (156: 9 *16, rest: 12)
13 0x1454 (16: 1 *16, rest: 0) ###
14 0x146c (400: 25 *16, rest: 0)

"Bip 01 Spine"
15 0x1604 (76: 4 *16, rest: 12)
16 0x1658 (16: 1 *16, rest: 0)
17 0x1670 (440: 27 *16, rest: 8 )
18 0x1834 (304: 19 *16, rest: 0)
19 0x1970 (16: 1 *16, rest: 0) ###
20 0x1988 (184: 11 *16, rest: 8 )

"Bip 01 Spine1"
21 0x1a48 (376: 23 *16, rest: 8 )
22 0x1bc8 (16: 1 *16, rest: 0)
23 0x1be0 (524: 32 *16, rest: 12)
24 0x1df8 (88: 5 *16, rest: 8 )
25 0x1e5c (208: 13 *16, rest: 0)
26 0x1f34 (12: 0 *16, rest: 12)
27 0x1f4c (136: 8 *16, rest: 8 )
28 0x1fdc (12: 0 *16, rest: 12)
29 0x1ff4 (12: 0 *16, rest: 12)
30 0x200c (460: 28 *16, rest: 12)
31 0x21e0 (16: 1 *16, rest: 0) ###
32 0x21f8 (440: 27 *16, rest: 8 )

...
354 0x12e48 (592: 37 *16, rest: 0)
355 0x130a0 (524: 32 *16, rest: 12)
356 0x132b8 (92: 5 *16, rest: 12)
357 0x1331c (208: 13 *16, rest: 0)
358 0x133f4 (156: 9 *16, rest: 12)
359 0x1349c (16: 1 *16, rest: 0)
360 0x134b4 (16: 1 *16, rest: 0)
361 0x134cc (456: 28 *16, rest: 8 )
362 0x136a0 (16: 1 *16, rest: 0) 
363 0x136b8 (404: 25 *16, rest: 4)
---------------

Which block for which bone?
Well, block numbers are the blue rectangled ones, I guess. (Ignore the 3F000000, was too lazy to erase those rectangles.)
Green rectangled: parent bone ids

I assume to "Bip 01 Pelvis" belong the blocks 9 to 0x0E, to "Bip 01 Spine" blocks 0x0F to 0x14 and so on; just wild guess.
Or, no, makes sense because of the ### blocks. see above.
.



std-act.png (35.3 KiB) Viewed 233 times


.
well, this is confusing: when I choose a different layout, the remainder is always 4:
1 0xce0 (208: 17 *12, rest: 4)
2 0xdb8 (184: 15 *12, rest: 4)
3 0xe78 (424: 35 *12, rest: 4)
4 0x1028 (88: 7 *12, rest: 4)
5 0x1088 (16: 1 *12, rest: 4)
6 0x10a0 (556: 46 *12, rest: 4)
7 0x12d4 (208: 17 *12, rest: 4)
8 0x13ac (184: 15 *12, rest: 4)
9 0x146c (400: 33 *12, rest: 4)
10 0x1604 (76: 6 *12, rest: 4)
11 0x1658 (16: 1 *12, rest: 4)
12 0x1670 (784: 65 *12, rest: 4)
13 0x1988 (184: 15 *12, rest: 4)
14 0x1a48 (376: 31 *12, rest: 4)
15 0x1bc8 (16: 1 *12, rest: 4)
16 0x1be0 (844: 70 *12, rest: 4)
17 0x1f34 (160: 13 *12, rest: 4)
18 0x1fdc (508: 42 *12, rest: 4)
19 0x21e0 (16: 1 *12, rest: 4)
20 0x21f8 (952: 79 *12, rest: 4)
21 0x25b8 (16: 1 *12, rest: 4)
22 0x25d0 (376: 31 *12, rest: 4)
23 0x2750 (100: 8 *12, rest: 4)
24 0x27bc (928: 77 *12, rest: 4)
25 0x2b64 (532: 44 *12, rest: 4)
26 0x2d80 (952: 79 *12, rest: 4)
27 0x3140 (484: 40 *12, rest: 4)
28 0x332c (16: 1 *12, rest: 4)
29 0x3344 (760: 63 *12, rest: 4)
30 0x3644 (184: 15 *12, rest: 4)
31 0x3704 (484: 40 *12, rest: 4)
32 0x38f0 (16: 1 *12, rest: 4)
...
(too less blocks then)
-------------------------------------
another layout (363 blocks again):
1 0xc34 (60: 5 *12, rest: 0) 
2 0xc7c (92: 7 *12, rest: 8 )
3 0xce0 (208: 17 *12, rest: 4)
4 0xdb8 (156: 13 *12, rest: 0)
5 0xe60 (16: 1 *12, rest: 4)
6 0xe78 (424: 35 *12, rest: 4)
7 0x1028 (88: 7 *12, rest: 4)
8 0x1088 (16: 1 *12, rest: 4)
9 0x10a0 (452: 37 *12, rest: 8 )
10 0x1270 (92: 7 *12, rest: 8 )
11 0x12d4 (208: 17 *12, rest: 4)
12 0x13ac (156: 13 *12, rest: 0)
13 0x1454 (16: 1 *12, rest: 4)
14 0x146c (400: 33 *12, rest: 4)
15 0x1604 (76: 6 *12, rest: 4)
16 0x1658 (16: 1 *12, rest: 4)
17 0x1670 (440: 36 *12, rest: 8 )
18 0x1834 (304: 25 *12, rest: 4)
19 0x1970 (16: 1 *12, rest: 4)
20 0x1988 (184: 15 *12, rest: 4)
...
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-22T20:51:57+00:00
- Post Title: Importing .act animation ,ect - We need your help!

As a test I set the rotation of the skeleton's bones to 0.0 0.0 0.0 and as you can see, it's fine:
.



hero_s3d-noRot.png (24.29 KiB) Viewed 208 times


So the problem is located in the rotation values.
## Post #12
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-11-30T15:36:01+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from shakotay2 ↑Tue Nov 23, 2021 4:51 am at Tue Nov 23, 2021 4:51 am
>
> 
As a test I set the rotation of the skeleton's bones to 0.0 0.0 0.0 and as you can see, it's fine:
.
hero_s3d-noRot.png
So the problem is located in the rotation values.

The information you provided seems very complicated to me, I thought it was easy
But I want to thank you very much for trying to find a solution
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-11-30T16:03:38+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Reply from masrawy2 ↑Tue Nov 30, 2021 11:36 pm at Tue Nov 30, 2021 11:36 pm
>
> The information you provided seems very complicated to me, I thought it was easy
Depends on where you start - as I always wrote: getting the skeleton is the first step when it comes to animations.
And, surprise, there's a very good tutorial concerning the bones:

> Reply from Bigchillghost ↑Fri Feb 01, 2019 2:46 pm at Fri Feb 01, 2019 2:46 pm
>
> 
------------------------------------

> But I want to thank you very much for trying to find a solutionSadly I'm too busy with RL and my own SW projects. So I can this give a thought just from time to time only.

What comes next would be a comparison of bones' transition data and the floats in the animation blocks. But I'm not very motivated because
blocksize of anims isn't constant, see my post above - you might read here where I mentioned frame interpolation (other 3D format, though!) but I don't remember where I got stuck then:

> Reply from shakotay2 ↑Mon Aug 19, 2019 3:43 am at Mon Aug 19, 2019 3:43 am
>
>
## Post #14
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2021-12-02T15:10:31+00:00
- Post Title: Importing .act animation ,ect - We need your help!

> Depends on where you start - as I always wrote: getting the skeleton is the first step when it comes to animations.
>
> And, surprise, there's a very good tutorial concerning the bones:
my experiences is so weak I don't even know what is concepts of animation 


> Sadly I'm too busy with RL and my own SW projects. So I can this give a thought just from time to time only.
I will wait you   
thanks
## Post #15
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2022-03-14T20:55:40+00:00
- Post Title: Importing .act animation ,ect - We need your help!

Hello
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-03-14T23:24:35+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

Well, sorry, totally forgot about that.  

Sadly I'm not very busy any more in this forum due to RL concerns.
But there's other contributors still being very active.
## Post #17
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-15T00:57:07+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

> Reply from shakotay2 ↑Tue Mar 15, 2022 7:24 am at Tue Mar 15, 2022 7:24 am
>
> 
Sadly I'm not very busy any more in this forum.
come back soon
## Post #18
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-03-15T14:30:59+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

> Reply from masrawy2 ↑Tue Mar 15, 2022 4:55 am at Tue Mar 15, 2022 4:55 am
>
> 
Hello

Post more sample
## Post #19
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2022-03-15T20:47:19+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

Post more sample
[/quote]
> Reply from shakotay2
>
> 
Well, sorry, totally forgot about that. 

Sadly I'm not very busy any more in this forum due to RL concerns.
But there's other contributors still being very active.
I will miss you bro  

> Reply from Durik256 ↑Tue Mar 15, 2022 10:30 pm at Tue Mar 15, 2022 10:30 pm
>
> 
Post more sample
here a some of animation sample bro 


 animation s3d_act.rar
(230.75 KiB) Downloaded 11 times
## Post #20
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2022-03-21T17:38:15+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

could anyone help me guys  
a lot of simple here
[https://drive.google.com/drive/folders/ ... 0_DssmnbqJ](https://drive.google.com/drive/folders/1qPk96NeW9LNQEO-nq6EAgA0_DssmnbqJ)
and that 4kb samble file also


 test.rar
(36.77 KiB) Downloaded 11 times


I hope u help me
## Post #21
- Username: masrawy2
- Rank: beginner
- Number of posts: 33
- Joined date: Thu Jan 07, 2016 8:15 am
- Post datetime: 2022-03-25T15:44:13+00:00
- Post Title: Re: Importing .act animation ,ect - We need your help!

Hello
